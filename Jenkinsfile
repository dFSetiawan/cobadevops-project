node {

    stage("Checkout Code") {
        checkout scm
    }

    stage("Debug Workspace") {
        sh '''
        pwd
        ls -la
        ls -la laravel-app
        '''
    }

    stage("Install Dependency") {
        sh '''
        docker run --rm \
        -v $PWD/laravel-app:/app \
        -w /app composer install
        '''
    }

    stage("Laravel Setup") {
        sh 'docker exec laravel_app php artisan key:generate'
    }

    stage("Migration") {
        sh 'docker exec laravel_app php artisan migrate'
    }

}
