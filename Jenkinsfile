node {
  checkout scm
  try {
    stage('Build') {
      echo "Buiding project ${JOB_NAME} with number ${BUILD_NUMBER}"
      sh 'javac -d . src/*java'
      sh "echo 'Main-Class: Rectangulator' > MANIFEST.MF"
      sh 'jar -cmf MANIFEST.MF rectangle.jar *.class'
    }
    stage('Test') {
      sh 'java -jar rectangle.jar 2 3'
    }
  } catch (e){
    throw e
  } finally {
    archiveArtifacts artifacts: 'rectangle.jar', fingerprint: true
  }
}
