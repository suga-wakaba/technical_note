# Send Mail with Standard Library

```
import smtplib
from email.message import EmailMessage

# Make a Message
msg = EmailMessage()
msg['Subject'] = 'Test Message'
msg['From'] = 'sender@example.com'
msg['To'] = 'recipient@example.com'
msg.set_content('This is a message with Python standard library.')

# Send Mail
server = smtplib.SMTP('smtp.example.com', 587)
server.starttls() # Encryption
server.login('user@example.com', 'password') # Certification
server.send_message(msg) # Send
```

