node {
  env.PATH = "${tool 'Maven 3'}/bin:${env.PATH}"
  
  stage 'checkout'
  checkout scm
  

  stage 'Build'
  sh 'mvn clean testCompile'

  stage 'Test'
  sh 'mvn test'

  echo "test echo"

  archive '**/target/*.jar'
  step([$class: 'JUnitResultArchiver', testResults: '**/target/surefire-reports/TEST-*.xml'])
}