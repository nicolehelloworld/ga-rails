BACK-END WEB DEVELOPMENT
============================

![GeneralAssemb.ly](https://github.com/generalassembly/ga-ruby-on-rails-for-devs/raw/master/images/ga.png "GeneralAssemb.ly")

# Windows Users - Install Ubuntu

## If you're on a Mac or Linux already, you can skip this.

1. __Install VirtualBox__
	* https://www.virtualbox.org/wiki/Downloads

2. __Download Ubuntu Linux__
	* http://www.ubuntu.com/download/desktop
	* Version 13.04 is probably preferable but 12.04 is also fine.
        * Download the 64-bit version (which is selected by default)
        * 
3. __Create your virtual machine__
  	* Open VirtualBox and click the "New" button
  	* Enter any name
  	* Select "Linux" as the type
  	* Select either "Ubuntu (64 bit)" because you downloaded the 64 bit version.
  	* Memory size is the amount of your RAM that will be used to run
    Linux. 2048MB should be more than enough, but if you have a lot of
    RAM you can boost this number. If your machine only has 1GB of RAM
    then 512MB will have to do. If you're not sure, don't worry because
    this value can be changed later.
  	* Hard drive - Select "Create a virtual hard drive now" then use the
    "VDI" type and then the "Dynamically allocated" option. Name the
    virtual hard drive file anything and select an amount of hard drive
    space that your computer is capable of supporting. 8GB should be plenty.
  	* After clicking "Create", select the new virtual machine you created
    in the left column and press the "Start" button.
  	* In the "Select start-up disk" window, browse for and select the Ubuntu Linux .iso
    file you downloaded and press start. You can then follow the Ubuntu
    installation instructions.

After Ubuntu installation, your VM will restart. Don't let it use the virtual CD drive.

Then, to speed up Ubuntu, do this:

  http://askubuntu.com/questions/207813/why-does-a-ubuntu-12-10-guest-in-virtualbox-run-very-very-slowly

To check if your Ubuntu 12.10 guest is using 3D acceleration, run this command:

```
$ /usr/lib/nux/unity_support_test -p
Not software rendered:    no
Not blacklisted:          yes
GLX fbconfig:             yes
GLX texture from pixmap:  yes
GL npot or rect textures: yes
GL vertex program:        yes
GL fragment program:      yes
GL vertex buffer object:  yes
GL framebuffer object:    yes
GL version is 1.4+:       yes
Unity 3D supported:       no
```

As you can see, "Not software rendered" and "Unity 3D supported" both return "no" in this example, which means Unity is using slow LLVMpipe.

1. Install VirtualBox Oracle VM VirtualBox Extension Pack.

2. Create a VirtualBox instance and install Ubuntu 12.10 on it.

3. Install some required packages for the guest additions:

	```sudo apt-get install linux-headers-$(uname -r) build-essential```
	
4. Install the guest additions by clicking Devices, Install Guest Additions and running this command from the CD-ROM's directory:

	```sudo ./VBoxLinuxAdditions.run```
	
5. Add the vboxvideo driver to the instance by running:

	```sudo bash -c 'echo vboxvideo >> /etc/modules'```

6. Shutdown the VirtualBox instance.
 
7. Open the settings of the Virtualbox instance, navigate to "Display", and tick "Enable 3D acceleration".

8. Boot your Ubuntu 12.10 guest, and check that 3D acceleration is working by running:

	```/usr/lib/nux/unity_support_test -p```
	
Now see the the installation instructions for Ubuntu Linux!
  
# Everybody (Mac and Linux)

# Install Sublime Text

http://www.sublimetext.com/

#Install Markdown Previewer
  
Because we will be using GitHub, many of your homework and agenda files will be in.md format. To view them you will need a markdown viewer.

##Mac Users 

 *	Markdown Preview:		[Mou](http://mouapp.com/) 
	
##Linux Users

*	Open Sublime Text

*	Go to "View" then "Show Console"

*	Copy and paste the following into the white text box at the bottom of sublime.

```import urllib2,os; pf='Package Control.sublime-package'; ipp=sublime.installed_packages_path(); os.makedirs(ipp) if not os.path.exists(ipp) else None; urllib2.install_opener(urllib2.build_opener(urllib2.ProxyHandler())); open(os.path.join(ipp,pf),'wb').write(urllib2.urlopen('http://sublime.wbond.net/'+pf.replace(' ','%20')).read()); print('Please restart Sublime Text to finish installation')```

*	Restart Sublime

*	"cmd+shift+P" and select Package Control: Install Package

*	Click Markdown Preview.

When you want to view rendered markdown, open the file in sublime "cmd+shift+P" and select Markdown Preview. 

# Run Terminal

Finder > Applications > Utilities > Terminal

# Install the 'subl' command line tool for Sublime Text

Mac:

	sudo ln -s "/Applications/Sublime Text 2.app/Contents/SharedSupport/bin/subl" /usr/bin/subl

When it asks you for a password, enter your Mac system password (the one you use when you install apps).

Linux:

(Figure out where you downloaded and unpacked it)

	sudo ln -s "<wherever you installed it>/bin/subl" /usr/local/bin/subl

Test the 'subl' command line tool.

	subl hello.rb
	
You should see your editor pop up. Type 

	puts "Hello world"

And save the file.
	
#Command Prompt

Make your command prompt prettier.

Terminal > Preferences > Settings > Text and Window

Set your terminal background to black, your foreground to light gray, and your bold to white.

Then, in terminal:

	$ subl ~/.bash_profile
	
Paste these lines into the end:

	alias ls='ls -Fc'
	export PS1="\[\e]0;\u@\h \w\a\]\n\[\e[34m\]\u@\h \[\e[33m\]\w\[\e[0m\]\n\$ "

Restart your terminal.

Now your prompt will show you the full current directory, highlighted in color:

	gtolle@Gilmans-MacBook-Air-2 ~/ga-rails
	$ 

#Install Git

##Mac Users 

Commands that look like ```this``` should be entered into your Terminal
application. It can be found in Applications/Utilities.

1.	__Make sure you have an apple ID__ (you should already have one). 

2. __Install Command Line Tools__
	*	[https://developer.apple.com/downloads/index.action](https://developer.apple.com/downloads/index.action)
	* First fill out an Apple Developer Profile - answer the questions as best you can
	* Search for "Command Line Tools" and select the version appropriate for your operating system.
	* If you're still on Snow Leopard (10.6), there's no Command Line Tools for you. Search for "xcode 4.2" and install the full Xcode 4.2 for Snow Leopard. Make sure all the checkboxes are checked in the installer, and it will come with the command line tools.
	* Install the command line tools from the downloaded file.

3. __Install Homebrew__

	* ```ruby -e "$(curl -fsSL https://raw.github.com/Homebrew/homebrew/go/install)"```
	* The install page if you have trouble: [http://mxcl.github.io/homebrew/](http://mxcl.github.io/homebrew/)

4.	__Install git__

	*	```brew update```
	*	```brew install git```

5.	__Configure git with your Name and Email__

  	* [https://help.github.com/articles/setting-your-email-in-git](https://help.github.com/articles/setting-your-email-in-git)
  	* [https://help.github.com/articles/setting-your-username-in-git](https://help.github.com/articles/setting-your-username-in-git)

##Linux Users

1. __Open a terminal window__
	* http://askubuntu.com/questions/196212/how-do-you-open-a-command-line

2. __Install git__
	* ```sudo apt-get install build-essential git-core```
	* Set your git name and email:
    * [https://help.github.com/articles/setting-your-email-in-git]
    * [https://help.github.com/articles/setting-your-username-in-git]

#Connect to GitHub

Sign up for a GitHub account.

Make your SSH keys, using this guide:

https://help.github.com/articles/generating-ssh-keys

Once your keys are all set up.

Try cloning this repository over SSH.

	$ git clone <paste the repo ssh URL here>

#Install the Git-Completion terminal file

	cd ga-rails
	cp .git-completion.sh ~
	
Then:

	subl ~/.bash_profile
	
Add this line:

	source ~/.git-completion.sh

Delete the 'PS1' line and replace it with this:

	export PS1="\[\e]0;\u@\h \w\a\]\n\[\e[34m\]\u@\h \[\e[33m\]\w\[\e[0m\]\$(__git_ps1)\n\$ "

Now quit your terminal and start it again.

Now cd into the ga-rails dir:

	cd ga-rails

You should see:

	gtolle@Gilmans-MacBook-Air-2 ~/ga-rails (master)
	$ 

Whenever you're in a git repository directory, you'll see "(master)" in your prompt. And if you change git branches, you'll see the current branch in parentheses instead of (master).

#Install Ruby

Linux only:

1. __Install curl__
	* ```sudo apt-get install curl```

Everybody:

1.	__Install RVM with Ruby 2.0.0__
  	* ```\curl -sSL https://get.rvm.io | bash -s stable --ruby```
  	* The backslash in font of "curl" is not a typo.

2.	__Restart Your Terminal__

3.	__Make sure the latest versions of RVM and Ruby were installed__
	*	run the commands below:
		*	For RVM
			*	```rvm -v```
				
				You should get rvm 1.0.0 or higher.
		* 	For Ruby

			*	```ruby -v```
			
				You should get ruby 2.0.0p0 or higher.

# Install Rails

1. __Install Rails__
   * ```gem install rails```

2. Create and run a rails app

```
	cd
	rails new myapp
	cd myapp
	rails server
```

In browser: http://localhost:3000

At terminal: Ctrl-C to kill the server
	
3. Delete that rails app

```
	cd ..
	rm -rf myapp
```

(note, I made it up to here in the most recent install session, and didn't have time for the following stuff)

# Install Postgres

https://devcenter.heroku.com/articles/heroku-postgresql#local-setup

# Install Heroku Toolbelt

Sign up for a Heroku account.

Go here to install the Heroku command-line tools:

https://devcenter.heroku.com/

https://devcenter.heroku.com/articles/quickstart

# Create and deploy a rails app on Heroku:

See:

https://devcenter.heroku.com/articles/getting-started-with-rails4

##Happy Coding :)

__You're ready for the first class.__
