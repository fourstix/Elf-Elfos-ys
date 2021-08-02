# ys

## YMODEM send for Elf/OS

Usage:
```
   ys file1 [file2... filen]
```

"ys" is a YMODEM send program for Elf/OS. You can specify
multiple files on the command line, but not (yet?) wildcards.

### Status

Build 8 includes automatic UART configuration. Using BIOS calls for
all I/O isn't quite fast enough to catch the ACK and CRC/NAK at the
end of a block 0 send using the big banged UART, so inlined code needs
to be used. The price that had to be paid for that is having to figure
out which EF line is being used, and what the idling states of that line
and Q are.

Thanks to [David Madole](https://github.com/dmadle) coming up with some
ingenious code to figure out which EF line is being used, ys can 
automatically configure itself for either a real UART (all BIOS calls) 
or a soft UART using any of the EF lines, and any polarity on both
receive and transmit.

### Inspiration

* [Elfos-yr](https://github.com/dmadle/Elfos-yr)<br>
* [Elfos-Elf-xr](https://github.com/rileym65/Elf-Elfos-xr)<br>
