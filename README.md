# PHP Email Gateway

**Universal PHP Email API using Resend**

This lightweight PHP system allows sending HTML emails from any PHP form or script using the [Resend API](https://resend.com).  
It works like a proper API, returns JSON responses, and can be reused in any project for sending emails. Optional database integration is supported for storing submissions before sending emails.

---

## 🚀 Installation

1. Clone or download this repository:

```bash
git clone https://github.com/yourusername/php-email-gateway.git
````

2. Copy `send.php` and your form file (e.g., `test.php`) into your PHP project folder.

3. Open `send.php` and edit configuration at the top:

```php
$RESEND_API_KEY = "re_xxxxxxxxxxxxxxxxx";  // Replace with your Resend API key
$DEFAULT_FROM   = "Your App <onboarding@resend.dev>"; // Default sender
```

4. Make sure your PHP environment has **cURL enabled**.

---

## 📄 Usage

### 1️⃣ Form Submission

* Point your form's `action` to `send.php`.
* Include `to`, `subject`, and `html` fields in POST request.
* `send.php` will process the request and return a JSON response.

### 2️⃣ PHP Script

* Include `send.php` using `require "send.php"`.
* Call the function:

```php
resend_send_mail($to, $subject, $html, $from);
```

* `$to`: Recipient email or array
* `$subject`: Email subject
* `$html`: HTML content of email
* `$from`: Optional sender email (defaults to `$DEFAULT_FROM`)

The function returns a JSON-like array indicating success or failure.

---

✅ This setup allows you to reuse a single email sending API (`send.php`) across all your PHP projects with minimal configuration.
