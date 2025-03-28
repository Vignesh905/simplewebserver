# EX01 Developing a Simple Webserver
## Date:28/03/2025

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
Run the P/thon script to serve web pages.

### Step 8:
Serve the HTML pages.

### Step 9:
Start the server script and check for errors.

### Step 10:
Open a browser and navigate to http://127.0.0.1:8000 (or the assigned port).

## PROGRAM:
````from http.server import HTTPServer, BaseHTTPRequestHandler
    content = """
    <html>
    <title> Simplewebserver </title>
    <body>
    <table border="3" cellspacing="12">
    <caption> Top Five Revenue Generating Software Companies </caption>

    <tr>
    <th>S.No</th>
    <th>Company</th>
    <th>Revenue</th>
    </tr>
    <tr>
    <td>1</td>
    <td>Microsoft</td>
    <td>65 Billion</td>
    </tr>
    <tr>
    <td>2</td>
    <td>Oracle</td>
    <td>29.6 Billion</td>
    </tr>
    <tr>
    <td>3</td>
    <td>IBM</td>
    <td>29.1 Billion</td>
    </tr>
    <tr>
    <td>4</td>
    <td>SAP</td>
    <td>6.4 Billion</td>
    </tr>
    <tr>
    <td>5</td>
    <td>Symantec</td>
    <td>5.6 Billion</td>
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
    server_address = ('',8000)
    httpd = HTTPServer(server_address,myhandler)
    print("my webserver is running...")
    httpd.serve_forever()


## OUTPUT:
!simplewebserver/Screenshot 2025-03-28 212440.png
!simplewebserver/Screenshot 2025-03-28 212714.png
    


## RESULT:
The program for implementing simple webserver is executed successfully.
