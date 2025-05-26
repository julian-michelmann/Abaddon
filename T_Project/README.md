## 🧭 Standard Workflow

This template follows Abaddon's methodology for systematic target exploitation.

### 📁 Directory Structure
- **T_** prefix: Template directories and files (starting points)
- **R_** prefix: Result files (where you save tool outputs and raw data)
- **E_** prefix: Extraction files (where Abaddon documents analyzed data and insights)

### 🔍 Basic Scanning
- [ ] Start UDP Scan (`R_NMAP_UDP.txt`)
- [ ] Start TCP Scan (`R_NMAP_TCP.txt`)
- [ ] Perform Subdomain Enumeration (`R_Subdomain_Enumeration.txt`)

### 🌐 Website Enumeration
- [ ] Run Directory Bruteforce (`R_Directory_Enumeration.txt`)
- [ ] Collect Technology Stack (`R_Wappalyzer.txt` → `E_TechStack.md`)
- [ ] Inspect Page Source
- [ ] Identify "features" input fields / APIs: `cp -r T_Web_Feature <FEATURE_NAME>`
- [ ] Test for Path Traversal (`R_Path_Traversal.txt` → `E_Path_Traversal.md`)
- [ ] Check for Local File Inclusion
- [ ] Explore Additional Traversal Opportunities
- [ ] Search for Known Vulnerabilities

### 📊 Workflow Process
1. You perform actions and save results in R_ files
2. Ask Abaddon to analyze these files
3. Abaddon extracts valuable data and saves it in E_ files
4. Abaddon takes notes in the E_Scratch.md file for potentially relevant information
5. Abaddon shares expert opinions about results and extracted data
6. Abaddon provides hints about what actions to pursue next
7. When asked, Abaddon can perform actions via terminal commands
8. Abaddon serves as a researcher when asked for specific information
9. Abaddon improves the templates when adjustments would make sense based on daily activities

### 📝 Documentation
- `E_Scratch.md`: Abaddon's notes on potentially relevant information
- `E_Notes.md`: Additional notes and observations
- `E_VULNERABILITIES.md`: Documented weaknesses and exploitation status
- `E_CREDENTIALS.md`: Harvested usernames, passwords, API keys, and tokens
