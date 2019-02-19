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
		sh 'vendor/bin/phpcs --report=checkstyle --standard=phpcs.xml --extensions=php,inc --ignore=autoload.php --ignore=Bootstrap.php --ignore=vendor/ module/Application'
            }
        }
        stage ('Deploy') {
            steps {
                echo 'Deploying..'
            }
        }
}}
