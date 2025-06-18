# Emails not Being Sent Due to SendGrid API Keys Being Revoked

Date: June 17, 2025

Emails were not being sent to customers starting around 3:45PM EST due to SendGrid API keys being automatically revoked. They were revoked because they were mistakenly checked into a public GitHub repository (internal-docs).  SendGrid sent a notification to mycomedytickets@gmail.com (the email on file for SendGrid) which was not checked, therefore there was a delay in noticing the issue.

I realized around 4:00 PM that emails were not being sent, but attributed it to info@mycomedytickets.com being blocked by SendGrid due to a bounce-back (which has happened before). It was only around 9PM EST when I decided to dig a little deeper and noticed that even ticket emails were not being sent, which is when this was diagnosed.

Remediations applied:

- Norm to check for notifications
- Use Logger.error [here](https://github.com/Jump-Comedy/punchline-backend/blob/main/src/services/send-grid.ts) and setup an alert in BetterStack.



