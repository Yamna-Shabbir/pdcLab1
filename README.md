Part 1:
CUDA threads are organized hierarchically:
•	Thread: the smallest unit of execution
•	Block: a group of threads (e.g., blockDim.x threads)
•	Grid: a group of blocks (e.g., gridDim.x blocks)
Index Calculation Formula
	int globalThreadId = threadIdx.x + blockIdx.x * blockDim.x;
This formula ensures each thread gets a unique global ID across all blocks.
Experiment with Different Launch Configurations
We will try by changing this line in main(): helloFromThread<<<2, 4>>>();
2 blocks × 4 threads = 8 total threads
Part 2:
Platform	Time (ms)	Comments
CPU
		~40–60
	Single-threaded loop

GPU
		~1–5	
	Parallel threads on device

Speedup
		10–30x+	
	Dependent on GPU


Part 3 
input.jpg is in the same directory
Sample output:
CPU Time: 6.2 ms
GPU Time: 0.4 ms
Images match.
Speedup = 15.5x
