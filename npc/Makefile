VERILATOR = verilator
VERILATOR_FLAGS = -Wall --cc
TOP_MODULE = DEFAULT
SIM_SRC = main.cpp

all:
    @echo "Usage: make sim"

sim:
	$(call git_commit, "sim RTL") # DO NOT REMOVE THIS LINE!!!
	$(VERILATOR) $(VERILATOR_FLAGS) vsrc/$(TOP_MODULE).v --exe csrc/$(SIM_SRC) --trace
	make -j -C obj_dir -f V$(TOP_MODULE).mk V$(TOP_MODULE)
	./obj_dir/V$(TOP_MODULE)

clean:
	rm -rf obj_dir waveform.vcd

include ../Makefile