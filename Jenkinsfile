pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/CHArsalan/Coffee-Shop.git'
            }
        }
        stage('Deploy Locally') {
            steps {
                script {
                    // Define the deployment path
                    def deployPath = 'C:\\Users\\IT CORP Inc\\Desktop\\devops_fp\\coffee_shop'
                    
                    // Ensure deployment directory exists
                    bat "if not exist \"${deployPath}\" mkdir \"${deployPath}\""
                    
                    // Copy files to deployment directory
                    bat "xcopy /E /I /Y . \"${deployPath}\""
                }
            }
        }
        stage('Post Deployment Check') {
            steps {
                echo 'Deployment Complete!'
                echo 'You can access the project at: C:\\Users\\IT CORP Inc\\Desktop\\devops_fp\\coffee_shop'
            }
        }
    }
}
