# In this project we learn how to extract emails and send it automatically to our gmail account.

# Hacker News Frontpage Scrapping:

Hacker News URL = ('https://news.ycombinator.com/')

# Website Structure:
```python
#extracting hacker news stories

def extract_news(url):
    print('Extracting Hacker News Stories...')
    cnt = ''
    cnt +=('<b>HN Top Stories:</b>\n'+'<br>'+'-'*50+'<br>')
    response = requests.get(url)
    content = response.content
    soup = BeautifulSoup(content, 'html.parser')
    for i, tag in enumerate(soup.find_all('td', attrs={'class':'title', 'valign':''})):
        cnt += ((str(i+1)+' :: '+tag.text + "\n" + '<br>') if tag.text!='More' else '')
        #print(tag.prettify) #find_all('span', 'attrs={'class':'sitestr'}))
    return(cnt)
```

# Email Authentication:
```python
cnt = extract_news('https://news.ycombinator.com/')
content += cnt
content += ('<br>---------<br>')
content += ('<br><br>End Of Message')
```

# Email Composing (Let's Send Email)
```python
print('Composing Email...')

# update your email details

SERVER = 'smtp.gmail.com' # your smtp sever
PORT = 587 # your port number
FROM = 'abc@gmail.com' # 'your from email ID'
TO = 'abc@gmail.com' # 'your to email id #can be a list
PASS = '********' # 'your email id password'

# fp = open(file_name, 'rb')
# create a text/plain message
# msg = MIMEText('')
msg = MIMEMultipart()

# msg.add_header'Content_Disposition', 'attachement', filename='empty.text')
msg['Subject'] = 'Top News Stories HN [Automated Email]' + ' ' + str(now.day) + '-' + str(now.month) + '-' + str(now.year)
msg['From'] = FROM
msg['To'] = TO

msg.attach(MIMEText(content, 'html'))
# fp.close()

print('Initiating Server...')

server = smtplib.SMTP(SERVER, PORT)
#server = smtplib.SMTP SSL ('smtp.gmail.com', 465)
server.set_debuglevel(1)
server.ehlo()
server.starttls()
#server.ehlo
server.login(FROM, PASS)
server.sendmail(FROM, TO, msg.as_string())

print('Email Sent...')

server.quit()
```
