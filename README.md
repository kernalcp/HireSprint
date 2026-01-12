# HireSprint 🚀

HireSprint is a lightweight Ruby on Rails application that helps job seekers send their resume to multiple HR email addresses efficiently using their **personal Gmail account**. It is built for speed, reliability, and simplicity — no paid email services required.

---

## ✨ Features

* 📧 Send the same email to **multiple HR emails** at once
* 📝 Rich-text email editor using **TinyMCE**
* 📎 Resume upload & automatic attachment
* 👀 **Email preview** before sending
* ⚙️ Background email delivery using **Sidekiq**
* 🔁 Automatic retry for **failed emails only** (no duplicates)
* 🧾 Email delivery logs (sent / failed / retried)
* 🧹 Auto-cleanup temporary resume files
* 🔐 Uses your **personal Gmail (App Password)**
* 💯 Completely **free & open-source**

---

## 🛠 Tech Stack

* Ruby on Rails 8
* Sidekiq + Redis
* Action Mailer (SMTP)
* TinyMCE
* SQLite (default)
* Gmail SMTP

---

## 📸 Use Case

Perfect for job seekers who want to:

* Reach multiple recruiters quickly
* Avoid copy-pasting emails
* Track email delivery status
* Stay within Gmail’s daily sending limits (e.g. 20/day)

---

## 🔐 Gmail Setup (Important)

HireSprint uses **Gmail App Passwords** (not your main Gmail password).

Steps:

1. Enable **2-Step Verification** in your Google account
2. Go to **Google Account → Security → App Passwords**
3. Generate an App Password for "Mail"
4. Use that password in the app configuration

---

## ⚙️ Configuration & Security

After the first login, each user can securely configure their own settings directly from the application.

### User Settings Include:

* 📧 **Gmail address** (used for sending emails)
* 🔐 **Gmail App Password** (never stored in plain text)
* 📝 **TinyMCE API key** (for rich email editing)

All credentials are stored securely at the user level and are never hard-coded or shared. This makes HireSprint fully **multi-user**, **safe**, and **personalized** without relying on environment variables.

---

## 📬 Email Flow

1. Fill the form with:

   * Multiple HR emails
   * Subject
   * Email body (rich text)
   * Resume upload
2. Preview the email
3. Submit → emails are queued via Sidekiq
4. Failed emails are retried automatically
5. All activity is logged

---

## ▶️ Running Locally

```bash
git clone https://github.com/your-username/HireSprint.git
cd HireSprint
bundle install
rails db:setup
redis-server
bundle exec sidekiq
rails server
```

Visit: [http://localhost:3000](http://localhost:3000)

---

## 🚨 Gmail Limits

* Recommended: **≤ 20 emails/day**
* Avoid spam-like content
* Use proper subject & formatting

---

## 📌 Future Enhancements

* ~~User authentication (Devise)~~ ✅ Done
* ~~Multiple resume templates~~ ✅ Done
* ~~Per-user email settings~~ ✅ Done
* 📊 Analytics dashboard (email delivery & engagement insights)
* 📂 Import HR emails from **CSV / XLS files** (bulk upload)
* 🏷️ Tag & organize HR contacts (company, role, location)
* ⏱️ Scheduled email sending (send later)
* 📈 Daily send limits & smart throttling
* 📨 Email templates per job role

---

## 🤝 Contributing

Pull requests are welcome. For major changes, please open an issue first.

---

## 📄 License

MIT License

---

## 🙌 Author

**Chander Prakash**
Rails Backend Developer

> Built to make job hunting faster, simpler, and stress-free.
