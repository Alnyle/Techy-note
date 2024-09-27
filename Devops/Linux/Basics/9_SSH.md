
SSH - Secure Shell

- SSH is network protocol that gives users a secure way to access a computer over the internet
- SSH refers also to the suite of utilities that implement that protocol
- Encrypted data communication
- To access remote server you need authenticate before access that remote 

#### There 2 ways to authenticate
##### 1.Username & Password

This is the most traditional and straightforward method of authentication.

- **How it Works:**
    
    - The user enters a username and a corresponding password.
    - The system checks the entered credentials against a stored database of usernames and hashed passwords.
    - If the credentials match, the user is granted access; otherwise, access is denied

##### 2.SSH Key Pair
 
This method uses a pair of cryptographic keys: a **private key** and a **public key**.
**How it Works:**

- **Key Generation:** The user generates a key pair using a tool like `ssh-keygen`. The private key is kept secret, while the public key is shared with the server or service.
- **Public Key Installation:** The public key is added to a special file (e.g., `~/.ssh/authorized_keys`) on the server.
- **Authentication Process:** When the user tries to log in, the server sends a challenge to the user's client. The client uses the private key to sign the challenge, proving possession of the private key without ever transmitting it.
- If the signature matches the one expected for the public key, the server grants access.

### SSH command

Display version of your ssh

```
ssh -V
```


Display the location of the binary file ssh commands

```
which ssh
```


he `openssh-server` is a software package that provides an implementation of the Secure Shell (SSH) protocol. It is part of the OpenSSH suite, which includes various tools for secure communication over unsecured networks. The `openssh-server` specifically allows a computer to accept incoming SSH connections, enabling secure remote access to the machine.

to check if your `openssh-server` is running 

```
sudo systemctl status sshd 
```

### Key Features and Functions:

- **Secure Remote Login:** Allows users to securely log into a remote machine over an encrypted connection. This is commonly used by system administrators to manage servers and other systems remotely.
    
- **File Transfers:** Through tools like `scp` (Secure Copy) and `sftp` (SSH File Transfer Protocol), users can securely transfer files between machines.
    
- **Port Forwarding:** Supports secure port forwarding, which can tunnel other types of traffic (like HTTP) through an encrypted SSH connection.
    
- **Tunneling:** Enables secure tunneling of network traffic, often used for securing insecure protocols or accessing restricted networks.
    
- **Authentication:** Supports multiple authentication methods, including:
    
    - **Password Authentication:** Users can log in with a username and password.
    - **Public Key Authentication:** More secure, uses SSH key pairs (public/private keys) for authentication.
    - **GSSAPI/Kerberos:** Supports Kerberos authentication for environments using Kerberos tickets.

### Common Use Cases:

- **Remote Server Management:** System administrators use `openssh-server` to remotely manage and administer servers.
    
- **Secure File Transfers:** Users can securely copy files between their local machine and a remote server.
    
- **Remote Development:** Developers can connect to remote development environments, run code, and manage files.
    

### Installation:

On a Linux system, you can typically install `openssh-server` using your package manager. For example, on Debian-based distributions (like Ubuntu), you would use:


```
sudo apt-get update
sudo apt-get install openssh-server
```


After installation, the SSH server starts automatically, and you can configure it by editing the `sshd_config` file, usually located at `/etc/ssh/sshd_config`.

### Configuration:

- **Default Port:** The SSH server listens on port 22 by default. This can be changed in the `sshd_config` file.
- **Allowing/Restricting Users:** You can configure which users or groups are allowed or denied access.
- **Key-based Authentication:** You can set up SSH keys for passwordless login and disable password-based authentication for enhanced security.

### Starting and Stopping the Service:

You can manage the `openssh-server` service using systemd (on most modern Linux distributions):

```
sudo systemctl start ssh
sudo systemctl stop ssh
sudo systemctl restart ssh
sudo systemctl status ssh

```

### Security Considerations:

- **Disable Root Login:** It’s common practice to disable SSH logins for the root user to minimize security risks.
- **Firewall Configuration:** Ensure your firewall allows SSH traffic if you're accessing the server over a network.
- **Keep Updated:** Regularly update the `openssh-server` to protect against known vulnerabilities.

Overall, `openssh-server` is a critical tool for secure remote administration, providing a robust and flexible solution for managing systems across networks.