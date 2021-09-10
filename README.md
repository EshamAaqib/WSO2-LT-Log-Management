# WSO2-Log-Management-Assignment

### Config Files - https://gitfront.io/r/eshamaaqib/2906784ff51d0ad86c3a5eed32d2ed75415eaed1/WSO2-Log-Management-Assignment/

## **Part 1 :**

### Followed all the steps 

## **Part 2 :**


| Hostname      | IP Address    |
| ------------- | ------------- |
| lt2021047-esn | 10.148.0.6    |
| lt2021047-aws | 10.148.0.7    |
| lt2021047-lss | 10.148.0.8    |
| lt2021047-nws | 10.148.0.9    |

### **2.** ![2](https://user-images.githubusercontent.com/75664650/132390464-93fc4e1b-be8f-4b97-9b66-13d49271c6fb.png)

### **3.** ![3](https://user-images.githubusercontent.com/75664650/132390477-9ead679e-f84e-41d2-87e4-9679567addf6.png)

### **4.** ![4](https://user-images.githubusercontent.com/75664650/132390493-e01fd59b-b6eb-4f79-ae29-040c7d48f213.png)

### **5.** ![5](https://user-images.githubusercontent.com/75664650/132390504-583ab650-4757-4980-abe7-b86275824195.png)

### **6 Screenshots of Config Files (I have uploaded the config files to the Config Files folder as well)**

### Elasticsearch Server (elasticsearch.yml)
![6 1 elasticsearch yml (Server Node)](https://user-images.githubusercontent.com/75664650/132390632-71b595ae-f454-432f-8602-6ecebc53892b.PNG)

### Elasticsearch Server (Kibana.yml)
![6 2 kibana yml (Server Node)](https://user-images.githubusercontent.com/75664650/132390659-8576e619-85e5-4ff2-a090-05c41f351eb0.PNG)

### Logstash Server (main-logstash.conf)
![6 3 main-logstash conf (logstash node)](https://user-images.githubusercontent.com/75664650/132390731-14813f92-f7fa-4f6a-9de7-68a73ba27cb6.PNG)

### Nginx Server (filebeat.yml)
![6 4) filebeat yml (nginx node)](https://user-images.githubusercontent.com/75664650/132390776-3cbbf91a-55f5-447d-8f2f-c2123081e2d8.PNG)

### Nginx Server (/module.d/nginx.yml)
![6 5) nginx yml (nginx node)](https://user-images.githubusercontent.com/75664650/132390825-7d22d9e7-f3e0-4ce3-bf6f-ce74df17a68e.PNG)

### Nginx Server (/module.d/system.yml)
![6 6) system yml (nginx node)](https://user-images.githubusercontent.com/75664650/132390859-953758b9-579c-4caf-b941-45200d55ba90.PNG)

### Apache Server (filebeat.yml)
![6 7) filebeat yml (apache node)](https://user-images.githubusercontent.com/75664650/132390870-6d3740e7-6987-4c80-b190-1bcc1b972479.PNG)

### Apache Server (/module.d/apache.yml)
![6 8) Apache yml (apache node)](https://user-images.githubusercontent.com/75664650/132390889-a536e0a4-4b92-419f-8e9e-64600c5453be.PNG)

### Apache Server (/module.d/System.yml)
![6 9) System yml (apache node)](https://user-images.githubusercontent.com/75664650/132390935-a7aae404-4915-4520-8db0-4f9f9739ac68.PNG)

### **7. CRUD Operation in Dev Tools**

### Create
![7 1](https://user-images.githubusercontent.com/75664650/132393410-3357b172-6a64-4745-86fb-0af9b97ba760.png)

### Create
![7 2)](https://user-images.githubusercontent.com/75664650/132393422-56d07b58-0d50-4f28-b4c5-4e555fda0069.png)

### Read
![7 3)](https://user-images.githubusercontent.com/75664650/132393449-9cff22ca-977c-4640-8408-42289b9c3d40.png)

### Update
![7 4)](https://user-images.githubusercontent.com/75664650/132393488-bea6aff0-e7fc-46bc-8ab8-fa34c7eb4ae3.png)

### Read
![7 5)](https://user-images.githubusercontent.com/75664650/132393500-2b4935ab-6b3f-49f8-a015-6c7c3a301da8.png)

### Delete
![7 6)](https://user-images.githubusercontent.com/75664650/132393523-c914c0ae-664b-4dcd-8d7e-0ac4f4cc7aaf.png)

## Part 3 :

### 1. What is an index, shard and replica-shard?

> i. Index - An index is similar to a database in a relational database. Index is a logical namespace where which is mapped to a single or more primary shard and also it can 0 or multiple replica shards or we can call it a collection of documents.

> ii. Shard - Data in Elasticsearch is organized into indices. Indices are divided into multiple units called shards. Additionally Shards helps to make elasticsearch horizontally scalable

> iii. Replica-shard: Every primary shards has its exact copy and we call it replica shards.The main purpose of replica shards are to to increase search performance and as a failover.

### 2. How does sharding help for performance?

> Sharding splits data into small subsets and it distributes them among seperate servers which has its Memory, CPU, Disk, etc. As its distrbuted among seperate servers it enables proper load balancing as its all the load is not handled by one single server which imrpoves the performance drastically and scalability 

### 3. What is Hot-Warm architecture?

> Elasticsearch uses a tiered architecture for large time data analytics. This architecture had 3 different types of nodes which are Master, Hot-Node and Wamr-Node. We can call this as the Hot-Warm Architecture. Master Nodes are responsible in handling cluster management and state which enhaces the overall stability. Hot nodes are used to perfom indexing within the cluster. Also they hold the most recent indices. Warm Nodes are designated to handle a large amount of read-only indices which very unlikely to be queried frequently. 

### 4. How does hot-warm architecture help for data management?

> As mentioned above the Hot-Warm Architecture use 3 type of nodes which we call Master, Hot-Node and Warm-Node. These speicifc nodes are specifically designed perform different tasks. Performing tasks seperately on the designated node will help improve the performance of the whole cluster and improves the availability of the cluster. Also as the tasks are performed sperately on the designated node it makes it easier to do the data managemnt.  

### 5. Compare the performance of Hot, Warm, Cold and Frozen nodes

> Hot Node - 
> > 1. Holds most recent, most frequently used time series data. 
> > 2. Needs to be fast for both reads and writes. 
> > 3. Required more hardware resources and faster storage

> Warm Node -
> > 1. Moved to Warm Node once the time sereis data is infrequently accessed from the hot Node.
> > 2. Does not require high performance as the hot node
> > 3. Update are allowed

> Cold Node -
> > 1. Its almost same as the warm node but it stores data that aren't updated.
> > 2. Data is not updated

> Frozen Node -
> > 1. Once data is no longer being queierd data is transferred to the Frozen node to the cold node for its lifetime
> > 2. Helps to cut down costs

### 6. Describe How did you achieve the 10th point of Part -1 (I assumed it as 9th point as there is no 10th point in Part 1)

> When configuring the nginx server I used filebeats to send the logs to the logstash server. But when it came to the apacher server the requirenment was to send the logs direclty yo the elasticsearch server, So I installed filebeat on apacher server and send the logs direclty to the elasticsearch server instead of sending it to the logstash server. I used the apache module and the system module in filebeats.

### 7. What are elasticsearch based products currently available in the market as log management solutions.Give a brief comparison about at least 3 products.

> ELK -  ELK stack combines three open source projects. Which ElasticSearch as a search and analytics engine. Logstash for centralizing loging and beign used as a pipeline. Kibana for visualizing the data using a user interface

> Akeno - Akeno also uses ElasticSearch and Akeno is a Product Information Management application which is designed to simplify the product management process. 

> SonarQube - SonarQube uses ElasticSearch as well. It is an open source Quality Management Platform that analyzes and measures code's technical quality.















