pipeline{
    agent any 
    
    stages{
        stage('checkout scm'){
            steps{
                git branch: 'main', changelog: false, poll: false, url: 'https://github.com/octobit8-pvt-ltd/Django_app_shoury.git'
            }
        }
        
    stage('build'){
        steps{
                bat 'python -m django --version'
                bat 'start /b python manage.py runserver 0.0.0.0:8000'
                bat 'python buildparser.py'
            }
            
        }
        
    }
}

post{
    always{
        mail(
            subject : 'Jenkins Build Notification',
            body : 'successfully built in jenkins',
            to : 'shourywardhan24@gmail.com' , 'shourywardhan@octobit8.com'
            
            )
    }
}










