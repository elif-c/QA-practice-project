# Test Scope

Feature tested: User Login  
Test Type: Manual Functional Testing  
Environment: Web Browser

## User Story

As a registered customer,
I want to log into the website using my email and password,
So that I can access my account.

## Acceptance Criteria

1. Customer can access the login form on the homepage.
1. Customer can enter their registered email address and password.
1. Customer can successfully login with valid credentials.
1. Customer cannot login with invalid credentials and an error message is displayed.
1. Customer cannot submit empty fields and if they try, an error message is displayed. 

## Test Scenarios

### LS01: Successful login with valid credentials 

| Test Case ID  | Test Case  | Steps  | Expected Result  | Actual Result  |  Status  |
|---|---|---|---|---|---|
|TC1|Login with registered email and password|1.Enter registered email and password|Login is successful|   |    |
|TC2|Login with correct registered email but wrong case|Enter registered email with wrong case|Login is successful|   |    |
|TC3|Login with valid credentials with spaces before and after|Enter valid credentials with spaces before and after|Login is successful|   |    |
|TC4|Login with valid password containing special characters|Enter correct password with special characters|Login is successful|   |    |

### LS02: Login attempt with invalid credentials

| Test Case ID  | Test Case  | Steps  | Expected Result  | Actual Result  |  Status  |
|---|---|---|---|---|---|
|TC5|Login with unregistered email and password|Enter unregistered email and password|Account not found error message displayed|   |   |
|TC6|Login with correct email and incorrect password|Enter registered email and incorrect password|Incorrect email or password error message displayed|   |    |
|TC7|Login with incorrect email and password|Enter incorrect email and password|Incorrect email or password error message displayed|   |    |

### LS03: Login attempt with invalid form input
| Test Case ID  | Test Case  | Steps  | Expected Result  | Actual Result  |  Status  |
|---|---|---|---|---|---|
|TC8|Submit form with empty fields|Leave email and password empty|Fill in required fields error message displayed|   |   |
|TC9|Submit form with empty password|Enter email only|Fill in required fields error message displayed|   |    |
|TC10|Submit form with invalid email format|Enter email with @@ and correct password|Enter valid email error message displayed|   |    |
|TC11|Submit form with long input|Enter 200 characters|Enter valid email error message displayed|   |    |

### LS04: Login security behavior
| Test Case ID  | Test Case  | Steps  | Expected Result  | Actual Result  |  Status  |
|---|---|---|---|---|---|
|TC12|Multiple failed login attempts|Enter wrong password 5 times|Account temporarily locked OR captcha triggered|   |   |
|TC13|SQL injection attempt|Enter `' OR 1=1 --` in email field|Account temporarily locked OR captcha triggered|   |   |

### Edge Cases Considered
- Extremely long email input
- Leading/trailing spaces in credentials
- Special characters in password field
- Browser refresh during login request
