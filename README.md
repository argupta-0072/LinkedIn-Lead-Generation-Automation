# LinkedIn Lead Generation Automation
<img width="1869" height="765" alt="image" src="https://github.com/user-attachments/assets/f3b36c24-f880-4cba-beca-

LinkedIn Lead Generation Automation with n8n
This project is an automated workflow built using the low-code platform n8n to perform targeted lead generation from LinkedIn. The system executes a detailed search, intelligently parses the results, cleans the data, and populates a Google Sheet with a structured list of potential leads, including their name, job title, company, and LinkedIn profile URL.

Key Features
Targeted Search: Utilizes an HTTP Request node to query a search engine API with specific criteria for job titles, industries, and company sizes.

Robust Data Parsing: Employs a sophisticated JavaScript function to intelligently parse unstructured and inconsistent titles from search results to reliably extract key information.

Advanced Exception Handling: The parsing logic is designed to handle numerous edge cases, such as varied title formats (e.g., "Job Title at Company," "Job Title, Company"), extra punctuation, and missing data points.

Automated Data Cleaning: Automatically cleans and structures the extracted data into a consistent format, ensuring the final output is clean and usable.

Google Sheets Integration: Seamlessly appends the structured lead data into a designated Google Sheet, creating an organized and actionable database.

How It Works
The entire process is orchestrated within a single n8n workflow:

Manual Trigger: The workflow is initiated on-demand with a manual trigger.

HTTP Request: The first node sends a precisely crafted search query (e.g., site:linkedin.com/in ("Marketing Manager") ("Computer Software")) to a search engine API like SerpApi to fetch a list of relevant LinkedIn profiles.

Data Processing (Code Expression): The raw JSON response from the API is then passed to the Google Sheets node. A powerful JavaScript expression embedded within this node performs the following actions:

It iterates through each search result.

It identifies valid LinkedIn profile links.

A custom parseLinkedInTitle function cleans the messy title string and intelligently extracts the Name, Job Title, and Company by testing for common separators like " at " and ",".

It handles exceptions gracefully, ensuring that malformed results do not crash the workflow.

Output to Google Sheets: The final, structured array of lead data is directly passed to the Google Sheets "Append Row" operation. The node then automatically adds each lead as a new row in the specified spreadsheet.

Technology Stack
Core Automation: n8n.io

Data Source: A search engine API (e.g., SerpApi, ScraperAPI)

Data Storage: Google Sheets

Core Logic: JavaScript (ES6)

This project serves as a powerful example of how low-code platforms can be extended with custom code to create sophisticated and reliable automation solutions for business-critical tasks like lead generation.

