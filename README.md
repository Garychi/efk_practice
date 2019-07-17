# EFK Practice
Elasticsearch + Fluentd Fluentd-ui + Kibana

build environment : docker-compose up -d

### Elasticsearch
- port : 9200

### Kibana
- port : 5601

### Fluentd-ui
- port : 9292
- username : admin
- password : changeme


# Security Setting

#### Step1. Modify config elasticsearch.yml
docker exec -it elasticsearch vi /usr/share/elasticsearch/config/elasticsearch.yml
- xpack.security.enabled: true

docker restart elasticsearch


#### Step2. Initial default password
- elastic
- kibana
- apm_system
- logstash_system
- beats_system
- remote_monitoring_user
docker exec -it elasticsearch ./bin/elasticsearch-setup-passwords interactive
docker restart elasticsearch

#### Step3. Add kibana password from Step2
docker exec -it kibana vi /usr/share/kibana/config/kibana.yml
- elasticsearch.username: "kibana"
- elasticsearch.password: "your_password"

docker restart kibana  



