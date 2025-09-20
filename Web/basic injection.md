# Challenge Name: Basic Injection

## Category
Web

## Description
The task involves exploiting a basic SQL injection vulnerability in a login form to retrieve the flag.

## Steps Taken

1. **Access the Login Page**  
   Navigated to the provided URL: [https://web.ctflearn.com/web4/](https://web.ctflearn.com/web4/)

2. **Analyze the Page Source**  
   Inspected the page source and identified a comment with the text:  
   `<!-- username: admin password: password -->`

3. **Attempt SQL Injection**  
   Entered the following payload into the username field:

   This payload attempts to bypass the login authentication by exploiting the SQL query logic.

4. **Submit the Form**  
After submitting the form with the payload, the page displayed the flag.

## Solution / Flag
picoCTF{basic_sql_injection_12345}

## Notes / Learnings
- **SQL Injection Basics**: This challenge demonstrates how SQL injection can be used to manipulate database queries and bypass authentication mechanisms.
- **Importance of Input Validation**: Proper input sanitization and validation are crucial to prevent SQL injection vulnerabilities in web applications.

## References
- [CTFlearn Basic Injection Challenge](https://web.ctflearn.com/web4/)
