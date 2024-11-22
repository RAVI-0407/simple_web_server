# EX01 Developing a Simple Webserver

# Date:
# AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

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
from django.shortcuts import render
content='''
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>Lenovo ThinkPad Gen 16 </title>
    <link rel="stylesheet" href="styles.css">
    <style>
        
       body {
           font-family: 'Arial', sans-serif;
           background-color:#333;
       }
       .container {
           width: 80%;
           margin: 0 auto;
       }
       header {
           background-color:cornflowerblue;
           color: white;
           padding: 20px 0;
           text-align: center;
       }
       header h1 {
           font: size 3em;;
       }
       .specs {
           background-color: white;
           margin-top: 60px;
           border-radius: 7px;
       }
       table {
           width: 100%;
           border-collapse: collapse;
       }
       th {
           padding: 12px;
           text-align:left;
           border-bottom: 1px solid #ddd;
           background-color:cornflowerblue;
           color: white;
       }
       td {
           background-color: #f9f9f9;
           padding: 12px;
           text-align:center;
           border-bottom: 1px solid #ddd;
       }
       tr {
           background-color: #f1f1f1;
       }
       footer {
           background-color:cornflowerblue; 
           color: white;
           text-align: center;
           margin-top: 100px;
           padding: 1px;
       }
       </style>
</head>
<body>
    <div class="container">
        <header>
            <h1>Lenovo ThinkPad Gen 16</h1>
        </header>
        
        <section class="specs">
            <table>
                <tr>
                    <th>Processor</th>
                    <td>Intel Core i5</td>
                </tr>
                <tr>
                    <th>Display</th>
                    <td>16-inch WQXGA</td>
                </tr>
                <tr>
                    <th>Memory</th>
                    <td>16GB DDR4 RAM</td>
                </tr>
                <tr>
                    <th>Storage</th>
                    <td>512GB SSD </td>
                </tr>
                <tr>
                    <th>Graphics</th>
                    <td>Intel Iris Xe Graphics</td>
                </tr>
                <tr>
                    <th>Operating System</th>
                    <td>Windows 11 </td>
                </tr>
                <tr>
                    <th>Battery</th>
                    <td>57Wh, up to 10 hours</td>
                </tr>
                <tr>
                    <th>Weight</th>
                    <td>1.67 kg </td>
                </tr>
                <tr>
                    <th>Ports</th>
                    <td>2 x USB 3.2, 2 x USB-C, HDMI, Ethernet</td>
                </tr>
                <tr>
                    <th>Camera</th>
                    <td>1080p HD webcam</td>
                </tr>
                 <tr>
                    <th>Color</th>
                    <td>Black</td>
                </tr>
            </table>
        </section>
        <footer>
            <p>&copy; 2024 Lenovo. All rights reserved.</p>
        </footer>
    </div>
  
</body>
</html>
'''
from http.server import HTTPServer,BaseHTTPRequestHandler
class Myserver(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200)
        self.send_header("content-type","text/html")
        self.end_headers()
        self.wfile.write(content.encode())

print("This is my webserver")
server_address = ('',8000)
httpd = HTTPServer(server_address,Myserver)
httpd.serve_forever()
```

# OUTPUT:


![Screenshot 2024-11-22 225102](https://github.com/user-attachments/assets/5d4a8987-042b-43b7-9283-35900690c372)


# RESULT:
The program for implementing simple webserver is executed successfully.
