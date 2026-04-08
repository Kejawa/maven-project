pipeline {
    agent any
    parameters {
        string defaultValue: 'kj', name: 'LASTNAME'
    }

    environment{
        NAME = "temi"
    }
    tools {
        maven 'mymaven'
    }    
    stages{
        stage('build')
        {
            steps {
                sh 'mvn clean package'
                echo "hello $NAME $(params.LASTNAME)"
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