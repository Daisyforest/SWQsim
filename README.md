# SWQsim

Repository for simulation data for "Closing the “Quantum Supremacy” Gap: Achieving Real-Time Simulation of a Random Quantum Circuit Using a New Sunway Supercomputer".


Under the folder simulation\_data, there are two folders square\_10\_10\_40 and sycamore, each of them stores the quantum circuit to sample from (.qsim), the simulation results (which is devided into two files\: output_1.txt.tar.bz2,output_2.txt.tar.bz2), the underlying tensor network which produces those amplitudes (arrays.txt) and the contraction path information (square\_10\_10\_40\:path.txt, sycamore\:path\_info.json)

The file square\_10\_10\_40/path.txt contains all the necessary information to reproduce the slicing scheme and the tensor contraction path. Particularly, it is stored as a txt file with the following $3$ keys:  
1. __CUT__ the position to cut the tensor to reduce the memory of storing the tensor in every path.
2. __EXPAND__ the routine of tensor contraction.
3. __MERGE__ the point to contract big tensors.

The file sycamore/path\_info.json contains all the necessary information to reproduce the slicing scheme and the tensor contraction path. Particularly, it is stored as a json file with the following $4$ keys:

1. __inputs__ stores the indexing of tensor network separately by ',', each unicode stands for one index of a tensor.
2. __sliced_inputs__ stores the indexing of the **sliced** tensor network with indices removed.
3. __sliced_indices__ stores the sliced indices. For example if there are $23$ sliced indices, the original tensor network will be sliced into $2^23$ smaller tensor networks, summing over the output of each smaller tensor network produces the same result as contracting the original tensor network.
4. __contraction_path__ stores the tensor contraction path for each **sliced** tensor network.




<!-- File sliced.txt include all of  the information of the contract path, except the  value of  391  initial tensor,records the trace of the whole path has 21 open node,and with 23 sliced edges.  

File arrays.txt is the  value of  391  initial tensor.  

File output.txt_ALL is the result of 2^21 amplitute form contracting the whole path.  
 -->
