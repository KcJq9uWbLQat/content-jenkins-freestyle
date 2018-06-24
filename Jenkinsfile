node {
    checkout scm
    stage('Build') {
        echo "Buiding project ${JOB_NAME} with number ${BUILD_NUMBER}"
        sh 'javac -d . src/*java'
        sh "echo 'Main-Class: Rectangulator' > MANIFEST.MF"
    }
}
