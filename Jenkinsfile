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
            docker_build("notes-app","latest","anushkahetawal")
            }
        }
        stage("Push to DockerHub"){
            steps{
                docker_push("notes-app","latest","anushkahetawal")
            }
        }
        stage("Deploy"){
            steps{
                docker_compose()
            }
        }
        
    }
}
