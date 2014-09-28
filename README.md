## Purpose ##
This repository is the basic Middleman repository used by me for static site
generation.  Feel free to use for your own purposes; this is an experiment for
me.  I make no promise as to usability or frequency of updates, but I do welcome
comments, helpful criticism, and encouragement.

***

## Setup procedure ##

### Prerequisites ###

Ubuntu 14.04 is installed with appropriate developer tools.
- Ruby
  - RVM with rvmrc support
- Sublime Text
- Git
  - Hashrocket dotmatrix configuration
- Git Flow
- NodeJS
- Node Package Manager (NPM)
- Bower
- Chrome
- Firefox
  - Firebug plugin
- Middleman
- Foundation

***

### Procedure ###

Follow the steps in the procedure below to duplicate this repository, or, just `git clone git@github.com:SRozick/middleman-foundation-min.git`, `$ bundle install`, `bundle update`.
  *NOTE:*  The Zurb Foundation license, which is part of the initial README, is required to be maintained with the project files and any distributions.  Handle accordingly.
  1. Create remote project repository (on github.com)
  1. `$ middleman init <project_name> --template=zurb-foundation (* see Middleman Foundation)`
  1. `$ cd <project_name>`
  1. `$ rvm use <ruby_ver>@<project_name> --create` (so, rvm use 2.1.2@my_new_project --create)
  1. `$ bundle install` (since we changed gemsets)
  1. `$ bower install`
  1. `$ git init`
  1. `$ subl .gitignore`
  1. Edit and save .gitignore file to meet project requirements
  1. `$ subl README.md`
  1. Edit and save README.md to meet project requirements.
  1. `$ mkdir source/images`
    OR, edit config.rb (approx lines 13 and 87) to locate image assets.
  1. `$ git remote add origin git@github.com:<git-username>/<remote_repo_name>.git`
  1. `$ git add .`
  1. `$ git commit -m "Initial commit"`
  1. `$ git push -u origin master`

***

### Notes ###

My notes on various packages and issues follow.

#### Gotchas ####

- Using capital letters in a project name can cause the livereload feature of Middleman to fail.  This appears to be a factor of the operating system(s) involved.
  - Once this bug occurs, the only way to correct it is to push the project to a remote repository, delete the project folder, and re-clone the project into a new folder.
- Chrome has occasionally exhibited odd behavior when the Element inspector is open.  Specifically, some CSS rules stop applying normally, and Livereload may also exhibit issues.
  - Simple to solve: close the element inspector.  Behavior with the element inspector closed will be correct; behavior with the element inspector open will revert to buggy behavior.  I find it useful, when using Chrome, to keep a separate window open and NO element inspector open, whenever possible.
- Be careful about CSS class names when using Foundation and Normalizr.  Like other CSS frameworks, using reserved classnames can create unexpected behavior.
  - Foundation's classnames are in `~</project/folder>/source/bower_components/foundation/css/foundation.css`
  - Normalizr is a javascript that adds a group of classes to the html tag.  Classnames can be found by using the inspector on an active page and looking at the html tag classes.

#### Middleman ####

Middleman is a static site generator for use with Ruby based applications.

Middleman sets up a static site framework and manages the development environment to simplify site deployment.

Middleman requires bower and npm to function properly (prerequisites).
Middleman will also load a host of gems to support its other functions.
Middleman's greatest advantages are its parallel structure to Rails and Sinatra (making future site upgrades easier, and lowering the slope of the learning curve for those who may be new to Ruby-based web development), the inclusion of a number of useful gems upon deployment, the ability to manage installed gems with a Gemfile, templates, and package management.

A few interesting features worth checking at setup:
- Project templates

  > You can create your own custom project skeletons by creating folders in the
  > ~/.middleman/ folder. For example, I can create a folder at ~/.middleman/mobile/
  > and fill it with files I intend to use on mobile projects.
   \-\- [Middleman documentation](http://middlemanapp.com/basics/gettingstarted "Middleman Documentation")

- Skeleton settings

  See config.rb in the Source folder of a new project.  Some useful options: configuration of standard CSS, Javascript, and image storage locations, blog mode, minifying css and javascript files on deploy, and run-time server deployments (for the advanced user).
- Livereload

  By default, all projects include the livereload gem.  This means that as you save changes to the active project folders, any open browser window will automatically refresh your site.
  Note that on some case-sensitive operating systems (notably, on Macs), using capital letters in the project name can cause issues with Livereload; this is a factor of the way those OS interpret file names.

***

### Conventions ###

The following conventions are used in this procedure:
- Text contained within '<' and '>' should be adjusted for each environment and project.
- Text preceded by '$' indicates a command to be entered at the terminal prompt.
- Terminal output is not normally provided; where this is a potential issue, terminal output is provided `as cli text`.
- Text preceded by `<application>#` indicates text to be entered at the appropriate application prompt.

***

## ZURB Foundation License ##

Copyright (c) 2011 ZURB, http://www.zurb.com/

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
"Software"), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE
LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION
OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION
WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
