# Dominis 


Per a la documentació completa visita [mkdocs.org](https://www.mkdocs.org).


---
## Introducció

Aquest projecte mostra el procés que he seguit per configurar un domini en una xarxa Windows. L’objectiu principal ha estat aprendre a gestionar usuaris, grups i perfils mòbils per centralitzar la informació, així com aplicar polítiques de seguretat per controlar l’accés als recursos.

També he treballat amb la configuració de servidors de fitxers, d’impressió i d’aplicacions, tot fent proves en màquines virtuals. Durant el projecte, he anat resolent problemes reals que poden aparèixer en un entorn informàtic i he après a aplicar bones pràctiques de seguretat i gestió.

![log](./fotos/fotointros1.jpg)

---

## Instal·lació Domini AD, Unir equips al domini i Gestió del Domini AD

Un domini és una xarxa controlada centralment on els usuaris i equips comparteixen recursos, com arxius i impressores. Un servidor de domini utilitza Active Directory (AD) per gestionar tots els comptes d’usuaris, equips i recursos. Així, els administradors poden controlar qui té accés a què i com es poden fer servir els recursos de la xarxa.

Per començar a usar un domini, primer hem d'instal·lar Active Directory Domain Services (AD DS) en un servidor. Aquest servidor es converteix en el controlador de domini, el cervell que controla qui pot entrar i què pot fer a la xarxa. Un cop tenim el domini creat, els equips poden unir-se al domini perquè els usuaris hi accedeixin fàcilment des de qualsevol dispositiu que estigui configurat per al domini.

### Creació del domini

1. El primer que haurem de fer és desactivar el Firewall de Windows, es necessari per que els clients i el servidor puguin estar comunicats.        
![domini](./fotos/ac1.png) 
![domini](./fotos/ac2.png) 
![domini](./fotos/ac3.png) 

2. Seguidament, canviarem el nom de l'equip, així ens serà més fàcil gestionar l'Active Directory.      
![domini](./fotos/ac4.png) 
![domini](./fotos/ac5.png) 
![domini](./fotos/ac6.png)

3. A més revisarem la configuració de xarxa i comprovarem que tenim connexió a internet.        
![domini](./fotos/ac52.png)
![domini](./fotos/ac53.png)

4. A continuació, en el panel de control del Windows Server clicarem en "Administrar", "Agregar roles y caracteristicas" i anirem clicant següent.      
![domini](./fotos/ac7.png) 
![domini](./fotos/ac8.png) 
![domini](./fotos/ac9.png) 
![domini](./fotos/ac10.png)

5. Aquí és important seleccionar l'opció "Servicios de dominio de Active Directory" i continuar amb el procés.      
![domini](./fotos/ac11.png)
![domini](./fotos/ac12.png)
![domini](./fotos/ac13.png)
![domini](./fotos/ac14.png)
![domini](./fotos/ac15.png)

6. Quan acabi, en les notificacions clicarem a "Promover este servidor a controlador de dominio".       
![domini](./fotos/ac16.png)

7. Aqui haurem d'afegir un nou bosc i crear un nom de domini, en aquest cas el meu és MARIA.local.      
![domini](./fotos/ac17.png)

8. Seguidament, li assignarem una contrasenya, aquest és important que sigui segura i evidenment recordar-la, ja que sinó hauríem de començar de nou.       
![domini](./fotos/ac18.png)

9. Continuarem clicant en següent fins que acabi la instal·lació i es reinicie automaticament.      
![domini](./fotos/ac19.png)
![domini](./fotos/ac21.png)
![domini](./fotos/ac22.png)
![domini](./fotos/ac23.png)
![domini](./fotos/ac24.png)

10. Un indicador de que el procés a sortit bé és que al inciar sessió com a adminitrador aparegui el nom del domini.        
![domini](./fotos/ac29.png)

---

### Usuaris, equips, grups i UOs

1. El primer que haurem de fer per crear usuaris, grups i UOs és clicar en "Herramientas" i després en "Usuarios y equipos de Active Directory".        
![domini](./fotos/ac30.png)

2. Per crear les Unitats Organitzatives haurem de clicar a sobre de MARIA.local (el domini), seleccionar "Nuevo" i clicar en "Unidad Organizativa".     
![domini](./fotos/ac31.png)

3. Seguidament li ficarem un nom, en aquest cas jo la he anomenat "Informatica".        
![domini](./fotos/ac32.png)

4. Ara crearem els grups, aquí haurem de clicar a sobre de la UO, "Nuevo" i "Grupo".        
![domini](./fotos/ac33.png)

5. A continuació li assignarem un nom, en aquest cas he creat el grup Hardware i Software.      
![domini](./fotos/ac34.png)
![domini](./fotos/ac35.png)

6. El següent pas serà crear els usuaris, aquí haurem de configurar tota una serie de dades, com el nom complet.        
![domini](./fotos/ac36.png)
![domini](./fotos/ac37.png)

7. Després li crearem una contrasenya, aquesta a de ser robusta a causa de les politiques de seguretat de Windows. A més podem escollir diferents opcions en respecte a la contrasenya, en aquest cas jo he escollit que no expiri mai.         
![domini](./fotos/ac38.png)
![domini](./fotos/ac39.png)

8. Ara farem el mateix per crear l'usuari Andrea.       
![domini](./fotos/ac40.png)
![domini](./fotos/ac41.png)
![domini](./fotos/ac42.png)

9. Tot seguit, clicarem en les propietats del grup Hardware i afegirem a Andrea.        
![domini](./fotos/ac43.png)
![domini](./fotos/ac44.png)
![domini](./fotos/ac45.png)
![domini](./fotos/ac46.png)

10. Per últim, farem el mateix amb l'usuari Maria en el grup Software.      
![domini](./fotos/ac47.png)
![domini](./fotos/ac48.png)
![domini](./fotos/ac49.png)
![domini](./fotos/ac50.png)
![domini](./fotos/ac51.png)

#### UNIR CLIENT A DOMINI

1. El primer que haurem de fer és desactivar el Firewall.       
![domini](./fotos/ugac31.png)
![domini](./fotos/ugac32.png)
![domini](./fotos/ugac33.png)

2. Seguidament comprovarem que ens podem comunicar des de el servidor amb el client.        
![domini](./fotos/ugac34.png)

3. És important que a la configuració de xarxa tinguem com a DNs la ip del server.      
![domini](./fotos/ugac43.png)

3. Després, clicarem en "Propiedades" i "Cambiar configuración".        
![domini](./fotos/ugac36.png)
![domini](./fotos/ugac38.png)

4. A continuació clicarem en "Cambiar..." i habilitarem l'opció de dominio, en la que ficarem el nom del domini.        
![domini](./fotos/ugac39.png)
![domini](./fotos/ugac40.png)
![domini](./fotos/ugac41.png)

5. Afegirem l'usuari administrador del domini i la contrasenya i quan acabi de sincronitzar reiniciem la vm.        
![domini](./fotos/ugac53.png)
![domini](./fotos/ugac45.png)
![domini](./fotos/ugac46.png)
![domini](./fotos/ugac47.png)
![domini](./fotos/ugac48.png)

6. Per últim, iniciem sessió amb l'usuari Maria i comprovem que des de el client ja estem connectats al domini. Una altra forma de verificar és anant al servidor, "Computers" i ens apareixerà el hostname del client.     
![domini](./fotos/ugac49.png)
![domini](./fotos/ugac50.png)
![domini](./fotos/ugac51.png)
![domini](./fotos/ugac52.png)

---

### Perfils mòbils i carpetes personals

Els perfils mòbils permeten que un usuari pugui iniciar sessió en qualsevol ordinador del domini i veure els seus fitxers i configuracions personals. Les carpetes personals són espais d’emmagatzematge en xarxa on els usuaris poden guardar els seus arxius, assegurant que els tingui disponibles sempre que ho necessiti, independentment de l’equip des del qual es connecti.

1. El primer pas serà crear la carpeta Perfils i anar a Propietats.         
![perfils](./fotos/pmac2.png) 
![perfils](./fotos/pmac4.png) 

2. Seguidament li treurem els permisos heredats en "Opciones avanzadas".        
![perfils](./fotos/pmac6.png) 
![perfils](./fotos/pmac7.png) 
![perfils](./fotos/pmac8.png) 

3. Després treurem tots els usuaris que hi han menys Administradores i seguidament afegirem els grups de la UO Informatica.     
![perfils](./fotos/pmac9.png) 
![perfils](./fotos/pmac10.png)
![perfils](./fotos/pmac11.png)

4. Ara clicarem en "Compartir..." i quan sobri la finestra tornarem a clicar en "Compartir".        
![perfils](./fotos/pmac14.png)
![perfils](./fotos/pmac15.png)
![perfils](./fotos/pmac16.png)

5. Seguidament anirem a l'usuari Andrea i clicarem en "Propiedades", després en "Perfil" i afegirem la ruta de la carpeta "Perfils".        
![perfils](./fotos/pmac1.png) 
![perfils](./fotos/pmac3.png) 

6. A continuació des de l'ordinador client, inciarem sessió amb l'usuari.       
![perfils](./fotos/pmac17.png)
![perfils](./fotos/pmac18.png)

7. Una vegada fet el pas anterior, si tornem al server i revisem el contigut de la carpeta "Perfils" podrem observar que s'ha creat una carpeta amb el username de Andrea.      
![perfils](./fotos/pmac19.png)

8. Tornarem a la màquina client per crear una carpeta anomenada "prova". Ara tot el que creem amb l'usuari Andrea és guardar al server.     
![perfils](./fotos/pmac20.png)

9. Tanquem sessió al client i inciem sessió des de un altre client.     
![perfils](./fotos/pmac21.png)
![perfils](./fotos/pmac22.png)
![perfils](./fotos/pmac23.png)

10. Per últim podrem observar que la carpeta esta quan iniciem sessió encara que sigui una altra màquina virtual.       
![perfils](./fotos/pmac24.png)

---

### Recursos compartits

Els recursos compartits com impressores i carpetes permeten que diversos usuaris de la xarxa accedeixin a aquests elements. Això vol dir que si un ordinador té una carpeta compartida, altres usuaris del domini poden accedir-hi per veure o editar els fitxers que hi ha dins.

#### CARPETES I FITXERS

1. El primer que farem és crear la carpeta "Informes", després anirem a "Propiedades".      
![compartir](./fotos/rcac1.png)

2. Clicarem en "Compartir" i afegirem permisos de lectura només al grup Hardware.       
![compartir](./fotos/rcac2.png)
![compartir](./fotos/rcac3.png)
![compartir](./fotos/rcac4.png)

3. Quan inciem sessió desde el client amb l'usuari Andrea que forma part del grup Hardware, podrem entrar dins de la carpeta, però quan intentessim crear algun fitxer ens sortirà el següent error:       
![compartir](./fotos/rcac5.png)

4. Per últim, si inciem sessió amb l'usuari Maria com forma part només del grup Software quan intente entrar no podrà. Ens sortirà el següent avís:     
![compartir](./fotos/rcac6.png)

5. També podem fer la compartició de fitxers a partir d'un rol, per començar haurem de afegir un nou disc de 5 GB.      
![compartir](./fotos/rc2ac1.png) 
![compartir](./fotos/rc2ac2.png) 
![compartir](./fotos/rc2ac3.png) 
![compartir](./fotos/rc2ac4.png) 
![compartir](./fotos/rc2ac5.png) 
![compartir](./fotos/rc2ac6.png) 
![compartir](./fotos/rc2ac7.png) 
![compartir](./fotos/rc2ac8.png) 
![compartir](./fotos/rc2ac9.png) 

6. Seguidament afegirem el rol de "Administración de recursos del servidor de archivos".        
![compartir](./fotos/rc2ac10.png) 
![compartir](./fotos/rc2ac11.png) 
![compartir](./fotos/rc2ac12.png) 
![compartir](./fotos/rc2ac13.png) 
![compartir](./fotos/rc2ac14.png) 
![compartir](./fotos/rc2ac15.png) 
![compartir](./fotos/rc2ac16.png) 
![compartir](./fotos/rc2ac17.png)

7. A continuació, entrarem en l'apartat de "Recursos compartidos", clicarem en "TAREAS" i "Nuevo recurso compartido...".        
![compartir](./fotos/rc2ac18.png) 

8. Aquí dins escollirem l'opció de "SMB - Avanzado".        
![compartir](./fotos/rc2ac19.png) 

9. Seleccionarem el disc nou, li ficarem un nom al recurs compartit i activarem la primera opció de "Parametros de configuración de recurso compartido".        
![compartir](./fotos/rc2ac20.png) 
![compartir](./fotos/rc2ac21.png) 
![compartir](./fotos/rc2ac22.png) 

10. Seguidament, deixarem els permissos predeterminats, en cas de que volguem aplicar permissos més especifics hauríem de fer el procés d'abans.        
![compartir](./fotos/rc2ac24.png) 

11. Clicarem en l'opció "Archivos de usuario".      
![compartir](./fotos/rc2ac25.png)

12. També tenim l'opció d'aplicar quotes, en aquest cas ens ho saltem perquè aquest tema ja l'hem donat.        
![compartir](./fotos/rc2ac26.png) 

13. Ara clicarem en "Crear" i quan acabi en "Cerrar".       
![compartir](./fotos/rc2ac27.png) 
![compartir](./fotos/rc2ac28.png) 

14. Des de el client anirem a Xarxa i afegirem la ruta.     
![compartir](./fotos/rc2ac29.png)   

15. Després crearem una carpeta.        
![compartir](./fotos/rc2ac30.png) 

16. En el servidor farem clic dret al recurs compartit i seleccionarem l'opció "Abrir recurso compartido".      
![compartir](./fotos/rc2ac31.png) 

17. Al obrir-ho podrem veure que està la carpeta creada amb el client.      
![compartir](./fotos/rc2ac32.png)

#### IMPRESSORES

1. El primer que haurem de fer és afegir un rol nou, aquest s'anomena "Servicios de impresión y documentos".        
![impressores](./fotos/imp1.png) 
![impressores](./fotos/imp2.png) 
![impressores](./fotos/imp3.png) 
![impressores](./fotos/imp4.png) 
![impressores](./fotos/imp5.png) 
![impressores](./fotos/imp6.png) 
![impressores](./fotos/imp7.png) 
![impressores](./fotos/imp8.png) 
![impressores](./fotos/imp9.png) 
![impressores](./fotos/imp10.png) 
![impressores](./fotos/imp11.png) 

2. Seguidament, desplegarem "Herramientas" i clicarem en "Administración de impresión".     
![impressores](./fotos/imp12.png) 

3. Aquí dins farem clic dret a sobre del domini i seleccionarem l'opció "Agregar impresora...".     
![impressores](./fotos/imp13.png) 

4. Tot seguit, podrem buscar la impressora o afegir-la manualment.      
![impressores](./fotos/imp14.png) 

5. Si escollim l'opció d'afegir-la manualment només haurem de ficar la ip o el nom especific.       
![impressores](./fotos/imp15.png) 

6. En aquest cas jo no tinc cap impressora, per tant no puc continuar el procés.        
![impressores](./fotos/imp16.png) 

7. Una vegada la tinguessim afegida, hauriem d'anar a "Propiedades" i "Compartir", el procés és similar al de compartir una carpeta.        
![impressores](./fotos/imp17.png)

---

## Polítiques de seguretat (GPOs)

Les Polítiques de Grup (GPOs) són un conjunt de regles que permeten als administradors controlar l’accés i la seguretat dins del domini. Per exemple, les GPOs poden configurar coses com les contrasenyes (quina complexitat han de tenir), els permisos d’accés a recursos, o les restriccions d'ús de programes. Això ajuda a garantir que els equips i usuaris de la xarxa segueixin unes normes de seguretat comunes.

1. El primer pas serà anar a "Herramientas" i "Administración de directivas de grupo".      
![GPO](./fotos/gpo1.png) 

2. Després clicarem en editar la GPO predeterminada i entrarem dins de "Directiva de contraseña".       
![GPO](./fotos/gpo2.png) 
![GPO](./fotos/gpo3.png) 
![GPO](./fotos/gpo4.png)

3. Seguidament en les propietats de la segona i cinquena opció configurarem que la longitud mínima del les contrasenyes sigui de 12 caracters.      
![GPO](./fotos/gpo5.png) 
![GPO](./fotos/gpo6.png) 
![GPO](./fotos/gpo7.png) 
![GPO](./fotos/gpo8.png) 
![GPO](./fotos/gpo9.png) 

4. Ara comprovarem que funcioni correctament, crearem un nou usuari i li ficarem una contrasenya de 4 carcters. Quan cliquem en "Finalizar" podrem observar que salta un error de contrasenya.      
![GPO](./fotos/gpo10.png)
![GPO](./fotos/gpo11.png)
![GPO](./fotos/gpo12.png)
![GPO](./fotos/gpo13.png)
![GPO](./fotos/gpo14.png)

5. Tot seguit, introduirem una contrasenya de 12 caracters i podrem observar que ja funciona.       
![GPO](./fotos/gpo15.png)
![GPO](./fotos/gpo16.png)
![GPO](./fotos/gpo17.png)

6. La segona GPO la crearem nosaltres, haurem de clicar en el nom del domini i clicar ne la primera opció.      
![GPO](./fotos/gpo18.png)
![GPO](./fotos/gpo19.png)

7. A continuació clicarem "Editar..." i entrarem en "Menu inicio y barra de tareas".        
![GPO](./fotos/gpo20.png)
![GPO](./fotos/gpo21.png)

8. Clicarem la quarta opció, aquesta serveix per no poder utilitzar les opcions d'apagar, reiniciar, suspendre o inverna el sistema.        
![GPO](./fotos/gpo22.png)

9. Seguidament clicarem en "Habilitada", quan anesim a apagar la màquina ja no podrem.      
![GPO](./fotos/gpo23.png)
![GPO](./fotos/gpo24.png)
![GPO](./fotos/gpo25.png)

10. Per fer la tercera GPO només la aplicarem en la UO Informatica.     
![GPO](./fotos/gpo26.png)
![GPO](./fotos/gpo27.png)
![GPO](./fotos/gpo28.png)

11. Haurem d'anar a "Active Desktop" i editar l'opció "Tapiz de escritorio".        
![GPO](./fotos/gpo29.png)

12. Seguidament anirem a C: i crearem la carpeta GPO. A més anirem a les propietats i compartirem la carpeta.       
![GPO](./fotos/gpo30.png)
![GPO](./fotos/gpo31.png)
![GPO](./fotos/gpo32.png)
![GPO](./fotos/gpo33.png)
![GPO](./fotos/gpo34.png)
![GPO](./fotos/gpo35.png)

13. Dins afegirem una foto per al fons de pantalla.     
![GPO](./fotos/gpo36.png)

14. Tornarem on ens habiem quedat abans amb la configuració de la GPO i clicarem en "Habilitada". A més a més, ficarem la ruta d'on està la foto per al fons de pantalla.       
![GPO](./fotos/gpo37.png)
![GPO](./fotos/gpo38.png)

15. Des de el terminal del Server actualitzarem les GPOs.       
![GPO](./fotos/gpo41.png)

16. Per últim iniciarem sessió amb un dels usuaris de la UO Informatica, com podem observar automaticament se li assigna el fons de pantalla.       
![GPO](./fotos/gpo42.png)


---

## Connexió remota

La connexió remota permet a un usuari o administrador connectar-se a un equip del domini des de qualsevol lloc a través d’Internet. Això és útil per resoldre problemes a distància, gestionar equips, o accedir a dades com si fossis davant de l’ordinador. La connexió remota es fa sovint mitjançant RDP (Remote Desktop Protocol), que permet controlar l'ordinador de forma visual i interactiva des d'un altre dispositiu.

1. El primer que haurem que fer és anar a Servidor local, "Escritorio remoto" i clicar en "Deshabilitado".      
![remot](./fotos/re1.png) 

2. Seguidament, clicarem en "permitir" i tancarem.      
![remot](./fotos/re2.png) 

3. Com podem observar al sortir, ara ja fica "Habilitado".      
![remot](./fotos/re3.png)

4. En el client, obrirem la aplicació "Connexió a Escritorio Remoto".       
![remot](./fotos/re4.png) 
 

5. Introduirem la ip i l'usuari.        
![remot](./fotos/re6.png) 

6. Ficarem la contrasenya i començarà a connectar-se.       
![remot](./fotos/re7.png) 
![remot](./fotos/re8.png) 
![remot](./fotos/re9.png)

7. Per últim ja estarem dins.       
![remot](./fotos/re5.png)

---

## Webgrafia

Molta de la informació extreta està al Moodle de 0369 - Implantació de Sistemes Operatius. Seguidament, els següents links són d'internet:

- **YouTube**. Crear un domini amb Windows Server. Disponible a: <https://www.youtube.com/watch?v=ZhoIlrVxy_c>  
- **LabsMac**. Establir fons de pantalla a través d’una GPO. Disponible a: <https://www.labsmac.es/establecer-fondo-de-pantalla-a-traves-de-una-gpo/>  
- **YouTube**. Crear usuaris i unitats organitzatives a Windows Server. Disponible a: <https://www.youtube.com/watch?v=tmr6iMdR6rs>  
- **YouTube**. Configurar perfils mòbils. Disponible a: <https://www.youtube.com/watch?v=dhii6VVLGNU>  
- **YouTube**. Connectar equips al domini. Disponible a: <https://www.youtube.com/watch?v=NimRpg_X9I4>

---