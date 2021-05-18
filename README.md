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

2. Privíta nás okno sprievodcu. Vyberieme si **Custom**, pretože sme predsa *(advanced)*. ;)

![VM_2](https://user-images.githubusercontent.com/18015488/118570945-62202180-b77d-11eb-9d01-8526c8d85528.png)

3. Nastavenie kompatibility necháme na *Workstation 16.x* (nebudeme VM prenášať do starších verzií programu Workstation).

![VM_3](https://user-images.githubusercontent.com/18015488/118570975-749a5b00-b77d-11eb-85ff-98e38de3bb5c.png)

4. Vyberieme si stiahnuté inštalačné ISO distribúcie **Manjaro**.

![VM_4](https://user-images.githubusercontent.com/18015488/118570988-79f7a580-b77d-11eb-8d4e-f0ca52b96f30.png)

5. Vyberieme si operačný systém typu *Linux*, ale, *Manjaro*, a navyše ani *Arch* v zozname distribúcií nenájdeme. :( 
    
![VM_5](https://user-images.githubusercontent.com/18015488/118570992-7d8b2c80-b77d-11eb-819b-341a5b135d5a.png)

6. Nevadí, zvolíme si *Debian 10.x 64-bit*, fungovať by to malo rovnako.

![VM_6](https://user-images.githubusercontent.com/18015488/118571002-811eb380-b77d-11eb-8662-904d984ba6da.png)

7. Zvolíme si názov pre našu VM. Mne stačí aj jednoduché *Manjaro 21.X*. Umiestnenie súborov VM necháme predvolené.

![VM_7](https://user-images.githubusercontent.com/18015488/118571011-85e36780-b77d-11eb-902d-09b54ead2dce.png)

8. Pridelíme VM virtuálne procesor-y a jadrá. V podstate výkon. 1 processor so štyrmi jadrami by mal byť až až...

![VM_8](https://user-images.githubusercontent.com/18015488/118571020-88de5800-b77d-11eb-8b7a-cbfaf0544eef.png)

9. Pridelíme VM virtuálnu pamäť. *Manjaro* ako také - postavené na **Arch**, určite nebude mať vysoké nároky na pamäť. Prostredie **XFCE** je taktiež jedno z najekonomickejších! 2GiB by mali celkom stačiť.

![VM_9](https://user-images.githubusercontent.com/18015488/118571024-8d0a7580-b77d-11eb-8fc2-1e9a81c43ce9.png)

10. Použijeme sieťovanie v móde NAT. Býva s ním najmenej komplikácií.

![VM_10](https://user-images.githubusercontent.com/18015488/118571028-8f6ccf80-b77d-11eb-9671-2e078f1cc4c2.png)

11. Necháme predvolené - na LSIL - pre naše použitie nepodstatné.

![VM_11](https://user-images.githubusercontent.com/18015488/118571031-91369300-b77d-11eb-97b2-3985d6c7b0fd.png)

12. Necháme predvolené - na SCSI - opäť, pre naše použitie nepodstatné.

![VM_12](https://user-images.githubusercontent.com/18015488/118571036-94318380-b77d-11eb-8c9b-6a238d80fde8.png)

13. Vytvoríme si nový virtuálny disk...

![VM_13](https://user-images.githubusercontent.com/18015488/118571052-972c7400-b77d-11eb-9d9f-16bd092d3a26.png)

14. ... s veľkosťou 10GiB. Pre reálny systém trochu málo, ale pre naše demonštračné účely dostačujúce. Súbor je dosť malý na to, aby sme zvolili možnosť **Store vd as a single file**.

![VM_14](https://user-images.githubusercontent.com/18015488/118571076-9eec1880-b77d-11eb-90a2-bb0967a7bbdb.png)

15. Pokiaľ máte málo miesta na disku s ostatnými súbormi VM, uložte si disk inam. Preferujte rýchle úložiská s nízkou latenciou a vysokou priepustnosťou.

![VM_15](https://user-images.githubusercontent.com/18015488/118571090-a57a9000-b77d-11eb-93cb-db224f9eacc3.png)

16. Súhrnné menu. Zatiaľ tu nič nepotrebujeme meniť.

![VM_16](https://user-images.githubusercontent.com/18015488/118571099-a8758080-b77d-11eb-8200-fceaeb64cb24.png)

17. Doplňujúci krok "pre odvážnych". Môžeme  si zapnúť podporu **UEFI**, keď chceme bootovať *moderne*. :)

![VM_17](https://user-images.githubusercontent.com/18015488/118571185-bf1bd780-b77d-11eb-9ace-a5484c6773fc.png)

18. Máme hotovo.

![VM_18](https://user-images.githubusercontent.com/18015488/118571196-c0e59b00-b77d-11eb-9ea2-ee6a6ee027d6.png)



# Prvé spustenie a inštalácia systému

To bolo pekných pár obrázkov. 18 aby som bol presný. Inštalácia ich bude mať tiež dosť. Ach, keby sme len mali niećo čo by tento problém riešilo...
**GitHub vraj podporuje videá v MarkDown-e! A natívne! Tak schválne, či nám to funguje ;) **
(a dúfam že sa mi to v PDF-ku nerozpadne :/ )



* Takže, spustíme si náš virtuálny stroj. Keď som to predtým skúšal, narazil som hneď na začiatku na problém. Systém sa pri bootovaní zasekol, a ďaľej sa mu veľmi nechcelo. Takže tu máme problém hneď na začiatku. (Pri mojom šťastí už ani nie som prekvapený :D ).
* Ako sa však ukázalo, **nie je to chyba našek konfigurácie**, vzhľadom na to, že tento problém konkrétne s kombináciou distribúcie Manjaro a VMware, sa ukázal iba nedávno, a nie som jediný kto si to všimol...

Podľa [tejto odpovede](https://forum.manjaro.org/t/installation-issue-livemedia-mhwd-script-hangs/59999/5), sa to dá "obísť" zmenou používaných ovládačov.
Pred spustením teda zmeníme ovládač na `mesa` a úspešne nabootujeme do live prostredia!

https://user-images.githubusercontent.com/18015488/118571723-fe96f380-b77e-11eb-81f1-512f4b7b2279.mp4

Keď už sme v grafickom Live prostredí, prečo nevyužiť grafický inštalátor?
(Pokiaľ by sme chceli systém inštalovať zarovno s tutoriálom, vďaka tomu že video má ovládacie prvky, si ho možene zastaviť alebo pretočiť ako je potrebné)


https://user-images.githubusercontent.com/18015488/118574525-efb33f80-b784-11eb-8520-9c898eae3a71.mp4

Annotácie k videu:
1. Spustíme grafický inštalátor,
2. Zvolíme si regionálne nastavenia, t.j. lokalita, časové pásmo a pod.
3. Zvolíme si mapovanie klávesnice. Ja si zvolím slovenskú, (za čo by mi niektorí jedinci možno ublížili na zdraví, ale na(ne)štastie, návštevy nie sú odporúčané :) )
4. Môžeme si dovoliť zvoliť vymazanie celého disku, keďže náš 10 GiB disk je aj tak prakticky čistý. Odkladací priestor (*swap*) si budeme ukladať do súboru. čisto iba z dôvodu že to takto robím radšej. Zjednodušuje to prípadné úpravy partícií na disku v budúcnosti.
5. Vytvárame si účet "prvého užívateľa", čo budeme my. Napríklad *Administrátor*. Meno na prihlásenie som si skrátil na *admin*. Názov systému bude *Code_Server_1* (ako by ich malo byť viac, heh...).
6. Pre zvýšenie **komfortu**, som si nedal žiadne heslo (som prekvapený že mi to bolo inštalátorom dovolené), zapol automatické prihlasovanie, a... uh... rovnaké heslo má... root...? ***Way to get hacked!***. Ukážka katastrofálnej bezpečnosti. Na testovanie vo VM je to ešte pochopiteľné, avšak v produkčných systémoch je toto **veľké no no**...
7. Potvrdíme zmeny na disku, ktoré budú už čoskoro nezvratné, a systém sa začne inštalovať. Ak neinštalujete zarovno s videom, určite si ho pretočte...
8. Hotovo! Klikneme na tlačidlo *Dokončiť* a v live systéme sme prakticky skončili!

# Prvé spustenie systému, a inštalácia aktualizácií

Cítite tú vôňu? No, možno to nie je nové auto, ale nabootovali sme do nového, čistého systému!
Teraz by to hneď na začiatok chcelo aktualizácie, predsa len, sme v Arch vetve. ;)


Na prvý boot systému sa môžete pozrieť tu, a potom už ale s videami končíme. :(
https://user-images.githubusercontent.com/18015488/118577616-052b6800-b78b-11eb-9dbe-b8b3fb08726f.mp4



1. Ako úplne prvé, príkazom `sudo pacman-mirrors -g`, vyhľadáme najrýchlešie mirrory. Nie je to nutný krok, ale niekedy je potrebný keď sťahovanie z repozitárov je pomalé. (spoiler alert - nepomohlo) Toto chvíľu trvá, takže tento krok možno budete chcieť pretočiť.

![Updates_1](https://user-images.githubusercontent.com/18015488/118577731-3c9a1480-b78b-11eb-90b7-5e39dc52a6be.png)

2. Príkazom `sudo pacman -Syu open-vm-tools` nainštalujeme podpornú službu pre VMware Workstation 16. Nie je to ale nutné mať. Každopádne sa nám rovno aj aktualizovali iné systémové komponenty, vrátane prehliadača Firefox.

![Updates_2](https://user-images.githubusercontent.com/18015488/118578456-77e91300-b78c-11eb-864f-5e499cefbf29.png)

![Updates_3](https://user-images.githubusercontent.com/18015488/118578625-c4cce980-b78c-11eb-9bbf-c94f9a1744ed.png)


3. Príkazom `sudo mhwd -a pci free 0300` by sme sa mali poistiť, aby sme sa nedostali ku podobnému problému s WMvare ako pri bootovaní Live systému na začiatku.

![Updates_4](https://user-images.githubusercontent.com/18015488/118578633-c8f90700-b78c-11eb-8dda-633440e83e20.png)

4. Napriek tomu, že linuxáci sa často chvália, že oproti Windowsu, Lunux nie je vždy potrebné reštartovať po aktualizáciách, my to pre istotu aj tak urobíme ;)

![reboot](https://user-images.githubusercontent.com/18015488/118579718-e4fda800-b78e-11eb-8793-2ec8fd261fd9.gif)
(Viete ako bolo vyššie napísané, že tu ďalšie videá už nebudú... ... ...toto je gif :D )




# Inštalácia aplikácií a nastavenie systému pre účely zadania

Zadaním bolo vytvoriť systém pre tím programátorov. Keďže nevieme kto bude v akom jazyku programovať, nainštalujeme len nejaké základné veci. Podpora pre konkrétne jazyky by sa v praxi doinštalovala neskôr - dodatočne. Čo sa komunikácie a plánovania týka, v aktuálnej situácií sú najpopulárnejšie služby asi Microsoft Teams, Slack, Discord, GitHub, možno Skype...? Z ktorých **všetky** sú web aplikácie a teda bežia natívne v browseri. Ak si do toho prirátam, že Teams robí na linuxe iba samé problémy, Discord je horor updatovať, a ešte som nikoho nevidel používať GitHub Desktop na Linuxe... (Taktiež Skype? Nainštalovaný na Linuxe? Ku tomu ma neprinútite), rozhodol som sa ich neinštalovať,
> "Veď, aj tak je to všetko len samý bloat..." - Určite nejaký Arch user


1. Príkazom `sudo -i` vstúpime do režimu superusera v interaktívnom móde. To aby sme pred všetky nasledujúce príkazy nemuseli písať `sudo`.

![Setup_1](https://user-images.githubusercontent.com/18015488/118583978-39585600-b796-11eb-85ce-fa7f57228572.png)

2. Príkazom `pacman -Sy git code base-devel neofetch` si nainštalujeme nejaké základné balíčky, kde `code` je aktuálne veľmi populárny editor *Microsoft Visual Studio Code*, tu dokonca v open-source verzii, `base-devel` nám poskytuje základné kompilačné nástroje vrátane `make`, a taktiež nesmie chýbať `neofetch`.

![Setup_2](https://user-images.githubusercontent.com/18015488/118584368-14181780-b797-11eb-8d59-19bee71ba605.png)

![neofetch](https://user-images.githubusercontent.com/18015488/118584378-18dccb80-b797-11eb-96fe-524c9f62ec6f.png)
Sme v Arch vetve, a nie, ja s tým neprestanem :D

3. Teraz si pridáme skupinu do ktorej budú patriť naši programátori, príkazom `groupadd coders`.
4. Začneme vytvárať používateľské účty pre programátorov, pre demonštráciu iba `coder1`, ale rovnakým postupom si ich pridáme koľko len bude potrebné.
5. Nastavíme im heslo, ale žiadny strach, taktiež ich prinútime, nech si pri prvom prihlásení urobia vlastné ;)
6. Pridáme ich do skupiny `coders`.

![Setup_3](https://user-images.githubusercontent.com/18015488/118584694-cc45c000-b797-11eb-8464-5b38574199fc.png)

7. Nakoniec nám stačí vytvoriť zdieľané úložisko, napríklad formou zdieľanej zložky `coders/` v `/shared/`, nastavením správnej skupiny, prístupových práv a samozrejme **setgid**.

![Setup_4](https://user-images.githubusercontent.com/18015488/118584711-d10a7400-b797-11eb-9e2d-ceac3f3668f8.png)

8. Skúsime si ešte overiť či doň programátori vedia zapisovať:

![Setup_5](https://user-images.githubusercontent.com/18015488/118585515-58a4b280-b799-11eb-8139-757b385fa072.png)



# Hotovo!

Tak, a je to! Programátori majú aspoň základné programátorské nástroje, súkromné úložisko vo forme svojho domovského adresára, a zdieľané úložisko vo forme zdieľaného adresára. Nejaké sieťové úložisko by možno bolo lepšie, avšak myslím, že to je už trochu mimo zadania. Ako bolo spomenuté, prípadná jazyková podpora by nemala predstavovať žiaden problém, stačí doinštalovať, obvykle 1 až pár príkazov (alebo odkaz na skript).


Kažopádne dúfam že je táto práca vyhotovená podľa predstáv, a taktiež že sa prezenácia pomocou Markdown-u páčila!
