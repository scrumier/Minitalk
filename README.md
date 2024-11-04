# Minitalk - Inter-Process Communication Project 💬

Welcome to **Minitalk**! This project explores inter-process communication (IPC) by implementing a messaging system between two programs using Unix signals. It’s an excellent introduction to IPC and working with low-level signal handling in C.

## 📖 Project Overview
The Minitalk project involves creating a **client-server** communication system in C. The server receives messages sent by the client, where each message is transmitted one character at a time using Unix signals:

- **SIGUSR1** and **SIGUSR2**: These signals are used to encode and send each bit of the message from the client to the server.

The challenge is to ensure reliable, sequential communication between the processes and manage the signals accurately for successful message delivery.

## 🔧 How It Works
1. **Encoding Messages**: The client encodes each character in the message as a series of binary bits. Each bit is then sent to the server through either SIGUSR1 or SIGUSR2, representing `0` and `1`, respectively.
2. **Decoding on the Server**: The server listens for signals from the client, reconstructing each character bit by bit. When a full character has been received, it is printed to the standard output.
3. **Error Handling and Signal Reliability**: Proper handling of signals and ensuring reliable delivery is key in this project. The server must manage incoming signals efficiently, and the client must handle cases where messages may need to be resent.

## 📝 Compilation & Usage
To compile the project, use:
```bash
make
```

This will create two executables:
- `server`: Starts the server to receive messages.
- `client`: Sends messages to the server.

### Usage
1. First, start the server to get its process ID (PID):
   ```bash
   ./server
   ```

   The server will output its PID, which the client will need to send messages.

2. Next, use the client to send a message to the server using its PID:
   ```bash
   ./client [server PID] "Your message here"
   ```

   The server will display the received message in real-time.

## 🌱 Learning Outcomes
Working on Minitalk has given me a deeper understanding of Unix signals, bitwise operations, and inter-process communication. Handling low-level communication between processes and ensuring accurate message transmission was both challenging and rewarding.

## 🔗 Connect with Me
If you’re interested in this project or would like to collaborate, feel free to reach out on [LinkedIn](https://www.linkedin.com/in/sonam-crumiere/).

Happy messaging!
