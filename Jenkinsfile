node {

    stage("Checkout Code") {
        checkout scm
    }

    stage("Check Workspace") {
        sh 'pwd'
        sh 'ls -la'
    }

    stage("Install Dependency") {
        sh 'docker run --rm -v $PWD/laravel-app:/app -w /app composer install'
    }

}
