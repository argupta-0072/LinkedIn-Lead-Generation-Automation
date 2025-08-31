# LinkedIn Lead Generation Automation

![Project Banner/Image]([<img width="1869" height="765" alt="image" src="https://github.com/user-attachments/assets/f3b36c24-f880-4cba-beca-e20055b37d16" />
])

A Python-based automation script designed to streamline the lead generation process on LinkedIn. This tool automates searching for profiles, sending connection requests with personalized messages, and exporting lead data, saving hours of manual work for sales and marketing professionals.

---

## 📜 Table of Contents

- [Overview](#-overview)
- [Key Features](#-key-features)
- [How It Works](#-how-it-works)
- [Tech Stack](#-tech-stack)
- [⚠️ Disclaimer](#️-disclaimer)
- [Setup & Installation](#-setup--installation)
- [Usage](#-usage)
- [Configuration](#-configuration)
- [Future Improvements](#-future-improvements)
- [Contributing](#-contributing)
- [License](#-license)

---

## 📖 Overview

Manually searching, connecting, and messaging potential leads on LinkedIn is a repetitive and time-consuming task. This project was created to automate these actions in a human-like manner to avoid detection. The script leverages Selenium to control a web browser, navigating LinkedIn's interface to perform tasks based on user-defined search criteria.

**The primary goal is to build a targeted lead list efficiently, allowing you to focus on building relationships rather than on manual prospecting.**

---

## ✨ Key Features

- **🎯 Targeted Search:** Automatically searches for profiles based on keywords like job title, company, industry, and location.
- **🤝 Automated Connections:** Sends personalized connection requests. You can use message templates with placeholders (e.g., `{firstName}`, `{jobTitle}`) for a personal touch.
- ** scrapping Profile Scraping:** Extracts key information from profiles, such as name, job title, company, and location.
- **✍️ Automated Messaging:** Sends customized follow-up messages to new connections after a specified delay.
- **📊 Data Export:** Saves all collected lead data into a structured format (e.g., CSV or Excel) for easy integration with CRM systems or further analysis.
- **⚙️ Configurable & Customizable:** Easily configure search parameters, message templates, and automation speed through a simple config file.
- **🧠 Human-like Behavior:** Incorporates random delays and realistic actions to minimize the risk of account suspension.

---

## 🔧 How It Works

The script operates by launching a browser instance controlled by **Selenium WebDriver**. It then performs the following steps:

1.  **Login:** Securely logs into your LinkedIn account using credentials stored in an environment file.
2.  **Search:** Navigates to the search page and inputs the criteria defined in the configuration file.
3.  **Iterate & Connect:** Scans through the search results, page by page. For each profile that is not yet a connection, it visits the profile, clicks the "Connect" button, and pastes a personalized message.
4.  **Data Extraction:** As it processes each profile, it scrapes relevant data.
5.  **Save Progress:** The collected data is appended to a CSV file in real-time.
6.  **Logout & Close:** Once the process is complete or the target number of connections is sent, it safely logs out and closes the browser.

---

## 💻 Tech Stack

- **Language:** Python 3.x
- **Automation/Scraping:** Selenium
- **Data Handling:** Pandas
- **Configuration Management:** JSON / YAML
- **Environment Variables:** `python-dotenv`

---

## ⚠️ Disclaimer

This script is intended for educational and research purposes only. Automating interactions on LinkedIn is against their User Agreement and can result in a temporary or permanent ban of your account. **Use this tool at your own risk.**

The developers of this project are not responsible for any consequences of its use. It is highly recommended to use this script with a test account and to implement conservative settings (long delays, limited daily actions) to minimize risk.

---

## 🚀 Setup & Installation

Follow these steps to get the project up and running on your local machine.

**Prerequisites:**
- Python 3.8+
- Google Chrome (or another supported browser)
- Git

**1. Clone the Repository:**
```bash
git clone [https://github.com/](https://github.com/)[YourUsername]/[YourRepoName].git
cd [YourRepoName]
```

**2. Create a Virtual Environment:**
It's recommended to use a virtual environment to manage dependencies.
```bash
# For Windows
python -m venv venv
venv\Scripts\activate

# For macOS/Linux
python3 -m venv venv
source venv/bin/activate
```

**3. Install Dependencies:**
```bash
pip install -r requirements.txt
```

**4. Download WebDriver:**
Download the appropriate [WebDriver](https://www.selenium.dev/documentation/webdriver/getting_started/install_drivers/) for your browser (e.g., ChromeDriver for Google Chrome) and place it in the project's root directory or ensure it's in your system's PATH.

**5. Configure Environment Variables:**
Create a `.env` file in the root directory by copying the example file:
```bash
cp .env.example .env
```
Now, open the `.env` file and add your LinkedIn credentials:
```
LINKEDIN_EMAIL="your_email@example.com"
LINKEDIN_PASSWORD="your_super_secret_password"
```

---

## 🏃 Usage

Once the setup is complete, you can run the script from the terminal.

**1. Customize Configuration:**
Open `config.json` (or your config file) and set your search parameters and message templates.
```json
{
  "search_keywords": "Software Engineer in Test",
  "location": "India",
  "connection_message": "Hi {firstName}, I came across your profile and was impressed by your experience at {companyName}. I'd love to connect and learn more about your work.",
  "max_connections_to_send": 50
}
```

**2. Run the Main Script:**
```bash
python main.py
```
The script will now launch the browser and begin the automation process. You can watch its progress in the terminal.

---

## 🛠️ Configuration

The `config.json` file allows you to control the bot's behavior without editing the code. Key parameters include:

- `search_keywords`: The job title or keywords to search for.
- `location`: The geographical location to target.
- `connection_message`: The template for your connection request message.
- `max_connections_to_send`: A limit to prevent sending too many requests in one session.
- `delay_settings`: Min/max values for random delays between actions.

---

## 🔮 Future Improvements

- [ ] **GUI Implementation:** Develop a simple graphical user interface using Tkinter or PyQT for easier use by non-developers.
- [ ] **Proxy Support:** Add proxy rotation to reduce the risk of IP-based blocking.
- [ ] **Advanced AI Messaging:** Integrate a language model (like GPT) to generate more dynamic and context-aware messages.
- [ ] **Dashboard:** Create a simple dashboard to visualize collected lead data and automation stats.
- [ ] **Dockerization:** Package the application into a Docker container for easy deployment.

---

## 🤝 Contributing

Contributions are welcome! If you have ideas for new features or improvements, feel free to fork the repository, make your changes, and submit a pull request. Please create an issue first to discuss the proposed changes.

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).
