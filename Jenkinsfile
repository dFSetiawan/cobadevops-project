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
        dir("laravel-app") {
            sh '''
            docker run --rm \
            -v $(pwd):/app \
            -w /app \
            composer install
            '''
        }
    }

}
