node {
    stage('Init') {
        checkout scm
    }

    stage('Build') {
        sh 'mvn clean package'
    }

    stage('Publish') {
        azureFunctionAppPublish appName: jenkinsCICD, 
                                azureCredentialsId: e3c32703-1668-4005-8bbf-ee02f6574451, 
                                filePath: '**/*.json,**/*.jar,bin/*,HttpTrigger-Java/*', 
                                resourceGroup: jenkinfunction, 
                                sourceDirectory: 'target/azure-functions/jenkinsCICD'
    }
}
