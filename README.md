# Setting Up Git and SSH for Private Repository Access

These instructions will help you to install git (an advanced file manager for programming projects), create and link an SSH key to Github, and download (clone) a repository from Github to your local computer.

You will need:
- A computer that you have admin rights over.
- A POSIX-compliant terminal (such as Git Bash, your default Linux or Mac terminal, or WSL).
- A web browser.
- A Github account.

> [!NOTE]
>   **Tips for Using the Terminal**
> - Some commands may not produce any visible output — this is normal.  
> - If you are asked something like *“Do you want to continue?”*, type **Y** (or **yes**) and press **Enter**.  
> - To **copy** in a terminal, use **Ctrl + Shift + C**.  
> - To **paste**, use **Ctrl + Shift + V**.  
> - For more shortcuts, see [this guide](https://gist.github.com/bradtraversy/cc180de0edee05075a6139e42d5f28ce).

---

## 1. Install Git
- Open the terminal (`Ctrl + Alt + T`).
- Run
```bash
sudo apt update
```
- Run
```bash
sudo apt install git
```
---

## 2. Configure Git

Run the following commands, replacing `"Your Name"` and `"your.email@example.com"` with your own name and email:
```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
````

---

## 3. Set up an SSH key

* Check for existing SSH keys with `ls -al ~/.ssh`.

  * NOTE: If the output has `id_ed25519`, then you already have an SSH key and can skip to Step 4.
    [IMAGE]
* If no key is found, generate one using:

  ```bash
  ssh-keygen -t ed25519 -C "your.email@example.com"
  ```

  * NOTE: You will be prompted to enter a file to save the key to. The default is recommended and can be chosen by simply pressing Enter.
    You will also be asked to give a passphrase. You can skip the passphrase by pressing Enter twice more.
    You will then be shown the SSH-key fingerprint and a “randomart” image — these are saved automatically.
    [IMAGE]

---

## 4. Add your SSH key to your GitHub account

* Copy the public key to your clipboard:

  ```bash
  cat ~/.ssh/id_ed25519.pub
  ```
* Open GitHub in your browser.
* In the top-right corner, click your profile photo → **Settings**.
  [IMAGE]
* In the sidebar, click **SSH and GPG keys**.
  [IMAGE]
* Click **New SSH key** or **Add SSH key**.
  [IMAGE]
* Paste your key into the “Key” field.
* Give it a descriptive title (e.g., *Laptop SSH Key*).
* Click **Add SSH key**.

---

## 5. Clone the repository

* Go to the GitHub repository you want to clone.
  [IMAGE]
* Click the green **Code** button, then select **SSH**.
  [IMAGE]
* Copy the given URL to your clipboard and return to the terminal.
* Run `git clone URL`, replacing `URL` with the SSH link you copied.

  * Example:

    ```bash
    git clone git@github.com:BYUMarsRover/BYU-Mars-Rover-Wiki.git
    ```
  * NOTE: You may see a warning asking if you want to trust GitHub. Reply with `yes`.
    [IMAGE]

Congratulations! You have cloned the repository onto your computer!

For any other repository you want to clone, you only need to repeat **Part 5** of these instructions. Good luck!
