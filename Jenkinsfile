pipeline {

  agent any
 
  stages {
      stage('Checkout SCM') {
        steps {
            git url: 'https://github.com/mulesoft-rahmat/jenkinscicd.git',
                branch: 'dev'
      }
    }
    stage('Build') {
      steps {
            bat 'mvn -B -U -e -V clean -DskipTests package'
      }
    }

    stage('Test') {
      steps {
          echo "********** MUNIT test execution goes here ************"
      }
    }

     stage('Deploy Development') {
      steps {
            bat 'mvn -U -V -e -B -DskipTests deploy -Pdev -DmuleDeploy -Dusername=mehreensoft -Dpassword=Moin@786m -Denc.key=abcdef0123456789 -Danypoint.platform.client_id=233045dcba4b4364a85a78968062c36e -Danypoint.platform.client_secret=49146cd2Ff554AA6B82Fc1f2Ed8F7cF5'
      }
    }
}
