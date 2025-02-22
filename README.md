# 📊 Udemy Course Analysis with ELT Stack

This project analyzes **98,000+ Udemy courses** using the **ELT stack (Elasticsearch, Logstash, Kibana)**, orchestrated with **Docker**. The goal is to gain insights into online courses by performing **data wrangling, querying, and visualization**.

---

## 🚀 Tech Stack
- **Elasticsearch** → Data indexing & queries
- **Logstash** → Data extraction & transformation
- **Kibana** → Interactive dashboards & visualizations
- **Docker** → Containerized setup for easy deployment

---

## 📂 Project Structure
```
📂 Other files/
   ├── docker-compose.yaml      # ELK Stack container setup
   ├── index.json               # Elasticsearch index mapping
   ├── logstash/                # Logstash configuration files
       ├── logstash.conf         # Logstash configuration file
   ├── kibanaDashboard.ndjson   # Kibana dashboard import file
```

---

## 🛠️ Setup & Usage
### 1️⃣ Start Elasticsearch and Kibana
```bash
cd "Other files"
docker-compose up es01 kibana
```

### 2️⃣ Create the Index in Elasticsearch
```bash
curl -u elastic:admin -X PUT "localhost:9200/udemy_courses"
```

### 3️⃣ Apply the Index Mapping
```bash
curl -u elastic:admin -X PUT "localhost:9200/udemy_courses/_mapping" \
    -H "Content-Type: application/json" -d @index.json
```

### 4️⃣ Start Logstash
```bash
docker-compose up -d logstash
```

### 5️⃣ Import CSV Data
```bash
cp /path/to/dataset.csv logstash/csvData/
```

### 6️⃣ Restart Logstash to Load Data
```bash
docker-compose restart logstash
```

---

## 📊 Example Queries
- **Top 5 free Python courses** based on ratings and reviews
- **Course distribution by category and level**
- **Comparison of ratings for free vs. paid courses**
- **Most popular business courses**

---

## 📜 Credits
- **Author:** Marco Minaudo
- **Course:** Systems and Methods for Big and Unstructured Data (SMBUD)
- **Academic Year:** 2024-2025

---

### 🌟 If you find this project useful, feel free to star ⭐ the repository!
