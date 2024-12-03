
Website Checker
Description
The Website Checker program reads a list of website URLs from a CSV file, checks their availability and security (whether they use HTTP or HTTPS), and prints the HTTP status description for each website.

This program utilizes the requests library to make HTTP requests and the fake_useragent library to simulate user agent strings, ensuring compatibility with most websites.

Features
Reads website URLs from a CSV file.
Automatically appends https:// to URLs without a proper scheme.
Sends an HTTP GET request to each website to check its availability.
Provides a detailed status description of each website (e.g., 200 OK, 404 Not Found).
Identifies if the website is using HTTP or HTTPS.
Handles errors gracefully when a website is unreachable or invalid.
Requirements
Python 3.8 or later
Libraries:
requests
fake-useragent
Installation
Clone or download this repository.

Install the required Python dependencies:

bash
Copy code
pip install requests fake-useragent
Ensure the websites.csv file exists in the same directory as the program. The CSV file should have the following format:

csv
Copy code
Name,URL
Google,google.com
Example,http://example.com
Invalid,invalid-url
Usage
Run the program by executing the following command in your terminal:

bash
Copy code
python3 website_checker.py
The program will read URLs from websites.csv, check their availability, and print the status for each website.

Output Example
For a CSV file containing:

csv
Copy code
Name,URL
Google,google.com
Example,http://example.com
Invalid,invalid-url
The program will produce output like:

vbnet
Copy code
https://google.com (200 OK) Request fulfilled, website is available.
https://example.com (200 OK) Request fulfilled, website is available.
**Could not get information for website: "https://invalid-url".
How It Works
Load Websites: The get_websites function reads URLs from the CSV file, ensuring each URL has a valid scheme (https:// is added if missing).

User Agent: The get_user_agent function uses the fake-useragent library to generate a browser-like user agent string for HTTP requests.

Check Status: The check_website function sends an HTTP GET request to the website, retrieves the HTTP status code, and provides a human-readable description using the HTTPStatus module.

Output: Results are printed to the console, detailing the status and security of each website.

Error Handling
If the program encounters an invalid website or cannot reach a site, it will print an error message instead of halting execution.
Example:

arduino
Copy code
**Could not get information for website: "https://invalid-url".
Future Enhancements
Add support for exporting results to a file (e.g., CSV or JSON).
Implement a retry mechanism for failed requests.
Add multithreading for faster processing of large lists of websites.
Integrate additional checks, such as SSL certificate validation.
License
This project is licensed under the MIT License. See the LICENSE file for details.

Contribution
Feel free to submit issues or contribute improvements to the project by submitting a pull request.