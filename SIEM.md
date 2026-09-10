# Configuration of my ELK Stack SIEM

## Content
- [Installing Elasticsearch](#Elasticsearch)
- [Installing Kibana](#Kibana)

## Elasticsearch
Step One: Imported Elastic PGP Key to make sure none of the packages are blocked and are trusted.
```
wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo gpg --dearmor -o /usr/share/keyrings/elasticsearch-keyring.gpg
```
Step 2: Install elasticsearch
```
sudo apt-get install apt-transport-https
echo "deb [signed-by=/usr/share/keyrings/elasticsearch-keyring.gpg] https://artifacts.elastic.co/packages/9.x/apt stable main" | sudo tee /etc/apt/sources.list.d/elastic-9.x.list
sudo apt-get update && sudo apt-get install elasticsearch
```
Step 3: Modifying elasticsearch.yml
```
1. cd /etc/elasticsearch/elasticsearch.yml
Changed cluster.name: elasticsearch-demo to cluster.name elasticsearch-dessy
2. Modify
network.host: 0.0.0.0
network.host: 0.0.0.0
```
Step 3: Enable elasticsearch system processes
```
sudo /bin/systemctl daemon-reload
sudo /bin/systemctl enable elasticsearch.service
sudo systemctl start elasticsearch.service
```
Step 4: Create enrollemnt token for kibana
```
run /usr/share/elasticsearch-create-enrollment-token -s kibana
Save the enrollemnt key for use when deploying kibana.
```
## Kibana
Step One: Import PGP Key
```
wget -qO - https://artifacts.elastic.co/GPG-KEY-elasticsearch | sudo gpg --dearmor -o /usr/share/keyrings/elasticsearch-keyring.gpg
```
Step 2: Install Kibana
```
sudo apt-get install apt-transport-https
echo "deb [signed-by=/usr/share/keyrings/elasticsearch-keyring.gpg] https://artifacts.elastic.co/packages/9.x/apt stable main" | sudo tee /etc/apt/sources.list.d/elastic-9.x.list
sudo apt-get update && sudo apt-get install kibana
```
Step 3: Modify kibana.yml
```
cd /etc/kibana/kibana.yml
Modify server.host: to 0.0.0.0 to make it accessible to the internet.
```
Step 4: Enable Kibana system processes
```
sudo /bin/systemctl daemon-reload
sudo /bin/systemctl enable kibana.service
sudo systemctl start kibana.service
```
Step 5: Enroll kibana with elasticsearch enrollment key
```
Open a new browser
Open https://YOUR-KIBANA-IP:5601
Paste your enrollment key.
Run /usr/share/kibana/bin/kibana-verification-code to receive the verification code to enroll kibana.
```
