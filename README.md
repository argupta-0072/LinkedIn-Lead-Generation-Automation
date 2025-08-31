# LinkedIn Lead Generation Automation with n8n

An automated workflow built using the low-code platform **[n8n](https://n8n.io/)** to perform **targeted lead generation from LinkedIn**.  
The system executes a detailed search, parses results, cleans the data, and stores potential leads in **Google Sheets**, including:

- **Name**
- **Job Title**
- **Company**
- **LinkedIn Profile URL**

---

## 🚀 Workflow Overview

<img width="935" height="383" alt="image" src="https://github.com/user-attachments/assets/50be8189-7da5-461d-a046-09415f274063" />


The workflow includes:

1. **Manual Trigger** → Initiates the workflow on demand.  
2. **HTTP Request** → Queries a search engine API (e.g., SerpApi, ScraperAPI) for LinkedIn profiles matching search criteria.  
3. **Data Processing (JavaScript Expression)** →  
   - Iterates through search results.  
   - Validates LinkedIn profile URLs.  
   - Cleans and parses job titles using a custom `parseLinkedInTitle` function.  
   - Extracts `Name`, `Job Title`, and `Company`.  
   - Handles exceptions gracefully.  
4. **Google Sheets Node** → Appends structured lead data into a designated Google Sheet.

---

## ✨ Key Features

- **🎯 Targeted Search**  
  Queries LinkedIn profiles filtered by job titles, industries, and company size.  

- **🧩 Robust Data Parsing**  
  Extracts clean, structured data from messy/unstructured titles.  

- **⚡ Exception Handling**  
  Handles edge cases (e.g., `"Title at Company"`, `"Title, Company"`, missing data).  

- **🧹 Automated Data Cleaning**  
  Ensures consistent and usable final output.  

- **📊 Google Sheets Integration**  
  Appends each lead into a structured spreadsheet.  

---

## 🛠️ Technology Stack

- **Core Automation** → [n8n.io](https://n8n.io/)  
- **Data Source** → Search engine API (e.g., [SerpApi](https://serpapi.com/), [ScraperAPI](https://www.scraperapi.com/))  
- **Data Storage** → Google Sheets  
- **Core Logic** → JavaScript (ES6)  

---

## ⚙️ How It Works

1. **Trigger Workflow**  
   - Run the workflow manually inside n8n.  

2. **Fetch Data**  
   - The HTTP Request node sends queries like:  
     ```plaintext
     site:linkedin.com/in ("Marketing Manager") ("Computer Software")
     ```

3. **Parse Results**  
   - Extracts and validates LinkedIn profile data.  
   - Uses `parseLinkedInTitle` function to split raw titles into **Name | Job Title | Company**.  

4. **Store Leads**  
   - Appends the cleaned results into Google Sheets.  



