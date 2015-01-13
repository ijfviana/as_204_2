## hdparam (I)

* Esta utilidad permite ajustar parámetros de discos PATA
* Muchas opciones no tiene efecto en discos SCSI

note:

* If you use a device via a Linux PATA driver, the hdparm utility can be used to tweak disk access parameters, not just to measure performance.
* Most of its options have no effect on SCSI disks, including most SATA, USB, and even PATA disks that use the new SCSI interface for PATA.
* Fortunately, this isn’t usually a problem, since true SCSI disks and the newer devices that are managed through the SCSI subsystem are generally configured optimally by default.



## hdparam (II)
### Opciones

<div class="table-responsive">
  <table class="table table-hover table-condensed table-bordered">
    <thead>
      <tr>
        <th width="400em">Opción</th>
         <th>Explicación</th>
      </tr>
    </thead>
    <tbody>
<tr>
<td>`-d n`</td>
<td>Activación modo PIO o dma</td>
</tr>
<tr>
<td>`-c mode`</td>
<td>Activación/Desactivación modo de transferencia de 32 bits.</td>
</tr>
<tr>
<td>`-S timeout`</td>
<td>Controla modo reposo del dispositivo</td>
</tr>
<tr>
<td>`-v`</td>
<td>Muestra opciones del dispositivo</td>
</tr>
<tr>
<td>`-X transfermode`</td>
<td>Modo de transferencia DMA</td>
</tr>
</tbody>
  </table>
</div>

note:

| Option  | Explanation |
| --------|-------------|
| -d n    | PATA devices can be run in either Programmed Input/Output (PIO) mode or in DMA mode. DMA mode produces lower CPU loads for disk accesses. Using -d0 enables PIO mode, and -d1 enables DMA mode. The -d1 option is generally used in conjunction with -X (described shortly). This option doesn’t work on all systems; Linux requires explicit support for the DMA mode of a specific ATA chipset if you’re to use this feature.
| -p mode | This parameter sets the PIO mode, which in most cases varies from 0 to 5. Higher PIO modes correspond to better performance.
| -c mode | Queries or sets 32-bit transfer status. Omit mode to query the status, set mode to 0 to disable 32-bit support, set mode to 1 to enable 32-bit support, or set mode to 3 to enable 32-bit support using a special sequence needed by some chipsets.
| -S timeout | This option sets an energy-saving feature: the time a drive will wait without any accesses before it enters a low-power state. It takes a few seconds for a drive to recover from such a state, so many desktops leave timeout at 0 , which disables this feature. On laptops, though, you may want to set timeout to something else. Values between 1 and 240 are multiples of 5 seconds (for instance, 120 means a 600-second, or 10-minute, delay); 241 – 251 mean 1–11 units of 30 minutes; 252 is a 21-minute timeout; 253 is a drive-specific timeout; and 255 is a 21-minute and 15-second timeout.
| -v      | You can see assorted disk settings with this option.
| -X transfermode | This option sets the DMA transfer mode used by a disk. The transfermode is usually set to a value of sdma x, mdma x, or udma x. These values set simple DMA, multiword DMA, or Ultra DMA modes, respectively. In all cases, x represents the DMA mode value, which is a number. On modern hardware, you should be able to use a fairly high Ultra DMA mode, such as -X udma5 or -X udma6 . Use this option with caution; setting an improper mode can cause the disk to become inaccessible, which in turn can cause your system to hang.



## sdparam (I)

* [`sdparam`](http://sg.danny.cz/sg/sdparm.html) se utiliza pra ajustar parámetros de un dispositivos SCSI

```
sdparm [OPTIONs] DEVICE [DEVICE...]
```

note:
* You can use sdparm to learn about and even adjust your SCSI devices.



## sdparam (II)
### Opciones

<div class="table-responsive">
  <table class="table table-hover table-condensed table-bordered">
    <thead>
      <tr>
        <th width="330em">Opción</th>
        <th>Explicación</th>
      </tr>
    </thead>
   <tbody>
<tr>
<td>`-a, --all`</td>
<td>Muestra información dispositivo</td>
</tr>
<tr>
<td>`-e, --enumerate`</td>
<td>Muestra campos que se pueden ajustar</td>
</tr>
<tr>
<td>`-f, --flexible`</td>
<td>Corrige problemas en la interpretación de las respuestas</td>
</tr>
<tr>
<td>`-g, --get field`</td>
<td>Obtiene información de un campo</td>
</tr>
<tr>
<td>`-i, --inquiry`</td>
<td>Muestra páginas del modo de consulta para el dispositivo.</td>
</tr>
</tbody>
  </table>
</div>

note:
| Long option name  | Short option name | Explanation |
|-------------------|-------------------|-------------|
| --all             | -a                | Displays a variety of technical information on the device.
| --enumerate       | -e                | Displays information on the pages and fields that can be adjusted by sdparm . Ignores the device specification.
| --flexible        | -f                | Corrects for problems in interpreting responses that can be caused by buggy devices or drivers.
| --get field       | -g field          | Retrieves an individual field of technical data.
| --inquiry         | -i                | Displays inquiry mode pages for the device.
| --long            | -l                | Creates additional output with many commands.
| --set= STR=n      | -s STR=n          | Sets a field to a specified value. Use with extreme caution!
| --six             | -6                | Uses a 6-byte interface mode, rather than the newer 10-byte mode. Useful with older SCSI devices.



## sdparam (III)
### Opciones (II)

<div class="table-responsive">
  <table class="table table-hover table-condensed table-bordered">
    <thead>
      <tr>
        <th width="400em">Opción</th>
        <th>Explicación</th>
      </tr>
    </thead>
   <tbody>
<tr>
<td>`-l, --long`</td>
<td>Crea salida adicional con más comandos.</td>
</tr>
<tr>
<td>`-s STR=n. --set= STR=n`</td>
<td>Establece un campo a un valor especificado.</td>
</tr>
<tr>
<td>`-6, --six`</td>
<td>Utiliza un modo de interfaz de 6 bytes</td>
</tr>
</tbody>
  </table>
</div>
