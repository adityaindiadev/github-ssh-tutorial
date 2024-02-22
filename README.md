# Setting up SSH Keys for GitHub on MacOS and Unix Systems

These instructions will guide you through the process of generating and adding SSH keys to your GitHub account on a Windows system.

## Prerequisites

- Git Bash installed on your Windows machine. You can download Git for MacOS and Unix Systems [here](https://git-scm.com/downloads).

## Steps

### 1. Generate SSH Key Pair:

- Open a terminal or command prompt on your local machine.

- Run the following command to generate a new SSH key pair. Replace <your_email@example.com> with the email address associated with your GitHub account.

```bash
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

- You will be prompted to choose a location to save the SSH key. Press Enter to accept the default location (~/.ssh/id_rsa), or specify a different location if you prefer.

### 2. Add SSH Key to SSH Agent:

- Start the SSH agent by running the following command:

```bash
eval "$(ssh-agent -s)"
```

- Add your SSH private key to the SSH agent. If you saved your key with a different filename, replace ~/.ssh/id_rsa with the path to your private key.

```bash
ssh-add ~/.ssh/id_rsa
```

### 3. Add SSH Key to GitHub:

- Copy the SSH public key to your clipboard using the following command:

```bash
cat ~/.ssh/id_rsa.pub
```

- Log in to your GitHub account in your web browser.

- Go to "Settings" from your profile dropdown menu.

- In the left sidebar, click on "SSH and GPG keys."

- Click on "New SSH key" or "Add SSH key."

- Paste your SSH key into the "Key" field.

- Optionally, provide a descriptive title for the key in the "Title" field.

- Click "Add SSH key."

### 4. Verify SSH Key Addition:

- To verify that your SSH key is set up correctly, you can run the following command in your terminal:

```bash
ssh -T git@github.com
```

- If the setup was successful, you should see a message indicating that you've successfully authenticated.

Once you've completed these steps, your SSH key should be set up and associated with your GitHub account, allowing you to use SSH for authentication when interacting with GitHub repositories.



<br /><br />

# Setting up SSH Keys for GitHub on Windows

These instructions will guide you through the process of generating and adding SSH keys to your GitHub account on a Windows system.

## Prerequisites

- Git Bash installed on your Windows machine. You can download Git for Windows [here](https://git-scm.com/downloads).

## Steps

### 1. Generate SSH Key Pair

You can use the built-in OpenSSH client on Windows 10 and later versions. Open PowerShell or Command Prompt to generate a new SSH key pair. Replace `<your_email@example.com>` with the email address associated with your GitHub account.

```bash
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

You will be prompted to choose a location to save the SSH key. Press Enter to accept the default location (C:\Users\your_username\.ssh\id_rsa), or specify a different location if you prefer.

### 2. Add SSH Key to SSH Agent

```bash
Start-Service ssh-agent
```

Add your SSH private key to the SSH agent:

```bash
ssh-add C:\Users\your_username\.ssh\id_rsa
```

### 3. Add SSH Key to GitHub:

Copy the SSH public key to your clipboard using the following command in PowerShell:

```bash
cat C:\Users\your_username\.ssh\id_rsa.pub | clip
```

- Log in to your GitHub account in your web browser.

- Go to "Settings" from your profile dropdown menu.

- In the left sidebar, click on "SSH and GPG keys."

- Click on "New SSH key" or "Add SSH key."

- Paste your SSH key into the "Key" field.

- Optionally, provide a descriptive title for the key in the "Title" field.

- Click "Add SSH key."

### 4. Verify SSH Key Addition:

To verify that your SSH key is set up correctly, you can run the following command in PowerShell:

```bash
ssh -T git@github.com
```



## At the end, now you can push code in GitHub

#### …or create a new repository on the command line

```bash
echo "# github-ssh-tutorial" >> README.md
git init
git add .
git commit -m "first commit"
git branch -M main
git remote add origin git@github.com:adityaindiadev/github-ssh-tutorial.git
git push -u origin main
```

#### …or push an existing repository from the command line

```bash
git remote add origin git@github.com:adityaindiadev/testHu.git
git branch -M main
git push -u origin main
```