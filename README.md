# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Installation Check (15 min)

## Part 1. Operating System

You can be a data scientist on any operating system. In general, most professionals choose a UNIX-type OS; typically Apple's OS X or a popular Linux distribution, such as Ubuntu. If you're already using Mac or Linux, great! Skip ahead to Part 2 and get started with your installs.

However, there is a growing need for (and interest in) data science in industries that traditionally use PCs. If you're on a Windows machine, that's ok too! You'll just need to install an additional piece of software to provide a development environment similar to OS X and Linux. 

Click [here to download the Git Bash shell](https://gitforwindows.org/). This will allow you to emulate most of the common commands and functions native to OS and Linux systems.

## Git Bash Download

### Mac

- Open a terminal by hitting the apple key + spacebar, and typing 'terminal' in the spotlight search. Open the Terminal application.
- Type `git --version` in the terminal and hit enter
- The returned version of git should be a major version of 2.x.x or greater, for example:

```bash
[greg@13z]$ git --version
git version 2.17.1
```

### Windows

<details>
 <summary>Windows has no native git support, so it must be downloaded from [here](https://git-scm.com/download/win)</summary>
<p align="center"><img src="./assets/gitbash0.png" width="800"></p>
</details>

Open the installation executable and accept the default directory.k

<p align="center"><img src="./assets/gitbash1.png" width="800"></p>

Check for updates daily.

<p align="center"><img src="./assets/gitbash2.png" width="800"></p>

Use vim as the default text editor.

<p align="center"><img src="./assets/gitbash3.png" width="800"></p>

This should be 'Use Git from Git Bash only'. Needs changed.

<p align="center"><img src="./assets/gitbash4.png" width="800"></p>

Change to 'Checkout as-is, commit Unix-style line endings'.

<p align="center"><img src="./assets/gitbash5.png" width="800"></p>

Uncheck the two boxes and click finish.

<p align="center"><img src="./assets/gitbash6.png" width="800"></p>

Open git bash via the desktop or start menu icons.


## Base Python Installation

### Windows

First, head over to [python.org](https://www.python.org/downloads/windows/). Click on the latest release for *Python 3* (do not use Python 2!!).

<p align="center"><img src="./assets/py1.png" width="800"></p>


That will bring you to this page. Click on the *Windows x86-64 executable installer* link. 

<p align="center"><img src="./assets/py2.png" width="800"></p>


Select a location to save the file to. Here, I've saved the file to my desktop. If you'd like to verify that the file downloaded correctly, you can run an [md5 checksum](https://en.wikipedia.org/wiki/Md5sum) on the file by using `md5sum.exe` (this comes bundled with gitbash) and verify the returned string (here shown ending in `be3e`) matches the checksum displayed on the webpage. 

<p align="center"><img src="./assets/py3.png" width="800"></p>

Run the installer by double clicking on it. *Uncheck* 'Add Python 3.x to PATH'. Click on 'Customize installation'.

<p align="center"><img src="./assets/py4.png" width="800"></p>

*Uncheck* 'tcl/tk and IDLE' installer.

<p align="center"><img src="./assets/py5.png" width="800"></p>

*Check* 'Add Python to environment variables'. *This is very important!!!*
Your install location should be `<Drive letter>:\Users\<username>\AppData\Local\Programs\Python\Python37`.

<p align="center"><img src="./assets/py6.png" width="800"></p>

Your installation should display the below screen if successful. You do *not* need to disable path length limit.

<p align="center"><img src="./assets/py7.png" width="800"></p>





## Part 2. Anaconda Installation

In this course, we'll be working closely with tools that utilize the Python programming language. Anaconda is a popular cross-platform tool that helps install and manage Python-related data science libraries.

1) [Download Anaconda](https://docs.anaconda.com/anaconda/install/) and follow the installation instructions package for your operating system. Please make sure that you're downloading the latest stable version for Python 3! Most modern computers will use 64-bit installation. When in doubt, use 32-bit as it is backward compatible.<br>

2) Agree to the terms and let Anaconda complete its default installation. <br>

3) Once installed, navigate to your command line (on OS X, this is the terminal application; on Windows, use your new `Git Bash` shell) and confirm that it's installed by typing in the `which conda` command. <br>

You should see:

```bash
$ which conda
/Users/USERNAME/anaconda3/bin/conda
```
  - If the command line returns a file path (like in the example below), you've successfully installed Anaconda.
  - If the command line returns nothing (and sends you back to the prompt), check in with your instructor.
    - **Note**: Your file path may look different.
    - **Note**: You'll often see commands that look like: `$ which conda` above — when you see those, type in everything **except** the dollar sign. The dollar sign is used to denote a code prompt in your window.

4) Once installed, run the following command to ensure that some frequently used libraries are installed. Anaconda may also update your packages at this time (which is OK!). You will be installing the file in this repository, which can be downloaded [here](./assets/utc_env.txt). <br>

First, create a new virtual environment, using the above file to specify packages. Make sure you've downloaded the `utc_env.txt` file the working directory of the bash shell. To check the working directory of the shell, use `pwd`.:

```bash
conda create -n utc -c conda-forge --file ./utc_env.txt
```

## Part 3. Git Configuration (OPTIONAL)

1) To check if your Git installation was successful, open a new terminal window and try to run Git from the command line: <br>

```bash
$ git --version
```

The output should be something like this:

```bash
$ git --version
git version 2.5.0
```

2. Make sure you've registered yourself for a [github](https://www.github.com) account first. Once you get your email and username set up, do the following locally on your machine:

```bash
$ git config --global user.name "Your Name"
$ git config --global user.email your.name@example.com
```

These identifiers will be added to your commits and show up when you push your changes to [GitHub](https://www.github.com) from the command line!

### Optional: Set Up SSH for Easier Remote Connection

While you can connect your local repositories (the work on your laptop) to remote repositories (those stored on [GitHub](https://www.github.com)) without much additional effort, this will prompt you to input your username and password quite  frequently. However, there's an alternative known as SSH, which will let you create a file on your computer that will authenticate you to [GitHub](https://www.github.com) without entering your username and password over and over again. 

**Note**: Remember, these steps are optional. If you're having trouble, feel free to chat w your instructor!

#### Using SSH and SSH Agent (Recommended)

You can use these guides to get started:

- [Working with SSH Key Passphrases](https://help.github.com/articles/working-with-ssh-key-passphrases/)
- [Generating a New SSH Key and Adding it to the SSH Agent](https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/)
- [Adding a New SSH Key to Your GitHub Account](https://help.github.com/articles/adding-a-new-ssh-key-to-your-github-account/)

#### What is Secure Shell (SSH)?

SSH, or Secure SHell, is a common means of adding an additional layer of security to a connection. It establishes authenticity between a client and a server. This can be useful for secure file sharing and remote application access.

#### How SSH Works

There are a couple of steps to the high-level SSH process:

- A client makes a request to the server.
- A server responds by asking for authentication.
- A client provides authentication.
- If authentication is correct, a connection is established.
