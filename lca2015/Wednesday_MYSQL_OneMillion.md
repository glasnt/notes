Stewart Smith - IBM nee MySQL, Percona

(post conference video stream)

Mysql still #1 opensource database, even w/out forks

NoSQL - what is a filesytem if not a hier. key/value store?

SQL is cool - general purpose queries being fast is still important

MySQL Cluster - 72-CPU cluster - 1 million reads per second (loaned hardware)

Hardware trends - more cores, not faster cores, wider not faster (just like people)

Mysql started around Windows NT - one-two CPU licences (now more cores on our mobile phones)

One thread per connection model

1990s - threads were cool ("still cool now? ... maybe")

Threads != multicore magic

users in the 90's were using x86 boxes

Big Locks - much easier than many small ones

MyISM - table level locks - one concurrent write, many concurrent reads

Transactional tables - innodb kernal lock

All the locks - everyone gets a lock - dozen a locks for one select query

Other features were a priority
 - sub queries, optimization, replication

SMP - mid 2000s - 4, 8 core servers, 8 not nessisarily better 
 - known to disable cores to make DB faster

"the fastest db to crash is probably not the best one"

.. then they hired all the patch submitters, killed developer community (all internal)

"Select 1;" - 12 mutexes

Mysql 5.5 GA - some improvements w/using mutexes in user space

3 years - 4-8 cores -> 32 cores (still plateaus out)

5.5 -> cores go up, performance goes down (after 16)
5.6 -> cores go up, performance goes up (plateaus higher)

SPARC - Sun tech (buyout 2008) - threads, lots of threads

Niagra T1000 chips - mysql couldn't scale up in time for end of life for SPARC

A lot of improvements weren't able to use hardware to capacity because of lack of hammering, hardware end of life

Power8 - 4, 6, 8, 12, cores per socket, plus threads, plus sockers - 192 threads per box 
 - will not work with old MySQL, like, at all


How to get it working on Power8

Step 1: it compiles - ship it
 - was actually easy
Step 2: get it to work
 - mutexes - spin and check
 - missing memory barriers
 - comments "#do magic here"

Mysql test suit passed with nonfunctioning mutexes - but would break with 1 or 2 concurrent connections

Step 3: ... profit


Corrupted data - worst. failure mode. ever

HOWTO test mutexes - benchmarks
 - unit tests are... "Bovine Digestion"

Sysbench - well known, not java, not cheating

Read only benchmarks  don't test disk subsystem
 - some test machines had orders of magnatide more memory than disk
 - able to test mutexes, not disk limitations

Previous record on Power8 - 275,000 QPS -- 2013, 16 cores, hyperthreading, mysql 5.6
 - (possibly just showing off, but power8 hype = good)

PThread mutexes compile option

`mutex->lock_word`

loop spins - w/out barrier, stale cache line 

patch 1: add barierrs
 - colaboration w/oracle patch 
 -> 264k QPS, with idle CPU time

Mutex contention - read views
 - cheating for RO transaction - no begin commit
 - bottleneck (known since x86)

Patch 2 - cache line size (ifdef for power8)

perf

Patch 3 - thread priority
 - 289k QPS SMT 4 (world record get)

Power8 is NUMA - depressing writing on the topic w/MySQL

4 numa nodes on dual sockets
 - bigger machine -> bigger numbers

Memory allocation per node - distances

Some DIMMs empty on development machines
 - literally empty mobo sockets

Solution: bind to single Numa node
 - bind process to one node, bind benchmark to another
 - patch pending

x86 systems get improvements still (is a win)

324,988 QPS (!!)
 - More MySQL improvements, config changes
 - 6 cores

Mysql tricks to allocate memory - malloc, jemalloc (malloc for multicore)
 - even more QPS!

one table + mutex contention => create 8 tables - partition the mutex
 - dimitri from oracle, published numbers
 - 8 x 1,000,000 row tables
 - only on part of a machine
 - theoretically, 4 x QPS -> 1,375,000 QPS

GOAL: 1 million QPS
 - mysql 5.7 port, incorporate improvements
 - edian problems! annoying
 - `volatile` considered harmful

cbit fields-> unsigned flags => 10k QPS increase
 - 411,000 QPS! (one one table)

Paritioning tables - splitting into multi tables, improvements galore

42% cpu idle w/511k QPS

some locks in permissions checking
 
comment out the mutex -> remove check, fine for a benchmark
 - 896,000 QPS SMT4
 - 915,000 QPS SMT8

9 tables - sysbench old version (less cpu) -> 1m+ QPS
 - optimised a benchmark
 - .. if no grant/revoke (makes QPS twice as fast w/out it)

Atomic variables hurt

possibly 1.3m, but less cool than 1m

MariaDB paper - more realistic lookups 

CRC32 - optimisation for POWER8?

21 current open bugs on MySQL Server
 - one is a spelling error in a comment




