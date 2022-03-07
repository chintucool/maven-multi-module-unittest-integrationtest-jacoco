pipeline {
   agent any
   tools{
        maven 'maven3'
    }
   stages{
      stage('Preparation') {
         steps{
            checkout scm
         }
      }
      stage('build and unit-test') {
         // all tests: other variants: only unit, integration, or all (incl. functional testing)
         steps{
            sh 'mvn clean install -P test-all'
         }
      }
      stage('SonarQube analysis') {
         steps{
           sh 'mvn sonar:sonar'
         }
      }
   }
}
