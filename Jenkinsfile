pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
    stage('QA'){
      agent{
        label 'TestExecute'
      }
      steps{
        testcompletetest credentialsId: 'tester',
          executorType: 'TE',
          launchType: 'lcRoutine',
          project: 'TestProject1',
          routine: 'Test1',
          suite: 'ProjectSuite1\\ProjectSuite1.pjs',
          unit: 'Unit1',
          useTCService: true
       }
    }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
