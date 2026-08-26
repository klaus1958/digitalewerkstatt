+++
date = '2026-07-21T20:10:08+02:00'
draft = false
title = 'My First Post'
+++

Posts werden in Hugo in Markdown geschrieben. Die links liefern einige Infos dazu.

[Syntax-Dokumentation][osd]
von [John Grubers][jg] [Markdown][md].

   [jg]: https://daringfireball.net/
   [md]: https://daringfireball.net/projects/markdown/
  [osd]: https://daringfireball.net/projects/markdown/syntax

* 1.8.26 
bis auf die Webapps möchte ich die Website wie einen Blog organisieren, aber statt mit Wordpress eben mit [**Hugo**](https://gohugo.io/), einem [**static site generator**](https://en.wikipedia.org/wiki/Static_site_generator)
* 3.8.26 meine style.css wird möglichst **classless** oder etwas weniger streng **classless-light** um dem Minimalismusgedanken genügend Raum zu geben 
  und die externen Links starten jetzt auf einer neuen Seite (_markup/render-link.html ist dafür verantwortlich)
* 18.8.26 **Links zum classless- und classless-light-css Thema** (werden erweitert wenn ich Erhellendes finde).Sicher wäre es einfach, mir ein passendes Classlessframework runter zu laden, aber ich will ja auch *"spielen können dürfen"*.

   - https://classlesscss.com/
   - https://readmedium.com/the-future-of-web-styling-classless-and-class-light-css-0bcd3fadab8f
   - https://classless.de/
   - *mit den Farben bin ich noch nicht ganz zufrieden*

* 22.8.26 pico.css in der min version eingebunden. Allerdings nicht ganz classless sonder momentain die class "container" genutzt die sollte normalerweise in main, aber das nutze ich scon über hugo. muss jetzt rausfinden ob main in pico irgendwelche styles hat, die gekoppekt sind oder obe ich main in hugo tausche. 
* 26.8.26 /layouts/index.html evtl. anders gestalten, könnte als Start/Home/Landingpage eine ganz andere Funktion erfüllen als so eine listseite (vergl. Hugo in action S.64 letzter Absatz ff.)