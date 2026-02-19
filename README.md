# Defensive-Security-Project
This project demonstrates reviewing Windows and Apache Attack Logs. This project we worked in a group and spit up the work I was tasked with reviewing the Apache Logs for a the simulated comapany **VSI**

# Objective
- Tracking what type of HTTP method was being used.
- Create a table showing the top 10 domains that refer to the VSI website
- Create a table showing the count of HTTP response codes
- Using splunk to compile this data

# Tools & Technologies
- Splunk
- Windows
- Apache
- SPL
- Dashboard & Visualizations

# Methodology

### 1. Preperation/Setup
- Imported Apache access logs into Splunk
- Verified timestamp extraction and field parsing
- Ensured fields such as method, status. referer, and uri_path were correctly recgonized

### 2. Data Collection
- I wrote SPL queries to answers specific questions about the dataset [questions with answers](
- **HTTP Methods Used:** index=apache_logs
| stats count by method
| sort - count

- **TOP 10 Referring Domains:** index=apache_logs
| stats count by referer
| sort - count
| head 10

- **HTTP Response Counts:** index=apache_logs
| stats count by status
| sort - count

### 3. Visualization
- Created tables for method usage, referrers, and response codes
- Built car charts and pie charts for easier interpretation
- Used Splunk dashboards to present findings clearly

# Key Findings

**HTTP Methods**

Identified which HTTP methods (GET, POST, HEAD, etc.) were most frequently used, helping understand user behaviors and potiential attack patterns.

**Top Referring Domains**

Created a table showing the top 10 domains sending traffic to the site. Useful for marketing, threat intel, and anaomaly detection.

**HTTP Response Codes**

**Analyzed response code distribution(200, 404, 500) to identify:**
- Successful requests
- Missing pages
- Server errors
- Potiential misconfigurations

**Splunk as Log Analysis Tool**

Splunk made it easy to:
- Parse large log files
- Build queries quickly
- Visualize trends
- Extract insights for security and operations

# Skills Deomonstrated
- Log ingestion and parsing
- SPL query writing
- HTTP traffic analysis
- Data visualization
- SIEM-style investigation
- Understading of wer server behavior

I learned how logs tell a story, how to distinguish normal from malicious behavior, and how to use tools to gain deeper insight.

[Full presentation here](











