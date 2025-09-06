# EX01 Developing a Simple Webserver
## Date: 1.9.2025

## AIM:
To develop a simple webserver to serve html pages and display the list of protocols in TCP/IP Protocol Suite.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Import the necessary modules.

### Step 5:
Define a custom request handler.

### Step 6:
Start an HTTP server on a specific port.

### Step 7:
Run the Python script to serve web pages.

### Step 8:
Serve the HTML pages.

### Step 9:
Start the server script and check for errors.

### Step 10:
Open a browser and navigate to http://127.0.0.1:8000 (or the assigned port).

## PROGRAM:
``` 
from http.server import HTTPServer,BaseHTTPRequestHandler


content= '''

<html>
    <head><title>my first page</title></head>
    <body>
        <table align="center" border="10" cellpadding="15" bgcolor="white">
            <caption>LIST OF PROTOCOLS IN TCP/IP PROTOCOL SUITE</caption>
            <tr><th>S.No</th><th>Name of the layer</th><TH>Name of the Prototype</TH></tr>
            <tr><td>1</td><td>Application Layer</td><th>HTTP,FTP,DNS,TELNET,SSH</th></tr>
            <tr><td>2</td><td>Transport Layer</td><td>TCP/UDP</td></tr>
            <tr><td>3</td><td>Networrk Layer</td><td>IPV4,IPV6</td></tr>
            <tr><td>4</td><td>Link Layer</td><td>Ethernet</td></tr>
    </body>
</html>

'''

class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200) 
        self.send_header("content-type", "text/html")       
        self.end_headers()
        self.wfile.write(content.encode())

print("This is my webserver, http://localhost:8000/") 
server_address =('',8000)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()

```


## OUTPUT:

![WhatsApp Image 2025-09-06 at 08 32 02_3e1f0dd2](https://github.com/user-attachments/assets/7a7d7805-b814-422b-b4d7-d78e1a0be889)


![Uploading WhatsApp Image 2025-09-06 at 08.31.38_e4989600.jpg…]()



## RESULT:
The program for implementing simple webserver is executed successfully.
