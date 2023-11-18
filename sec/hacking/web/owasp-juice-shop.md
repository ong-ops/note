# OWASP Juice Shop

## Walking through the application (Reconnaissance)

- In Burp, set the Intercept mode to `off`
- Browse around the site
- Burp will log different requests from the server

## Injection

### Type of injection attack

- SQL Injection
- Command Injection
- Email Injection: allow malicious users to send email messages without prior authorization by the email server when attacker adds extra data to fields, which are not interpreted by the server correctly.
- https://owasp.org/www-project-top-ten/2017/A1_2017-Injection.html

### SQL Injection

- Inject `{"email":"' or 1=1--","password":"a"}` to login Admin account
- Inject `{"email":"bender@juice-sh.op'--","password":"a"}` to login bender account
- Inject `1=1` can be used when the email or username is not known or invalid

## Exploting authentication

### Vulnerable

- Weak passwords in high privileged accounts
- Forgotten password pages
- https://owasp.org/www-project-top-ten/2017/A2_2017-Broken_Authentication.html

## Sensitive Data

- `Poison Null Byte` character bypass (`%00`)

 You successfully solved a challenge: Error Handling (Provoke an error that is neither very gracefully nor consistently handled.)
169940f83378cc420ae4fdeb9c1f73631a2baee6

## Broken Access Control

## XSS

- DOM (Special) uses the HTML env to execute malicious js. commonly uses the `<script></script>` HTML tag
- Persistent (Server-side) is run when the server loads the page containing it. occur when the server does not sanitise the user data when it is uploaded to a page. commonly found on blog posts
- Reflected (Client-side) is run on the client-side end of the web app. commonly found when the server doesn't sanitise search data
- Attackers can use XSS to defeat any automated CSRF defense the app might employ
