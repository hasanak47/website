properties([
    buildDiscarder(logRotator(numToKeepStr: '3')),
    pipelineTriggers([
        pollSCM('* * * * *')
    ])
])

node(){
stage('Build'){
 	if(isUnix()){
 	sh 'mvn clean package'
 	}else{
 	bat 'mvn clean package'
 	}
 	}
}
