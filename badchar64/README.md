# badchars

## notes
ropper -f ./badchars -b 78 -b 67 -b 61 -b 2e > gadgets.txt
    -f filepath
    -p, --ppr             Searches for 'pop reg; pop reg; ret' instructions [only x86/x86_64]
    --search <regex>      Searches for gadgets 
    --chain <generator>   Generates a ropchain [generator parameter=value[ parameter=value]
    -b <badbytes>, --badbytes <badbytes>


0x0000000000400634: mov qword ptr [r13], r12; ret;
0x000000000040069c: pop r12; pop r13; pop r14; pop r15; ret;

24  0x00001038    0x0 0x00601038    0x8 -rw- NOBITS      .bss

0x00400620      e8ebfeffff     call sym.imp.print_file
0x00000000004006a3: pop rdi; ret;
┌ 17: sym.usefulFunction ();
│           0x00400617      55             push rbp
│           0x00400618      4889e5         mov rbp, rsp
│           0x0040061b      bfc4064000     mov edi, str.nonexistent    ; 0x4006c4 ; "nonexistent"
│           0x00400620      e8ebfeffff     call sym.imp.print_file
│           0x00400625      90             nop
│           0x00400626      5d             pop rbp
└           0x00400627      c3             ret
