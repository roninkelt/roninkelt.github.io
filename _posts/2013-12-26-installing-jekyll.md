---
layout: post
category : lessons
tagline: "Supporting tagline"
tags : [intro, beginner, jekyll, tutorial]
---
{% include JB/setup %}
## Installation

these are the steps I used to set up this blog to use ruby and jekyll.

###Step 1: Install Ruby

 As of the time of this writing Ruby 1.9.3 is recommended for Windows 

1. Download and install the ruby installer from http://rubyinstaller.org/downloads/.
2. If you don't use the default directory, be sure to not have any spaces in install directory. I used c:\bin\Ruby193.

3. Select the Add Ruby executables to your PATH checkbox, so your windows PATH will be updated automatically.

3. Test that installation was successful.

        > ruby --version

###Step 2: Install Ruby Dev Kit
1. Download and install ruby dev kit from http://rubyinstaller.org/downloads/.
2. Unpack ruby dev kit installer (as before no spaces in the path - c:\bin\Ruby193-DevKit).
3. Add the dev kit, dev kit bin and dev kit mingw bin to your path - C:\bin\Ruby193-DevKit; c:\bin\Ruby193-DevKit\bin; c:\bin\Ruby193-DevKit\mingw\bin
4. Initialize Dev Kit

        > ruby dk.rb init

        [INFO] found RubyInstaller v2.0.0 at C:\bin\Ruby193

Initialization complete! Please review and modify the auto-generated
'config.yml' file to ensure it contains the root directories to all
of the installed Rubies you want enhanced by the DevKit.

5. Install Ruby Dev Kit

        > ruby dk.rb install

        [INFO] Updating convenience notice gem override for 'C:\Ruby200-x64'
        [INFO] Installing 'C:\Ruby200-x64/lib/ruby/site_ruby/devkit.rb'

###Step 3: Install Jekyll gem

        >gem install jekyll --platform=ruby

###Step 4: Install rdiscount gem for markdown processing

        >gem install rdiscount --platform=ruby

###Step 5: Install Python

If you are going to use pygments for code highlighting, then you need to  install a compatible version of python. I used a portable version found here - http://portablepython.com/wiki/PortablePython2.7.5.1/

Once again I put it in C:\bin with no spaces in the path

1. Add c:\bin\Python275\App to the path

2. test python to see if it is properly installed.

        >python --version

###Step 6: Install Easy Install

1 Get the setup tool - https://pypi.python.org/pypi/setuptools#windows.
2. Run the setup file from the directory you downloaded it to.

        > python ez_setup.py

3. Add C:\bin\Python275\App\Scripts to your PATH.

4. Test easy_install to see if it is working

        >easy_install --help

###Step 7: Install Pygments

        > easy_install Pygments

5 you will likely get too new a version of pygments (it has to be 0.5.0 currently)

        >gem uninstall pygments.rb

        >gem install pygments.rb --version "=0.5.0" --platform=ruby

###Step 8: initialize and start Jekyll 

        >jekyll new c:\path\to\site

        >chdir c:\path\to\site

        >jekyll serve --watch

That should do the trick. Now you are ready to go.  
Open http://localhost:4000/ to see your site.

I use ampps (http://www.ampps.com/) to do my local full stack development on so if you decide to do it that way just add a link from your ampps www directory to the _site directory of your just created project. 

        >mklink /D c:\Users\Public\Documents\www c:\Path\to\site\_site




## Next Steps

Please take a look at [{{ site.categories.api.first.title }}]({{ BASE_PATH }}{{ site.categories.api.first.url }})
or jump right into [Usage]({{ BASE_PATH }}{{ site.categories.usage.first.url }}) if you'd like.
