Rag, a project helper
=====================

**Homepage**: [https://github.com/GutenYe/rag](https://github.com/GutenYe/rag) <br/>
**Author**:	Guten <br/>
**License**: MIT-LICENSE <br/>
**Documentation**: [http://rubydoc.info/gems/rag/frames](http://rubydoc.info/gems/rag/frames) <br/>
**Issue Tracker**: [https://github.com/GutenYe/rag/issues](https://github.com/GutenYe/rag/issues) <br/>

Overview
--------

a project helper, include create, develop, test, release.

depends Gemfile.

Usage
-----

	rag new # when first time run. create ~/.ragrc file, edit this file, than goto next step
	rag new foo # create a foo project in current directory

	rag new -l # list templates

	rag -T # list tasks

	rag release # build gem and push to Ruygems


Features
--------

* easy to extend.
* use thor as default task DSL.
* with vim support. see resources 

Configuration
-------------

there are two places you can set up settings, ~/.ragrc, APP/.ragrc

.ragrc # a yaml file

	author: foo
	email: foo@bar.com

Extension
---------
 
you can write your own task in Ragfile, APP/tasks/\*.rag

	class Rag < Thor
		desc "hello", "it says hello"
		def hello
			puts 'hello'
		end
	end

or you can write a plugin.
	
lib/rag/foo.rb
	
	class Rag < Thor
		...
	end

in Ragfile

	require 'rag/foo'

available variable for writing extension. they are read from .gemspec file

	Rc.o.project  # project name
	Rc.o.version


Template
--------

from system-level: GEM(rag)/template and user-level: ~/.rag/template

template/foo/a.erb

	<%=project%>

local variables in erb file are from ~/.ragrc and APP/.ragrc

default template see {file:template/default.readme}

Contributing
-------------

* report bugs/featues to issue tracker.
* fork it and pull a request.
* improve documentation.
* feel free to post any ideas. 

Install
----------

	gem install --no-wrappers rag
	gem update --no-wrappers rag

or you can write `gem: --no-wrappers` into ~/.gemrc file, then

	gem install rag
	gem update rag

Resources
---------

* [gem.vim](https://github.com/GutenYe/gem.vim): a project helper for ruby gem/library development
* [Hoe](https://github.com/seattlerb/hoe): a rake/rubygems helper for project


Copyright
---------
Copyright &copy; 2011 by Guten. this library released under MIT-LICENSE, See {file:LICENSE} for futher details.
