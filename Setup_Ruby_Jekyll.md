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


