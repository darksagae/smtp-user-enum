# smtp-user-enum
`smtp-user-enum` is a tool used in Kali Linux for enumerating valid users on an SMTP server. It helps identify which email addresses exist on a server by using a technique known as "SMTP enumeration."

### How to Use `smtp-user-enum`

1. **Installation**: Typically, `smtp-user-enum` comes pre-installed with Kali Linux. If you need to install it manually, you can use:
   ```bash
   sudo apt install smtp-user-enum
   ```

2. **Basic Command Structure**:
   The basic syntax for using `smtp-user-enum` is:
   ```bash
   smtp-user-enum -M <method> -U <userlist> -t <target>
   ```

### Common Options

- `-M`: Specify the method to use (e.g., `EXISTS`, `VRFY`, `RCPT`).
- `-U`: Specify the file containing a list of usernames (one per line).
- `-t`: Specify the target SMTP server (IP address or hostname).
- `-T`: Set the timeout for the connection.
  
### Example Usage

1. **Basic Enumeration**:
   To enumerate users using the `EXISTS` method:
   ```bash
   smtp-user-enum -M EXISTS -U userlist.txt -t smtp.example.com
   ```
   **Expected Output**:
   ```
   [*] Checking smtp.example.com for valid users...
   [*] User: user1 - Valid
   [*] User: user2 - Invalid
   [*] User: user3 - Valid
   ```

2. **Using Different Methods**:
   You can also try different methods like `VRFY` or `RCPT`:
   ```bash
   smtp-user-enum -M VRFY -U userlist.txt -t smtp.example.com
   ```
   **Expected Output**:
   ```
   [*] Checking smtp.example.com using VRFY...
   [*] User: user1 - Valid
   [*] User: user2 - Invalid
   [*] User: user3 - Valid
   ```

### Conclusion

`smtp-user-enum` is a useful tool for penetration testers and security professionals to identify valid users on an SMTP server. Always ensure that you have permission to test the target server to avoid legal issues.



                           ALTERNATIVE
I'd be happy to help you with your query about smtp-user-enum.

smtp-user-enum is a Kali Linux tool used for enumerating users on a remote SMTP server. It can be used to check if a user exists on a mail server, which is useful for penetration testing and network reconnaissance.

### How to Use smtp-user-enum

The basic syntax for using smtp-user-enum is:
```
smtp-user-enum -U <user_file> -t <target>
```
Here, `<user_file>` is a file containing a list of usernames to test, and `<target>` is the IP address or hostname of the remote SMTP server.

### Common Options

* `-U <user_file>`: Specifies the file containing a list of usernames to test.
* `-t <target>`: Specifies the IP address or hostname of the remote SMTP server.
* `-m <method>`: Specifies the method to use for enumeration (default is VRFY).
* `-T <threads>`: Specifies the number of threads to use for enumeration.
* `-v`: Enables verbose mode, showing more detailed output.

### Examples and Expected Outcomes

1. **Basic User Enumeration**:
```
smtp-user-enum -U users.txt -t 192.168.1.100
```
**Expected Output**:
```
[+] 192.168.1.100:25      220 mail.example.com ESMTP
[+] Users found:
    - admin
    - user1
    - user2
    - ...
```
This will test the usernames in `users.txt` against the remote SMTP server at `192.168.1.100` and list the valid users.

2. **Verbose Mode**:
```
smtp-user-enum -U users.txt -t 192.168.1.100 -v
```
**Expected Output**:
```
[+] 192.168.1.100:25      220 mail.example.com ESMTP
[+] Testing user: admin
[+] User exists: admin
[+] Testing user: user1
[+] User exists: user1
[+] Testing user: user2
[+] User exists: user2
...
```
This will show more detailed output, including the testing of each username and whether it exists or not.

Note: Always ensure you have permission to use this tool on the target system, as unauthorized use may be illegal.



                  ALTERNATIVE
Understood. Here is how to use the `smtp-user-enum` tool in Kali Linux:

`smtp-user-enum` is a tool used to enumerate valid usernames on an SMTP server. It can be useful during penetration testing to identify valid user accounts that can be targeted for further attacks.

**How to Use `smtp-user-enum`**

1. **Installation**: `smtp-user-enum` is typically included in the default Kali Linux installation. If not, you can install it using:

   ```
   sudo apt-get install smtp-user-enum
   ```

2. **Basic Command Structure**:
   The basic syntax for using `smtp-user-enum` is:

   ```
   smtp-user-enum -U <username_file> -t <target_host>
   ```

   Here, `<username_file>` is a file containing a list of usernames to test, and `<target_host>` is the IP address or hostname of the SMTP server.

**Examples and Expected Outputs**

1. **Enumerating Users Using a Username List**:
   ```
   smtp-user-enum -U usernames.txt -t 192.168.1.100
   ```

   **Expected Output**:
   ```
   smtp-user-enum v1.2 ( http://pentestmonkey.net/tools/smtp-user-enum )

   Starting smtp-user-enum at Sat May  6 12:34:56 2023

   Trying host 192.168.1.100 on port 25
   SMTP enum started on Sat May  6 12:34:56 2023

   emailuser1    exists  200 OK
   emailuser2    exists  200 OK
   emailuser3    exists  200 OK
   emailuser4    doesn't exist  550 User unknown 
   emailuser5    doesn't exist  550 User unknown

   Statistics:
   Attempted: 5, Valid: 3, Invalid: 2

   Done, closing down
   ```

   This output shows that `emailuser1`, `emailuser2`, and `emailuser3` are valid user accounts on the target SMTP server, while `emailuser4` and `emailuser5` do not exist.

2. **Enumerating Users with a Different SMTP Port**:
   ```
   smtp-user-enum -U usernames.txt -t 192.168.1.100 -p 587
   ```

   **Expected Output**:
   ```
   smtp-user-enum v1.2 ( http://pentestmonkey.net/tools/smtp-user-enum )

   Starting smtp-user-enum at Sat May  6 12:34:56 2023

   Trying host 192.168.1.100 on port 587
   SMTP enum started on Sat May  6 12:34:56 2023

   emailuser1    exists  200 OK
   emailuser2    exists  200 OK
   emailuser3    doesn't exist  550 User unknown
   emailuser4    doesn't exist  550 User unknown
   emailuser5    doesn't exist  550 User unknown

   Statistics:
   Attempted: 5, Valid: 2, Invalid: 3

   Done, closing down
   ```

   In this example, the tool is using port 587 instead of the default port 25 to connect to the SMTP server.

**Important Notes**:
- `smtp-user-enum` relies on the SMTP server's response to determine if a username is valid or not.
- The effectiveness of the tool depends on the SMTP server's configuration and its response handling.
- Always ensure you have permission to perform SMTP enumeration on a target system.




                            ALTERNATION
`smtp-user-enum` is a tool in Kali Linux used for enumerating valid email addresses on an SMTP server. It helps in identifying valid users by attempting to gather information about email accounts.

### How to Use `smtp-user-enum`

1. **Installation**: If it's not already installed, you can typically install it using:
   ```bash
   sudo apt-get install smtp-user-enum
   ```

2. **Basic Command Structure**:
   The basic syntax for using `smtp-user-enum` is:
   ```bash
   smtp-user-enum -M <method> -U <user_list> -t <target>
   ```

### Common Options

- `-M <method>`: Specify the enumeration method (e.g., `VRFY`, `EXPN`, `RCPT`).
- `-U <user_list>`: Provide a file containing the list of usernames to check.
- `-t <target>`: Specify the target SMTP server (IP address or domain).

### Example Usage

1. **Basic User Enumeration**:
   To check for valid users on an SMTP server:
   ```bash
   smtp-user-enum -M VRFY -U users.txt -t smtp.example.com
   ```
   Here, `users.txt` contains a list of usernames to check.

   **Expected Output**:
   ```
   Valid users:
   user1@example.com
   user2@example.com
   ```

2. **Using Different Methods**:
   You can also use the `EXPN` method:
   ```bash
   smtp-user-enum -M EXPN -U users.txt -t smtp.example.com
   ```

   **Expected Output**:
   ```
   Valid users:
   user3@example.com
   ```

### Conclusion

`smtp-user-enum` is a simple yet effective tool for identifying valid email addresses on an SMTP server, which can assist in further penetration testing or security assessments. Always ensure you have permission before testing against any SMTP servers.
