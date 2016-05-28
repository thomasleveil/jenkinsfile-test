node {
  stage 'Build and Test'
  env.PATH = "${tool 'Maven 3'}/bin:${env.PATH}"
  checkout scm
  sh 'mvn clean package'

  stage 'Build and Test 2'
  env.PATH = "${tool 'Maven 3'}/bin:${env.PATH}"
  checkout scm
  sh 'mvn clean package'
  echo "test echo"
}