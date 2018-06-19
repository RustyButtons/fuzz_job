=================================================================
==5550==ERROR: AddressSanitizer: heap-buffer-overflow on address 0x6280000083a5 at pc 0x55f74604a211 bp 0x7ffc463edf90 sp 0x7ffc463edf80
READ of size 1 at 0x6280000083a5 thread T0
    #0 0x55f74604a210 in get_text_rgb_row /home/fuzzbox/Desktop/libjpeg/rdppm.c:173
    #1 0x55f746049984 in main /home/fuzzbox/Desktop/libjpeg/cjpeg.c:642
    #2 0x7f56badaeb96 in __libc_start_main (/lib/x86_64-linux-gnu/libc.so.6+0x21b96)
    #3 0x55f746047069 in _start (/usr/local/bin/cjpeg+0x8069)

Address 0x6280000083a5 is a wild pointer.
SUMMARY: AddressSanitizer: heap-buffer-overflow /home/fuzzbox/Desktop/libjpeg/rdppm.c:173 in get_text_rgb_row
Shadow bytes around the buggy address:
  0x0c507fff9020: fa fa fa fa fa fa fa fa fa fa fa fa fa fa fa fa
  0x0c507fff9030: fa fa fa fa fa fa fa fa fa fa fa fa fa fa fa fa
  0x0c507fff9040: fa fa fa fa fa fa fa fa fa fa fa fa fa fa fa fa
  0x0c507fff9050: fa fa fa fa fa fa fa fa fa fa fa fa fa fa fa fa
  0x0c507fff9060: fa fa fa fa fa fa fa fa fa fa fa fa fa fa fa fa
=>0x0c507fff9070: fa fa fa fa[fa]fa fa fa fa fa fa fa fa fa fa fa
  0x0c507fff9080: fa fa fa fa fa fa fa fa fa fa fa fa fa fa fa fa
  0x0c507fff9090: fa fa fa fa fa fa fa fa fa fa fa fa fa fa fa fa
  0x0c507fff90a0: fa fa fa fa fa fa fa fa fa fa fa fa fa fa fa fa
  0x0c507fff90b0: fa fa fa fa fa fa fa fa fa fa fa fa fa fa fa fa
  0x0c507fff90c0: fa fa fa fa fa fa fa fa fa fa fa fa fa fa fa fa
Shadow byte legend (one shadow byte represents 8 application bytes):
  Addressable:           00
  Partially addressable: 01 02 03 04 05 06 07 
  Heap left redzone:       fa
  Freed heap region:       fd
  Stack left redzone:      f1
  Stack mid redzone:       f2
  Stack right redzone:     f3
  Stack after return:      f5
  Stack use after scope:   f8
  Global redzone:          f9
  Global init order:       f6
  Poisoned by user:        f7
  Container overflow:      fc
  Array cookie:            ac
  Intra object redzone:    bb
  ASan internal:           fe
  Left alloca redzone:     ca
  Right alloca redzone:    cb
==5550==ABORTING
