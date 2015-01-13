## Interrupciones (I)

* Interrupciones: mecanismo de comunicación entre dispositivos y CPU
* Tradicionalmente se soporta 16 niveles de interrupción
* Los niveles 14 y 15 **estaban** reservados a controladores PATA

<div class="container">
<div class="row">
    <div class="col-xs-4 col-sm-4 col-md-4 col-lg-4 col-centered">
<a class="fancybox" href="img/irq.png" data-fancybox-group="gallery" title="irq">
<img height="350px" src="img/irq.png" alt="irq">
</a>
    </div>
</div>
</div>

note:
* Disk controllers  use hardware resources.
* For the most part, resource use is managed automatically by the Linux kernel and its drivers; however, you may want to check on, and perhaps adjust, some details.
* One important hardware resource is the interrupt request (IRQ, or interrupt) used by the device.
* The traditional x86 architecture supports 16 interrupts, numbered 0–15; however, modern computers support more interrupts than this.
* In the traditional x86 scheme, IRQs 14 and 15 are dedicated to the primary and secondary PATA controllers.



## Interrupciones (II)

* El fichero `/proc/interrupts` devuelve información sobre irq

``` bash
~$ cat /proc/interrupts
           CPU0       CPU1       CPU2       CPU3       CPU4       CPU5       CPU6       CPU7
  0:         19          0          0          0          0          0          0          0  IR-IO-APIC-edge      timer
  1:          2          0          0          0          0          1          0          0  IR-IO-APIC-edge      i8042
  8:          0          0          0          0          0          0          0          1  IR-IO-APIC-edge      rtc0
  9:          0          0          0          0          0          0          0          0  IR-IO-APIC-fasteoi   acpi
 12:          0          1          0          0          2          1          0          0  IR-IO-APIC-edge      i8042
 16:      29783      20123      15390      21680     116654      77017      77887      97624  IR-IO-APIC-fasteoi   ehci_hcd:usb1, nvidia
 17:         80         19         10         41         71         20         14         84  IR-IO-APIC-fasteoi   snd_hda_intel
 23:       9005       3153         54         25     210956      32591        305         37  IR-IO-APIC-fasteoi   ehci_hcd:usb2
 40:          0          0          0          0          0          0          0          0  DMAR_MSI-edge      dmar0
 42:        872       6473      17668       1095       7296      84286      89768       8080  IR-PCI-MSI-edge      xhci_hcd
 43:      14882      16420       2955       2997      37435     103227      16579      21715  IR-PCI-MSI-edge      ahci
 44:          4          0          2          1          1          0          5          2  IR-PCI-MSI-edge      mei_me
 45:        126         46        132         14         92        105         21         24  IR-PCI-MSI-edge      snd_hda_intel
 46:        580          9          7     296299         16         12          6          3  IR-PCI-MSI-edge      0000:03:00.0
 47:     325685         15         12          3         33          8          6         18  IR-PCI-MSI-edge      eth0
NMI:         50         49         50         51         38         41         38         29   Non-maskable interrupts
LOC:    1207202    1159136    1426198    1123626     380521     406236     553989     358394   Local timer interrupts
SPU:          0          0          0          0          0          0          0          0   Spurious interrupts
PMI:         50         49         50         51         38         41         38         29   Performance monitoring interrupts
IWI:      23219      23749      24001      24196      23561      16840      17226      16992   IRQ work interrupts
RTR:          0          0          0          0          0          0          0          0   APIC ICR read retries
RES:    3196963    3137743    3116261    3338444    1823199    1860791    1935770    1806793   Rescheduling interrupts
CAL:      18990       6171       6053       6138       1496       1493       1361       1514   Function call interrupts
TLB:      19983      16958      15591      22998      13058      21530      13148      14209   TLB shootdowns
TRM:          0          0          0          0          0          0          0          0   Thermal event interrupts
THR:          0          0          0          0          0          0          0          0   Threshold APIC interrupts
MCE:          0          0          0          0          0          0          0          0   Machine check exceptions
MCP:         40         40         40         40         40         40         40         40   Machine check polls
ERR:          0
MIS:          0
```

note:
* Today, though, these interrupts might not be used. You can learn how your interrupts are allocated by examining the /proc/interrupts pseudo-file:
* IRQ 17 and 45 are asociated with hda_intel, a disk driver;
* and IRQ 43 and 9 are linked with ahci, a modern disk-access method.
* IRQs 16 in this example is shared—multiple devices use the same interrupt.



## Interrupciones (III)

* Compartir IRQ puede acarrear problemas
 * Cambiamos IRQ pasando argumentos al módulo
 * Usamos la BIOS
 * Usamos [`sysctl`](http://linux.die.net/man/8/sysctl) y sus fichero de configuración `/etc/sysctl.conf`

note:
This seldom causes problems on modern
hardware, but if you suspect your disk accesses are being impaired by a shared interrupt, you can look into driver
module options to change how interrupts are assigned. Research the drivers for both your disk devices and
whatever is sharing the interrupts with them, as described in Chapter 2. You can also review your computer’s
firmware options; these may enable you to adjust IRQ assignment. Finally, the sysctl utility and its configuration
file, /etc/sysctl.conf, can often be used to adjust IRQ assignments. Try typing sysctl -a | grep irq to learn about
relevant options and then change any you find in /etc/sysctl.conf.



## DMA (I)

* Modo de transferencia entre dispositivo y memoria
* No pueden usar la misma dma

<a class="fancybox" href="img/dma.png" data-fancybox-group="gallery" title="dma">
<img height="350px" src="img/dma.png" alt="dma">
</a>

note:
* In a DMA configuration, a device transfers data directly to and from an area of memory, as opposed to passing data through the computer’s CPU.
* DMA can speed access, but if two devices try to use the same DMA channel, data can be corrupted.



## DMA (II)

* El fichero `/proc/dma` devuelve información sobre dma
```bash
~$ cat /proc/dma
 4: cascade
```
* Es muy raro que se produzcan problemas de IRQ y DMA en los sistemas modernos

note:
* You can examine /proc/dma to review DMA address assignments:
$ cat /proc/dma
3: parport0
4: cascade
* DMA problems are extremely rare on modern computers.
* If you need to adjust them, though, you can review your driver documentation and sysctl settings much as you would for IRQ conflicts to find a way to reassign a device to use a new DMA channel.
