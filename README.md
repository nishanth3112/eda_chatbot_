# **Conversational EDA Chatbot**

![Python](https://img.shields.io/badge/Python-3.10-blue)
![OpenAI](https://img.shields.io/badge/OpenAI-GPT--4%20%2F%20GPT--3.5--Turbo-green)
![LangChain](https://img.shields.io/badge/LangChain-Framework-orange)
![MySQL](https://img.shields.io/badge/Database-MySQL-lightblue)
![Streamlit](https://img.shields.io/badge/Frontend-Streamlit-red)
![Prompt Engineering](https://img.shields.io/badge/Feature-Prompt%20Engineering-yellow)
![Matplotlib](https://img.shields.io/badge/Visualization-Matplotlib%20%2B%20Plotly-purple)
![API](https://img.shields.io/badge/API-Integration-lightgrey)

This project demonstrates the implementation of a **Streamlit-based conversational chatbot** integrated with **LangChain** and **OpenAI** for **Exploratory Data Analysis (EDA)**.  
The system enables natural language interaction with a **MySQL database**, allowing users to perform data exploration and visualization without writing code or SQL queries manually.

---

## 🧠 **Project Overview**

Data analysis and visualization are critical in modern businesses to understand market trends, customer behavior, and operational performance.  
This project empowers non-technical users to interact with data using **natural language**, leveraging **Large Language Models (LLMs)** like GPT-4 and GPT-3.5 Turbo.

Users can ask questions such as:
> “What’s the total revenue last month?”  
> “Show me a bar chart of product categories by sales.”

The chatbot converts these queries into SQL commands, fetches data from **MySQL**, and dynamically generates **Python visualization code** using **Matplotlib** or **Plotly** — all within a **Streamlit** app.

---

## 🧩 **Architecture**
<img width="540" height="409" alt="architecture_diagram" src="https://github.com/user-attachments/assets/c2473b24-6812-4e13-bc4a-f407bf7aff9d" />


**Flow:**
1. User inputs a query in **Streamlit**.  
2. **LangChain SQL Agent** interprets the query → generates SQL → queries **MySQL**.  
3. **Python Script Agent** creates Python code for visualization.  
4. Results and plots are displayed in **Streamlit**.

---

## ⚙️ **Tech Stack**

- **Language:** Python 3.10.4  
- **Database:** MySQL  
- **Frontend:** Streamlit  
- **Framework:** LangChain  
- **Model:** OpenAI GPT-4 / GPT-3.5 Turbo  
- **Visualization Libraries:** Matplotlib, Plotly  
- **Packages:** `mysql-connector-python`, `pydantic`, `langchain`, `streamlit`, `plotly`, `matplotlib`, `mysqlclient`

---

## 📊 **Dataset Description**

The e-commerce dataset includes **7 interconnected tables**:

| Dataset | Description |
|----------|--------------|
| **Distribution Centers** | Unique identifiers, names, and geo-coordinates. |
| **Events** | User events (IDs, timestamps, user IDs, session IDs, event types). |
| **Inventory Items** | Product creation/sale timestamps, details, and associations. |
| **Order Items** | Order details, timestamps (shipping, delivery, return). |
| **Orders** | Order IDs, timestamps, quantities, and statuses. |
| **Products** | Product IDs, prices, categories, brands, and costs. |
| **Users** | User demographics, traffic sources, and creation timestamps. |

---

## 🧱 **Project Structure**

```bash
├── app.py                          # Main Streamlit app
├── sql_agent.py                    # LangChain SQL Query Agent
├── python_agent.py                 # LangChain Python Script Agent
├── utils.py                        # Helper functions for DB connection, query handling
├── requirements.txt                # Project dependencies
├── data/
│   ├── products.csv
│   ├── users.csv
│   ├── orders.csv
│   └── other_datasets.csv
├── architecture_diagram.png        # Architecture diagram (optional)
├── PROJECT 4 SOLUTION.pdf          # Solution methodology
└── README.md                       # Documentation file
```

## 💾 **MySQL Installation & Setup**

### **macOS**
**1. Install MySQL:**
- Download from [MySQL Community Downloads](https://dev.mysql.com/downloads/mysql/)
- Choose **macOS DMG Archive**, install, and set your **root password**.

**2. Install MySQL Workbench:**
- Download from [MySQL Workbench Downloads](https://dev.mysql.com/downloads/workbench/)
- Drag the `.app` to your **Applications** folder.

---

### **Linux (Ubuntu)**
```bash
sudo apt update
sudo apt install mysql-server
sudo mysql_secure_installation
sudo systemctl start mysql
sudo systemctl enable mysql
```
### **Install Workbench**
```bash
sudo dpkg -i mysql-workbench-community-*.deb
sudo apt-get -f install
```
### **Windows**

1. **Download from MySQL Community Downloads:**  
   - Visit [MySQL Community Downloads](https://dev.mysql.com/downloads/mysql/)  
   - Select **Developer Default** installation.  
   - Set your **root password** during setup.  

2. **Install MySQL Workbench:**  
   - Download from [Workbench Downloads](https://dev.mysql.com/downloads/workbench/).  
   - Complete installation and launch MySQL Workbench.

---

## 🔗 **Connecting MySQL to Workbench**

1. Launch **MySQL Workbench**.  
2. Click **MySQL Connections → + (Add Connection)**.  
3. Enter:  
   - **Hostname:** `localhost`  
   - **Port:** `3306`  
   - **Username:** `root`  
4. Click **Test Connection**, enter your password, and then click **Save**.  

---

## 🧰 **System Requirements for OpenAI API**

| **Component** | **Requirement** |
|----------------|------------------|
| **OS** | Windows 10+, macOS Catalina+, Ubuntu 18.04+ |
| **Processor** | Multi-core CPU |
| **Memory** | ≥ 8 GB RAM |
| **Storage** | SSD recommended |
| **Internet** | ≥ 2–4 Mbps, stable connection |
| **API Key** | Obtain from [OpenAI Platform](https://platform.openai.com/) |

---

## ⚡ **Virtual Environment Setup**

### **For Windows**
```bash
cd C:\path\to\project
python -m venv myenv
myenv\Scripts\activate
pip install -r requirements.txt
```
### **For macOS/Linux**
```bash
cd /path/to/project
python3.10 -m venv myenv
source myenv/bin/activate
pip install -r requirements.txt
```
### **If Multiple Python Versions Installed**
```bash
py -3.10 -m venv myenv
myenv\Scripts\activate
pip install -r requirements.txt
```
## ▶️ **Run the Streamlit Application**

Run the app using:
```bash
streamlit run app.py
```
- Opens automatically at **http://localhost:8501**

Try sample prompts like:
> “Show me total revenue by product category.”  
> “Plot customer acquisition trends this quarter.”

---

## ⚙️ **Configuration Tips**

- Ensure your **OpenAI API key** and **MySQL credentials** are correctly configured in `.env` or `config.py`.  
- Verify your **MySQL connection** before launching Streamlit.  
- The **first query** might take longer due to model initialization.  

---

## 🧠 **Prompt Engineering Scenarios**

- **Acting as a Role:** “You are a financial analyst. Summarize the revenue trends.”  
- **Language Translation:** “Translate product descriptions to French.”  
- **Travel Guide Example:** “Suggest top 5 regions with high customer density.”  
- **Chained Workflows:** Combine multiple prompts for SQL + visualization generation.  

---

## 🧩 **LangChain Integration**

- **SQL Agent:** Converts natural language to SQL queries.  
- **Python Script Agent:** Generates Python visualization code.  
- **Memory Integration:** Maintains conversational context.  
- **Guardrails:** Prevents invalid SQL or harmful code execution.  

---

## 💸 **Cost Breakdown**

| **Component** | **Description** | **Estimated Cost** |
|----------------|------------------|--------------------|
| **OpenAI API Calls** | GPT-4 / GPT-3.5 Turbo responses | ~$5–$10 per project |
| **Model Pricing** | GPT-4 Turbo: $0.01 / $0.03 per 1K tokens (input/output) | [OpenAI Pricing](https://openai.com/pricing) |

💡 *Use **GPT-3.5 Turbo** for faster, cheaper testing. Use **GPT-4 Turbo** for advanced analysis.*

---

## 🧪 **Project Takeaways**

- Understand **LLM fundamentals** & attention mechanisms.  
- Learn **LangChain** workflow for conversational data analysis.  
- Apply **prompt engineering** for SQL generation and visualization.  
- Integrate **Streamlit**, **OpenAI**, and **MySQL** for real-time analytics.  
- Automate **data visualization** with dynamically generated Python scripts.  
- Explore **memory & guardrails** for safe, context-aware model execution.  
---
