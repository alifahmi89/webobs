# make arch=32|64|mac target
PATH := $(PATH):/sbin
MCC32 := /usr/local/MATLAB/R2011b32/bin/mcc
MCC64 := /usr/local/MATLAB/R2011b/bin/mcc
MCCmac := /Applications/MATLAB_R2011b.app/bin/mcc
OPT32 := -glnx86
SRC := .

allprocs: genplot gnss meteo waters afm jerk hypomap tremblemaps extenso naqssohplot music3c tilt volcgas raingauge helicorder rsam sara
allmaps: locastat gridmaps gnss hypomap tremblemaps extenso tilt rsam
all: locastat gridmaps sefran3 allprocs clean

MCC = $(MCC$(arch))
OUT32 = bin/linux-32
OUT64 = bin/linux-64
OUTmac = bin/maci-64
OPT = $(OPT$(arch))
OUT = $(OUT$(arch))

clean:

%: $(SRC)/superprocs/%.m
	$(MCC) $(OPT) -m -R -nodisplay -d $(OUT) $<
	chmod -R a+x $(OUT)/*$@*
