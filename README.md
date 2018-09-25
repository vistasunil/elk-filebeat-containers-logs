# elk-filebeat-containers-logs
This will help you to capture docker containers logs using Elasticsearch,Logstash and Kibana with help of filebeats.
# Usage
1. Make sure that the vm_max_map_count kernel setting is set to at least 262144:

   sysctl -w vm.max_map_count=262144
   
2. Run below command to setup the elk stack and filebeats service in containers

   docker-compose up -d
   
3. Check if the elastic search is up and running :

   curl localhost:9200
   
4. Check whether the logstash idices are available in elasticsearch

   curl 'localhost:9200/_cat/indices?v'

5. Once the logstash indices are available in step 4 ,login to Kibana portal using below link

   http://<localhost>:5601
  
6. Set the indices path as given below

   logstash*
  
   Note: Do not select timestamp filter in next step.
   
7. Now go to discovery and add Timestamp and Message Column

   
