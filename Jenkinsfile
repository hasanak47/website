properties([
    buildDiscarder(logRotator(numToKeepStr: '3')),
    pipelineTriggers([
        pollSCM('* * * * *')
    ])
])

node(){
    def mavenHome=tool name: "MAVEN_HOME", type: "maven"
    
stage("checkout code from SCM"){
git credentialsId: 'c45f9148-718e-401c-aec8-d4052b65ba17', url: 'https://github.com/hasanak47/website.git'
}
 stage('building the onlineshoping artifactBuild')
 {
  sh  "${mavenHome}/bin/mvn clean package"
 }
 stage('deploying to nexus')
 {
  sh  "${mavenHome}/bin/mvn clean deploy"
  }
 /* 
 stage('DeplotoTomcat'){
     
     sh "cp $WORKSPACE/target/*.war /opt/apache-tomcat-9.0.17/webapps/"
 }

 stage("sending email notification"){
     mail bcc: '', body: '''Build has successfully completed.
  Regards,
  Hasan Ala''', cc: 'hasanrocking@gmail.com', from: '', replyTo: '', subject: 'Build Done', to: 'hasan.ala02@gmail.com'
 }
  */ 
}
