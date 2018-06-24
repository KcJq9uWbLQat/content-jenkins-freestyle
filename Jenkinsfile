node {
  checkout scm
  stage('Build') {
    echo "Buiding project ${JOB_NAME} with number ${BUILD_NUMBER}"
    sh 'javac -d . src/*java'
    sh "echo 'Main-Class: Rectangulator' > MANIFEST.MF"
    sh jar -cmf MANIFEST.MF rectangle.jar *.class
  }
  stage('Test') {
    sh 'java -jar rectangle.jar 2 3'
  }
}
