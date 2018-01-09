node {
   
   stage('App Stack Provision') {
   echo " its dev branch"
properties([parameters([string(defaultValue: '123456', description: '', name: 'timestamp')]), pipelineTriggers([])])
sh '''echo "timestamp = ${timestamp}"
export tapip1=`curl -X GET http://192.168.131.1:8080/api/v1/awsipfetch/${timestamp}/ | jq .value[0]`
export tapip2=`curl -X GET http://192.168.131.1:8080/api/v1/awsipfetch/${timestamp}/ | jq .value[2]`
echo "tap ip : " $tapip1 " ---- "  $tapip2'''
sh 'curl -X GET http://192.168.131.1:8080/api/v1/awsipfetch/20171001/installed/'   
   }

}