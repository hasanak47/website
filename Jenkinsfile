properties([
    buildDiscarder(logRotator(numToKeepStr: '3')),
    pipelineTriggers([
        pollSCM('* * * * *')
    ])
])

node(){
    def MVN_HOME=tool name: "MVN_HOME", type: "maven"
 stage('building the onlineshoping artifactBuild')
 {
  sh  "${MVN_HOME}/bin/mvn clean package"
 }
}
