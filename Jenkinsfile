pipeline {
    agent any

    stages {

        stage('Hello') {
            steps {
                echo 'Hello from Jenkins!'
            }
        }

        stage('Check Environment') {
            steps {
                bat '"C:\\Users\\INDU\\AppData\\Local\\Programs\\Python\\Python312\\python.exe" --version'
                bat '"C:\\Users\\INDU\\AppData\\Local\\Programs\\DockerDesktop\\resources\\bin\\docker.exe" --version'
            }
        }

        stage('Install Dependencies') {
            steps {
                bat '"C:\\Users\\INDU\\AppData\\Local\\Programs\\Python\\Python312\\python.exe" -m pip install -r app\\requirements.txt'
            }
        }

        stage('Run Tests') {
            steps {
                bat '"C:\\Users\\INDU\\AppData\\Local\\Programs\\Python\\Python312\\python.exe" -m pytest app\\test_app.py'
            }
        }
	stage('Docker Build') {
    	   steps {
               bat '"C:\\Users\\INDU\\AppData\\Local\\Programs\\DockerDesktop\\resources\\bin\\docker.exe" build -t my-python-app app'
           }
}
    }
}