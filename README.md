# email-opener
# A project that allows one to automatically open emails using the python language 

# use the code below
import imaplib
import base64
email_user = input ("Email:")
email_pass = input ("Password:")

M = imaplib.IMAP4_SSL("imap-mail.gmail.com", 993)
M.login(email_user, email_pass)
M.select ()
typ,message_numbers = M.search(None, "ALL")
for num in message_numbers[0].split():
typ, data = M.fetch(num, "(RFC822)")
print (data)

# The above code allows access into your mail
# From here you can write other codes to do other cool stuffs
# But as a newbie, this is all i know
