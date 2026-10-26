# 🛒 E-commerce Order Exception Automation with n8n

## 📌 Project Overview
This project is Phase 8 of an E-commerce Order Automation system. It focuses on validating order data, detecting exceptions, placing invalid orders on hold, recording issues in Google Sheets, and sending automated email alerts using n8n.

## 🎯 Project Objectives
- ✅ Validate customer information and email format.
- 🔍 Verify product IDs and product details.
- 📦 Check order quantity and stock availability.
- 💳 Validate payment status and payment amounts.
- ⛔ Place invalid orders on hold.
- 📝 Log detected exceptions in Google Sheets.
- 📧 Send email alerts for manual review.
- 🔁 Check for existing exceptions to reduce duplicate records.

## 🧰 Tools & Technologies
- ⚙️ **n8n Cloud** — Workflow automation and conditional logic
- 📊 **Google Sheets** — Orders, Products, and Exceptions data
- 📩 **Gmail** — Automated exception notifications
- 💻 **JavaScript** — Order validation and error detection

## 🔄 Workflow Architecture
1. ▶️ Manual Trigger starts the workflow.
2. 📥 Get Orders retrieves order records from Google Sheets.
3. 🧠 Validate Orders & Detect Errors checks order data.
4. 🔀 Is Order Valid? separates valid and invalid orders.
5. ⛔ Update Invalid Order Status sets invalid orders to On Hold.
6. 🔎 Check Existing Exception checks existing exception records.
7. 🚦 Is Duplicate? evaluates whether an exception already exists.
8. 📝 Log Order Exceptions records exception details.
9. 📧 Send Order Exception Alert sends email notifications.

## 🧪 Test Cases
| Order ID | Test Scenario | Result |
|---|---|---|
| ORD-3001 | Missing customer information | ❌ Invalid |
| ORD-3002 | Invalid product ID | ❌ Invalid |
| ORD-3003 | Zero quantity | ❌ Invalid |
| ORD-3004 | Insufficient stock | ❌ Invalid |
| ORD-3005 | Payment failure and amount mismatch | ❌ Invalid |
| ORD-3006 | Payment amount mismatch | ❌ Invalid |
| ORD-3007 | Valid control order | ✅ Passed validation |
| ORD-3008 | Negative quantity / inconsistent payment data | ❌ Invalid |

## 📊 Key Results
- ✅ Detected multiple order validation errors.
- ⛔ Updated invalid orders to On Hold.
- 📝 Recorded exception details in Google Sheets.
- 📧 Tested automated email notifications.
- 📦 Verified that product stock remained unchanged during exception-handling tests.
- 🔀 Tested valid and invalid order branches.


## ⚠️ Important Notes
- The current JavaScript validation code uses a predefined product catalogue. Reading product details dynamically from Google Sheets is a future improvement.
- Duplicate prevention should be tested carefully. Re-running the workflow without reliable deduplication can create repeated exception records or emails.
- A valid order passing validation does not mean its fulfillment is complete.
- Screenshots should not expose API keys, passwords, credentials, or private customer data.

## 🚀 Future Improvements
- 🔄 Read product and inventory data dynamically from Google Sheets.
- 🛡️ Strengthen duplicate prevention using Order ID and Error Type.
- 🔔 Add retry handling and error notifications.
- 📈 Add monitoring and exception resolution tracking.
- 🔁 Process only new or unhandled orders.

## 🧠 Skills Demonstrated
n8n Automation · JavaScript · Google Sheets Integration · Gmail Automation · Conditional Logic · Data Validation · Exception Handling

## 🙏 Acknowledgment
This project is part of my AI Automation learning journey. Thanks to **Big Brains** and **Shoaib Hamza** for the learning opportunity and guidance.

---
⭐ Built as a hands-on project to practice reliable e-commerce order validation and exception handling.
