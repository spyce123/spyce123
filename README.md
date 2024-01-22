# Python 3.x
import http.server
import socketserver
import os
# Set the port you want to use (e.g., 8000)
port = 8000

# Change to the directory where your HTML file is located
directory = "."  # You can change this to the path where your HTML file is located

# Create a simple HTTP server
handler = http.server.SimpleHTTPRequestHandler

# Change to the specified directory
os.chdir(directory)

# Start the server
with socketserver.TCPServer(("", port), handler) as httpd:
    print(f"Serving at port {port}")
    httpd.serve_forever()
