# RPA - Robotic Process Automation in vulnerability scanning on the NVD website - National Vulnerability Database

## Vulnerability Query Website
##### This is a website where software vulnerabilities can be viewed through a search by a time interval of up to 120 days. The site (available at: https://nvd.nist.gov/vuln/search) is linked to NIST (National Institute of Standards and Technology). Vulnerabilities have identifiers (CVEs - Common Vulnerabilities and Exposures) to catalog them and scoring (CVSSs - Common Vulnerability Scoring System) that labels them as low, medium, high, or critical vulnerabilities (more about CVE and CVSS: https://aiqon.com.br/blog/explicar-o-cve-e-o-cvss/).
![image](https://user-images.githubusercontent.com/8295184/169683165-3aeaf0d2-ff8d-4f45-b024-87fad264ff30.png)

## The Solution
##### An RPA was developed, consisting of 4 bots and 2 access methods, as well as 2 means of receiving results. All programs were developed in Python (using various packages such as Selenium, Pandas, Openpyxl, BeautifulSoup, etc.) with the help of QT Designer (linked to Python via PyQt6 package) for creating the graphical interface, and the use of Flask, Heroku, HTML, and others for creating the web application. In the generated spreadsheet, critical CVEs are highlighted in red and high CVEs in yellow. The same data is sent in the body of the requester's email and also via a WhatsApp text message if the user wishes. Attached to both the email and the WhatsApp message, the complete spreadsheet with all results (regardless of the CVSS values) is sent. CVEs with CVSS scores greater than or equal to 7 are the ones highlighted in the message body. Furthermore, for study and protection purposes, the file containing the login and configuration data of the application's sender email was encrypted (algorithm used: AES - Advanced Encryption Standard). In summary, to make all this work, it was necessary to create the following bots:
  * Web scraping execution bot
  * Excel registration bot
  * Email sending bot
  * WhatsApp sending bot

### This is how the graphical interface looks:
<img src="https://user-images.githubusercontent.com/8295184/170782742-adcbaa72-7005-49bf-8e0a-7939bb24934e.png" width="300" height="400">

### This is how the web interface looks:
<img src="https://user-images.githubusercontent.com/8295184/169683476-b7e3657b-a2df-4493-91d5-8d361f3cb1e6.png" width="300" height="400">

### This is how the emails roughly look like:
<img src="https://user-images.githubusercontent.com/8295184/169682516-90f78a2c-bb8c-410e-91cf-2d7985b6ac8a.png" width="900" height="600">

### This is how the WhatsApp messages roughly look like:
<img src="https://user-images.githubusercontent.com/8295184/169682569-13e73088-cfef-44ce-975e-f53d63223473.png" width="500" height="400">

## Links to the website, desktop application download, and explanatory video:
  * https://appg3wspwa.herokuapp.com/ >>> Site
  * https://www.4shared.com/s/fJjZATZ0-ea >>> Download
  * https://youtu.be/ei0uTlXjT6Y >>> Vídeo
