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
