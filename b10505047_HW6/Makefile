CUDIR     := /usr/local/nvidia

CC      := gcc
CFLAGS  := -O3 -Wall -g
CPP     := g++
CFLAGS  := -O2 -Wall -g
NVCC    := $(CUDIR)/bin/nvcc
NVFLAGS := -O3 -I$(CUDIR)/include -m64 -arch=compute_61 -code=sm_61 -Xptxas -v

BIN1    := exp_hist_1gpu_gmem 
BIN2    := exp_hist_1gpu_shmem 
LIB     :=

all: $(BIN1) $(BIN2)

$(BIN1): exp_hist_1gpu_gmem.cu
	$(NVCC) -o $(BIN1) $(NVFLAGS) exp_hist_1gpu_gmem.cu $(LIB)

$(BIN2): exp_hist_1gpu_shmem.cu
	$(NVCC) -o $(BIN2) $(NVFLAGS) exp_hist_1gpu_shmem.cu $(LIB)

clean:
	rm -f $(BIN1) $(BIN2) 
