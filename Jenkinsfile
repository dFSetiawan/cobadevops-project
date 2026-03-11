node {

    stage("Install Dependency") {
        sh '''
        docker run --rm \
        -v /var/jenkins_home/workspace/cobadevopm6/laravel-app:/app \
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
