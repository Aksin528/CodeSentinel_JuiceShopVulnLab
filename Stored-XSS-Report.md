# Vulnerability Report: Reflected XSS

## 1. Title
Reflected Cross-Site Scripting (XSS) in Search Functionality

## 2. Summary
The application’s search input does not properly sanitize user input, allowing an attacker to inject malicious JavaScript that executes in the browser of other users.

## 3. Vulnerability Type
Reflected Cross-Site Scripting (XSS)

## 4. Impact
- Arbitrary JavaScript execution in users’ browsers
- Potential session hijacking, phishing, or redirection
- Could lead to further attacks if combined with social engineering

## 5. Reproduction Steps
1. Navigate to:  
   `http://localhost:3000/#/search?q=<iframe src="javascript:alert('you have been hacked')">`

2. Result: JavaScript is executed, displaying an alert popup in the user’s browser.

3. Score Board confirms "XSS Tier 1" as solved.

## 6. Evidence
- Alert popup appeared
- Payload was executed in the search result page

## 7. Recommendation
- Sanitize and encode user input on both server and client side
- Implement a strict Content Security Policy (CSP)
- Disable unsafe HTML tags and attributes (like `<iframe>`, `javascript:`)

## 8. CVSS (Estimated): 6.4 (Medium)

