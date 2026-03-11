node {

    stage("Install Dependency") {
        sh 'docker run --rm -v $PWD:/app -w /app composer install'
    }

    stage("Laravel Setup") {
        sh 'docker run --rm -v $PWD:/app -w /app php:8.2-cli php artisan key:generate'
    }

    stage("Migration") {
        sh 'docker run --rm -v $PWD:/app -w /app php:8.2-cli php artisan migrate'
    }

}