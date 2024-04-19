---
title: "Validating different types of data like Gmail, Outlook email addresses, phone numbers, and URLs"
seoTitle: "Validate Emails, Phone Numbers & URLs - Powerful Data Validation Tool"
seoDescription: "Ensure data accuracy with our powerful validation tool. Quickly verify email addresses (Gmail, Outlook, etc.), phone numbers, and URLs to prevent invalid en"
datePublished: Fri Apr 19 2024 17:05:14 GMT+0000 (Coordinated Universal Time)
cuid: clv6x8e6l00090ajt23qfau54
slug: validating-different-types-of-data-like-gmail-outlook
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1713545985867/19c40e2e-c095-4509-9ecd-3d9b845a7dcd.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1713546023591/43353741-ca67-4363-aae6-6dfde4dd5366.png
tags: data, data-science, databases, data-analysis, data-structures

---

Validating different types of data like Gmail, Outlook email addresses, phone numbers, and URLs in SQL can be a bit challenging since SQL is primarily used for data manipulation in databases and not for complex data validation. However, depending on the database system you are using, there might be some limited string manipulation functions available that can help you perform basic validation checks.

Keep in mind that SQL might not be the ideal choice for these types of validations, and you may need to consider using a programming language or tool that offers better support for data validation. However, I'll provide you with some basic examples of how you could attempt these validations in SQL. Please note that these examples may not cover all possible cases and may vary depending on the database system you are using.

```sql
SELECT email_address
FROM your_table
WHERE email_address LIKE '%@gmail.com';
SELECT email_address
FROM your_table
WHERE email_address LIKE '%@outlook.com' OR email_address LIKE '%@hotmail.com' OR email_address LIKE '%@live.com';
SELECT phone_number
FROM your_table
WHERE phone_number LIKE '[0-9]%';  -- Assuming the phone number starts with a digit
SELECT url
FROM your_table
WHERE url LIKE 'http://%' OR url LIKE 'https://%';
```