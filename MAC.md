# Installfest: Mac Users
![](https://www.sadanduseless.com/wp-content/uploads/2019/06/new-apple-mug.png)
## Overview
We'll be installing most of the necessary tools for software engineering. These tools are what we'll be utilizing during our conquest to take over the dev world.
## Objectives
- Install Homebrew
- Install Fish and Oh-My-Fish
- Install Node
- Install VsCode
- Install Git
- Install Python
- Install Vercel
- Install MongoDB
- Install Postgres
## Installing Homebrew
Homebrew is a package manager for Mac Os. It makes installing programs fast and easy.
To Install Homebrew paste the following command into your terminal and hit the enter key:
```sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
The above command will perform the installation for you.
## Installing Fish and Oh-My-Fish
### Fish Installation
What is Fish? Fish is a shell designed for interactive use, it provides us with useful shortcuts to execute terminal commands faster and also enables auto completion.
To install Fish, execute the following command in your terminal:
```sh
brew install fish
```
Now you’re not quite ready to go, you need to add Fish to your systems shell listing in /etc/shells, this does require administrative access.
```sh
sudo echo '/usr/local/bin/fish' >> /etc/shells
```
Now that fish is installed, in order to use it lets begin by setting it as your default terminal shell environment.
```sh
chsh -s /usr/local/bin/fish
```
### Oh-My-Fish Installation
What is Oh-My-Fish?
> Oh My Fish is an open source, community-driven framework for managing your Fish configuration. It comes with a bunch of features out of the box and improves your terminal experience.
It also provides us with preset themes to make reading your terminal much easier.
#### To install Oh-My-Fish:
Execute the following command's in your terminal:
```sh
curl -L https://get.oh-my.fish | fish
```
## Installing NodeJs
What is NodeJS? NodeJS is a javascript runtime that allows us to execute Javascript outside of a browser.
To intall NodeJS, execute the following in your terminal:
```sh
brew install node
```
To confirm your installation, execute the following in your terminal:
```sh
node -v
```
You should see a node version listed.
## Installing VsCode
VsCode is going to be our text editor of choice throughout the course, it provides us with a wonderful environment to run and test our code.
To install VsCode, execute the following in your terminal:
```sh
brew install --cask visual-studio-code
```
Verify your installation by running:
```sh
code .
```
This should open a VsCode window.
If the above does not work, open VsCode which will be located in your Applications folder.
Once a VsCode window opens, press and hold `cmd+shift+p ` to open the command pallete. In the command pallate, type in `path` and an option named:
> Shell Command: Install `code` command in PATH.
Select this option and reconfirm the `code .` command in your terminal.
## Installing Git
Git is a version control manager that we'll be using in conjunction with Github to manage code updates during this course.
To install Git, execute the following in your terminal:
```sh
brew install git
```
Once the installation completes, execute the following in your terminal, one by one.
```sh
git config --global user.name "Your Name Here"
```
```sh
git config --global user.email "your_email@youremail.com"
```
Replace your name and email with the name and email you use on Github.
### Setting Up Github Authentication
In order for Github to deem our machines as "safe" to push code, we need to setup an identification key known as a `ssh key`.
Enter the following commands in your terminal:
```sh
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```
**NOTE**: Replace the above email with your github email!
You should see the following prompt:
```sh
> Enter a file in which to save the key (/Users/you/.ssh/id_ed25519): [Press enter]
```
Hit enter to save it in a default file.
You'll now be prompted to password protect the ssh key, we can skip this portion. When prompted with the following:
```sh
> Enter passphrase (empty for no passphrase): [Type a passphrase]
> Enter same passphrase again: [Type passphrase again]
```
**Hit enter to leave the password as blank.**
Let's start the mac os ssh-agent, enter the following into your terminal:
```sh
eval "$(ssh-agent -s)"
> Agent pid 59566
```
Now copy the ssh key to your clipboard:
```sh
pbcopy < ~/.ssh/id_rsa.pub
```
To complete this setup, following the instructions starting from step 2 listed at this link **[HERE](https://docs.github.com/en/github/authenticating-to-github/adding-a-new-ssh-key-to-your-github-account)**.
## Installing Python
Python is a popular language that we'll be learning in Unit 4 of this course.
We'll be installing Python3.
To install Python3, execute the following in your terminal:
```sh
brew install python
```
To confirm your installation, execute the following in your terminal:
```sh
python --version
```
You should see a python version listed.
## Installing Heroku (Not Fk Heroku) Installing Vercel!
Vercel is a hosting site that we'll be using to deploy projects.
Execute the following in your terminal to install the Vercel CLI:
```npm
npm i -g vercel
```
If you do not have a Vercel Account it is highly reccomended that you get one, its free, lean, mean and delicious.
**[Register with your GitHub Here](https://vercel.com/)**
## Installing MongoDB
MongoDB is a document based database that we'll be using in this course.
To install MongoDB, execute the following commands in your terminal:
```sh
xcode-select --install
```
```sh
brew tap mongodb/brew
```
```sh
brew tap | grep mongodb
```
```sh
brew install mongodb-community@4.4
```
To start the mongo service:
```sh
brew services start mongodb-community@4.4
```
**NOTE**: the above command will keep MongoDB running in the backround on your machine even after shutdowns.
To confirm your installation, enter the following in your terminal:
```sh
mongo
```
An interactive shell should appear. To exit this shell, enter the following command:
```sh
exit
```
## Installing PostgreSQL
PostreSQL is going to be our column based database of choice for this course. PostgreSQL is an open source relational database management system (RDBMS).
To install PostgreSQL, execute the following in your terminal:
```sh
brew install postgres
```
To confirm the installation, run the following in your terminal:
```sh
postgres -V
```
Next enter the following command in your terminal:
```sh
brew services start postgresql
```
This will ensure postgres remains running on our machines.
Now create a database with your username:
```sh
createdb `whoami`
```
Confirm that you can enter the postgres shell:
```sh
psql
```
To exit the shell:
```sh
\q
```
## Recap
At this point we've successfully installed all of the basic silky smooth tools we'll needed to rule the dev world!
## Resources
- [Mac Setup Guide](https://sourabhbajaj.com/mac-setup/)