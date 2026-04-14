# SQL-Injection-Lab
Simple SQL Injection Attack Demo

Since you are interviewing with Upwind, a good README should look clean, professional, and emphasize the security concepts behind the code.

Here is a template you can copy and paste into a file named README.md in your GitHub repository.
SQL Injection (SQLi) Demonstration Lab

A lightweight, interactive web-based lab designed to demonstrate common SQL injection vulnerabilities, including Authentication Bypass and In-Band (UNION-based) Data Extraction.
🚀 Purpose

This project serves as a training tool for novices to understand how unsanitized user input can manipulate backend database queries. It provides a visual representation of how attackers transition from bypassing login screens to exfiltrating sensitive record sets.
🛠️ Vulnerabilities Demonstrated
1. Authentication Bypass

By using a tautology (a statement that is always true), an attacker can bypass credential verification.

    Payload: ' OR 1=1 --

    Concept: This modifies the query logic to WHERE username = '' OR 1=1, which evaluates to True for every row, granting access without a valid password.

2. UNION-Based Data Extraction

Attackers use the UNION operator to combine the results of the original query with a secondary query of their choosing.

    Payload: ' UNION SELECT id, username, secret FROM users --

    Concept: This forces the application to append and display the contents of the users table (IDs, usernames, and sensitive secrets/hashes) directly in the UI.

🛡️ Mitigation & Prevention

To secure applications against these attacks, the following defenses are implemented at the code level:

    Parameterized Queries (Prepared Statements): The primary defense. Input is treated as a literal value, never as executable code.

    Input Validation: Enforcing strict allow-lists for expected input formats.

    Principle of Least Privilege: Ensuring the database user account has restricted permissions.

💻 Tech Stack


How to Run

    Clone the repository.

    Open index.html in any modern web browser.

    Use the payloads listed above in the Username field to trigger the simulated vulnerabilities.

    Frontend: HTML5, CSS3, JavaScript (ES6)

    Hosting: GitHub Pages / Azure Static Web Apps
