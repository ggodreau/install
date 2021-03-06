# ![](https://ga-dash.s3.amazonaws.com/production/assets/logo-9f88ae6c9c3871690e33280fcf557f33.png) Installation

## Part 1. Operating System

You can be a data scientist on any operating system. In general, most professionals choose a UNIX-type OS; typically Apple's OS X or a popular Linux distribution, such as Ubuntu. If you're already using Mac or Linux, great! Skip ahead to Part 2 and get started with your installs.

However, there is a growing need for (and interest in) data science in industries that traditionally use PCs. If you're on a Windows machine, that's ok too! You'll just need to install an additional piece of software to provide a development environment similar to OS X and Linux.

Click [here to download the Git Bash shell](https://gitforwindows.org/). This will allow you to emulate most of the common commands and functions native to OS and Linux systems.

## Terminal

### Mac

- Open a terminal by hitting the apple key + spacebar, and typing 'terminal' in the spotlight search. Open the Terminal application.
- Type `git --version` in the terminal and hit enter
- The returned version of git should be a major version of 2.x.x or greater, for example:

```bash
[person@computer]$ git --version
git version 2.17.1
```

### Windows

Windows has no native git or terminal support. To achieve equivalent functionality, a program named GitBash must be downloaded from [here.](https://git-scm.com/download/win)

<ol>
  <li>
    <details>
      <summary>Open the installation executable and accept the default directory.</summary>
      <p align="center"><img src="./assets/gitbash0.png" width="800"></p>
    </details>
  </li>
  <li>
    <details>
      <summary>Check for updates daily.</summary>
      <p align="center"><img src="./assets/gitbash1.png" width="800"></p>
    </details>
  </li>
  <li>
    <details>
      <summary>Use vim as the default text editor.</summary>
      <p align="center"><img src="./assets/gitbash2.png" width="800"></p>
    </details>
  </li>
  <li>
    <details>
      <summary>This should be 'Use Git from Git Bash only' Needs changed.</summary>
      <p align="center"><img src="./assets/gitbash3.png" width="800"></p>
    </details>
  </li>
  <li>
    <details>
      <summary>Change to 'Checkout as-is, commit Unix-style line endings.'</summary>
      <p align="center"><img src="./assets/gitbash4.png" width="800"></p>
    </details>
  </li>
  <li>
    <details>
      <summary>Uncheck the two boxes and click finish.</summary>
      <p align="center"><img src="./assets/gitbash5.png" width="800"></p>
    </details>
  </li>
  <li>
    <details>
      <summary>Open git bash via the desktop or start menu icons.</summary>
      <p align="center"><img src="./assets/gitbash6.png" width="800"></p>
    </details>
  </li>
</ol>


## Base Python Installation

### Windows (Mac & Linux similar)

<ol>
  <li>
    <details>
      <summary>First, head over to <a href="https://www.python.org/downloads/windows/">python.org</a>. Click on the latest release for <b>Python 3</b> (do not use Python 2!!).</summary>
      <p align="center"><img src="./assets/py1.png" width="800"></p>
    </details>
  </li>
  <li>
    <details>
    <summary>That will bring you to this page. Click on the <b>Windows x86-64 executable installer</b> link.</summary>
    <p align="center"><img src="./assets/py2.png" width="800"></p>
    </details>
  </li>
  <li>
    <details>
    <summary>Select a location to save the file to. Here, I've saved the file to my desktop. If you'd like to verify that the file downloaded correctly, you can run an <a href="https://en.wikipedia.org/wiki/Md5sum">md5 checksum</a> on the file by using <code>md5sum.exe</code> (this comes bundled with gitbash) and verify the returned string (here shown ending in `be3e`) matches the checksum displayed on the webpage.</summary>
    <p align="center"><img src="./assets/py3.png" width="800"></p>
    </details>
  </li>
  <li>
    <details>
    <summary>Run the installer by double clicking on it. <b>Uncheck</b> 'Add Python 3.x to PATH'. Click on 'Customize installation'.</summary>
    <p align="center"><img src="./assets/py5.png" width="800"></p>
    </details>
  </li>
  <li>
    <details>
    <summary><b>Check</b> 'Add Python to environment variables'. <b>This is very important!!!</b> Your install location should be <code><Drive letter>:\Users\<username>\AppData\Local\Programs\Python\Python37</code>. </summary>
    <p align="center"><img src="./assets/py6.png" width="800"></p>
    </details>
  </li>
  <li>
    <details>
    <summary>Your installation should display the below screen if successful. You do <b>not</b> need to disable path length limit.</summary>
    <p align="center"><img src="./assets/py7.png" width="800"></p>
    </details>
  </li>
  <li>
    <details>
    <summary>Run <code>which python</code> to verify the installation location (it should be in <code><Drive letter>:/Users/<username>/AppData/Local/Programs/Python/Python37/python</code>). Verify your python version is 3.x.x with <code>python -V</code>. Verify your pip package manager is installed with <code>pip -V</code>. Don't worry about the version of pip - we'll update it in the next step. </summary>
    <p align="center"><img src="./assets/py8.png" width="800"></p>
    </details>
  </li>
  <li>
    <details>
    <summary>Update your pip version to the latest one with <code>python -m pip install --upgrade pip</code></summary>
    <p align="center"><img src="./assets/py9.png" width="800"></p>
    </details>
  </li>
  <li>
    <details>
    <summary>Install virtualenvwrapper, an environment manager for python, by typing <code>pip install virtualenvwrapper</code></summary>
    <p align="center"><img src="./assets/py10.png" width="800"></p>
    </details>
  </li>
  <li>
    <details>
    <summary>Upon completion, you need to add a few lines to your <code>~/.bash_profile</code> file. This will set environment variables and paths for the virtualenvwrapper tool.</summary>
    <p align="center"><img src="./assets/py11.png" width="800"></p>
    </details>
  </li>
  <li>
    <details>
    <summary>When opened, insert the following code block. Press <code>i</code> to enter insert mode before pasting the text below. When finished, press <code>Esc</code> followed by <code>wq</code>. Press <code>Enter</code> to write the changes to file.</summary>
    <code>
      export WORKON_HOME=$HOME/.virtualenvs
      export PROJECT_HOME=$HOME/Devel
      source ~/AppData/Local/Programs/Python/Python37/Scripts/virtualenvwrapper.sh
    </code><br>
    <p align="center"><img src="./assets/py12.png" width="800"></p>
    </details>
  </li>
  <li>
    When finished, type <code>source ~/.bash_profile</code> to deploy the above changes. You may see some output on your terminal screen for the environment variables and directories being created. This is normal and a one-time occurrence.
  </li>
  <li>
    <details>
    <summary>Type <code>mkvirtualenv <your environment name></code>. The envrironment name can be anything you'd like. Here, we're using an environment named <code>utc</code>.</summary>
    <p align="center"><img src="./assets/py13.png" width="800"></p>
    </details>
  </li>
  <li>
    <details>
    <summary> Now comes the big installation! Be sure you have activated your environment. It will display <code>(<your environment name>)</code> above your terminal. Notice how we have <code>(utc)</code> above our terminal prompt here, denoting we are in the utc virtual environment.</summary>
    <code>pip install jupyter pandas matplotlib seaborn requests openpyxl pytime pdfminer.six PyPDF4</code><br>
    <p align="center"><img src="./assets/py14.png" width="800"></p>
    </details>
  </li>
  <li>
    <details>
    <summary>It make take a few minutes to install everything. When finished, you should have a screen that looks like this. Run <code>echo $?</code> at the prompt. If the returned value is <code>0</code>, you have successfully installed all your packages!</summary>
    <p align="center"><img src="./assets/py15.png" width="800"></p>
    </details>
  </li>
  <li>
    <details>
    <summary>Now start your jupyter notebook! Type in <code>jupyter notebook</code> in your terminal. You should see the following window automatically pop up in your system's default browser.</summary>
    <p align="center"><img src="./assets/py16.png" width="800"></p>
    <br>
    <p align="center"><img src="./assets/py17.png" width="800"></p>
    </details>
  </li>
  <li>
    <details>
    <summary>Open a new notebook by clicking on New -> Python 3. Make sure it says 'Python 3' and <b>not</b> 'Python 2'.</summary>
    <p align="center"><img src="./assets/py18.png" width="800"></p>
    </details>
  </li>
  <li>
    <details>
    <summary>Finally, test all the dependent libraries and python version using the following code.</summary>
    <br>
    <pre>
      import pandas as pd
      import matplotlib
      import seaborn
      import requests
      import openpyxl
      import pytime
      import pdfminer
      import PyPDF4
      !python -V
    </pre>
    <br>
    <p align="center"><img src="./assets/py19.png" width="800"></p>

    The returned results should be <code>Python 3.x.x</code> with no errors (no text in red).
    </details>
  </li>
</ol>

## Part 2. Git Configuration

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
