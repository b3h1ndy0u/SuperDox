# ClatScope Info Tool
ClatScope Info Tool – A versatile OSINT utility for retrieving geolocation, DNS, WHOIS, phone, email, usernames, person related data, password strength, data breach information and more. Perfect for investigators, pentesters, or anyone looking for a quick reconnaissance script.

![clatscope](https://github.com/user-attachments/assets/0bb01589-79db-4b46-8637-43832106ac2b)



**Version:** BETA  
**Author:** Joshua M Clatney aka Clats97 (Ethical Pentesting Enthusiast)

## Description
ClatScope Info Tool is an all-in-one OSINT (Open-Source Intelligence) utility script that queries public APIs, DNS records, and other online resources to gather and display information about IPs, domains, emails, phone numbers, and more. You will need a Google Custom Search API and a Have I Been Pwned API to take advantage of all the features ClatScope has to offer.

## Features
1. **IP Information** – Extract IP geolocation, ISP, and Google Maps link.  
2. **Deep Account Search & Username Search** – Check over 250 websites to see if a given username exists.  
3. **Phone Number Parsing** – Validate phone numbers, determine carriers, and check region.  
4. **DNS & Reverse DNS** – Retrieve DNS records (A, CNAME, MX, NS) and PTR records.  
5. **Email Lookup** – Check MX records, validate format, parse email headers for IP addresses, and more.
6. **Email Breach Search** - Checks Have I Been Pwned to determine if an email address has been compromised.
7. **Email Header Analysis** - Analyzes an email header and extracts data.
8. **Person Search** - Look up public details about a person.   
9. **WHOIS Lookup** – Fetch domain registration details.  
10. **Password Strength Check** – Rate your password’s strength based on multiple criteria.  
11. **Theme/Color Settings** – Adjust console output color.

## Installation
1. **Clone the Repository**:
    
    git clone https://github.com/Clats97/ClatScope-Info-Tool.git
    
2. **Install Dependencies**:
    
    pip install requests pystyle phonenumbers dnspython email_validator beautifulsoup4 whois 
   
3. **Run the Script**:
    bash
    python clatscope_info_tool.py
    
## Usage
When you run the script, it will present you with a menu. Simply type the number corresponding to the function you wish to use, and follow the on-screen prompts. For example:

- **IP Info Search** – Option [1]
- **Deep Account Search** – Option [2]
- **DNS Search** – Option [4]
- etc.

- **IN ORDER FOR THE PASSWORD STRENGTH ANALYZER TO WORK PROPERLY, YOU MUST OPEN CLATSCOPE INFO TOOL IN THE FOLDER THAT HAS "PASSWORDS.TXT"**

- You will need to enter your own Google Custom Sesarch & Have I been Pwned API key to use all the features in this tool.

## Contributing
1. Fork this repository`
2. Create a new Pull Request  

We welcome any improvements or additional OSINT features!

## License
This project is released under the Apache 2.0 License.

