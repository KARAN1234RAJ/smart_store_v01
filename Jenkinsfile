pipeline {
    agent any
    stages {
        stage('nugget restore'){
            steps{
                 echo "nugget restoring packages"
                     bat 'C:/tools/nuget.exe  restore  src/SmartStoreNet.sln'
                
                    }
                }
                stage('Build') {
                        steps {
                               bat "\"${tool 'MSBuild'}\" src/SmartStoreNet.sln /p:DeployOnBuild=true /p:DeployDefaultTarget=WebPublish /p:WebPublishMethod=FileSystem /p:SkipInvalidConfigurations=true /t:build /p:Configuration=Release /p:Platform=\"Any CPU\" /p:DeleteExistingFiles=True /p:publishUrl=c:\\iis\\wwwroot"

                        }
                    }
        stage('Test: Unit Test'){
   steps {
     bat "C:\Users\KARAN\Downloads\TestJenkins\\UnitTest_src/SmartStoreNet.sln"
     }
  }
       
 stage('Test: Integration Test'){
    steps {
       bat "C:\Users\KARAN\Downloads\TestJenkins\\IntegrateTest_src/SmartStoreNet.sln"
      }
   }
            }
}
 



