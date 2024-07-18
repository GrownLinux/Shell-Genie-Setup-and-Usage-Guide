# Shell-Genie-Setup-and-Usage-Guide
This guide provides step-by-step instructions for installing and configuring Shell Genie, a command-line tool that uses artificial intelligence to convert your questions into executable commands in the terminal.


## Prerequisites

- Debian-based system (e.g., Ubuntu)
- Python 3.10 or higher
- Internet connection
- OpenAI API key (if using GPT-3.5 backend)

## Installation

### Step 1: Install pipx

First, ensure you have `pipx` installed. `pipx` is an installer for Python packages.

```
sudo apt update
sudo apt install pipx
pipx ensurepath
```

Step 2: Install Shell Genie

Use pipx to install Shell Genie:
```
pipx install shell-genie
```

Step 3: Initialize Shell Genie

Initialize Shell Genie and select the backend. If the Free Genie backend is not accessible, you can use the GPT-3.5 backend from OpenAI.
```
shell-genie init
```

During initialization, you will be prompted to choose a backend. Select openai-gpt-3.5-turbo if Free Genie is unavailable. You will need to enter your OpenAI API key when prompted.
Usage

Once initialized, you can start using Shell Genie to generate commands.
Example Commands

 Find all .txt files in the current directory:
```
shell-genie ask "find all files with the txt suffix in the current directory"
```

Find .md files larger than 50KB in the current directory and subdirectories:
```
shell-genie ask "find all files with the md suffix and a file size larger than 50kb in the current directory and its subdirectories"
```

Replace letters A and B with a and b in .txt files:
```
    shell-genie ask "find all text files and replace the first letters A and B with a and b"
```

Creating an Alias

To simplify the usage, you can create an alias in your ~/.bashrc file:

  Open your ~/.bashrc file with a text editor:
```
nano ~/.bashrc
```

Add the following line to the end of the file:
```
alias genie='shell-genie ask'
```

Save the file and reload your bash configuration:

    source ~/.bashrc

Now you can use the alias genie to ask questions:
```
genie "find all files with the txt suffix in the current directory"
```

Troubleshooting
DNS Resolution Issues

If you encounter issues with DNS resolution, try switching to public DNS servers:

  Open your /etc/resolv.conf file with a text editor:
```
sudo nano /etc/resolv.conf
```

Add the following lines:

    nameserver 8.8.8.8
    nameserver 8.8.4.4

    Save the file and close the editor.

Verifying Connectivity

Ensure your internet connection is working and you can resolve domain names:
```
ping google.com
nslookup shell-genie.dylancastillo.co
```

If the Free Genie backend is still inaccessible, consider using the GPT-3.5 backend from OpenAI.
