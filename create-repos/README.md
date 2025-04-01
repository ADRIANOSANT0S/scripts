# Create GitHub Repository Script

This script automates the process of creating a new repository on GitHub, initializing it locally, and pushing it to the remote GitHub repository.

## Requirements

Before running the script, make sure you have the following installed:

- **Git**: To handle version control and repository operations.
- **GitHub CLI (`gh`)**: To interact with GitHub from the command line.
- **jq**: A lightweight and flexible command-line JSON processor.

## Install Required Tools

### **Linux (Ubuntu/Debian)**
```bash
sudo apt update
sudo apt install git gh jq -y
```

### **macOS (Using Homebrew)**
```bash
brew install git gh jq
```

### **Windows (Using Chocolatey)**
Run the following commands in **PowerShell (Administrator)**:
```powershell
choco install git gh jq -y
```

⚠️ **Note:** Ensure that Git, GitHub CLI, and jq are available in your system's **PATH**.

---

## Script Usage

### 1. Download the Script

Clone or download the script to your local machine:
```bash
git clone https://github.com/yourusername/scripts.git
cd scripts
```
Or manually download `create-repository.sh` and move it to a directory of your choice.

### 2. Make the Script Executable

After downloading, make sure the script has execution permissions:
```bash
chmod +x create-repository.sh
```

### 3. Running the Script

To run the script from its directory:
```bash
./create-repository.sh
```
The script will ask for:

- Repository visibility (**public/private**)
- GitHub account change (**optional**)
- Git username and email (**if not already configured**)
- Repository name
- Remote repository prefix (**optional**)

---

## Running the Script Globally on Different Operating Systems

### **Linux/macOS**
Move the script to `/usr/local/bin` (a directory in the system's **PATH**):
```bash
sudo mv create-repository.sh /usr/local/bin/create-repository
```
Ensure it is executable:
```bash
sudo chmod +x /usr/local/bin/create-repository
```
Now you can run the script from anywhere using:
```bash
create-repository
```

### **Windows (Git Bash or PowerShell)**

Move the script to a folder included in your **PATH**, such as:
```powershell
C:\Program Files\Git\usr\bin\
```
Rename the file to `create-repository` (without `.sh` extension) for easier execution.

Now, you can run the script in **Git Bash** using:
```bash
create-repository
```

Alternatively, if using **PowerShell**, modify `~/.bashrc` or `~/.bash_profile` (in Git Bash) and add:
```bash
export PATH=$PATH:/c/Program\ Files/Git/usr/bin/
```
Then run:
```bash
source ~/.bashrc
```
Now, the script can be executed from any directory.

---

## How the Script Works

1. **GitHub Login Check:** Verifies if you're logged in to **GitHub CLI (`gh`)**. If not, it prompts you to log in.
2. **GitHub Account Switch:** Allows you to switch GitHub accounts if necessary.
3. **Repository Creation:** Creates a new repository on GitHub based on user input.
4. **Git Configuration:** If Git isn't configured with your username and email, the script prompts you to set them up.
5. **Push to GitHub:** Initializes a local repository and pushes it to GitHub.

---

## Troubleshooting

- **"You are not logged in to GitHub CLI"**  
  Run:
  ```bash
  gh auth login
  ```
  to log in.

- **"Command not found"**  
  Ensure **Git, GitHub CLI, and jq** are installed and added to your **PATH**.

- **Permission Issues**  
  Run:
  ```bash
  chmod +x create-repository.sh
  ```
  to ensure the script is executable.

- **GitHub Repository Already Exists**  
  The script will prompt you before overwriting an existing directory.

---

🚀 Now you can quickly create and initialize GitHub repositories with ease!
