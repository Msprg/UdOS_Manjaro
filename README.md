# UdOS_Manjaro

Semestrálny projekt pre predmet Úvod do Operačných systémov.

Autor: Matúš Prančík

# Zadanie semestrálneho projektu


Z ponúkaných zadaní som si vybral urobiť základný systém pre tím piatich programátorov. Ako distribúciu som si vybral Manjaro, čo je distribúcia založená na Arch linuxe.

Z oficiálnej stránky distribúcie Manjaro:

>  (Manjaro) Is an accessible, friendly, open-source operating system. Providing all the benefits of cutting-edge software combined with a focus on getting started quickly, automated tools to require less manual intervention, and help readily available when needed. Manjaro is suitable for both newcomers and experienced computer users.

>  Unlike proprietary operating systems you have full control over your hardware without restrictions. This makes Manjaro a powerful Operating System ideal in home, work, and development environments.

>  It is easily possible to run many popular Windows applications, using compatibility software such as Wine, PlayonLinux or Proton via Steam. The examples given here are far from comprehensive!

>  Representing a perfect middle-ground for those who want good performance, full control, and cutting-edge software but also a degree of software stability.

# Kde a ako získať Manjaro

Manjaro sa z [oficiálnej stránky](https://manjaro.org/download/) dá získať v podobe pripravených ISO obrazov, s rôznymi desktopovými prostrediami. Na výber aktuálne máme hlavné 3:

* S prostredím XFCE:
![image](https://user-images.githubusercontent.com/18015488/118568566-64cc4800-b778-11eb-9f7a-2c87b31a82df.png)

* S prostredím KDE (Plasma):
![image](https://user-images.githubusercontent.com/18015488/118568581-6b5abf80-b778-11eb-8ebf-525009b82446.png)

* S prostredím GNOME:
![image](https://user-images.githubusercontent.com/18015488/118568597-731a6400-b778-11eb-89a9-8a62c358f061.png)



Ja som sa z dôvodov asi najnižších HW nárokov, rozhodol pre verziu s XFCE...


# Príprava nového virtuálneho stroja vo VMware Workstation 16

Po nainštalovaní a otvorení programu **VMware Workstation 16**, môžeme začať tvorbou nového virtuálneho stroja, ktorou sa vás teraz pokúsim previesť:

1. V hornom menu, si z menu *Files*, vyberieme položku *New Virtual Machine...*. Alternatívne môžeme stlačiť `ctrl+N`.

![VM_1](https://user-images.githubusercontent.com/18015488/118569168-ac070880-b779-11eb-9e3f-d23fe5bd5a6e.png)

2. Privíta nás okno sprievodcu. Vyberieme si **Custom**, pretože sme predsa *(advanced)* ;) .
3. Nastavenie kompatibility necháme na *Workstation 16.x* (nebudeme VM prenášať do starších verzií programu Workstation).
4. Vyberieme si stiahnuté inštalačné ISO distribúcie **Manjaro**.
5. Vyberieme si operačný systém typu *Linux*, ale, *Manjaro*, a navyše ani *Arch* v zozname distribúcií nenájdeme :( .
6. Nevadí, zvolíme si *Debian 10.x 64-bit*, fungovať by to malo rovnako.
7. Zvolíme si názov pre našu VM. Mne stačí aj jednoduché *Manjaro 21.X*. Umiestnenie súborov VM necháme predvolené.
8. Pridelíme VM virtuálne procesor-y a jadrá. V podstate výkon. 1 processor so štyrmi jadrami by mal byť až až...
9. Pridelíme VM virtuálnu pamäť. *Manjaro* ako také - postavené na **Arch**, určite nebude mať vysoké nároky na pamäť. Prostredie **XFCE** je taktiež jedno z najekonomickejších! 2GiB by mali celkom stačiť.
10. Použijeme sieťovanie v móde NAT. Býva s ním najmenej komplikácií.
11. Necháme predvolené - na LSIL - pre naše použitie nepodstatné.
12. Necháme predvolené - na SCSI - opäť, pre naše použitie nepodstatné.
13. Vytvoríme si nový virtuálny disk...
14. ... s veľkosťou 10GiB. Pre reálny systém trochu málo, ale pre naše demonštračné účely dostačujúce. Súbor je dosť malý na to, aby sme zvolili možnosť **Store vd as a single file**.
15. Pokiaľ máte málo miesta na disku s ostatnými súbormi VM, uložte si disk inam. Preferujte rýchle úložiská s nízkou latenciou a vysokou priepustnosťou.
16. Súhrnné menu. Zatiaľ tu nič nepotrebujeme meniť.
17. Doplňujúci krok "pre odvážnych". Môžeme  si zapnúť podporu **UEFI**, keď chceme bootovať *moderne*. :)
18. Máme hotovo.




