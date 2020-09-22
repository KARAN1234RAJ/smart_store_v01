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
     bat "https://github.com/KARAN1234RAJ/smart_store_v01.git\\UnitTest_src/SmartStoreNet.sln"
     }
  }
       
 stage('Test: Integration Test'){
    steps {
       bat "https://github.com/KARAN1234RAJ/smart_store_v01.git\\IntegrateTest_src/SmartStoreNet.sln"
      }
   }
            }
}
 



