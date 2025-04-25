# Instal·lació, configuració inicial i programari de base


Per a la documentació completa visita [mkdocs.org](https://www.mkdocs.org).


---
## Introducció
En aquest treball explico com he instal·lat Windows 10 en una màquina virtual. He creat una partició de 20 GB en un disc de 40 GB, deixant els altres 20 GB per instal·lar Ubuntu 24 més endavant. Després, he restaurat el sistema d'arrencada per gestionar els dos sistemes operatius.

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

### Xarxa bàsica

1. Al ser un windows server el que farem és configurar-li una ip estàtica, per fer això haurem d'anar a "Configuració", "Xarxa", "Adaptadors de xarxa" i farem clic dret per escollir l'opció "Propietats".     
![xarxa](./fotos/xarxa3.png) 

2. Després, clicarem a sobre de IPv4.       
![xarxa](./fotos/xarxa2.png)

3. Aquí afegirem l'ip que més ens sigui convenient.         
![xarxa](./fotos/xarxa1.png)



## Recuperar gestor d'arrencada de Windows 10

### Instal·lació d'Ubuntu en la vm Windows 10

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

### Recuperació amb ISO Windows
1. Seguidament tancarem la màquina i afegirem la iso de Windows 10, aquesta la utilitzarem per reparar el gestor d'arrencada. Per carregar la iso haurem de clicar qualsevol tecla.     
![ubuntu](./fotos/uww1.png)

2. Després, escollirem l'idioma.        
![ubuntu](./fotos/uww2.png)

3. Aquí haurem de anar a la part d'abaix a l'esquerra i clicar "Reparar el equipo".     
![ubuntu](./fotos/uww3.png)

4. A continuació, clicarem en "Solucionar problemas" i "Símbolo del sistema".       
![ubuntu](./fotos/uww4.png)
![ubuntu](./fotos/uww5.png)

5. Seguidament, llistarem els discs, després seleccionarem el disc 0, llistarem les particions i escollirem la primera ja que és on està el gestor d'arrencada. Aquesta partició la configurarem com a "active" i després sortirem, per configurar el disc. Introduirem una serie de comandes que  repararan el MBR, la seqüència d'inici BOOT i reconstruirà la base de dades d'arrencada BCD.     
![ubuntu](./fotos/uww6.png)
![ubuntu](./fotos/uww7.png)
![ubuntu](./fotos/uww8.png)

6. El següent que haurem de fer és afegir la iso de gparted per a eliminar la partició d'Ubuntu.        
![ubuntu](./fotos/uww9.png)

7. Seguidament, una vegada encesa la màquina configurarem l'idioma.     
![ubuntu](./fotos/uww10.png)
![ubuntu](./fotos/uww11.png)
![ubuntu](./fotos/uww12.png)

8. Després seleccionarem la partició d'ubuntu i l'eliminarem.        
![ubuntu](./fotos/uww13.png)
![ubuntu](./fotos/uww14.png)

9. El següent que haurem de fer és guardar el canvis.       
![ubuntu](./fotos/uww15.png)
![ubuntu](./fotos/uww16.png)
![ubuntu](./fotos/uww17.png)





## Instal·lar programari

1. El primer que haurem de fer és anar a la pàgina oficial de Google i descarregar l’executable de Chrome.      
![ap](./fotos/ap1.png)

2. Una vegada descarregat i instal·lat iniciarem sessió o crearem un compte per començar a utilitzar-lo.        
![ap](./fotos/ap2.png)

3. Seguidament, descarregarem Drive en local per a ordinadors des de la página oficial.         
![ap](./fotos/ap3.png)

4. Després començarem amb la instal·lació.      
![ap](./fotos/ap4.png)

5. A continuació, quan acabi el programa de instal·lar-se clicarem en “Lanzar” per obrir-lo.        
![ap](./fotos/ap5.png)

6. Quan estem dins començarem a configurar algunes opcions i iniciarem sessió.      
![ap](./fotos/ap6.png)
![ap](./fotos/ap7.png)
![ap](./fotos/ap8.png)


## Punts de restauració

1. Obrim el menú Inici i escrivim restauració al quadre de cerca.       

2. Seleccionem l’opció "Crear un punt de restauració" dels resultats que apareixen.     

3. A la finestra que s’obre, anem a la pestanya "Protecció del sistema" i fem clic al botó "Crear..." que hi ha a la part inferior de la finestra.      
![restauracio](./fotos/rest1.png)

4. Escrivim un nom per identificar el punt de restauració.        
![restauracio](./fotos/rest2.png) 

5. Fem clic a "Crear" per iniciar la creació del punt. El procés pot durar uns minuts.      
![restauracio](./fotos/rest3.png) 

6. Quan ens aparegui el missatge que indica que s’ha creat correctament, fem clic a "Tancar".       
![restauracio](./fotos/rest4.png) 

7. El primer que haurem de fer és anar a la pàgina oficial i descarregar l’executable de winrar.            
![restauracio](./fotos/rest5.png) 

8. Una vegada descarregat, l'instal·larem.        
![restauracio](./fotos/rest6.png) 
![restauracio](./fotos/rest7.png) 
![restauracio](./fotos/rest8.png) 
![restauracio](./fotos/rest9.png) 
![restauracio](./fotos/rest10.png)
![restauracio](./fotos/rest11.png)

9. Després afegirem una carpeta amb un quants fitxers, per després demostrar que les resturacions no afecten als arxius.        
![restauracio](./fotos/fit1.png)
![restauracio](./fotos/fit2.png) 

9. Seguidament clicarem en "Restaurar sistema...", escollirem la restauració que hem creat abans i esperarem.       
![restauracio](./fotos/rest12.png)
![restauracio](./fotos/rest13.png)
![restauracio](./fotos/rest14.png)
![restauracio](./fotos/rest15.png)
![restauracio](./fotos/rest16.png)
![restauracio](./fotos/rest17.png)

10. Quan acabi la restauració ens sortira un missatge de que s'ha fet correctament i veurem que el winrar ja no esta instal·lat. A més de que els arxius continuen estan.        
![restauracio](./fotos/rest18.png)
![restauracio](./fotos/rest19.png)
![restauracio](./fotos/fit2.png) 







