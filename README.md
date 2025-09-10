# 🔍 Simple TCP Port Scanner in C

A lightweight **TCP connect-based port scanner** written in C.  
This tool attempts to establish a TCP connection to a target IP address and reports which ports are open.  

---

## ✨ Features
- Scans a given range of TCP ports on a target host  
- Reports **open ports** (uses standard `connect()` method)  
- Simple, single-threaded design (great for learning socket programming)  
- Works on Linux/Unix systems  

---

## ⚙️ Usage
Compile with `gcc`:
```bash
gcc portscanner.c -o portscanner
```
Run the scanner:
./portscanner <IP> <start_port> <end_port>

Example:
./portscanner 127.0.0.1 1 1024

Output:
Scanning 127.0.0.1 from port 1 to 1024...

Port 22 is OPEN

Scan complete.

📚 How It Works

Takes target IP and port range as arguments.

Creates a TCP socket for each port in the range.

Calls connect() to check if the port accepts connections.

If success → port is OPEN

If error/timeout → port is closed/filtered

Prints results to the console.

🚀 Future Improvements
- Add timeout for filtered ports
- Multi-threading for faster scans
- Banner grabbing (identify services on open ports)
- Support for UDP scanning
