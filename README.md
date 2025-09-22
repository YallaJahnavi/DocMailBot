# DocMailBot

# Purpose of DocMailBot
1. DocMailBot is a python-based automation tool.
2. It automatically sends respective documents from a folder to their respective mail Id's.
3. Instead of manually attaching files & sending mails one by one, you can do this in one click.
4. Designed for efficiently, especially in academic, business or organizational contexts where
   multiple personalized documents like (certificates, invoices, reports and admit cards etc) need to be sent.


# Technology Stack
1. Programming language : Python
2. IDE : Visual Studio Code (for coding, debugging & running the python script).
3. Libraries used :
        "smtplib" for sending emails through Gmail SMTP server.
        "OS" for accessing PDF files from the folder.
        "email.mime" modules for constructing email.

# Why name "DocMailBot"
1. Doc represents documents.
2. Mail represents email delivery.
3. Bot highlights automation, reducing manual work.

# Working of DocMailBot
1. Email Authentication: Uses GmailId and App Password for secure login. "server.login(SENDER_MAIL, APP_PASSWORD) connects python to Gmail's SMTP server.
2. Recipient Mapping: Recipients are stored in list of email Id's. The PDF filename is assumed to be part before "@" in the email.
3. Fetching pdf files: from the given folder path (pdf_folder) checks if the respective PDF exists for each recipient. If not found it shows an error message.
4. Email Construction:
       MIMEMutlipart() is used to create a full email(sender, receiver, subject, body, attachments).
       MIMEText() adds the text message body.
       MIMEBase() attaches the PDF file in binary format then encodes it with base64.
5. Email Sending: For each recipient, the email is sent with their own PDF attached. Success or Failure is printed on the console for tracking.
6. LogOut: server.quit() closes the SMTP connection after sending all emails.

# Code Flow in short
1. Login to Gmail -> server.login()
2. Loop through recipients -> for email in recipients:
3. Match PDF name with email prefix -> email.split("@")[0]+ ".pdf"
4. Create email body -> MIMEMultipart()+MIMEText()
5. AttachPDF -> MIMEBase() + encoders.encode_base64()
6. Send -> Server.send_message(msg)
7. Show Status -> wrong or right symbols with the message on the console.

# Advantages of DocMailBot
1. Time-saving: No need to manually attach and send files.
2. Error-free: Ensures the right document goes to the right recipient.
3. Reusable: Can be used in schools, companies, HR, Billing etc
4. Customizable: Body text, subject and attachment logic can be easily modified.
   
# Limitations of DocMailBot
1. Requires proper app password (normal Gmail Password won't work)
2. PDF file naming convention must be followed (emailprefix.pdf)
3. Needs internet connection
4. Limited by Gmail sending quota (usually 500 mails/day for personal accounts)

# Real-life use cases
1. Sending admit cards to students.
2. Mailing salary slips to employees.
3. Delivering certificate for workshops or online courses.
4. Distributing invoices or bills to clients.

# Steps for Creating App Password
1. Open your Gmail Account.
2. Click on "manage your google account" option.
3. Go to "security".
4. Search for "App Passwords".
5. If your gmail account is on 2 step verification it asks for password of your Gmail account.
6. You will be asked to give a "App Name" and it named it as "Email Automation" & after clicking on create.
7. You will be displayed a 16 digits app password for gmail. Don't forget to copy & then click on done.
8. Now your app password is with you, kindly paste it anywhere for further use.

# Steps for creating a folder to store all the documents
1. Create a folder with any name of your wish on the desktop.
2. Now place all the documents of all the recipients in this folder.

Note: Make sure that the prefix of the email should be the same for the name of the pdf.
For Example: If the email of the recipient is "jahnavisudhababu@gmail.com", the PDF name should be "jahnavisudhababu.pdf".
Now copy the location of the created folder and keep it safe for further use.

# Steps to do in visual studio code
1. Create another folder and name as your wish. (For eg: "EmailAutomation")
2. Open the same folder in the visual studio code and create a file in the same folder and nme it as your wish. (For eg: "send_pdfs.py")
3. Paste the code in the "send_pdfs.py" file.
4. Go to view and open terminal, then follow the commands
=> py --version
=> cd "place the path of the new created folder for code"
=> dir
=> python send_pdfs.py (this command is used to run the python script code)










