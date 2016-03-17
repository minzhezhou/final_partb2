Big Data in Finance final exam, Part B2, calculating PI using CUDA Thrust
=========================================================================

The CUDA Thrust program has several bugs. These bugs can be in the C code,
the makefile, or the PBS job file. Your task is to find these bugs,
fix them, compile and run the program, then share your results.

In this file, write any thoughts or comments that might help
improve your grade.

And, remember, to use Git you must first load Git:

  module load git
  
Similarly, to use CUDA (and CUDA Thrust):

  module load cuda
  
These may also be useful commands:

  module list
  
  module avail
  
And a hint to help you on your way. Remember that every GPU program has
two parts: a CPU part and a GPU part. To run this example you will have
to engage, at a minimum, at least 1 CPU and at least 1 GPU.

There are 7 errors
0. cuda_thrust.cu line 24:
  return (((p.x-0.5)*(p.x-0.5)+(p.y-0.5)*(p.y-0.5))<0.25) ? 1 : 0;             
1. cuda_thrust.cu line 1&2
   The 2 includes should not be comented
2. cuda_thrust.cu line 28
    It should be __device__ not **device**
3. cuda_thrust.pbs line 4
    ncpus=1
4. cuda_thrust.pbs line 18
    ./cuda-thrust
5. makefile line 5
    source should be cuda-thrust.cu not cuda-thrust.c
6. uncomment in cuda-thrust.pbs
cd $PBS_O_WORKDIR
