# Practica1SOII
# Practica 1 Sistemas Operativos 2
# Intergrantes: Alejandro Velazquez Peña, Montserrat Valencia Garaicochea, Raul Pallas Talavera y Diego Jair Hernandez Monter

##########################################################################################################################################################################
### Sda = El primer disco detectado.
### Hda = Partición individual en el disco
### Vda = Es el primer controlador del disco 
### Los discos se muestran en orden alfabetico por ejemplo sda es el primer disco detectado, sdb el segundo y asi ..., Los numeros se refieren a particiones por ejemplo:
### Sda1 significa que es la primera particion del Primer disco duro o del disco maestro.

### HDA
Cuando se habla de dev/hda se esta hablando del disco maestro en el controlador primario.
El nombre base de un disco controlado por (E)IDE es dev/hd? El "?" es una sola letra. Para GRUB esto equivale a hd"?" El "?" equivale a las posiciones 1 a 4.

Nombre de la unidad
dev/hda: disco maestro en la primera controladora
dev/hdb: disco esclavo en la primera controladora
dev/hdc: disco maestro en la segunda controladora
dev/hdd: disco esclavo en la segunda controladora
Nombre de GRUB
hd1: disco maestro en la primera controladora
hd2: disco esclavo en la primera controladora
hd3: disco maestro en la segunda controladora
hd4: disco esclavo en la segunda controladora
La denominación de las particiones es sencilla, ya que se adjunta un número al dispositivo apropiado.

### SDA
Unidades de interfaz serial de adjunto de tecnología avanzada (SATA)
Con la llegada de las unidades SATA, la convención cambió y en la actualidad se utiliza mayormente sda en lugar de hda para referirse a los discos duros. Donde sd quiere decir serial drive (unidad de serie).

Tablas de partición
Una tabla de partición muestra las particiones de un disco duro o de cualquier dispositivo de almacenamiento. Existen dos estándares para el diseño de la tabla de partición:

Registro de inicio maestro (MBR): MBR, también conocido como ms-dos, es lo que se puede llamar el estándar original. MBR sigue siendo la tabla de partición mayormente utilizada y viene con dos importantes limitaciones

No permite la creación de más de cuatro particiones principales. Dichas particiones se denominan particiones primarias.

Las particiones del disco no deben exceder los 2 TB.

Tabla de partición GUID (GPT): GPT salió más adelante. Aunque MBR aún está en uso, sus limitaciones impulsaron el desarrollo de GPT. GPT supera las dos limitaciones de MBR. Puede tener múltiples limitaciones primarias y los tamaños de las unidades pueden exceder los 2 TB.

### VDA
sirve para unidades de disco virtual. Todo lo que hace el kernel cuando está en E / S es decirle al software de virtualización que los bits deben leerse / escribirse y listo. En general, vdxes más rápido porque el kernel no necesita decirle al disco duro que haga un montón de basura aleatoria que realmente no debería ser necesaria porque solo necesita decirle al hipervisor de VM que haga cosas.

#########################################################################################################################################################################


___ _  _ ___ ____ ____ _ ____ _    
 |  |  |  |  |  | |__/ | |__| |    
 |  |__|  |  |__| |  \ | |  | |___ PARA MONTAR Y DESMONTAR UNA USB EN NUESTRO PC LINUX UTILIZAREMOS LOS SIGUIENTES COMANDOS EN TERMINAL PARA MONTAR "MOUNT" y "UMOUNT" para desmontar el usb
##PARA INICIAR EL TUTORIAL ES NECESARIO ABRIR UNA TERMINAL 
### 1.- INSERTAMOS LA USB FLASH AL ORDENADOR. (NORMALMENTE CUANDO CONECTAMOS LA USB SE MONTA AUTOMATICAMENTE LO CUAL NO NOS SERVIRA PARA ESTE TUTORIAL)
   1.0.- PARA SABER EN DONDE ESTA LA USB FLASH MONTADA ES NECESARIO ABRIR UNA TERMINAL (ctrl + ALT + T EN LINUX).
    ![image](https://user-images.githubusercontent.com/100113533/155017463-1d4359c0-a8a9-4a84-93b6-2ed6ebc4d9f6.png)
    
   SEGUIDO DEL SIGUIENTEs COMANDOS: 
        
         ls /dev/sd*
         df - h
    
   ![image](https://user-images.githubusercontent.com/100113533/155020738-f2ee12a5-1bf4-4709-9cbf-b055db362aaf.png)
    
   COMO PODEMOS OBSERVAR EN LA IMAGEN LA USB FLASH CUENTA CON 3 PARTICIONES, IGUALMENTE CON EL COMANDO df -h NOS DAREMOS CUENTA EN DONDE ESTA MONTADA LA USB
   Y NORMALMENTE EL ULTIMO TEXTO QUE APARECE AL EJECUTAR EL COMANDO 
        
        ls /dev/sd* 
        df -h
        
   ES LA USB MONTADA AUTOMATICAMENTE. TENEMOS AQUI QUE LA USB ESTA DETECTADA O MONTADA
   EN /dev/sdb (indicando que es el segundo disco duro detectado) LA CUAL TIENE 3 PARTICIONES /dev/sdb1 /dev/sdb2 y /dev/sdb3
   
   1.1 UNA VEZ LOCALIZADA LA VAMOS A DESMONTAR CON EJECUTANDO EL SIGUINTE COMANDO: 
  
  
    sudo umount /dev/sd** en los asteriscos van los identificador por defecto que el sistema
    le pone por defecto. 
   EN ESTE CASO VOY A DESMONTAR AMBAS PARTICIONES DE LA USB FLASH QUE ME APARECEN, UNA VES INGRESADO EL COMANDO OS PEDIRA LA CONTRASEÑA DEL EQUIPO
   
   ![image](https://user-images.githubusercontent.com/100113533/155027086-4488688f-87a0-4447-8024-7ad171624793.png)
   
   Y COMO PODEMOS OBSERVAR SI EJECUTAMOS EL COMANDO
    
    df -h 
   
   LA UNIDAD FLASH ESTARA DESMONTADA.
   
   ![image](https://user-images.githubusercontent.com/100113533/155027251-ae482924-7105-4b75-9bf7-bea1d6d57b6b.png)
   
   ### MONTANDDO LA UNIDAD FLASH DE NUEVO----------------------
   
   2.- CREAMOS UN DIRECTORIO CON EL NOMBRE QUE GUSTES PERO QUE RECUERDES, EN MI CASO LA LLAMARE USB, USANDO EL SIGUIENTE COMANDO 
   
    mkdir *nombre de tu directorio*
    
   Y CON EL COMANDO "ls" mostrara el directorio que hemos creado.
   
   ![image](https://user-images.githubusercontent.com/100113533/155028351-5ffdfdf5-5f84-44c6-8b30-06deaa27a989.png)

   CON EL COMANDO: 
     
     ls /dev/sd* mostraremos en que direccion esta la usb desmontada.
   
   ![image](https://user-images.githubusercontent.com/100113533/155029350-848b7464-befb-4c2f-bf29-3a3e4382df86.png)
  
   Y OBTUVIMOS LA DIRECCION /dev/sdb1 la cual esta desmontada,  si volvemos a usar el comando umount nos dira que no esta montada.
   UNA VEZ LOCALIZADA VAMOS A EJECUTAR EL SIGUIENTE COMANDO EN CONSOLA: "sudo mount /dev/sdb1" seguido de la ubicacion en donde quieran montar la unidad flash(en este caso para    mi es sdb pero dependiendo de cuantas unidades de almacenamiento tengan este puede cambiar)
   EL COMANDO EN MI CASO QUEDA ASI: 
             
              sudo mount /dev/sdba1 ./usb
   
   ![image](https://user-images.githubusercontent.com/100113533/155036051-f1d25d9f-dca4-448a-9d01-56007f7e043e.png)
   
   Y QUEDARÁ MONTADA.
  
  ### 3.- Enlistar la información de los dispositivos de bloque conectados aunque no estén montados en terminal.
  Para desplegar la información de los dispositivos de bloque introducimos el siguiente comando en terminal:
         
          sudo fdisk -l
   ![image](https://user-images.githubusercontent.com/100113533/155036446-0dba2d30-5dc1-40db-bf3d-cf27f37c8ec7.png)
   ![image](https://user-images.githubusercontent.com/100113533/155036491-d7072b68-9caf-4da3-8aad-668940add450.png)
 
 ### 4.-  Mostrar la tabla de particiones del disco donde está instalado el sistema operativo en terminal.
  EJECUTAREMOS LA SIGUIENTE LINEA DE CODIGO
  
      lsblk
  
  ![image](https://user-images.githubusercontent.com/100113533/155036650-9a11a2f9-074c-4201-b025-a15eca0feeb3.png)

### 5.- Conectar una memoria usb (“usb”) y mostrar su tabla de particiones en terminal (hacer respaldo antes porque se va a borrar toda la información dentro del usb en pasos posteriores).

![image](https://user-images.githubusercontent.com/100113533/155037185-fcf5a5b5-83cd-42b4-a7d4-3358ba8c8c04.png)

### 6.- Borrar todas las particiones del “usb” en terminal
  PRIMERO DEBEMOS SABER EN DONDE ESTA LA USB PARA ESO PODEMOS USAR LA SECCION 1 DE ESTE TUTORIAL.
  UNA VEZ LOCALIZADA EJECUTAREMOS EL SIGUIENTE COMANDO EN TERMINAL
  
    sudo fdisk /dev/sdb
   
   ![image](https://user-images.githubusercontent.com/100113533/155038723-b34df40b-909f-4aff-887b-0a13659d37fc.png)

  TECLEAMOS LA TECLA "P" Y LUEGO "D" y quedaran eliminadas todas las particiones y para guardar cambios basta con teclear una "W" y darle un ENTER y listo
  
  ![image](https://user-images.githubusercontent.com/100113533/155039263-09f2e8d3-7ce9-4a84-a8fa-a1d1d081e873.png)
  
 ### 7.- Crear en el “usb” tres particiones físicas y una extendida en terminal
 seleccionaremos el disco, conociendo su direccion apoyandonos en la seccion 1 de estutorial, correremos en el siguiente comando para entrar en "DISK"
 
    fdisk /dev/sdb
    
 UNA VEZ AHÍ VAMOS A EJECUTAR UNA "P" EN CONSOLA PARA VER CUANTAS PARTICIONES TIENE EL DISCO
  ![image](https://user-images.githubusercontent.com/100113533/155040683-2276d536-958a-463b-ba21-9c97966e84a2.png)
AHI MISMO VAMOS A CREAR NUESTRAS 3 PARTICIONES, PARA ESO VAMOS A EJECUTAR UNA "N" EN CONSOLA Y NOS SALDRA EL SIGUIENTE MENU
![image](https://user-images.githubusercontent.com/100113533/155040778-6e916cad-3947-43d3-a94a-eb60dc1824ae.png)
NOS PREGUNTA PARTICION DE QUE TIPO VAMOS A CREAR, PRIMERO CREAREMOS NUESTRAS 3 PRIMERAS PARTICIONES POR LO QUE DEBEREMOS DE EJECUTAR UNA "P" Y SIGUIENTE ESCRIBIR EL NUMERO DE LA PARTICIÓN EN ESTE CASO VAMOS A CREAR LAS TRES RESPETANDO EL ORDEN NUMERICO 1 2 Y 3
![image](https://user-images.githubusercontent.com/100113533/155040942-2e54ea07-9834-4fde-87ed-57ecd2562d72.png)
DESPUES TENDREMOS QUE DAR UN "ENTER" PARA CONFIRMAR EL SECTOR, Y AHORA DEBEREMOS DAR EL TAMAÑO DE LA PARTICIÓN EN MI CASO LA VOY A HACER DE 2GB POR LO QUE DEBERÉ DE TECLEAR LO SIGUIENTE
    
    +2GB "ENTER"
    
 Y LA PARTICION SE CREARA
 
 ![image](https://user-images.githubusercontent.com/100113533/155041908-b49dd8e0-4efd-488e-b9f8-a823b19976d3.png)

 HAREMOS LO MISMO PARA CREAR LAS 2 PARTICIONES EXTRAS PEDIDAS
 
 ![image](https://user-images.githubusercontent.com/100113533/155042179-ebca7230-d796-46aa-adf5-11f66b71d67e.png)
 
 POR ULTIMO VAMOS A CREAR UNA PARTICION EXTENDIDA, EN EL MISMO MENU DE "fdisk" VAMOS A TECLEAR UNA "N" Y NOS SALDRÁ DE NUEVO EL MENU Y TECLEAREMOS LA LETRA "E" DAREMOS ENTER YA QUE SOLO SOBRA EL ESPACIO 4 PARA LA PARTICION EXTENDIDA Y DAREMOS OTRO ENTER PARA SELECCIONAR EL SECTOR
 
 
 ![image](https://user-images.githubusercontent.com/100113533/155042479-f49def9d-2f25-45d1-8876-0516a1a82fd3.png)

Y POR ULTIMO DAREMOS EL TAMAÑO DE ESTA EN MI CASO VOY A HACERLA DE 2 GB

      +2GB "ENTER"

![image](https://user-images.githubusercontent.com/100113533/155042650-39a4bd8d-ebfa-4d86-8c95-1cbec48a1488.png)

Y LISTO TENDREMOS NUESTRA PARTICION EXTENDIDA CREADA

### 8.- CREAR PARTICION DENTRO DE LA PARTICION EXTENDIDA
    
 VAMOS A APLICAR EL COMANDO
 
    cfdisk /dev/sdb
    
 Y NAVEGAREMOS A DONDE NOS DICE ESPACIO LIBRE Y AHÍ LE DAREMOS A NEW Y HAREMOS LOS PASO DE LA SECCION PASADA PARA CREAR LA PARTICION
 
 ![image](https://user-images.githubusercontent.com/100113533/155043854-eeba4e74-f45d-4d0c-8f77-21a649d6662b.png)
 
 DAREMOS 2 ENTER Y NOS DARA EL TAMAÑO DE LA PARTICION Y OTRO ENTER Y LA PARTICION QUEDARÁ HABILITADA DENTRO DE LA PARTICION EXTENDIDA
 
 ![image](https://user-images.githubusercontent.com/100113533/155043948-286ca47a-d7b0-485d-b4f7-423d7b489c70.png)

### 9.- En la interfaz gráfica de la aplicación disks, borrar las particiones para que sólo exista una partición que abarque toda la “usb”

PARA ESTO VAMOS A UTILIZAR EL COMANDO 

    fdisk /dev/sdb
 Y VAMOS A BORARR TODAS LAS PARTICIONES Y NOS APOYAREMOS DE LOS BLOQUES 2 y 3 DE ESTE TUTORIAL
 
 ![image](https://user-images.githubusercontent.com/100113533/155044281-a3903087-ca2d-47f5-8ea2-b5840902f03a.png)
 
YA ESTA CREADA LA PARTICION QUE OCUPA TODA LA USB

### 10.- POR ULTIMO VAMOS A COPIAR UN ISO DE UN SO EN LA USB UTILIZANDO EL COMANDO dd

PRIMERO VAMOS A DESCARGAR EL ISO EN NUESTRA MAQUINA
![image](https://user-images.githubusercontent.com/100113533/155045090-6598f122-9b01-4c06-9247-b02f89d1fef5.png)
UNA VEZ OBTENIDA LA DIRECCION EN DONDE SE GUARDO EL ISO VAMOS A IR A TERMINAL Y UTILIZAR EL COMANDO

  
    dd if=Downloads/archivo.iso if=/dev/sdb1
    
    
![image](https://user-images.githubusercontent.com/100113533/155045819-5368fe97-a972-4c56-98c4-6c0f34ba46f5.png)

EL ARCHIVO ISO SE COPIARA CON EXITO A LA MEMORIA FLASH

    
 




