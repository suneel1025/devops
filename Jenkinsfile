node{
  stage ('Clone From Git') {

    git url: 'https://github.com/ganeshdev1/service-pipeline.git'
  }
    stage('Continue Trigger')
    {
        cron('H */8 * * *') //regular builds
        pollSCM('* * * * *') //polling for changes, here once a minute
    } 
   stage('Gradle Build') {
     def gradleHome = tool name: 'gradle', type: 'gradle'
     def gradleCMD = "${gradleHome}/bin/gradle"
     sh "${gradleCMD} clean build"
    }
}
