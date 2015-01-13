## Introducción

<div class="container">
<div class="row">
    <div class="col-xs-11 col-sm-11 col-md-11 col-lg-11">
        <a class="fancybox" href="img/tipos_de_hd.png" data-fancybox-group="gallery" title="Introducción">
        <img height="550px" src="img/tipos_de_hd.png" alt="Introducción">
        </a>
    </div>
</div>
</div>

note:
* Hard disks can be classified in many ways; however, from a Linux point of view, the most important distinction between disk types is how the disks interface with the computer



## PATA (I)

* *P*arallel *A*dvanced *T*echnology *A*ttachment
* Antes conocido como *I*ntegrated *D*evice *E*lectronics (IDE), o *E*nhanced *IDE* (EIDE)

<a class="fancybox" href="img/pata1.png" data-fancybox-group="gallery" title="Introducción">
<img height="350px" src="img/pata1.png" alt="Introducción">
</a>

note:
* The Parallel Advanced Technology Attachment (PATA) interface was once king of the PC marketplace.
* Previously known as ATA, Integrated Device Electronics (IDE), or Enhanced IDE (EIDE),
* PATA devices are characterized by wide 40- or 80-pin ribbon cables for data transfer.
* These cables can connect up to two disks to a single connector on a motherboard or plug-in PATA card.



## PATA (II)

<div class="container">
<div class="row">
    <div class="col-xs-7 col-sm-7 col-md-7 col-lg-7 col-centered">
<a class="fancybox" href="img/pata2.png" data-fancybox-group="gallery" title="Introducción">
<img height="550px" src="img/pata2.png" alt="Introducción">
</a>
    </div>
</div>
</div>

note:
* In years past, PATA drives had to be configured as master or slave via a jumper;
* but modern PATA drives have an auto-configure setting that works well in most cases.
* The term ATA today often refers to either PATA or the more recent SATA (described next).
* A data format associated with ATA, the ATA Packet Interface (ATAPI), enables ATA to be used for devices other than hard disks, such as optical discs.



## PATA (III)

<div class="container">
<div class="row">
    <div class="col-xs-12 col-sm-12 col-md-12 col-lg-12 col-centered">
        <a class="fancybox" href="img/pata3.png" data-fancybox-group="gallery" title="Precios IDE">
        <img height="550px" src="img/pata3.png" alt="Precios IDE">
        </a>
    </div>
</div>
</div>

note:



## SATA (I)

* Serial ATA (SATA) es el sucesor de SATA

<div class="container">
<div class="row">
    <div class="col-xs-10 col-sm-10 col-md-10 col-lg-10 col-centered">
        <a class="fancybox" href="img/sata1.png" data-fancybox-group="gallery" title="Conexión SATA">
            <img height="450px" src="img/sata1.png" alt="Conexión SATA">
        </a>
    </div>
</div>
</div>

note:
* The Serial ATA (SATA) interface is the successor to PATA.
* SATA drives use much slimmer cables
* Each SATA cable connects one device to the motherboard or SATA controller card, obviating the need for jumper configuration related to the drive identification.



## SATA (II)

<div class="container">
<div class="row">
    <div class="col-xs-10 col-sm-10 col-md-10 col-lg-10 col-centered">
        <a class="fancybox" href="img/esata.png" data-fancybox-group="gallery" title="Conexión ESATA">
<img height="450px" src="img/esata.png" alt="Conexión ESATA">
</a>
    </div>
</div>
</div>

note:
* Although most SATA devices are internal to the computer, an external variant of the protocol, known as eSATA, is used by some external drives.



## SATA (III)

<div class="container">
<div class="row">
    <div class="col-xs-10 col-sm-10 col-md-10 col-lg-10 col-centered">
        <a class="fancybox" href="img/sata2.png" data-fancybox-group="gallery" title="Precios SATA">
        <img height="450px" src="img/sata2.png" alt="Precios SATA">
        </a>
    </div>
</div>
</div>

note:



## SCSI (I)

* *S*mall *C*omputer *S*ystem *I*nterface (SCSI)

<div class="container">
<div class="row">
    <div class="col-xs-9 col-sm-9 col-md-9 col-lg-9 col-centered">
        <a class="fancybox" href="img/scsi.png" data-fancybox-group="gallery" title="SCSI">
<img height="450px" src="img/scsi.png" alt="SCSI">
</a>
    </div>
</div>
</div>

note:
* The Small Computer System Interface (SCSI) standard physically resembles PATA, in that it uses ribbon cables, although they’re slightly wider, with 50 pins.
* SCSI supports up to 8 or 16 devices per cable, depending on the SCSI version,
* SCSI host adapter in the computer counts as a device, so the limit on the number of disks is seven or fifteen.
* In the past, SCSI was the favorite for servers and high-end workstations.



## SCSI (II)
### SAS (*S*erial *A*ttached *S*CSI)

<div class="container">
<div class="row">
    <div class="col-xs-9 col-sm-9 col-md-9 col-lg-9 col-centered">
        <a class="fancybox" href="img/sas1.png" data-fancybox-group="gallery" title="Precios SATA">
            <img height="450px" src="img/sas1.png" alt="Precios SATA">
        </a>
    </div>
</div>
</div>

note:
* Today, SCSI has faded in popularity, but SCSI devices are still available.
* A next-generation SCSI interface, known as Serial Attached SCSI (SAS), is also available.
* In addition to being the next-generation SCSI interface, SAS is a step toward integrating the SCSI and ATA lines.



## SCSI (III)

<div class="container">
<div class="row">
    <div class="col-xs-11 col-sm-11 col-md-11 col-lg-11 col-centered">
        <a class="fancybox" href="img/sas2.png" data-fancybox-group="gallery" title="Precios SAS">
            <img height="550px" src="img/sas2.png" alt="Precios SAS">
        </a>
    </div>
</div>
</div>

note:



## *U*niversal *S*erial *B*us (I)

<div class="container">
<div class="row">
    <div class="col-xs-10 col-sm-10 col-md-10 col-lg-10 col-centered">
        <a class="fancybox" href="img/usb.png" data-fancybox-group="gallery" title="Precios SAS">
<img height="550px" src="img/usb.png" alt="Precios SAS">
</a>
    </div>
</div>
</div>

note:
* The Universal Serial Bus is a popular method of interfacing external devices, including portable hard disks and USB flash drives.
* The first and second generations of USB are poor performers compared to all but rather elderly dedicated hard disk interfaces, but USB 3.0 greatly improves USB speed.



## USB (II)

<div class="container">
<div class="row">
    <div class="col-xs-12 col-sm-12 col-md-12 col-lg-12 col-centered">
<a class="fancybox" href="img/usb2.png" data-fancybox-group="gallery" title="Precios SAS">
<img height="550px" src="img/usb2.png" alt="Precios SAS">
</a>
    </div>
</div>
</div>

note:



## Conjunto de drivers

* Desde un punto de vista software, los distintos dispositivos se tratan con:
* PATA drivers:
  * Identificados en el núcleo como ATA/ATAPI/MFM/RLL
  * Oficialmente en desuso.
  * Los nombre que se dan a los dispositivos son `/dev/hd*`
* SCSI drivers:
  * Se usan para dispositivo SCSI, SATA, SAS...
  * Los nombre que se le dan a los dispositivos son `/dev/sd*` salvo los dispositivos óptimos que son `/dev/sr*`



## Identificación  dispositivos (I)

* ¿Cómo hacemos referencia a un dispositivo?
 * Persistentes (inmutable a cambio de configuración y sistema)
 * No persistentes (cambiante con el sistema)



## Identificación  dispositivos (II)
### No Persistente (I)

<div class="container">
<div class="row">
    <div class="col-xs-5 col-sm-5 col-md-5 col-lg-5 col-centered">
<a class="fancybox" href="img/lun.png" data-fancybox-group="gallery" title="Lun">
<img height="550px" src="img/lun.png" alt="lun">
</a>
    </div>
</div>
</div>

Identificación mediante camino: HBA + #Channel + #Id + LUN (*Logical Unit Number*)

note:

* The operating system issues I/O to a storage device by referencing the path that is used to reach it.
* For SCSI devices, the path consists of the following:
 * PCI identifier of the host bus adapter (HBA)
 * channel number on that HBA
 * the remote SCSI target address
 * the Logical Unit Number (LUN)



## Identificación  dispositivos (III)
### No Persistente (II)

* Los principales sistemas no persistentes:
    * `/dev/sd*`
    * major:minor number
```
brw-rw---- 1 root disk 8,  1 dic 16 17:13 sda1
```
    * Enlaces simbólicos mantenidos en `/dev/disk/by-path/`
```
pci-0000:02:0e.0-scsi-0:0:0:0 -> ../../sda
```

note:

* This path-based address is not persistent.
* It may change any time the system is reconfigured
*  It is even possible for the path identifiers to change when no physical reconfiguration has been done, as a result of timing variations during the discovery process when the system boots, or when a bus is re-scanned.
* The operating system provides several non-persistent names to represent these access paths to storage devices.
 * One is the /dev/sd name;
 * another is the major:minor number.
 * A third is a symlink maintained in the /dev/disk/by-path/ directory. This symlink maps from the path identifier to the current /dev/sd name.



## Identificación  dispositivos (IV)
### No Persistente (III)

* Desventajas
 * Cambios en el sistema -> cambios en el camino
 * Dependiente del sistema del sistema
 * En sistemas multipath pueden provocar inconsistencias

<div class="container">
<div class="row">
    <div class="col-xs-12 col-sm-12 col-md-12 col-lg-12 col-centered">
<a class="fancybox" href="img/multipath.png" data-fancybox-group="gallery" title="Lun">
<img height="550px" src="img/multipath.png" alt="lun">
</a>
    </div>
</div>
</div>

note:
* It is generally not appropriate for applications to use these path-based names.
* This is because
 * The storage device these paths reference may change, potentially causing incorrect data to be written to the device.
 * Path-based names are also not appropriate for multipath devices, because the path-based names may be mistaken for separate storage devices, leading to uncoordinated access and unintended modifications of the data.
 * In addition, path-based names are system-specific. This can cause unintended data changes when the device is accessed by multiple systems, such as in a cluster.
* For these reasons, several persistent, system-independent, methods for identifying devices have been developed. The following sections discuss these in detail.




## Referenciando  dispositivos (V)
### Persistente (I)

* Métodos que permiten identificar un dispositivo de forma unívoca.
 * WWID (*World Wide Identifier*) o WWN (*World Wide Name*)
 * UUID (*Universally Unique Identifier*)
 * Filesystem label

note:



## Identificando  dispositivos (VI)
### Persistente (II)

* *WWID/WWN* identifican de forma unívoca a dispositivos SCSI
* Podemos obtener este identificador
 * *Device Identification Vital Product Data* (page 0x83)
 * o *Unit Serial Number* (page 0x80).
* El mapeo entre este identificador y el fichero de dispositivo se almacena y mantiene automáticamente en `/dev/disk/by-id/`
```
scsi-SSEAGATE_ST373453LW_3HW1RHM6 -> ../../sda
```

note:

* The World Wide Identifier (WWID): is guaranteed to be unique for every storage device, and independent of the path that is used to access the device.
* The mappings from these WWIDs to the current /dev/sd names can be seen in the symlinks maintained in the /dev/disk/by-id/ directory.



## Identificando  dispositivos (VII)
### Persistente (III)

* El UUID y la etiqueta del SF se usan para hacer referencia a un SF almacenado en un dispositivo de almacenamiento
* Estos dos identificadores se almacenan en los metadatos del SF y su valor depende de las características del SF
* Podemos usar el comando [`blkid`](http://linux.die.net/man/8/blkid) para obtener la etiqueta y el UUID de un SF
```
root@localhost:/~$ sudo blkid /dev/sda1
/dev/sda1: LABEL="Datos" UUID="8a69b113-61f3-4943-bd99-a4b7907225f2" TYPE="ext4"
```

note:
* If a storage device contains a filesystem, then that filesystem may provide one or both of the following:
 * Universally Unique Identifier (UUID)
 * Filesystem label
* These identifiers are persistent, and based on metadata written on the device by certain applications.
* Use the blkid -L label command to retrieve the partition's UUID



## Identificando  dispositivos (VIII)
### Persistente (IV)

* La relación entre estos identificadores y el fichero de dispositivo se guarda en
 * `/dev/disk/by-label/`
```
lrwxrwxrwx 1 root root  10 dic 16 17:13 Datos -> ../../sda1
```
 * y  `/dev/disk/by-uuid/`
```
lrwxrwxrwx 1 root root  10 dic 16 17:13 8a69b113-61f3-4943-bd99-a4b7907225f2 -> ../../sda1
```

note:
* They may also be used to access the device using the symlinks maintained by the operating system in
  * the /dev/disk/by-label/ (e.g. boot -> ../../sda1 )
  * and /dev/disk/by-uuid/ (e.g. f8bf09e3-4c16-4d91-bd5e-6f62da165c08 -> ../../sda1) directories.
