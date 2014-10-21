---
layout: post
title: Compile Ruby on PP64 (Power 8 Runabove)
---

	wget http://cache.ruby-lang.org/pub/ruby/2.1/ruby-2.1.3.tar.gz

	tar -zxvf ruby-2.1.3.tar.gz

	cd ruby-2.1.3/

	# With time set in front of the command
	./configure
	real	1m2.496s
	user	0m16.961s
	sys	0m9.041s

	make -j176
	Generating RI format into /home/amonier/compil_ruby_test/ruby-2.1.3/.ext/rdoc...

	  Files:        962

	  Classes:     1414 ( 566 undocumented)
	  Modules:      268 (  87 undocumented)
	  Constants:   2098 ( 624 undocumented)
	  Attributes:  1146 ( 272 undocumented)
	  Methods:    10651 (2228 undocumented)
	
	  Total:      15577 (3777 undocumented)
	   75.75% documented

	  Elapsed: 118.9s


	real	2m56.221s
	user	6m46.162s
	sys	0m18.853s

	sudo make -j176 install
	./miniruby -I./lib -I. -I.ext/common  ./tool/runruby.rb --extout=.ext  -- --disable-gems -r./powerpc64-linux-fake ./tool/rbinstall.rb --make="make" --dest-dir="" --extout=".ext" --mflags="" --make-flags=" --jobserver-fds=4,5 -j" --data-mode=0644 --prog-mode=0755 --installed-list .installed.list --mantype="doc" --install=all --rdoc-output=".ext/rdoc"
	installing binary commands:   /usr/local/bin
	installing base libraries:    /usr/local/lib
	installing arch files:        /usr/local/lib/ruby/2.1.0/powerpc64-linux
	installing pkgconfig data:    /usr/local/lib/pkgconfig
	installing command scripts:   /usr/local/bin
	installing library scripts:   /usr/local/lib/ruby/2.1.0
	installing common headers:    /usr/local/include/ruby-2.1.0
	installing manpages:          /usr/local/share/man/man1
	installing extension objects: /usr/local/lib/ruby/2.1.0/powerpc64-linux
	installing extension objects: /usr/local/lib/ruby/site_ruby/2.1.0/powerpc64-linux
	installing extension objects: /usr/local/lib/ruby/vendor_ruby/2.1.0/powerpc64-linux
	installing extension headers: /usr/local/include/ruby-2.1.0/powerpc64-linux
	installing extension scripts: /usr/local/lib/ruby/2.1.0
	installing extension scripts: /usr/local/lib/ruby/site_ruby/2.1.0
	installing extension scripts: /usr/local/lib/ruby/vendor_ruby/2.1.0
	installing extension headers: /usr/local/include/ruby-2.1.0/ruby
	installing default gems:      /usr/local/lib/ruby/gems/2.1.0 (build_info, cache, doc, extensions, gems, specifications)
	                              bigdecimal 1.2.4
	                              io-console 0.4.2
	                              json 1.8.1
	                              minitest 4.7.5
	                              psych 2.0.5
	                              rake 10.1.0
	                              rdoc 4.1.0
	                              test-unit 2.1.3.0
	installing rdoc:              /usr/local/share/ri/2.1.0/system
	installing capi-docs:         /usr/local/share/doc/ruby

	real	0m16.498s
	user	0m10.557s
	sys	0m3.500s


	ruby -v
	ruby 2.1.3p242 (2014-09-19 revision 47630) [powerpc64-linux]



---
