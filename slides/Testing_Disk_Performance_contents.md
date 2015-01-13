## Rendimiento del disco

* A veces sospechamos de un bajo rendimiento del disco duro
* Podemos hacer un test de velocidad usando [`hdparm`](http://linux.die.net/man/8/hdparm):

```bash
~$ sudo hdparm -t /dev/sda

/dev/sda:
 Timing buffered disk reads: 456 MB in  3.01 seconds = 151.45 MB/sec
 
~$ sudo hdparm -t /dev/sda

/dev/sda:
 Timing buffered disk reads: 442 MB in  3.00 seconds = 147.29 MB/sec
~$ sudo hdparm -t /dev/sda

/dev/sda:
 Timing buffered disk reads: 450 MB in  3.01 seconds = 149.49 MB/sec
~$ sudo hdparm -t /dev/sda

/dev/sda:
 Timing buffered disk reads: 456 MB in  3.01 seconds = 151.73 MB/sec
~$ 
```

note:
* If you suspect disk problems, you should first try to quantify the nature of the problem. 
* The hdparm utility can be useful for this. 
* Pass it the -t parameter to test uncached read performance on the device:
# hdparm -t /dev/sda
/dev/sda:
Timing buffered disk reads: 264 MB in 3.00 seconds = 87.96 MB/sec



## Rendimiento de la cache de disco

* Podemos comprobar el rendimiento de la cache del disco también con [`hdparm`](http://linux.die.net/man/8/hdparm):

``` bash
~$ sudo hdparm -T /dev/sda

/dev/sda:
 Timing cached reads:   28164 MB in  2.00 seconds = 14096.68 MB/sec
~$ sudo hdparm -T /dev/sda

/dev/sda:
 Timing cached reads:   28124 MB in  2.00 seconds = 14077.40 MB/sec
~$ sudo hdparm -T /dev/sda

/dev/sda:
 Timing cached reads:   28280 MB in  2.00 seconds = 14156.18 MB/sec
~$ sudo hdparm -T /dev/sda

/dev/sda:
 Timing cached reads:   29024 MB in  2.00 seconds = 14527.22 MB/sec
~$ sudo hdparm -T /dev/sda

/dev/sda:
 Timing cached reads:   27756 MB in  2.00 seconds = 13892.32 MB/sec
```

note:
* Using an uppercase -T the performance of the disk cache, which is mostly a measure of your computer’s memory performance.
* As a general rule, conventional disks in 2011 should produce performance figures in the very high tens of megabytes per second and above.
* SSD performance can be significantly better than that of conventional spinning disks, at least when using a true disk interface such as SATA.
* If you apply hdparm to a RAID 0, 4, 5, 6, or 10 array, you’re likely to see very good transfer rates, too.
* Be aware that performance in actual use is likely to be lower than that produced by hdparm;



## Otras consideraciones

* Los dispositivos SSD dan mejores tasas de rendimiento
* Podemos aplicar este tipos de test a RAID. Salvo el RAID 1, el resto deberían dar buenos resultados
* [`hdparm`](http://linux.die.net/man/8/hdparm) hace una predicción muy optimista, en entornos reales el rendimiento en mucho menor.

note:
* SSD performance can be significantly better than that of conventional spinning disks, at least when using a true disk interface such as SATA. 
* If you apply hdparm to a RAID 0, 4, 5, 6, or 10 array, you’re likely to see very good transfer rates, too.
* Be aware that performance in actual use is likely to be lower than that produced by hdparm; 
