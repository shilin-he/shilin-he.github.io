---
layout: post
title:  "Build bootstrap3 and run documentation locally on Windows"
date:   2013-06-21 11:03:31
categories: bootstrap jekyll make
---

### Get and build bootstrap3:
1. Run> git clone https://github.com/twitter/bootstrap.git
2. Run> git branch --track 3.0.0-wip origin/3.0.0-wip
3. Run> git checkout 3.0.0-wip
4. Run> npm install  
        
The above command will install required node packages in the current folder. 
If something goes wrong, run the following commands to clean up then run the 
above command again:
    * npm uninstall uglify-js jshint recess connect
    * npm uninstall -g uglify-js jshint recess connect

5. Install [make for windows][make-win], add the path of make.exe to the path
environment 
6. Build and make a copy of bootstrap 3 into a sub-folder default to bootstrap, 
run the following command in git bash (it won't work in windows command prompt): 

    > make bootstrap

### Running documentation locally:
1. [Install Jekyll on Windows][jekyll-win]:
    * Requires Ruby(1.9.3, won't work on 2.0), Python, [Pygments][pygments]
    * Install [ruby development kit][ruby-dk] and run the following commands:
     - Run> dk.rb init
     - Run> dk.rb install
    * Run> gem install jekyll
2. Run the following command in bootstrap folder:

    > jekyll serve

3. Go to http://localhost:9001 to browse the documentation

*All commands run in the Windows command prompt unless specified.*

[make-win]: http://gnuwin32.sourceforge.net/packages/make.htm
[jekyll-win]: http://www.madhur.co.in/blog/2011/09/01/runningjekyllwindows.html
[ruby-dk]: http://rubyinstaller.org/downloads/
[pygments]: http://pygments.org/
