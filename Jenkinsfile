pipeline {
    agent any
    tools {
        maven 'mymaven'
    }    
    stages{
        stage('build')
        {
            steps {
                sh 'mvn clean package'
            }

            post {
            success {
                archiveArtifacts artifacts: '**/target/*.war'
            }    
            }
        }

        // stage('test')
        // {
        //     steps {
        //         echo "this is test stage"
        //     }
        // }

        // stage('deploy')
        // {
        //     steps{
        //         echo "this is deploy stage"
        //     }
        // }
    }
}