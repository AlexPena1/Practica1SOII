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
 |  |__|  |  |__| |  \ | |  | |___ PARA MONTAR Y DESMONTAR UNA USB EN NUESTRO PC LINUX 
 
#UTILIZAREMOS LOS SIGUIENTES COMANDOS EN TERMINAL PARA MONTAR "MOUNT" y "UNMOUNT" para desmontar el usb
##PARA INICIAR EL TUTORIAL ES NECESARIO ABRIR UNA 
### 1.- INSERTAMOS LA USB FLASH AL ORDENADOR. (NORMALMENTE CUANDO CONECTAMOS LA USB SE MONTA AUTOMATICAMENTE LO CUAL NO NOS SERVIRA PARA ESTE TUTORIAL)
   1.0.- PARA SABER EN DONDE ESTA LA USB FLASH MONTADA ES NECESARIO ABRIR UNA TERMINAL (ctrl + ALT + T EN LINUX).
    
