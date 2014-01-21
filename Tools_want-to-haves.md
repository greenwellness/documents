

Document-transcending abbreviations, auto-expanding shortcut references. Define and reference once fully, use shorthands forever.

Say I have text file `A.md` and `B.rst` and `C.textile` (the extension doesn't matter) and I started with `A` which has the following content:

```
Lorem ipsum dolor sit amet, consectetur {<http://github.com>}+ adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.
```

Now when I have a very large amount of texts, I would be quite sure *somewhere* I would have github defined and could be reasonably sure its shorthand would be `gh` 

Usage:

#### Textile abbr+

(textile) ABBR(Abbreviation) ~> tooltip
(us) ABBR(Abbreviation) ~> {tooltip}+
     ABBR ~> [Abbreviation]tooltip

[GH|><http://www.github.com><|foo]

{<http://www.github.com>}+

Probleem 000
- nog steeds: een script dat .md, .txt, .textile etc. documenten scant op gebruikte webadressen (http\[s\]) en deze met een algoritme op basis van een NLP tool tokenized en afkort (abbreviations). Dit is een complex probleem aangezien veel domeinnamen gehele woorden samengevoegd zijn en geen werkelijk woord in het Engels vormen zoals men dat in het Nederlands wel doet. `bandenkampioen` is wellicht in het Nederlands geen woord maar zou het wel kunnen zijn zoals `appelboom` dat is, in het Engels mag dat laatste `apple tree` niet. Op zijn hoogst is `Tire-champion` mogelijk gewenst maar `apple-tree` niet. Een tokenizer werkt meestal met zinnen, niet met woordconstructies van deze aard. Want eigenlijk zou ik willen dat woorden als `github` gezien worden als `git en hub` (bijvoorbeeld `['git 'hub]` in Clojure vectoren als symbool) en afkortbaar dus als `gh`. Op posities (string lengte) afsnijden geeft onlogische afkortingen logischerwijs. Het probleem zit hem in het feit dat dit soort structurele zaken in de mondelinge communicatie zijn oorsprong kent en men, dit soort afkortingen, dus op basis van lettergrepen veelal doet. Syllables kennen helaas, in tegenstelling tot de eenvoudige Nederlandse (4) regels om de lettergrepen te bepalen, in het Engels een erg moeilijk eenduidig te formuleren structuur. Er zijn veel uitzonderingen maar, gelukkig, kennen deze ook wel enige mate van structuur. In de thesis `[Word Hy-phen-a-tion by Com-put-er](http://www.tug.org/docs/liang/)` wordt dit probleem uitgewerkt voor de Engelse taal en in de informatica bruikbare wiskundige algoritme opgeschreven.

