node {

    stage("Install Dependency") {
        sh 'composer install'
    }

    stage("Laravel Setup") {
        sh 'cp .env.example .env'
        sh 'php artisan key:generate'
    }

    stage("Migration") {
        sh 'php artisan migrate'
    }

}