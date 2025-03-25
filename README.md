# EX01 Developing a Simple Webserver

# Date:21.03.2025
# AIM:
To develop a simple webserver to serve html pages and display the tabular column of multiple Companies and its Revenue

# DESIGN STEPS:
## Step 1:
HTML content creation.

## Step 2:
Design of webserver workflow.

## Step 3:
Implementation using Python code.

## Step 4:
Serving the HTML pages.

## Step 5:
Testing the webserver.

# PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<html>
<head>
<title>Top Software Industries</title>
</head>
<body>
<table border="2" cellspacing="10" cellpadding="6">
<caption>Top 5 Revenue Generating Software Companies</caption>
<tr>
<th>S.No</th>
<th>Companies</th>
<th>Revenue</th>
</tr>
<tr>
<th>1</th>
<th>Microsoft</th>
<th>65 billion</th>
</tr>
<tr>
<th>2</th>
<th>Oracle</th>
<th>29.6 billion</th>
</tr>
<tr>
<th>3</th>
<th>IBM</th>
<th>29.1 billion</th>
</tr>
<tr>
<th>4</th>
<th>SAP</th>
<th>6.4 billion</th>
</tr>
<tr>
<th>5</th>
<th>Symantec</th>
<th>5.6 billi
"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',80)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```
# OUTPUT:
![image](https://github.com/user-attachments/assets/6b26fa55-8514-4eb1-8fb9-0ef9db102efa)

![image](https://github.com/user-attachments/assets/69b488d0-d5c9-4b05-b5dd-2b9eec9d9798)

# RESULT:
The program for implementing simple webserver is executed successfully.
