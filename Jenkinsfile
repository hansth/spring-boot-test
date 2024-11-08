pipeline {

    agent any

//     tools {
//         // Note: this should match with the tool name configured in your jenkins instance (JENKINS_URL/configureTools/)
//         maven "Maven 3.6.0"
//     }

    environment {
        // This can be nexus3 or nexus2
        NEXUS_VERSION = "nexus3"
        // This can be http or https
        NEXUS_PROTOCOL = "http"
        // Where your Nexus is running
        NEXUS_URL = "192.168.2.9:8081"
        // Repository where we will upload the artifact
        NEXUS_REPOSITORY = "maven-nexus-repo"
        // Jenkins credential id to authenticate to Nexus OSS
        NEXUS_CREDENTIAL_ID = "nexus-credentials"
    }

    stages {
        stage("mvn build") {
            steps {
                script {
                    // If you are using Windows then you should use "bat" step
                    // Since unit testing is out of the scope we skip them
//                     sh "mvn clean package -DskipTests=true"
                    sh "mvn clean deploy -s ./settings.xml"
                }
            }
        }
    }
}
