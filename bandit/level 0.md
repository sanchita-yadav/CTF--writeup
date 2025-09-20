# OverTheWire Bandit Writeups: Levels 0–23

## Level 0 → Level 1
- **Objective:** Log in using SSH.
- **Command:**
  ```bash
  ssh bandit0@bandit.labs.overthewire.org -p 2220
Password: bandit0
	•	Next Level: The password for Level 1 is stored in a file called readme in the home directory.
cat readme
