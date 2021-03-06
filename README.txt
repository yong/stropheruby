== OVERVIEW

Stropheruby is a ruby bindings for Strophe, a C library for writing XMPP clients.

This is a fork of flamontagne's stropheruby (http://github.com/flamontagne/stropheruby/tree/master) with the following improvements:

* A patched version of libstrophe (trunk) is included. So there is no extra library to install. 
* (libstrophe) Fixed a timeout issue on Mac OSX: http://groups.google.com/group/strophe-dev/browse_thread/thread/ef4cb19785020fb6
* (libstrophe) Fixed basic auth: http://groups.google.com/group/strophe-dev/browse_thread/thread/b770f72c83d1a0b9
* (libstrophe) Changed xmpp_run_once's return code so that the application can tell if an error or timeout occurs
* (libstrophe) Better error reporting for login failure
* (libstrophe) If no password given, do not login. This will give 'register' a chance to run 
* (stropheruby) Added send_raw_string method
* (stropheruby) Detect login failure
* (stropheruby) Fixed a resource leak
* (stropheruby) Added wrapper class for xmpp_stream_error_t (StropheRuby::StreamError)

== INSTALLATION

sudo gem sources -a http://gems.github.com
sudo gem install yong-stropheruby

For Rails app, add this line in your config/environment.rb:
config.gem "yong-stropheruby", :source => "http://gems.github.com", :lib => "strophe_ruby"

== EXAMPLE

See examples/xmpp_client.rb
