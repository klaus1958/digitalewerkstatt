+++
date = '2026-07-21T20:10:08+02:00'
draft = false
title = 'Mein Startpost'
+++

Posts werden in Hugo und zumindest auch in Zola in Markdown geschrieben. Die Links liefern einige Infos dazu.

[Syntax-Dokumentation][osd]
von [John Grubers][jg] [Markdown][md].

   [jg]: https://daringfireball.net/
   [md]: https://daringfireball.net/projects/markdown/
  [osd]: https://daringfireball.net/projects/markdown/syntax
Gleichzeitig ist das hier die Timeline für mich, damit ich seh wie sich mein Projekt entwickelt -vor oder zurück oder doch lieber Neuland.  
. . .
<!--more-->
* 1.8.26 
bis auf die Webapps möchte ich die Website wie einen Blog organisieren, aber statt mit Wordpress eben mit [**Hugo**](https://gohugo.io/), einem [**static site generator**](https://en.wikipedia.org/wiki/Static_site_generator)
* 3.8.26 meine style.css wird möglichst **classless** oder etwas weniger streng **classless-light** um dem Minimalismusgedanken genügend Raum zu geben 
  und die externen Links starten jetzt auf einer neuen Seite (_markup/render-link.html ist dafür verantwortlich)
* 18.8.26 **Links zum classless- und classless-light-css Thema** (werden erweitert wenn ich Erhellendes finde).Sicher wäre es einfach, mir ein passendes Classlessframework runter zu laden, aber ich will ja auch *"spielen können dürfen"*.

   - https://classlesscss.com/
   - https://readmedium.com/the-future-of-web-styling-classless-and-class-light-css-0bcd3fadab8f
   - https://classless.de/
   - *mit den Farben bin ich noch nicht ganz zufrieden*

* 22.8.26 pico.css in der min version eingebunden. Allerdings nicht ganz classless sonder momentain die class "container" genutzt die sollte normalerweise in main, aber das nutze ich schon über hugo. muss jetzt rausfinden ob main in pico irgendwelche styles hat, die gekoppekt sind oder obe ich main in hugo tausche. 
* 26.8.26 /layouts/index.html evtl. anders gestalten, könnte als Start/Home/Landingpage eine ganz andere Funktion erfüllen als so eine listseite (vergl. Hugo in action S.64 letzter Absatz ff.) - Hab ich am 27.8.26 direkt erledigt, die ganzen "loop2-Sachen auskommentiert und damit unsichtbar gemacht
* 18.10.26  pico.css wird nicht mehr supported. Blades.css wäre der Nachfolger, aber classless css erscheint mir doch eher ein eher sektiererischer Ansatz zu sein. Alos hab ich das über Bord geworfen, mir von der KI eine styles.css im [**Milligramstil**](https://milligram.io/) schreiben lassen mit noch weniger Codezeilen.  
Dieses Frameworks wird auch seit Jahren nicht mehr gepflegt, dann nehm ich lieber etwas, das ich vollständig verstanden habe und selber jederzeit gefahrlos erweitern kann.  
* 18.10.26 und weil es so lustig war, hab ich diese Wochenende auch noch einen blick auf [**Zola**](https://www.getzola.org/). Auch ein static site generator so wie hugo, das ich aktuell verwende. Angeblich ist der code etwas sprechender, aber wenn eine Seite erstmal steht, fasse ich den Code lange nicht an und dann muss ich eh wieder nachschlagen, um zu verstehen was ich da im detail wollte. Darum so einfach wie möglich und so komplex wie nötig.
 