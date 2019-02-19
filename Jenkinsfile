pipeline {
    agent any

    stages {
        stage ('Build') {
            steps {
		echo 'Buildind..'
                sh 'composer install'
                sh 'vendor/bin/phing setup'
	    }
        }
        stage ('Test') {
            steps {
                echo 'Testing..'
                sh 'vendor/bin/phpunit -c ./module/Application/tests'
            }
        }
        stage ('Deploy') {
            steps {
                echo 'Deploying..'
            }
        }
}}
