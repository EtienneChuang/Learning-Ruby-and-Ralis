<ul>
      <li><a href="#make a workspace">Make a workspace</a></li>
      <li><a href="#create an application">Create an application</a></li>
      <li><a href="#bundle">Bundle</a></li>
</ul>

<h3 id="#mkworkspace">Make a workspace</h3>
For creating an appliation, we should create a workspace to work in.
Use <code>mkdir</code> command to make a new directory if it dosen't exist.<br>
![make workspace](https://lh5.googleusercontent.com/-bq_vHtP7X3A/VEOf8uoGUnI/AAAAAAAACB0/S9bP8zbuT5g/w379-h106-no/workspace.JPG)
<h3 id="#createanapp">Create an application</h3>
Create application using <code>ralis <version> new projectname.app</code> command.
The result will be the following.
<pre>
etiennechuang@rails-tutorial:~/workspace $ rails _4.2.0.beta2_ new hello_app
      create
      create  README.rdoc
      create  Rakefile
      create  config.ru
      create  .gitignore
      .
      .
      .
         run  bundle install
Fetching gem metadata from https://rubygems.org/..........
Resolving dependencies...
Installing rake 10.3.2
Using i18n 0.7.0.beta1
Using json 1.8.1
Using minitest 5.4.2
      .
      .
      .
Your bundle is complete!
Use `bundle show [gemname]` to see where a bundled gem is installed.
Post-install message from rdoc:
Depending on your version of ruby, you may need to install ruby rdoc/ri data:

<= 1.8.6 : unsupported
 = 1.8.7 : gem install rdoc-data; rdoc-data --install
 = 1.9.1 : gem install rdoc-data; rdoc-data --install
>= 1.9.2 : nothing to do! Yay!
         run  bundle exec spring binstub --all
* bin/rake: spring inserted
* bin/rails: spring inserted
</pre>
The file structure of the project<br>
![file structure](https://lh6.googleusercontent.com/-kVp-eZeXDOM/VEOf8qSyURI/AAAAAAAACCA/xqAt8luVIKc/w982-h516-no/workspaceapp.JPG)
<h3 id="#bundle">Bundle</h3>
Bundle is run automatically via <code>bundle install</code> when we create the new app. But now, we're going to <b>make some changes to the default gems</b> and <b>run bundle</b> again.<br/>
Double-click the <i>Gemgile</i> in the diretory and you can see the file like picture below, if you can't see anything, try to click the gear icon on the top right to refresh file tree and then try again.<br>
![gem file] (https://)<br>
Bundle will install the latest version automatically unless we specify a verson number.<br>
There are to common ways to do some control over the version used by Rails.<br>
First one look like this:<br/>
<code>gem 'uglifier', '>= 1.3.0'</code> that means install the latest version of uglifier gem which is greater than or equal to version 1.3.0<br/>
Seconde one may look like this:<br/>
<code>gem 'coffee-rails', '~> 4.0.0'</code> this installs the version which is newer than 4.0.0 but not newer than 4.1.X.<br/>
the <code>~>4.0.0 </code> notation means only install the latest version representing minor point releases.<br>
Then rewrite the Gemfile with exact version as following:<br>
<pre>
source 'https://rubygems.org'


gem 'rails', '4.2.0.beta2'
gem 'sass-rails', '5.0.0.beta1'
gem 'uglifier', '2.5.3'
gem 'coffee-rails', ' 4.0.1'
gem 'jquery-rails', '3.1.2'
gem 'turbolinks', '2.3.0'
gem 'jbuilder', '2.1.3'
gem 'rails-html-sanitizer', '1.0.1'
gem 'sdoc', '0.4.0', group: :doc


group :development, :test do
  gem 'splite3',     '1.3.9'
  gem 'byebug',      '3.4.0'
  gem 'web-console', '2.0.0.beta3'
  gem 'spring',      '1.1.3'
end
</pre>
Once we have done above, install the gems using <code>bundle install</code>
It maybe take few moments.
<pre>
etiennechuang@rails-tutorial:~/workspace/hello_app $ bundle install
Fetching gem metadata from https://rubygems.org/..........
.
.
.
Using uglifier 2.5.3
Installing web-console 2.0.0.beta3 (was 2.0.0.beta4)
Your bundle is complete!
Use `bundle show [gemname]` to see where a bundled gem is installed.
</pre>
