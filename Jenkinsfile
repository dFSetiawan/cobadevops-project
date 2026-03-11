node {

    stage("Check Workspace") {
        sh 'pwd'
        sh 'ls -la'
        sh 'ls -la laravel-app'
    }

    stage("Install Dependency") {
        sh 'docker run --rm -v $PWD/laravel-app:/app -w /app composer install'
    }

}
