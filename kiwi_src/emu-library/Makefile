SHELL   ?= /bin/bash
KIWI    ?= $(HPRLS)/kiwipro/kiwic/distro
KIWIDLL ?= $(KIWI)/support/Kiwi.dll

MONO    ?= mono
KIWIC   ?= $(MONO) $(KIWI)/lib/kiwic.exe
CSC     ?= gmcs

ENABLE_THREADS  ?= -compose=disable
HIDE_REGS       ?= enable
KIWI_FLAGS      ?= -bevelab-default-pause-mode=hard -vnl-resets=synchronous -vnl-roundtrip=disable -res2-loadstore-port-count=0 -restructure2=disable -conerefine=$(HIDE_REGS) $(ENABLE_THREADS)

emu_library: *.cs
        $(CSC) /target:library /r:$(KIWIDLL) emu_library_*.cs -out:../emu_library.dll

clean:
        - rm -f *.dll

