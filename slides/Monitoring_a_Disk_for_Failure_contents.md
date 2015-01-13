## SMART

* [S*elf-*M*onitoring, *A*nalysis, and *R*eporting *T*echnology](http://es.wikipedia.org/wiki/S.M.A.R.T.)

<a class="fancybox" href="img/smart.png" data-fancybox-group="gallery" title="mart">
<img height="550px" src="img/smart.png" alt="Smart">
</a>

note:
* Modern hard disks provide a feature known as Self-Monitoring, Analysis, and Reporting Technology (SMART).
* It is a self-diagnostic tool that you can use to predict impending failure.
* Periodically checking your drives for such problems can help you avoid costly incidents; 
* if a SMART tool turns up a problem, you can replace the disk before you lose any data!



## Smartools (I)

* Las [smartools](http://sourceforge.net/projects/smartmontools/) monitorizan el estado del disco

``` bash
~$  sudo smartctl -i /dev/sdb
smartctl 5.41 2011-06-09 r3365 [x86_64-linux-3.0.0-1-amd64] (local build)                                                      
Copyright (C) 2002-11 by Bruce Allen, http://smartmontools.sourceforge.net
                                                                                                                               
=== START OF INFORMATION SECTION ===                                                                                           
Device Model:     TOSHIBA MK3483GSX                                                                                            
Serial Number:    91UF003ES                                                                                                    
LU WWN Device Id: 5 000039 385e8ff10                                                                                           
Firmware Version: GT001U                                                                                                       
User Capacity:    320,072,933,376 bytes [320 GB]                                                                               
Sector Sizes:     512 bytes logical, 4096 bytes physical                                                                       
Device is:        Not in smartctl database [for details use: -P showall]                                                       
ATA Version is:   8                                                                                                            
ATA Standard is:  Exact ATA specification draft version not indicated                                                          
Local Time is:    Fri Jan 27 18:47:22 2012 CET                                                                                 
SMART support is: Available - device has SMART capability.                                                                     
SMART support is: Enabled
``` 

note:
* Several SMART-monitoring tools for Linux are available. 
* Smartctl controls the Self-Monitoring, Analysis and Reporting Technology (SMART) system built into most ATA/SATA and SCSI/SAS hard drives and solid-state drives. 
* -i option 
 *  prints the device model number, 
 *  serial number, 
 *  firmware version, 
 *  ATA Standard version/revision information. 
 *  Says if the device supports SMART, and if so, whether SMART support is currently enabled or disabled. 
 *  If the device supports Logical Block Address mode (LBA mode) print current user drive capacity in bytes. (If drive is has a user protected area reserved, or is "clipped", this may be smaller than the potential maximum drive capacity.) 
 *  Indicates if the drive is in the smartmontools database (see '-v' options below). If so, the drive model family may also be printed. If '-n' (see below) is specified, the power mode of the drive is printed.
* Si no tiene activo el soporte SMART ejecutamos smartctl -s on /dev/<device>



## Smartools (II)

* Podemos consultar errores anteriores con la opción `-l`

```bash
~$ sudo smartctl -l error /dev/sdb
smartctl 5.41 2011-06-09 r3365 [x86_64-linux-3.0.0-1-amd64] (local build)                                                      
Copyright (C) 2002-11 by Bruce Allen, http://smartmontools.sourceforge.net                                                     
                                                                                                                               
=== START OF READ SMART DATA SECTION ===                                                                                       
SMART Error Log Version: 1                                                                                                     
No Errors Logged
``` 

note:
* Para ver los errores de los que informó el último test usamos la opción -l error
* Si queremos un informe detallado usaremos la opción -a



## Smartools (III)

* Em cualquier momento podemos programar un test gración a la opción `-t`

```bash
~$ sudo smartctl -t short /dev/sdb 
smartctl 5.41 2011-06-09 r3365 [x86_64-linux-3.0.0-1-amd64] (local build)                                                      
Copyright (C) 2002-11 by Bruce Allen, http://smartmontools.sourceforge.net                                                     
                                                                                 

=== START OF OFFLINE IMMEDIATE AND SELF-TEST SECTION ===                                                                       
Sending command: "Execute SMART Short self-test routine immediately in off-line mode".                                         
Drive command "Execute SMART Short self-test routine immediately in off-line mode" successful.                                 
Testing has begun.                                                                                                             
Please wait 2 minutes for test to complete.                                                                                    
Test will complete after Fri Jan 27 18:51:22 2012                                                                              
                                                                                                                               
Use smartctl -X to abort test.
```

note:
* Para ver los test posibles ejecuto  smartctl -c /dev/<device>



## Smartools (IV)
### gsmartcontrol

<a class="fancybox" href="img/gsmartcontrol.png" data-fancybox-group="gallery" title="Introducción">
<img height="550px" src="img/gsmartcontrol.png" alt="Introducción">
</a>

note:
http://gsmartcontrol.berlios.de

