# asc markhor-security-tools
Cybersecurity tools by asc markhor
import socket

target = input("Target IP or Hostname: ")

print(f"\nScanning {target}...\n")

for port in range(1, 1025):
    try:
        sock = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
        sock.settimeout(0.5)

        result = sock.connect_ex((target, port))

        if result == 0:
            try:
                service = socket.getservbyport(port)
            except:
                service = "Unknown"

            print(f"[OPEN] Port {port} ({service})")

        sock.close()

    except KeyboardInterrupt:
        print("\nScan stopped.")
        break

    except:
        pass
