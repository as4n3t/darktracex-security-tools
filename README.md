# ASC Markhor-security-tools
Cybersecurity tools by DarktraceX
basic_port_scanner.py
import socket

target = input("Enter target IP: ")
print(f"Scanning {target}...")

for port in range(1, 1025):
    sock = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
    socket.setdefaulttimeout(0.5)
    
    result = sock.connect_ex((target, port))
    
    if result == 0:
        print(f"Port {port} is OPEN")
    
    sock.close()
