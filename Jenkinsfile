node {
  env.PATH = "${tool 'Maven 3'}/bin:${env.PATH}"
  
  stage 'checkout'
  checkout scm

  stage 'Test'
  sh 'mvn clean test'

  stage 'echo'
  echo "test echo"

  archive '**/target/*.jar'
  step([$class: 'JUnitResultArchiver', testResults: '**/target/surefire-reports/TEST-*.xml'])
}