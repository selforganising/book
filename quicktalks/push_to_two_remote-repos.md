#How do you push to github and Heroku at the same time?#

##Where we're all at right now

We're all used to dealing with GitHub by now. And we've just learned about the wonders of Heroku.

But with the introduction of Heroku we have encountered a new issue. We are now using a second remote git repositry. Wacky hey?

If you're doing things right you should push your changes both to:

Heroku (to create your server)

and

GitHub (so you can work on your files with other people).

    "What?! So I have to git push to heroku and GitHub every time I make a significant change? That will take forever!"

##Well I have a solution for you!

Believe it or not - we're going to get a stage where we can push to both with one simple command.

##Going under the hood

Let's take a look into our .git/config to get a better understanding of what's going on "under the hood".

You may have something that looks like this:

    [core]
    	repositoryformatversion = 0
    	filemode = true
    	bare = false
    	logallrefupdates = true
    [remote "heroku"]
    	url = git@heroku.com:serene-escarpment-2761.git
    	fetch = +refs/heads/*:refs/remotes/heroku/*
    [remote "origin"]
    	url = git@github.com:imbenclifford/her-OH.git
    	fetch = +refs/heads/*:refs/remotes/origin/*

This means that when you perform a "git push heroku" it will push to your heroku server and when you perform a "git push origin" it will push to your github.

Complicated hey?

##So how do we make it simpler?

Well, all we have to do is edit this config a bit. What about if we made it look like this:

    [core]
    	repositoryformatversion = 0
    	filemode = true
    	bare = false
    	logallrefupdates = true
    [remote "heroku"]
    	url = git@heroku.com:serene-escarpment-2761.git
    	fetch = +refs/heads/*:refs/remotes/heroku/*
    [remote "github"]
    	url = git@github.com:imbenclifford/her-OH.git
    	fetch = +refs/heads/*:refs/remotes/origin/*
    [remote "origin"]
    	url = git@github.com:imbenclifford/her-OH.git
    	url = git@heroku.com:serene-escarpment-2761.git

We now have the same options as before but we can now push both with one simple command:
"git push origin"!

Take a look inside your git config and have a go yourself!

###References:
http://maxburstein.com/blog/push-to-multiple-git-repos/
