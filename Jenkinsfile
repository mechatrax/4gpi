pipeline{
	agent any

	stages {
		stage("Checkout GIT") {
			steps {
				withCredentials([usernamePassword(credentialsId: '5b25baba-433c-41a9-b104-59e49ec74e49', passwordVariable: 'JENKINS_TOKEN', usernameVariable: 'JENKINS_USERNAME')]){
					script {
						def vars = checkout(scm: [$class: 'GitSCM',
							branches: [[name: 'main']],
							userRemoteConfigs: [[url: 'https://github.com/mechatrax/4gpi']]
						], poll: true)
						def msg = sh(
							script: 'git log --decorate=no --oneline | sed -e \'s/[0-9a-f]\\+ //\' | grep ^Release | head -1',
							returnStdout: true
						).trim()
						if ( ! msg.contains("Release") ) {
							sh 'curl -s -X POST -u ${JENKINS_USERNAME}:${JENKINS_TOKEN} http://127.0.0.1:8080/job/${JOB_NAME}/${BUILD_NUMBER}/stop'
						}
						env.RELEASE_NAME = msg.replaceFirst('Release.*(4gpi-.*)', '$1')
						if ( env.RELEASE_NAME == "" ) {
							sh 'curl -s -X POST -u ${JENKINS_USERNAME}:${JENKINS_TOKEN} http://127.0.0.1:8080/job/${JOB_NAME}/${BUILD_NUMBER}/stop'
						}
						if ( msg.contains('legacy') ) {
							env.RELEASE_SUFFIX = '-legacy'
							env.RELEASE_MODIFIER = ' Legacy 版'
							env.SUM_FILE = '4gpi_oldstable_lite_armhf.sha256sum'
						} else {
							env.RELEASE_SUFFIX = ''
							env.RELEASE_MODIFIER = ''
							env.SUM_FILE = '4gpi_lite_armhf.sha256sum'
						}
						env.TWEET_MESSAGE = "弊社ラズベリーパイ用 4G（LTE）通信モジュール 4GPi（フォージーパイ）の${RELEASE_MODIFIER} OS イメージ ${RELEASE_NAME} をリリースしました。\\nhttps://github.com/mechatrax/4gpi/blob/master/os${RELEASE_SUFFIX}/${RELEASE_NAME}.md"
					}
				}
			}
		}
		stage("Upload") {
			when {
				expression { return RELEASE_NAME != 'none' }
			}
			steps {
				withCredentials([
				usernamePassword(credentialsId: 'aa4ddfcc-11d9-418d-b794-8963612b6a78', passwordVariable: 'FTP_PASSWORD', usernameVariable: 'FTP_USERNAME'),
				string(credentialsId: '0e3efab3-616e-439d-806b-55aac4cd84fd', variable: 'FTP_IP')
				]) {
					sh 'curl -sS -T /dev/shm/${RELEASE_NAME}.img.xz -u ${FTP_USERNAME}:${FTP_PASSWORD} ftp://${FTP_IP}/data/4gpi${RELEASE_SUFFIX}/'
				}
			}
		}
		stage("Check") {
			when {
				expression { return RELEASE_NAME != 'none' }
			}
			steps {
				sh 'test -e /dev/shm/${RELEASE_NAME}.img.xz && sudo mv /dev/shm/${RELEASE_NAME}.img.xz /dev/shm/${RELEASE_NAME}.img.xz.orig'
				sh 'wget -q https://mechatrax.com/data/4gpi${RELEASE_SUFFIX}/${RELEASE_NAME}.img.xz -P /dev/shm'
				sh 'sha256sum -c /dev/shm/${SUM_FILE}'
				sh 'sudo rm -vf /dev/shm/${RELEASE_NAME}.img.xz /dev/shm/${RELEASE_NAME}.img.xz.orig /dev/shm/${SUM_FILE}'
			}
		}
		stage("Tweet") {
			when {
				expression { return RELEASE_NAME != 'none' }
			}
			steps {
				withCredentials([
					usernamePassword(credentialsId: '5862efc0-4e22-4447-9ac4-af71c72f7fea', passwordVariable: 'APISECRET', usernameVariable: 'API'),
					usernamePassword(credentialsId: '555f6776-fbe8-4833-b8dd-cf9e4838a7d6', passwordVariable: 'ACCESSSECRET', usernameVariable: 'ACCESS')
				]) {
					sh 'python3 -c "from twython import Twython; Twython(\\"${API}\\",\\"${APISECRET}\\",\\"${ACCESS}\\",\\"${ACCESSSECRET}\\").update_status(status=\\"${TWEET_MESSAGE}\\")"'
				}
			}
		}
	}
	environment{
		POST_CREDS = credentials('c1957e02-a3d9-42e0-9dae-db8ce27974e1')
	}
	post {
		success {
			hangoutsNotify message: "✔ 4GPi の SD イメージ ${RELEASE_NAME} のリリースに成功しました\r\nhttps://twitter.com/mechatracks", token: '${POST_CREDS}', threadByJob: false
		}
		failure {
			hangoutsNotify message: "❌ 4GPi の SD イメージ ${RELEASE_NAME} のリリースに失敗しました", token: '${POST_CREDS}', threadByJob: false
		}
	}
}
