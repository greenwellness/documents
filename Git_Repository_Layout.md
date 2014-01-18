* Momenteel zijn er meerdere repos en users in gebruik, het doel is dit uiteindelijk uniform te verdelen tot het noodzakelijke.

* In verband met problemen met de site en de backup hiervan, is deze strategie opgesteld voor de live omgeving.

* Er zijn een aantal fail-safes ingebouwd waardoor het mogelijk is om praktisch zonder tijdverlies terug te gaan tot eerdere momenten in de boom.

* Door de werking van git en magento samen, vereist dit wel enige toelichting.


### BitBucket `wellbon`

Voor de live productie code is een account gemaakt bij BitBucket. Dit omdat er sprake is van een online productieomgeving waarin betalingen plaatsvinden en dat er configuratiebestanden zijn met gevoelige gegevens zoals wachtwoorden van de database, is het **strict noodzakelijk** een *private repository* te hebben. Aangezien de meest gebruikte aanbieder in de development wereld, GitHub, alleen open-source repositories gratis aanbiedt, en derhalve de bestanden door de hele wereld in te zien zijn, is gekozen voor Bitbucket.org (BB).

BitBucket, BB, ondersteunt namelijk wel - in tegenstelling tot GitHub (GH) - well een gratis private repository. Slechts 1 stuk maar dat is voor ons voldoende omdat de technologie van `git` het mogelijk maakt een complexe boom van samenhangende (branch) takken of deze seperaat van de boom (orphan) aan kan maken. Daarnaast zijn er nog een soort bookmarks (tags) aan te maken om snel in bomen te kunnen springen.

Voor de indeling van deze repository is gekozen gebruik te maken van het programma `git-flow` welke de strategie volgt die uitgewerkt is in het blogbericht [A successful Git branching model][gitflow] van <http://nvie.com>.

```sh
wellnessbon.nl@ssh1.c60 ~ $ git-flow init
Initialized empty Git repository in /home/users/wellvftp/.git/
No branches exist yet. Base branches must be created now.
Branch name for production releases: [master]     
Branch name for "next release" development: [develop] 

How to name your supporting branch prefixes?
Feature branches? [feature/] 
Release branches? [release/] 
Hotfix branches? [hotfix/] 
Support branches? [support/] 
Version tag prefix? [] 
```
Geef een `RETURN` toetsaanslag voor iedere standaard instelling. Mogelijkerwijs wil je een systeem van tags gebruiken, de prefix kun je dus wijzigen indien nodig.

Het `~` teken op de eerste regel geeft aan dat ik deze, per ongeluk, in de `$HOME` van onze gebruiker geplaatst heb. Aangezien dit niet gewenst is en dit een demo betreft verwijder ik snel deze lokale repository met `cd; rm -rf .git`.

> LET OP: Onze huidige shell begint te hoesten bij enige vorm van complexere prompt. Hoewel ik succesvol `zsh` gecompileerd heb en `oh-my-zsh` geinstalleerd heb, wordt toch op (Unicode?) tekens moeilijk gedaan. Ook een bash variant, die onze huidige .git repo, status en branch in de prompt toont, `bash-it`, wordt niet gevroten zonder performance impact die ongewenst is. Je ziet dus nergens in de prompt of je nu in een .git managed directory bent en welke branch dan + of deze map dirty is.

Byte prompt: `wellnessbon.nl@ssh1.c60 ~/wellnessbon.nl $ `
Development prompt: `ijzervreter :: ~/well/wellnessbon.nl ‹resources/media› »`

[gitflow]: <http://nvie.com/posts/a-successful-git-branching-model/>






