node {

    stage("Checkout Code") {
        checkout scm
    }

    stage("Start Container") {
        sh 'docker compose up -d'
    }

    stage("Install Dependency") {
        sh 'docker compose exec app composer install'
    }

    stage("Laravel Setup") {
        sh 'docker compose exec app php artisan key:generate'
    }

    stage("Migration") {
        sh 'docker compose exec app php artisan migrate'
    }

}
