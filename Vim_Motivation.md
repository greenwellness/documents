## Vim

### Inleiding

De development machine van RJ bevat een besturingssysteem met daarop de `vim` tekstverwerker. Vim is een lange tijd geleden gemaakt door een Nederlander, Bram Molenaar, en wereldberoemd: het is een van de twee meest bekend tekstverwerkers op traditionele \*NIX machines waar iedere self-proclaimed computerfanaat mee bekend zou moeten zijn. Onze Green Wellness machines bevatten soms/veelal een Linux shell met daarin als de meest veelzijdige tekstverwerker `vim`. Daarnaast is wel nog `nano` beschikbaar (maar men kan hier veel, veel minder aanpassen) en onze huidige virtuele machine van [Byte.nl](http://ssh045657.bytenet.nl) heeft zelfs geen `ed` (van editor, een nog meer antieke tekstverwerker van pre-vi tijdperk) of [emacs](http://www.emacswiki.org/) installatie. Vim is dus de enige optie.

### Opmerkingen

LET OP: Getracht is de vim distributie (bundel plugins en configuraties) [spf13](https://github.com/spf13/spf13-vim) te gebruiken. Dit sloopt de performance in de shell die maximaal afgeknepen wordt momenteel. Ook een lichtere variant werkt nagenoeg niet zonder frustratie. Hierover ga ik (RJ) nog contact zoeken en een oplossing laten zoeken door Byte.

Wellicht niet geheel ondenkbaar, meerdere developers zullen me mij/ons samenwerken en hebben ongetwijfeld een eigen machine met instellingen.

Gebruikt men echter vim, dan kan deze SOP bruikbaar zijn.

### Noodzakelijk en actueel

Omdat `vim` als bare-bones installatie en configuratie (oorspronkelijke programma vi, soms vim maar dan verouderde versies etc.) een vervelende standaard configuratie bevat, is het vaak wijs om deze zo spoedig mogelijk te vervangen door de stabiele en volwassen ViM (Vi iMproved) van versie 7.3+.

### Prerequisites

**Optimaal:** spf13 of gelijkgestelde distributie

**Minimaal:** vundle

Vundle wordt gebruikt om makkelijk de in deze tekst verwezen plugins te installeren.

Voor een overzicht van alle GitHub vim repositories kun je [de zoekfunctie van GitHub gebruiken](https://github.com/search?q=vim&ref=cmdform&s=stars&search_target=global&type=Repositories) maar handiger nog (alleen niet volledig) is het vim command `:Bundles`. Gebruik vervolgens, als normaal, `/` om te zoeken. Daarnaast is het eenvoudig om  plugins die niet in de lijst voorkomen, direct vanuit GitHub te klonen in de juiste map: `:BundleInstall username/repo` waar username en repo naar GitHub gebruikersnaam en project (en in de URL) verwijzen.


