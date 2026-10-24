# EX01 Developing a Simple Webserver
## Date:15/10/2026
## REG NO:26012348

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
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Network Protocols List</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 20px;
            background-color: #f4f7f6;
        }
        h2 {
            color: #333;
            text-align: center;
        }
        .table-container {
            overflow-x: auto;
            margin-top: 20px;
        }
        table {
            width: 100%;
            border-collapse: collapse;
            background-color: #fff;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            border-radius: 8px;
            overflow: hidden;
        }
        th, td {
            padding: 12px 15px;
            text-align: left;
        }
        th {
            background-color: #007bff;
            color: white;
            text-transform: uppercase;
            font-size: 14px;
            letter-spacing: 0.5px;
        }
        tr {
            border-bottom: 1px solid #dddddd;
        }
        tr:nth-of-type(even) {
            background-color: #f9f9f9;
        }
        tr:last-of-type {
            border-bottom: 2px solid #007bff;
        }
        tr:hover {
            background-color: #f1f1f1;
        }
        @media (max-width: 600px) {
            th, td {
                padding: 8px 10px;
                font-size: 14px;
            }
        }
    </style>
</head>
<body>

    <h2>Common Network Protocols</h2>

    <div class="table-container">
        <table>
            <thead>
                <tr>
                    <th>Protocol</th>
                    <th>Full Name</th>
                    <th>Default Port</th>
                    <th>Primary Function</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td><strong>HTTP</strong></td>
                    <td>Hypertext Transfer Protocol</td>
                    <td>80</td>
                    <td>Transmitting web pages over the internet unsecured.</td>
                </tr>
                <tr>
                    <td><strong>HTTPS</strong></td>
                    <td>Hypertext Transfer Protocol Secure</td>
                    <td>443</td>
                    <td>Securely transmitting encrypted web pages.</td>
                </tr>
                <tr>
                    <td><strong>FTP</strong></td>
                    <td>File Transfer Protocol</td>
                    <td>20, 21</td>
                    <td>Transferring files between a client and a server.</td>
                </tr>
                <tr>
                    <td><strong>SSH</strong></td>
                    <td>Secure Shell</td>
                    <td>22</td>
                    <td>Securely accessing and managing remote servers.</td>
                </tr>
                <tr>
                    <td><strong>DNS</strong></td>
                    <td>Domain Name System</td>
                    <td>53</td>
                    <td>Translating human-readable domain names to IP addresses.</td>
                </tr>
                <tr>
                    <td><strong>SMTP</strong></td>
                    <td>Simple Mail Transfer Protocol</td>
                    <td>25, 465, 587</td>
                    <td>Sending email messages between servers.</td>
                </tr>
            </tbody>
        </table>
    </div>

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
```
## OUTPUT:
![alt text](<Screenshot (47).png>)

## RESULT:
The program for implementing simple webserver is executed successfully.

