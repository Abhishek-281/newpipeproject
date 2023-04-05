pipeline {
    agent any
    stages {
        stage("build")  {
            steps {
                sh 'npm install'
                sh 'npm run build'
            }
        }
        stage("deployment")  {
            steps {
                sshagent(['Deploy']) {
                    sh 'scp ssh -o StrictHostKeyChecking=no /workspace/newpipeline/build/* ubuntu@54.144.193.165:/var/www/html/'
                }
            }
        }      
    } 
}
