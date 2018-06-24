# Notes on The Odin Project Installfest

This is a test run through The Odin Projects install fest located at <https://www.theodinproject.com/courses/web-development-101/lessons/installations>. I'm doing the installfest on a VM with Ubuntu 16.04 without running the first command from the installfest.

## Installation instructions

Download Ubuntu 16.04LTS (the 64bit version): http://releases.ubuntu.com/16.04/
install on virturalbox (so you can save the state)
set up completely, (run sudo apt update and sudo apt upgrade first) but before starting the installfest. Create a snapshot of the VM (so you can revert back to a clean machine without re-installing.)
go through the installfest, WITHOUT running the large apt command at the start and note what dependencies are missing and post it here: https://forum.theodinproject.com/t/ubuntu-16-04-lts-installfest-notes/6074 

### Installation

0. I ran sudo apt update and sudo apt upgrade
  
1. Install packaged software and libraries

   Skipped this as instructed.

2. Install Git

   After installing (sudo apt-get install git) git tried git --version. The output is : git version 2.7.4 . So I guess this is ok.

3. RVM Installation.

   1. Install RVM.
   Checked the 'run command as login shell' in profile preferences.
   
   Tried to install RVM using the curl command, but since I did not run the first command of the guide, I do not have curl installed. So I got this error : The program 'curl' is currently not installed.
   
   I installed curl using the recommended command and ran the curl rvm installation command again, this time the installation started but I got an error just like the guide anticipated "GPG signature failed ...". I tried the recommended solution and ran "gpg2 --recv-keys ..." but I got another error saying : "gpg: keyserver receive failed: No keyserver available" then I tried the next recommended command "command curl -sSL https://rvm.io/mpapis.asc | gpg2 --import -" after that I ran the curl command again to install rvm, the installation was successful and after restarting the terminal the result of rvm -v was : rvm 1.29.3(latest) by ...



2. Configure your shell / verify.

      Worked as expected. Rvm version was right and 'rvm is a function'.

4. Install Ruby

  Ran rvm install 2.5.1 (I assumed that's what I should test for, rather than the old version suggested by the guide)
  Ruby was installed successfully without any issues. Ran rvm use and rvm default without any issues.

5. Install Rails. 
   
   No issues.

6. Install Atom

   * The instructions in the installfest are basically "Go to the atom website and find out how to install it." That ends up being:

   ```linux
   curl -sL https://packagecloud.io/AtomEditor/atom/gpgkey | sudo apt-key add -
   sudo sh -c 'echo "deb [arch=amd64] https://packagecloud.io/AtomEditor/atom/any/ any main" > /etc/apt/sources.list.d/atom.list'
   sudo apt-get update
   sudo apt-get install atom
   ```

   I would suggest a section on editing programs, listing a few of the easy ones (Atom, Sublime, Notepad++ Visual Studios Code) with the explanation that it's time to learn how to read docs and find the best way to install their editor with the terminal. 

NOTE: I did not edit this part, as everything was the same and I agree with the suggestion. I would also like to add Ruby Mine to the list as it is awesome and can be free for students.

7. Configure Git. 

Worked as intended.

8. Create an SSH key. 

Worked as intended.

9. Create Heroku Account

   * Since we're trying to avoid snap we should make it apparent that they should not follow the first instructions seen on the page but, instead, use `curl https://cli-assets.heroku.com/install.sh | sh` to install Heroku CLI. Other than that, everything else seems to work as intended.

^ Christopher's stament. Edit: I installed it using snap, did not know I wasn't supposed to do that. It worked ok though


10. The Heroku App.
  
  Made the app, couldn't run it because of no Javascript runtime installed, after running sudo apt-get install nodejs everything worked ok
   

12. Get a sticker.

    * There are no stickers. This is a critical issue that must be fixed. x 2


CONCLUSION : Curl and NodeJs are required for the guide to work
