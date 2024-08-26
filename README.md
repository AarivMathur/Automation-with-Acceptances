# Student Enrollment Email Automation - README

## Project Overview

This Google Apps Script automates the process of sending a welcome email along with a Google Classroom code to students after they sign up via a Google Form. The form responses are captured in a Google Sheet, and the script extracts the student’s email from the sheet, then sends a personalized email containing the classroom code and a welcome message.

## Workflow Overview

1. **Form Submission:**
   - Students sign up using a Google Form. Their responses, including email addresses, are stored in a Google Sheet.

2. **Google Classroom Code:**
   - The script automatically sends each student an email that includes:
     - A welcome message
     - A Google Classroom code for the course
     - The email is sent only if the email address is valid.

## Script Description

### Function: `sendEmails()`

This function automates the email-sending process. It operates as follows:

1. **Access the Google Sheet:**
   - The script accesses the active Google Sheet where the form responses are stored: `var sheet = SpreadsheetApp.getActiveSpreadsheet().getActiveSheet();`.

2. **Loop Through Each Row:**
   - The script iterates through each row (starting from the second row, since the first is the header), extracts the student’s email address, and prepares a personalized message.

3. **Email Content:**
   - The script constructs an email message that includes:
     - A predefined Google Classroom code (you will need to replace `"YOUR_CLASSROOM_CODE"` with the actual code).
     - A customizable introduction message.
     - The student’s email is inserted into the email's `to` field.

4. **Send Email:**
   - If the email address is valid (i.e., contains `@`), the email is sent using the `MailApp.sendEmail()` method. If the email fails to send, an error is logged.

### Example Email Content:
```text
Subject: Welcome to the Course!

Dear student,

Welcome to the course!

Your Google Classroom code is: YOUR_CLASSROOM_CODE

Welcome to the course!

Best regards,
Your Instructor
