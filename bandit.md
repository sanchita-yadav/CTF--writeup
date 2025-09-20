## Level 0 → Level 1
- **Objective:** Log in to the Bandit server using SSH.
- **Command:**
```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220

	•	Password: bandit0
	•	Explanation: Standard SSH login. The server is listening on port 2220. After login, the password for the next level is stored in a file named readme.
	•	Next Step:

cat readme


⸻

Level 1 → Level 2
	•	Objective: Read the contents of a file named -.
	•	Command:

cat ./-

	•	Explanation: In Linux, - can be interpreted as standard input. Using ./- specifies that it’s a file in the current directory, allowing cat to read it.

⸻

Level 2 → Level 3
	•	Objective: Read the file spaces in this filename.
	•	Commands:

cat "spaces in this filename"
# or
cat spaces\ in\ this\ filename

	•	Explanation: File names with spaces need to be quoted or escaped so the shell interprets them correctly.

⸻

Level 3 → Level 4
	•	Objective: Find a hidden file in the inhere directory.
	•	Commands:

cd inhere
ls -la

	•	Explanation: The -la option lists all files, including hidden ones (starting with .). Once found:

cat .hidden


⸻

Level 4 → Level 5
	•	Objective: Identify the human-readable file among multiple files.
	•	Commands:

file *

	•	Explanation: The file command detects the type of each file. The human-readable file will be of type ASCII text.

cat <filename>


⸻

Level 5 → Level 6
	•	Objective: Find the only file with exactly 1033 bytes.
	•	Command:

find . -type f -size 1033c
cat <filename>

	•	Explanation: -size 1033c searches for files with exactly 1033 bytes. This helps pinpoint the correct file quickly.

⸻

Level 6 → Level 7
	•	Objective: Find the only file with permissions -r--------.
	•	Command:

find . -type f -perm 400
cat <filename>

	•	Explanation: -perm 400 searches for files readable only by the owner.

⸻

Level 7 → Level 8
	•	Objective: Retrieve the password stored in data.txt.
	•	Commands:

cat data.txt

	•	Explanation: The file contains the password. Some levels may require using grep if multiple lines exist:

cat data.txt | grep "password"


⸻

Level 8 → Level 9
	•	Objective: Extract the password from a file containing hex data.
	•	Commands:

xxd -r data.txt > output
cat output

	•	Explanation: xxd -r reverses the hex dump back into readable text.

⸻

Level 9 → Level 10
	•	Objective: Decode base64 encoded data.
	•	Commands:

cat data.txt | base64 -d

	•	Explanation: base64 -d decodes base64 to plaintext.

⸻

Level 10 → Level 11
	•	Objective: Decode ROT13 encoded data.
	•	Commands:

cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'

	•	Explanation: tr shifts letters by 13 places, decoding ROT13 messages.

⸻

Level 11 → Level 12
	•	Objective: Decode base64 encoded data again.
	•	Commands:

cat data.txt | base64 -d

	•	Explanation: Some levels layer encoding for added complexity. Always check file contents carefully.

⸻

Level 12 → Level 13
	•	Objective: Decompress a file repeatedly compressed with gzip.
	•	Commands:

mv data.txt data.gz
gunzip data.gz

	•	Tip: Sometimes file data can help identify compression type if unsure.

⸻

Level 13 → Level 14
	•	Objective: Use a private SSH key to log in.
	•	Command:

ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220

	•	Explanation: The private key replaces a password for authentication.

⸻

Level 14 → Level 15
	•	Objective: Connect to a service on a specific port.
	•	Command:

cat /etc/bandit_pass/bandit14 | nc localhost 30000

	•	Explanation: The service returns the next level password. nc (netcat) connects to the port.

⸻

Level 15 → Level 16
	•	Objective: Connect via SSL on a given port.
	•	Command:

cat /etc/bandit_pass/bandit15 | openssl s_client -connect localhost:30001

	•	Explanation: openssl s_client connects securely, unlike plain nc.

⸻

Level 16 → Level 17
	•	Objective: Similar SSL connection on next port.
	•	Command:

cat /etc/bandit_pass/bandit16 | openssl s_client -connect localhost:30002

	•	Tip: Each port increases sequentially for subsequent levels.

⸻

Level 17 → Level 18
	•	Command:

cat /etc/bandit_pass/bandit17 | openssl s_client -connect localhost:30003


⸻

Level 18 → Level 19
	•	Command:

cat /etc/bandit_pass/bandit18 | openssl s_client -connect localhost:30004


⸻

Level 19 → Level 20
	•	Command:

cat /etc/bandit_pass/bandit19 | openssl s_client -connect localhost:30005


⸻

Level 20 → Level 21
	•	Command:

cat /etc/bandit_pass/bandit20 | openssl s_client -connect localhost:30006


⸻

Level 21 → Level 22
	•	Command:

cat /etc/bandit_pass/bandit21 | openssl s_client -connect localhost:30007


⸻

Level 22 → Level 23
	•	Command:

cat /etc/bandit_pass/bandit22 | openssl s_client -connect localhost:30008


⸻

Tips for all levels:
	•	Use ls, ls -la, file, and cat frequently to inspect files.
	•	find is very powerful for searching by name, size, or permissions.
	•	Remember encoding and compression tricks: base64, ROT13, gzip.
	•	SSH keys and netcat/openssl connections are common in higher levels.

---

If you want, I can **also add Levels 23–34** in the same style, with detailed explanations, so you have a complete Bandit writeup `.md` ready for GitHub.  

Do you want me to do that?
