@Library('shared') _
pipeline{
    agent { label "vinod"}
    
    stages{
        stage("Code clone"){
            steps{
            clone("https://github.com/LondheShubham153/django-notes-app.git","main")
            }
        }
        stage("Code Build"){
            steps{
            dockerbuild("notes-app","latest","anushkahetawal")
            }
        }
        stage("Push to DockerHub"){
            steps{
                dockerpush("notes-app","latest","anushkahetawal")
            }
        }
        stage("Deploy"){
            steps{
                deploy()
            }
        }
        
    }
}
