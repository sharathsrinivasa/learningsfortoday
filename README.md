# learningsfortoday


### Change the author/email of already committed commit
git commit --amend --author="Author Name <email@address.com>" --no-edit

### Point to a local brew formula
brew install --build-from-source ./fooBar.rb

### Multiple SSH Keys settings for different github account

create different ssh key according the article [Mac Set-Up Git](http://help.github.com/mac-set-up-git/)

	$ ssh-keygen -t rsa -C "your_email@youremail.com"

Please refer to [github ssh issues](http://help.github.com/ssh-issues/) for common problems.

for example, 2 keys created at:

	~/.ssh/id_rsa_foo
	~/.ssh/id_rsa_bar

then, add these two keys as following

	$ ssh-add ~/.ssh/id_rsa_foo
	$ ssh-add ~/.ssh/id_rsa_bar
  
you can delete all cached keys before

	$ ssh-add -D

finally, you can check your saved keys

	$ ssh-add -l

Modify the ssh config
---------------------------------

	$ cd ~/.ssh/
	$ touch config
	$ subl -a config

Then added

	#activehacker account
	Host github.com-foo
		HostName github.com
		User git
		IdentityFile ~/.ssh/id_rsa_foo

	#jexchan account
	Host github.com-bar
		HostName github.com
		User git
		IdentityFile ~/.ssh/id_rsa_bar


Useful git config commands

	$ git config user.name "fooBar"
	$ git config user.email "fooBar@gmail.com" 
 
or you can have global git config
	$ git config --global user.name "fooBar"
	$ git config --global user.email "fooBar@gmail.com"


then use normal flow to push your code

	$ git add .
	$ git commit -m "your comments"
	$ git push

