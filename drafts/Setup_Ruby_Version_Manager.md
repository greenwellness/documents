
# Opzetten van Jekyll

## Benodigdheden development machine

* C-compiler (gebruikt: `clang` want `gcc` werkte niet meer)
* Ruby Version Manager (zeer gewenst)

## Procedure

### RVM

```sh
DevBox :: ~ » curl -sSL https://get.rvm.io | bash -s stable
Downloading https://github.com/wayneeseguin/rvm/archive/stable.tar.gz
Installing RVM to /home/username/.rvm/
    RVM PATH line found in /home/username/.bashrc.
    RVM PATH line not found for Zsh, run the installer with '--auto-dotfiles' to fix it.
    RVM sourcing line found in /home/username/.bash_profile /home/username/.zprofile /home/username/.zshrc.
Installation of RVM in /home/username/.rvm/ is almost complete:

  * To start using RVM you need to run `source /home/username/.rvm/scripts/rvm`
    in all your open shell windows, in rare cases you need to reopen all shell windows.

# username,
#
#   Thank you for using RVM!
#   We sincerely hope that RVM helps to make your life easier and more enjoyable!!!
#
# ~Wayne, Michal & team.

In case of problems: http://rvm.io/help and https://twitter.com/rvm_io
/home/username/.zshrc:132:export PATH=/var/tmp/bin:/usr/bin:/usr/local/bin:/bin:/usr/local/sbin:/usr/sbin:/sbin

  * WARNING: Above files contains `PATH=` with no `$PATH` inside, this can break RVM,
    for details check https://github.com/wayneeseguin/rvm/issues/1351#issuecomment-10939525
    to avoid this warning append #PATH.

  * WARNING: Found --user-install in /etc/gemrc, please remove it, as it will break rubygems in RVM.
    If it is intended or a mistake 'export rvm_ignore_gemrc_issues=1' to avoid this warning.
```

Merk op dat we 2 foutmeldingen / waarschuwingen krijgen. Deze zijn verholpen door:

1. `DevBox :: ~ » vim /home/username/.zshrc +132` toevoegen van `:${PATH}` op het einde van `export PATH=/var/tmp/bin:/usr/bin:/usr/local/bin:/bin:/usr/local/sbin:/usr/sbin:/sbin:${PATH}` in het bestand `~/.zshrc`
2. `DevBox :: ~ » sudo -rm /etc/gemrc`

We zien dat er daarnaast nog een andere melding is nl. die van `--auto-dotfiles`.

We proberen RVM te gebruiken:

#### `rvm install --auto-dotfiles`
*Can not use or install 'all' rubies.* Noot dat er een versienummer ontbreekt.

#### `rvm install --auto-dotfiles 1.9.3`
*Error running './configure --prefix=...* Er is iets mis met mijn `gcc` C-compiler en dus schakel ik over op een expliciete verwijzing: `rvm install --auto-dotfiles 1.9.3 --with-gcc=clang`

```sh
ruby-1.9.3-p484 - #removing src.
Checking requirements for arch.
Requirements installation successful.
Installing Ruby from source to: /home/username/.rvm/rubies/ruby-1.9.3-p484, this may take a while depending on your cpu(s)...
ruby-1.9.3-p484 - #downloading ruby-1.9.3-p484, this may take a while depending on your connection...
ruby-1.9.3-p484 - #extracting ruby-1.9.3-p484 to /home/username/.rvm/src/ruby-1.9.3-p484.
ruby-1.9.3-p484 - #applying patch /home/username/.rvm/patches/ruby/GH-488.patch.
ruby-1.9.3-p484 - #configuring.............................................
ruby-1.9.3-p484 - #post-configuration.
ruby-1.9.3-p484 - #compiling..............................................................................................................................................................
ruby-1.9.3-p484 - #installing........................
ruby-1.9.3-p484 - #making binaries executable.
ruby-1.9.3-p484 - #downloading rubygems-2.2.1
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  401k  100  401k    0     0   961k      0 --:--:-- --:--:-- --:--:--  962k
No checksum for downloaded archive, recording checksum in user configuration.
ruby-1.9.3-p484 - #extracting rubygems-2.2.1.
ruby-1.9.3-p484 - #removing old rubygems.
ruby-1.9.3-p484 - #installing rubygems-2.2.1............
ruby-1.9.3-p484 - #gemset created /home/username/.rvm/gems/ruby-1.9.3-p484@global
ruby-1.9.3-p484 - #importing gemset /home/username/.rvm/gemsets/global.gems......
ruby-1.9.3-p484 - #generating global wrappers.
ruby-1.9.3-p484 - #gemset created /home/username/.rvm/gems/ruby-1.9.3-p484
ruby-1.9.3-p484 - #importing gemsetfile /home/username/.rvm/gemsets/default.gems evaluated to empty gem list
ruby-1.9.3-p484 - #generating default wrappers.
ruby-1.9.3-p484 - #adjusting #shebangs for (gem irb erb ri rdoc testrb rake).
Install of ruby-1.9.3-p484 - #complete 
WARNING: Please be aware that you just installed a ruby that is no longer maintained, for a list of maintained rubies visit:

    http://bugs.ruby-lang.org/projects/ruby/wiki/ReleaseEngineering

Please consider upgrading to ruby-2.1.0 which will have all of the latest security patches.
Ruby was built without documentation, to build it run: rvm docs generate-ri
```

Laten we even kijken welke versie we nu actief hebben met `rvm list`

```sh
rvm rubies 

  ruby-1.9.3-p484 [ x86_64 ]
```


``` sh
DevBox :: ~ » rvm use ruby-1.9.3-p484@base --default

RVM is not a function, selecting rubies with 'rvm use ...' will not work.

You need to change your terminal emulator preferences to allow login shell.
Sometimes it is required to use `/bin/bash --login` as the command.
Please visit https://rvm.io/integration/gnome-terminal/ for a example.

DevBox :: ~ » su - $USER                                 
```

#### Finally

We maken hier gelijk een nieuwe basis gemset aan door de switches `--create` en `--default` plus de toevoeging `@base`.

``` sh
DevBox :: ~ » rvm use ruby-1.9.3-p484@base --default --create                                       

ruby-1.9.3-p484 - #gemset created /home/baal/.rvm/gems/ruby-1.9.3-p484@base
ruby-1.9.3-p484 - #generating base wrappers - please wait
Using /home/baal/.rvm/gems/ruby-1.9.3-p484 with gemset base

```



