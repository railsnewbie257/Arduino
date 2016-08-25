##These instruction are for OSX

$ <b>brew install du-util</b>
<pre>
==> Installing dependencies for dfu-util: libusb
==> Installing dfu-util dependency: libusb
==> Downloading https://homebrew.bintray.com/bottles/libusb-1.0.20.el_capitan.bottle.1.tar.gz
######################################################################## 100.0%
==> Pouring libusb-1.0.20.el_capitan.bottle.1.tar.gz
🍺  /usr/local/Cellar/libusb/1.0.20: 27 files, 492.9K
==> Installing dfu-util
==> Downloading https://homebrew.bintray.com/bottles/dfu-util-0.9.el_capitan.bottle.tar.gz
######################################################################## 100.0%
==> Pouring dfu-util-0.9.el_capitan.bottle.tar.gz
🍺  /usr/local/Cellar/dfu-util/0.9: 10 files, 122.5K
</pre>

####[Deploying MicroPython Firmware](http://docs.micropython.org/en/latest/esp8266/esp8266/tutorial/intro.html#deploying-the-firmware)


$ <b>pip install esptool</b>
<pre>
Collecting esptool
  Downloading esptool-1.1-py2-none-any.whl
Collecting pyserial (from esptool)
  Downloading pyserial-3.1.1-py2.py3-none-any.whl (200kB)
    100% |████████████████████████████████| 200kB 573kB/s 
Installing collected packages: pyserial, esptool
Successfully installed esptool-1.1 pyserial-3.1.1
You are using pip version 7.1.2, however version 8.1.2 is available.
You should consider upgrading via the 'pip install --upgrade pip' command.
</pre>



$ <b>esptool.py --port</b> <em>/dev/cu.usbserial-A105C7AI</em> <b>erase_flash</b>
<pre>
esptool.py v1.1
Connecting...
Erasing flash (this may take a while)...

</pre>

$

<pre>
==> Downloading https://homebrew.bintray.com/bottles/picocom-2.1.el_capitan.bottle.tar.gz
######################################################################## 100.0%
==> Pouring picocom-2.1.el_capitan.bottle.tar.gz
🍺  /usr/local/Cellar/picocom/2.1: 6 files, 96.3K

$ <b>picocom --help</b>
picocom v2.1

Compiled-in options:
  TTY_Q_SZ is 32768
  USE_FLOCK is enabled
  LINENOISE is enabled
  HISTFILE is: .picocom_history

Usage is: picocom [options] <tty device>
Options are:
  --<b>aud <baudrate>
  --<f>low s (=soft) | h (=hard) | n (=none)
  --parit<y> o (=odd) | e (=even) | n (=none)
  --<d>atabits 5 | 6 | 7 | 8
  --sto<p>bits 1 | 2
  --<e>scape <char>
  --e<c>ho
  --no<i>nit
  --no<r>eset
  --no<l>ock
  --<s>end-cmd <command>
  --recei<v>e-cmd <command>
  --imap <map> (input mappings)
  --omap <map> (output mappings)
  --emap <map> (local-echo mappings)
  --<h>elp
<map> is a comma-separated list of one or more of:
  crlf : map CR --> LF
  crcrlf : map CR --> CR + LF
  igncr : ignore CR
  lfcr : map LF --> CR
  lfcrlf : map LF --> CR + LF
  ignlf : ignore LF
  bsdel : map BS --> DEL
  delbs : map DEL --> BS
<?> indicates the equivalent short option.
Short options are prefixed by "-" instead of by "--".
</pre>
