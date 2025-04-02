# Instal·lació, configuració inicial i programari de base


Per a la documentació completa visita [mkdocs.org](https://www.mkdocs.org).


---
## Introducció
En aquest treball explico com he instal·lat Windows 10 en una màquina virtual. He creat una partició de 20 GB en un disc de 40 GB, deixant els altres 20 GB per instal·lar Ubuntu 24 més endavant. Després, he restaurat el sistema d'arrencada amb Grub Repair per gestionar els dos sistemes operatius.

A més, també he instal·lat Windows Server 2022 per ampliar els coneixements sobre diferents entorns de treball. Durant el procés, he revisat opcions de llicència i configurat els elements bàsics perquè tot funcioni correctament.

He anat apuntant tot el procés amb captures de pantalla i anotacions per tenir-ho tot ben documentat.

![log](./fotos/fotointros1.jpg)

---

## Preparació màquines

### Instal·lació Windows 10 Enterprise

1. El primer que haurem de fer és crear la màquina al virtualbox, afegir la ISO, l'espai de disc de 40GB, etc. Una vegada encenem la maquina, afegirem l'idioma, distribució de teclat, acceptarem el termes de llicencia, i escollirem una instal·lació personalitzada per a només instal·lar el windows.      
![windows10](./fotos/win1.png)
![windows10](./fotos/win2.png)
![windows10](./fotos/win3.png)
![windows10](./fotos/win4.png)

2. Tot seguit, al disc de 40GB li crearem una partició de 20GB. Aquesta l'utilitzarem més endavant, per fer una sèrie de activitats.        
![windows10](./fotos/win27.png)
![windows10](./fotos/win28.png)
![windows10](./fotos/win29.png)

3. Seguidament confinuarem amb la instal·lació.     
![windows10](./fotos/win6.png)
![windows10](./fotos/win7.png)
![windows10](./fotos/win8.png)
![windows10](./fotos/win9.png)

4. Ara crearem un usuari local clicant a 'Unirse a un dominio', seguidament afegirem el nom i la contrasenya, a més de les preguntes de seguretat.      
![windows10](./fotos/win10.png)
![windows10](./fotos/win11.png)
![windows10](./fotos/win12.png)
![windows10](./fotos/win13.png)
![windows10](./fotos/win14.png)
![windows10](./fotos/win15.png)
![windows10](./fotos/win16.png)

5. Seguidament clicarem les opcions que ens interesen més a nivell personal, aquest no és un pas important de la instal·lació.      
![windows10](./fotos/win17.png)
![windows10](./fotos/win18.png)
![windows10](./fotos/win19.png)
![windows10](./fotos/win20.png)
![windows10](./fotos/win21.png)
![windows10](./fotos/win22.png)
![windows10](./fotos/win23.png)
![windows10](./fotos/win24.png)
![windows10](./fotos/win25.png)

6. Una vegada ja ha acabat la instal·lació, revisarem que les particions s'han fet correctament amb l'administrador de discs.       
![windows10](./fotos/win26.png)
![windows10](./fotos/win30.png)

---

### Instal·lació Windows Server 2022

La instal·lació en Windows Server 2022 és molt similar a la de Windows 10, per tant si heu fet l'apartat anterior sabreu fer aquest sense cap problema.

1. El primer que farem és crear la vm al virtualbox, després afegirem la ISO i la mida del disc serà de 50GB. Després una vegada encesa la màquina començarem amb la instal·lació.      
![windowsserver](./fotos/winser1.png)
![windowsserver](./fotos/winser2.png)

2. En aquest apartat de la instal·lació escollirem l'última opció, ja que volem tindre interfície gràfica.      
![windowsserver](./fotos/winser3.png)

3. Els següents passos són clicar 'Siguiente'.      
![windowsserver](./fotos/winser4.png)
![windowsserver](./fotos/winser5.png)
![windowsserver](./fotos/winser6.png)
![windowsserver](./fotos/winser7.png)
![windowsserver](./fotos/winser8.png)

4. Per últim, ja tindrem el sistema operatiu.       
![windowsserver](./fotos/winser8.png)

## Instal·lació d'Ubuntu en la vm Windows 10

1. El primer que haurem de fer és entrar dins del windows i comprovar a partir de l'administrador de discs que realment hi ha un espai al disc dur disponible per Ubuntu.       
![ubuntu](./fotos/uw1.png)

2. Seguidament apagarem la màquina virtual, afegirem la iso de Ubuntu 24 i tornarem a iniciar-la.       
![ubuntu](./fotos/uw2.png)

3. En aquest següent punt realitzarem tota la configuració de forma normal, però quan arribessem a l'apartat d'on instal·lar el SO clicarem en l'opció "Install Ubuntu alongside Windows 10", així podrem tindre els dos sistemes operatius a la vegada.        
![ubuntu](./fotos/uw3.png)
![ubuntu](./fotos/uw4.png)
![ubuntu](./fotos/uw5.png)
![ubuntu](./fotos/uw6.png)
![ubuntu](./fotos/uw7.png)
![ubuntu](./fotos/uw8.png)
![ubuntu](./fotos/uw9.png)
![ubuntu](./fotos/uw10.png)
![ubuntu](./fotos/uw11.png)
![ubuntu](./fotos/uw12.png)
![ubuntu](./fotos/uw13.png)
![ubuntu](./fotos/uw14.png)
![ubuntu](./fotos/uw15.png)

4. Seguidament una vegada acaba la instal·lació, reinciarem la vm, clicarem Enter per treure la iso i comprovarem que Ubuntu funciona. Com hem pogut observar no apareix un grub per triar el sistema operatiu, això és perque el sistema d'arrencada de windows està danyat.       
![ubuntu](./fotos/uw16.png)
![ubuntu](./fotos/uw17.png)
![ubuntu](./fotos/uw18.png)

5. Per això, recuperarem el gestor d'arrencada de Windows amb Boot-Repair. Primer haurem d'afegir la iso amb la vm apagada.     
![ubuntu](./fotos/uw19.png)
![ubuntu](./fotos/uw20.png)

6. Aquest programa és molt sencill, de forma que només haurem d'anar clicant següent i les opcions més recomanades.     
![ubuntu](./fotos/uw21.png)
![ubuntu](./fotos/uw22.png)
![ubuntu](./fotos/uw23.png)
![ubuntu](./fotos/uw24.png)

7. Una vegada ja ha acabat apagarem la vm i treurem a iso.      
![ubuntu](./fotos/uw25.png)
![ubuntu](./fotos/uw26.png)

8. Per últim, quan inciem la màquina podrem observar que ara si que hi ha un menu per escollir entre els dos sistemes operatius. Seguidament comprovarem que els dos funcionen de forma correcta i en Windows en l'administrador de discs podrem veure que la partició de Ubuntu està utilitzant-se.        
![ubuntu](./fotos/uw27.png)
![ubuntu](./fotos/uw28.png)
![ubuntu](./fotos/uw29.png)
![ubuntu](./fotos/uw30.png)


