# EX01 Developing a Simple Webserver
## Date:11/11/26

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
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html>
<head>
    <title>TCP/IP Protocol Suite</title>
    <style>
        body {
            font-family: Arial;
            background: #eef2f7;
            margin: 30px;
        }
        h1 {
            text-align: center;
            color: #1e3a8a;
        }
        table {
            width: 80%;
            margin: auto;
            border-collapse: collapse;
            background: white;
        }
        th, td {
            border: 1px solid #333;
            padding: 12px;
            text-align: center;
        }
        th {
            background: #2563eb;
            color: white;
        }
    </style>
</head>

<body>
    <h1>TCP/IP Protocol Suite</h1>

    <table>
        <tr>
            <th>Layer</th>
            <th>Protocols</th>
            <th>Purpose</th>
        </tr>

        <tr>
            <td>Application</td>
            <td>HTTP, HTTPS, FTP, SMTP, DNS, DHCP, SSH</td>
            <td>Provides network services to applications</td>
        </tr>

        <tr>
            <td>Transport</td>
            <td>TCP, UDP</td>
            <td>Provides end-to-end communication</td>
        </tr>

        <tr>
            <td>Internet</td>
            <td>IP, ICMP, ARP, IGMP</td>
            <td>Addressing and packet routing</td>
        </tr>

        <tr>
            <td>Network Access</td>
            <td>Ethernet, Wi-Fi, PPP</td>
            <td>Transfers data through physical networks</td>
        </tr>
    </table>
</body>
</html>
"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',880)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()



## OUTPUT:


## RESULT:
The program for implementing simple webserver is executed successfully.

