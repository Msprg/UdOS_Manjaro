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

**GitHub vraj podporuje vidá v MarkDown-e! A natívne! Tak schválne, či nám to funguje ;) **
(a dúfam že sa mi to v PDF-ku nerozpadne :/ )


https://user-images.githubusercontent.com/18015488/118571723-fe96f380-b77e-11eb-81f1-512f4b7b2279.mp4


