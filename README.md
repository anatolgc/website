# Lessons learned (the knowledge gained from the exercizes)

1. Using git clean to remove subdirectories containing git repositories
I cloned a repository into a directory which was inside another repository. Here’s what I did:
~~~~
$ cd ~/website // this is my main repository
$ mkdir tmp 
$ cd tmp
$ git clone git@github.com:anatosiek/website.git //that led to cloning a repository in subdirectory - tmp/website
~~~~
Then I realized, that exercise task was slightly differrent, so I decided to delete nested repository. I tried:
~~~~
git rm -r tmp // failed
git checkout // failed
~~~~
Then I found [*Major Hayden blog post*](https://major.io/2012/10/24/using-git-clean-to-remove-subdirectories-containing-git-repositories/) and discovered new git clean option: -ff. Befour I was using git clean -fd, which wasn't forcing enough to delete. Double f '-ff' helped and I go rid of tmp/website folders.

Problem was, that I accidentaly created 'submodule' with nested repository. The topic complitly unknown to me at that time.



2. This is a sample website made as part of [*Learn EnoughTM Git to Be Dangerous*](http://learnenough.com/git-tutorial), possibly the greatest beginner Git tutorial in the history of the Universe. You should totally [ check it out](http://learnenough.com/git-tutorial), and be sure to [join the email list](http://learnenough.com/#email_list) and [follow @learnenough ](http://twitter.com/learnenough) on Twitter.

After finishing *Learn Enough™ Git to Be Dangerous*, you'll know enough Git to be *dangerous*. This means you'll be able to use Git to track changes in your projects, back up data, share your work with others, and collaborate with programmers and other users of Git.

For more information on Git, see the
[official Git documentation](https://git-scm.com/).