pipeline {
    agent any
    
    environment {
        MAVEN_HOME = "/usr/share/maven" 
        PATH = "$PATH:$MAVEN_HOME/bin"
        USERNAME = "${USERNAME}"  
        APIKEY = "${APIKEY}"      
        APPIUM_VERSION = "${APPIUM_VERSION}" 
        ANDROID_APPLICATION = "${ANDROID_APPLICATION}"
        IOS_APPLICATION = "${IOS_APPLICATION}"
        ANDROID_APPPACKAGE = "${ANDROID_APPPACKAGE}"
        ANDROID_APPACTIVITY = "${ANDROID_APPACTIVITY}"
        IOS_BUNDLEID = "${IOS_BUNDLEID}"
        CLOUD="${CLOUD}"
    }
    
    stages {
        stage('Build') {
            steps {
                withEnv(["PATH=$PATH:$MAVEN_HOME/bin"]) 
                sh 'mvn clean'
            }
        }
        stage('Test') {
            steps {
                withEnv(["PATH=$PATH:$MAVEN_HOME/bin"]) 
                sh """
                    mvn test \
                    -Dusername=${USERNAME} \
                    -DapiKey=${APIKEY} \
                    -DappiumVersion=${APPIUM_VERSION} \
                    -DandroidApplication=${ANDROID_APPLICATION} \
                    -DiosApplication=${IOS_APPLICATION} \
                    -DandroidAppPackage=${ANDROID_APPPACKAGE} \
                    -DandroidAppActivity=${ANDROID_APPACTIVITY} \
                    -DiosBundleId=${IOS_BUNDLEID} \
                    -Dcloud=${CLOUD}
                """
            }
        }
    }
}

