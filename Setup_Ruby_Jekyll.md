https://help.github.com/articles/using-jekyll-with-pages

Na instellen RVM:

1. » `gem i bundler`
``` sh
Fetching: bundler-1.5.2.gem (100%)
Successfully installed bundler-1.5.2
Installing ri documentation for bundler-1.5.2
1 gem installed
```

1. » `gem i rake --no-rdoc -no-ri`
``` sh
Fetching: rake-10.1.1.gem (100%)
Successfully installed rake-10.1.1
Installing ri documentation for rake-10.1.1
1 gem installed
```

1. » `gem i ffi -v '1.9.3'`
``` sh
Fetching: ffi-1.9.3.gem (100%)
Building **native extensions**.  This could take a while...
Successfully installed ffi-1.9.3
(... truncated output)
Installing ri documentation for ffi-1.9.3
1 gem installed
```

Maak je map aan en verplaats er je `pwd` naartoe. Dan kun je het volgende commando gebruiken om de gewenste Gemfile aan te maken:

```sh
cat <<EOF > Gemfile
source 'https://rubygems.org'
gem 'github-pages'
EOF
```

Finally:


<small>~/ghpages <font color="brown">‹master›</font></small> **»** *bundle*

```sh
Fetching gem metadata from https://rubygems.org/.........
Fetching additional metadata from https://rubygems.org/..
Resolving dependencies...
Installing RedCloth (4.2.9)
Installing blankslate (2.1.2.4)
Installing fast-stemmer (1.0.2)
Installing classifier (1.3.4)
Installing colorator (0.1)
Installing highline (1.6.20)
Installing commander (4.1.5)
Using ffi (1.9.3)
Installing liquid (2.5.5)
Installing rb-fsevent (0.9.4)
Installing rb-inotify (0.9.3)
Installing rb-kqueue (0.2.0)
Installing listen (1.3.1)
Installing maruku (0.7.0)
Installing posix-spawn (0.3.8)
Installing yajl-ruby (1.1.0)
Installing pygments.rb (0.5.4)
Installing redcarpet (2.3.0)
Installing safe_yaml (0.9.7)
Installing parslet (1.5.0)
Installing toml (0.1.0)
Installing jekyll (1.4.3)
Installing kramdown (1.3.1)
Installing rdiscount (2.1.7)
Installing github-pages (14)
Using bundler (1.5.2)
Your bundle is complete!
Use `bundle show [gemname]` to see where a bundled gem is installed.
```


