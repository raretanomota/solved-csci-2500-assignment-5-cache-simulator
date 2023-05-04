Download Link: https://assignmentchef.com/product/solved-csci-2500-assignment-5-cache-simulator
<br>
For this assignment you will be constructing a software cache simulator similar to what will be required in the group project. We will be simulating the differences between a direct-mapped, 2-way, and 4-way set associative cache. Simultaneously, we will be using either a least recently used (LRU) or <a href="https://en.wikipedia.org/wiki/Cache_replacement_policies#B.C3.A9l.C3.A1dy.27s_Algorithm">Bélády’s algorithm</a>.

LRU was discussed in class, on the slides, and in the textbook. Essentially, when an item needs to be evicted from the cache (and we have a choice) we will select the item in our set that was used longest ago.

Bélády’s algorithm on the other hand will evict the item currently in the cache set that will be used furthest in the future. If an item is never accessed again, it will always be safe to evict it. Note that while Bélády’s algorithm sounds impressive, in practice it is not possible to implement due to the required foresight of memory accesses.

Your cache will hold 256 items regardless of its configuration. In other words, 256 by 1 for direct-mapped, 128 by 2 for 2-way set associative, etc. You can initialize your cache lines with zeroes as no zeroes will appear in the memory trace. The memory trace will contain 1,000 non-zero addresses. In this simplified cache, finding your set will be as simple as taking the desired memory address and modding it by the set count:

int set = mem_address % set_count;

Sample output below (running on only 10 accesses):

bash-3.2$ ./a.out

Enter associativity (1, 2, 4): 2

Cache size 256 items

Cache has associativity of 2 Cache has 128 sets

Choose either 1) LRU or 2) Belady:

1

1

33

2 34

65

1

66

2

97

1

65

Starting Simulation…

Statistics:

LRU &amp; Cache Associativity: 2

Cache Accesses: 10

Cache Hits: 3

Cache Misses: 7 Overall Hit Rate: 0.300000

bash-3.2$ ./a.out Enter associativity (1, 2, 4): 2

Cache size 256 items

Cache has associativity of 2

Cache has 128 sets

Choose either 1) LRU or 2) Belady:

2

1

33

2

34

65

1

66

2

97

65

Starting Simulation…

Statistics:

Belady &amp; Cache Associativity: 2

Cache Accesses: 10

Cache Hits: 3

Cache Misses: 7

Overall Hit Rate: 0.300000

2