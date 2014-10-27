<ul>
      <li><a href="#make-a-workspace">Make a workspace</a></li>
      <li><a href="#create-an-application">Create an application</a></li>
      <li><a href="#bundle">Bundle</a></li>
      <li><a href="#rails-server">Rails server</a></li>
      <li><a href="#model-view-controllermvc">Model-View-Controller(MVC)</a></li>
</ul>

<h3 id="#make-a-workspace">Make a workspace</h3>
For creating an appliation, we should create a workspace to work in.
Use <code>mkdir</code> command to make a new directory if it dosen't exist.<br>
![make workspace](https://lh5.googleusercontent.com/-bq_vHtP7X3A/VEOf8uoGUnI/AAAAAAAACB0/S9bP8zbuT5g/w379-h106-no/workspace.JPG)
<h3 id="#create-an-application">Create an application</h3>
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
![gem file](https://lh4.googleusercontent.com/-psNAVEnPFBk/VEiLKZnLisI/AAAAAAAACDc/q--_hvPYs-Y/w981-h479-no/gemfile.JPG)<br>
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
<h3 id="rails-server">Rails server</h3>
After finishing installing above, now we have app which can run, now, all we need is server.<br>
To run a server, use <code>rails server</code>, this is for using on localhost, whereas, on Cloud9, we should add two arguments: <i>IP</i> and <i>PORT</i>, these value can be fetched by using environment variables: <i><b>$IP</b></i> and <i><b>$PORT</b></i>. We should open a new terminal to run the server so that we can still issue command in first terminal.
When running server successfully, we can see the result like below:<br>
![server](https://lh4.googleusercontent.com/-y9nBGn5GQnI/VEiKfUsSz0I/AAAAAAAACCs/n7ktGJTtLmg/w981-h171-no/server.JPG)
Then what should we do to go into the application? type <a href="#">http://localhost:3000/</a> on browser URL bar; on Cloud9 IDE, we should go to <i>Share</i> and copy the URL of the application that Cloud9 provides,<br>
![share](https://lh4.googleusercontent.com/-BAOUheq1_ts/VEiL7tjvd6I/AAAAAAAACD4/0F2aolBgct8/w939-h593-no/share.JPG)
and then put it on browser URL bar,we will get a page like below:
![page](https://lh3.googleusercontent.com/-60HA6xVcrqo/VEiKfrVYVlI/AAAAAAAACC0/-Cku3NxBq1E/w982-h451-no/page.JPG)
To see infomation about the environment, click the link <i>"about your application environment"</i>.
![info](https://lh5.googleusercontent.com/--P0nCUY3DYY/VEiKfgSsOHI/AAAAAAAACCw/YysFhGrTI04/w982-h497-no/info.JPG)

<h3 id="Model-View-Controller-MVC-">Model-View-Controller(MVC)</h3>
![mvc](https://softcover.s3.amazonaws.com/636/ruby_on_rails_tutorial_3rd_edition/images/figures/mvc_schematic.png)<br>
"<i>I think a web server diagram should be added between browser and controller.</i>"<br>
How it works?<br>
-<b>browser</b> send a request to <b>web server</b><br>
-<b>web server</b> render the request then send to <b>controller</b><br>
-according to the request, the <b>controller</b> will receive a view which is the converted HTML page to send back to <b>browser</b>.<br>
-for dynamic sites, <b>controlle</b>r also interacts with <b>model</b> and communicates with the database, after that, <b>controller</b> send back the complete page to <b>browser</b><br>
