The Design Aumtomation website:
http://design-automation.net/


To setup, follow the instructions here:

    https://help.github.com/articles/setting-up-your-github-pages-site-locally-with-jekyll/

To run locally, open git bash in the root folder, and execute the following:

    bundle exec jekyll serve

You may get the message, " No GitHub API authentication could be found." This can be ignored.

If you get the message, "bundle: command not found", then check the path.

----

Note all file names and extensions must be lower-case. If you have committed files with upper-case extensions, then you need to do teh following:

git config core.ignorecase false
git add .
git commit -m"change file extensions"
git push
