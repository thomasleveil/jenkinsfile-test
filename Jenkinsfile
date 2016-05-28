node {
  env.PATH = "${tool 'Maven 3'}/bin:${env.PATH}"
  
  stage 'checkout'
  checkout scm
  

  stage 'Build'
  sh 'mvn clean compile'

  stage 'Test'
  sh 'mvn test'

  stage 'Package'
  sh 'mvn package'
  echo "test echo"

  archive '**/target/*.jar'
  step([$class: 'JUnitResultArchiver', testResults: '**/target/surefire-reports/TEST-*.xml'])
}