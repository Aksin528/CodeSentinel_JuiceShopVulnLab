
# Vulnerability Report: SQL Injection

## 1. Title
SQL Injection in Login Functionality

## 2. Summary
The application’s login mechanism is vulnerable to SQL Injection, allowing an attacker to bypass authentication and gain unauthorized access, including to administrator accounts.

## 3. Vulnerability Type
SQL Injection (Authentication Bypass)

## 4. Impact
- Unauthorized access to user/admin accounts
- Potential for full database compromise
- Loss of confidentiality and integrity

## 5. Reproduction Steps
1. Navigate to the login page: `http://localhost:3000/#/login`
2. Enter the following credentials:

   **Email/Username:** `admin' OR 1=1--`  
   **Password:** `anypassword`

3. Click “Log In”

4. Result: The application logs in as the administrator without verifying the actual password.

## 6. Evidence
- Gained access to the admin interface.
- Score Board marked "Login Admin" as solved.

## 7. Recommendation
- Use parameterized queries (prepared statements) to handle input data.
- Implement proper input validation and escaping.
- Avoid direct string concatenation in SQL statements.

## 8. CVSS (Estimated): 9.1 (Critical)
