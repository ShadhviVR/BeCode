# Configure Git & GitHub

## Goals

- Configure Git on your computer
- Being able to use Git and GitHub using SSH keys

## Deadline

- Estimated duration: We'll find out together :D

## Pre-requisites

Make sure you have completed your [GitHub profile](https://github.com/settings/profile).
Your name, surname and a recent picture of yourself are required.

## Instructions

### 1. Configure Git

After you have installed Git, you should configure it with a name and email address. This is important because when you work on the same project with multiple people, you will be able to know who changed what.

#### Set your Git user name and email address

1. [Set your Git username for every repository on your computer](https://help.github.com/en/github/using-git/setting-your-username-in-git#setting-your-git-username-for-every-repository-on-your-computer)
2. [Set your commit email address in Git](https://help.github.com/en/github/setting-up-and-managing-your-github-user-account/setting-your-commit-email-address#setting-your-commit-email-address-in-git)

For your future knowledge (you don't need to do it now), here you can find more things you can configure: https://git-scm.com/book/en/v2/Getting-Started-First-Time-Git-Setup

### 2. Use GitHub on the terminal

To log in into GitHub from your terminal you need an **SSH key**. An **SSH Key** is like a password saved to your computer that is used automatically every time you need to perform an action as a user of a platform.
In the next steps we will see how to generate one and link it to your GitHub account, so that every time you use the `git` command to interact with a GitHub repository you will be automatically authenticated.

#### Generate an SSH-key

1. Open your terminal
2. Copy the following command into your terminal.
   Change "your_email@example.com" to the email address linked to your GitHub account and press <kbd>Enter</kbd>.

   ```shell
   ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
   ```

   This will create an SSH key that is linked to your email.

3. Generate a private/public RSA key pair
   - When you are asked to "Enter a file in which to save the key", just press <kbd>Enter</kbd>. This will accept the standard location.
   - When you are asked to enter a passphrase, just press <kbd>Enter</kbd> twice to use an empty passphrase.
4. Follow this tutorial to add the SSH key to your GitHub account: https://help.github.com/en/github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account

[Back to Git](./)
