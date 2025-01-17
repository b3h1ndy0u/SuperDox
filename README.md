# ClatScope Info Tool
ClatScope Info Tool – A versatile OSINT utility for retrieving geolocation, DNS, WHOIS, phone, email, usernames, person related data, password strength, data breach information and more. Perfect for investigators, pentesters, or anyone looking for a quick reconnaissance script.

![OSINT](https://github.com/user-attachments/assets/7ab0f57d-091b-46c7-92fd-db61dad5809a)

**DONT WANT TO SET UP YOUR API KEYS TO GET FULL FUNCTIONALITY OF CLATSCOPE INFO TOOL? STARTING JANUARY 12, 2024 A SUBSCRIPTION SERVICE IS AVAILABLE. YOU WILL BE PROVIDED WITH A CUSTOM SCRIPT WITH API KEYS THAT LOGS IP ADDRESS, USER AGENT, USAGE, AND OTHER DETAILS TO ENSURE THERE IS NO UNAUTHORIZED ACCESS OR MISUSE. SHARING IS PROHIBITED AND WILL RESULT IN AN IMMEDIATE REVOCATION OF THE KEY. TURN OFF YOUR VPN WHEN USING IT TO PREVENT AN AUTOMATIC BAN FOR IMPOSSIBLE TRAVEL / SHARING. YOUR SUBSCRIPTION IS VALID FOR 30 DAYS. IF YOU RENEW, YOU WILL BE ISSUED A NEW KEY AT THE START OF YOUR RENEWAL. KEYS ARE ROTATED MONTHLY AND ARE SINGLE USE AND MONITORED. EMAIL SKYLINE92X@PM.ME FOR DETAILS AND / OR VISIT https://buymeacoffee.com/clats97/e/357348 TO SUBSCRIBE. NO REFUNDS**

![Screenshot 2025-01-14 161144](https://github.com/user-attachments/assets/947375f5-fe38-443e-bb2f-83b4393aa812)

ClatScope is an OSINT tool that performs various lookups and analyzes provided data:

1.	**IP Address Lookups:**

- Retrieves IP geolocation details, ISP, and region.
- Performs DNSBL checks to see if an IP is blacklisted.

2.	**Phone Number Lookups:**

- Fetches basic phone number details (region, carrier).
- Conducts a reverse phone lookup via Google search (Custom Search API).

3.	**Email Lookups and Analysis:**

- Checks email validity and existence of mail exchanger (MX) records.
- Performs data breach checks against Have I Been Pwned (HIBP).
-Analyzes raw email headers (extracting IP addresses, SPF, DKIM, DMARC alignment, etc.).

4.	**Username Searches:**

- Searches across multiple platforms (e.g., Facebook, Twitter, Instagram, etc.) to see if a username exists.

5.	**Domain / Website Lookups:**

- DNS record queries (A, CNAME, MX, NS).
- WHOIS details (registrar, creation date, etc)
- IS details (registrar, creation date, etc.).
- SSL certificate analysis.
- Robots.txt and sitemap.xml retrieval to discover site structure.
- Webpage metadata extraction (title, meta keywords, meta description).

7.	**Password Strength Checking:**

- Evaluates complexity based on length, character variety, and common word usage.

8.	**Additional Features:**

- Person name searches (via Google’s Custom Search API) to get text from resulting pages.
- Reverse DNS lookups for IP addresses.
- Settings menu to change color scheme.

Throughout the script, a textual UI is presented, prompting the user for inputs (e.g., IP address, phone number). Results are printed in styled ASCII frames using the pystyle library for aesthetics.

**Version:** 1.02
**Author:** Joshua M Clatney aka Clats97 (Ethical Pentesting Enthusiast)

## Description
ClatScope Info Tool is an all-in-one OSINT (Open-Source Intelligence) utility script that queries public APIs, DNS records, and other online resources to gather and display information about IPs, domains, emails, phone numbers, and more. You will need to enter the required API keys to take advantage of all the features ClatScope Info Tool v1.02 has to offer.

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
11. **Reverse Phone Search** - Gets references from a number and extracts data from Google.
12. **Robots.txt / Sitemap.xml Check** - Finds a websites robots.txt and Sitemp.xml files.
13. **SSL Certificate Search** - Finds a webpage's SSL certificate information 
14. **DNSBL Search** - Gets blacklist information on a URL
15. **Website Metadata Fetch** - Retrieves meta tags and more from a website.
16. **Travel Risk Search** - Provides a detailed, 40 parameter analysis of a geographical location.
17. **Botometer Search** - Helps identify possible X/Twitter bots. The lower the score, the lower probability it is not a bod. A higher score indicates a higher probability that the account is a bot.
18. **Business Search** - Provides details about a business.
19. **Theme/Color Settings** – Adjust console output color.

## Installation
1. **Clone the Repository (or download the zip)**:
    
    git clone https://github.com/Clats97/ClatScope.git
    
2. **Install Dependencies**:
    Open command prompt and write:

   pip install requests pystyle phonenumbers dnspython email-validator beautifulsoup4 lxml tqdm python-whois openai==0.28

   3. **Run the Script**:
    Click on the Python file or open it in Visual Studio Code 
    
## Usage
When you run the script, it will present you with a menu. Simply type the number corresponding to the function you wish to use, and follow the on-screen prompts. For example:

- **IP Info Search** – Option [1]
- **Deep Account Search** – Option [2]
- **DNS Search** – Option [4]
- etc.

- **IN ORDER FOR THE PASSWORD STRENGTH ANALYZER TO WORK PROPERLY, YOU MUST OPEN CLATSCOPE INFO TOOL IN THE FOLDER THAT HAS "PASSWORDS.TXT"**

- You will need to enter your own Google Custom Search, OpenAI, Botometer, Perplexity & Have I been Pwned API key to use all the features in this tool (unless you subscribe to the above mentioned service).
- If you want to use the password strength checker against a dictionary or known common-passwords file, place your dictionary file as passwords.txt in the same directory as the script. There is already a dictionary file in the installation package with millions of common passwords.
- The script references a Google Custom Search API key (API_KEY, CX, and CLIENT_ID), an OpenAI API key, a Perplexity API key, a Botometer API key, and HIBP API key. If you want to use the features that query external services (like Google search or HIBP), you must obtain valid keys and place them in the script.
- **Important:** If you do not have valid API keys, the related external queries (e.g. person search, reverse phone lookup, business search, travel risk search, Botometer search) will fail or return errors.


**Below is a closer look at what each function in the script accomplishes:**

1.	**Main Menu & main() Function**
- Displays the ASCII-based menu.
- Repeatedly prompts for user input.
- Clalls the relevant function (like ip_info(ip) or deep_account_search(nickname)) based on the menu choice.

2.	**ip_info(ip)**
- Uses requests.get("https://ipinfo.io/{ip}/json") to fetch IP-related information.
- Displays city, region, country, ISP (org), approximate location, etc.

3.	**deep_account_search(nickname)**
-Iterates over a large list of possible platform URL formats (e.g., https://twitter.com/{}, https://reddit.com/user/{}, etc.).
- Sends asynchronous HTTP requests with ThreadPoolExecutor to quickly check which URLs respond with status code 200.
- Prints whether each potential profile is “Found” or “Not Found.”

4.	**phone_info(phone_number)**
- Parses the phone number using phonenumbers.parse(...).
- Receives geocoding (country, region) and the carrier operator.
- Validates whether the number format is correct.

5.	**reverse_phone_lookup(phone_number)**
- Uses Google’s Custom Search API to search references to the phone number on the internet.
-Fetches text from each top link and displays them.

6.	**dns_lookup(domain)**
- Uses the dns.resolver.resolve() method to query A, CNAME, MX, and NS records.
- Shows “No records found” if none exist.

7.	**email_lookup(email)**
- Validates email format with email_validator.
- Checks DNS MX records for the domain.
- Declares “Likely Valid” if MX records are found, or “Might be invalid” otherwise.

8.	**person_search(first_name, last_name, city)**
- Leverages Google’s Custom Search API to look for references to a person’s name + location.
- Fetches page text, then displays top results in a nicely formatted table.

9.	**analyze_email_header(raw_headers**
- Parses raw email headers using Python’s built-in email.parser.
- Extracts IP addresses from any “Received” lines.
- Performs geolocation on each IP.
- Checks for SPF, DKIM, and DMARC results in Authentication-Results fields.

10.	**haveibeenpwned_check(email)**
- Calls the HIBP v3 API.
- If breaches are found, prints each breach name, domain, date, data classes.
- Otherwise, declares “No breaches found.”

11.	**whois_lookup(domain)**
- Uses Python’s whois to retrieve domain registration data.
- Shows registrar name, creation/expiration dates, name servers, etc.

12.	**password_strength_tool() / check_password_strength(password)**
- Checks password length and usage of uppercase, lowercase, digits, and symbols.
- Looks for common words in the passwords.txt file if present.
- Outputs “Weak,” “Moderate,” or “Strong.”

13.	**check_ssl_cert(domain)**
- Creates a secure socket connection on port 443 to retrieve the SSL certificate.
- Prints the certificate issuer, validity range, etc.

14.	**check_robots_and_sitemap(domain)**
- Tries to retrieve robots.txt and sitemap.xml from https://{domain}/.
- Prints the HTTP status code and the first few lines of the file, if it exists.

15.	**check_dnsbl(ip_address)**
- Reverses the IP (e.g., 1.2.3.4 → 4.3.2.1) and checks several DNS blacklists by querying
4.3.2.1.zen.spamhaus.org, etc.
- If an answer is returned, the IP is blacklisted on that DNSBL.

16.	**fetch_webpage_metadata(url**
- Fetches a webpage’s <title>, meta description, and meta keywords to provide quick SEO context.

17.	**settings() / change_color()**
- Provides a submenu to alter the default console color for script output.

18. **travel_risk_search**
- Provides over 40 references to risks while travelling abroad.

19. **botometer_search**
- Identifies potential X/Twitter bot accounts.

20. **business_search**
- Retrieves information about a business.
________________________________________


**THIS TOOL IS NOT PERFECT. THERE IS STILL ROOM FOR IMPROVMENT, AND I AM WORKING ON ADDING NEW FEATURES AND REFINEMENTS. SOMETIMES A USERNAME SEARCH WILL RESULT IN A FALSE POSITIVE AND/OR THE URL WILL NOT RESOLVE. IT HAS BEEN TESTED AND IS ACCURATE, BUT NOT 100% ACCURATE. VERIFY THE OUTPUTS IF YOU ARE NOT SURE.**

## Contributing
1. Fork this repository`
2. Create a new Pull Request
3. Email me at skyline92x@pm.me for feature requests or ideas.

I welcome any improvements or additional OSINT features!

## License
This project is released under the Apache 2.0 License.

Copyright 2025 Joshua M Clatney (Clats97s ClatScope Info Tool) 

