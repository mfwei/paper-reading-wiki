# Welcome to my ZNS paper wiki!

* :bulb: [Johnson's Secret Recepits](https://www.csie.ntu.edu.tw/~johnson/Notebook.php)

***

## Table of Content 
1. [File Systems](#1-file-systems)
2. [Host interfacing, OS and Storage I/O Stack](#2-host-interfacing-os-and-storage-io-stack)
3. [NVMe, Flash, PMEM, SSD](#3-nvme-flash-pmem-ssd)
4. [Storage Virtualization, Emulation, Simulation](#4-storage-virtualization-emulation-simulation)
5. [Flash I/O Scheduling and quality-of-service/multi-tenancy](#5-flash-io-scheduling-and-quality-of-servicemulti-tenancy)
6. [Database, Timeseries, VectorDB, Lookup, Indexes on Storage](#6-database-timeseries-vectordb-lookup-indexes-on-storage)
7. [Storage IO Characterization](#7-storage-io-characterization)
8. [SNIA/NVMe weblinks](#8-snianvme-weblinks)
9. [Other Applications](#9-other-applications)
10. [Courses](#10-books-courses)

## 1. File Systems
  ### 1.1 Btrfs
  * [BTRFS documentation](https://btrfs.readthedocs.io/en/latest/)
    > * :closed_book:	[Btrfs Wiki](https://archive.kernel.org/oldwiki/btrfs.wiki.kernel.org/index.php/Main_Page.html) has been archived and the content is no longer updated.
    > * :bar_chart: [Status Page](https://btrfs.readthedocs.io/en/latest/Status.html)
    > * :octocat: [Developer documentation on Github](https://github.com/btrfs/btrfs-dev-docs)
  * [Btrfs at Facebook](https://facebookmicrosites.github.io/btrfs/docs/btrfs-facebook.html)
    > * :film_strip: [2020 - Deploying Btrfs at Facebook Scale - Josef Bacik](https://www.youtube.com/watch?v=U7gXR2L05IU), [LWN Article](https://lwn.net/Articles/824855/)
    > * [2018 - Facebook open-sources new suite of Linux kernel components and tools](https://engineering.fb.com/2018/10/30/open-source/linux/), 
  * 2006 - [B-trees, Shadowing, and Range-Operations](https://dominoweb.draco.res.ibm.com/262a285a5ee7b4818525723500570316.html), IBM Tech. Rep.
  * 2008 - [B-trees, shadowing, and clones](https://dl.acm.org/doi/10.1145/1326542.1326544), ACM Transactions on Storage
  * 2013 - [BTRFS: The Linux B-tree filesystem](https://dl.acm.org/doi/10.1145/2501620.2501623), ACM Transactions on Storage
  * 2021 - [Btrfs on zoned block devices](https://lwn.net/Articles/853308/), LWN.net
    >  :octocat: [Btrfs: zoned: automatic BG reclaim](https://lwn.net/ml/linux-btrfs/cover.1618494550.git.johannes.thumshirn@wdc.com/)
  * 2024 - [High-Performance Computing Storage Performance and Design Patterns—Btrfs and ZFS Performance for Different Use Cases](https://www.mdpi.com/2073-431X/13/6/139), MDPI

  ### 1.2 Filesystem Aging
  * 1997 - [File system aging—increasing the relevance of file system benchmarks](https://dl.acm.org/doi/10.1145/258612.258689), SIGMETRICS '97
  * 2009 - [Generating Realistic Impressions for File-System Benchmarking](https://dl.acm.org/doi/10.1145/1629080.1629086), ACM Transactions on Storage, [FAST '09](https://www.usenix.org/legacy/event/fast09/)
    > :octocat: [GitHub](https://github.com/ionathanch/impressions)
  * 2017 - [How to Fragment Your File System](https://www.usenix.org/publications/login/summer2017/conway), ;login: issue: Summer 2017, Vol. 42, No. 2
  * 2017 - [File Systems Fated for Senescence? Nonsense, Says Science!](https://www.usenix.org/conference/fast17/technical-sessions/presentation/conway), FAST '17
  * 2018 - [Geriatrix: Aging what you see and what you don’t see. A file system aging approach for modern storage systems](https://www.usenix.org/conference/atc18/presentation/kadekodi), FAST '18
    > :octocat: [GitHub](https://github.com/saurabhkadekodi/geriatrix)
  * 2019 - [Filesystem Aging: It’s more Usage than Fullness](https://www.usenix.org/conference/hotstorage19/presentation/conway), HotStorage '19
  * 2024 - [We Ain’t Afraid of No File Fragmentation: Causes and Prevention of Its Performance Impact on Modern Flash SSDs](https://www.usenix.org/conference/fast24/presentation/jun), FAST '24
    
  ### 1.3 Others
  * 2013 - [Extending the lifetime of flash-based storage through reducing write amplification from file systems](https://dl.acm.org/doi/10.5555/2591272.2591299), FAST '13
  * 2020 - [How to Copy Files](https://www.usenix.org/conference/fast20/presentation/zhan), FAST '20
  * 2021 - [Copy-on-Abundant-Write for Nimble File System Clones](https://dl.acm.org/doi/10.1145/3423495), ACM Transactions on Storage
    > :earth_americas:	[BetrFS](https://www.betrfs.org/) - A write-optimized, general purpose Linux file system.
  * 2022 - [Optimizing CoW-based File Systems on Open-Channel SSDs with Persistent Memory](https://ieeexplore.ieee.org/document/9774695), DATE '22
  * 2022 - [IPLFS: Log-Structured File System without Garbage Collection](https://www.usenix.org/conference/atc22/presentation/kim-juwon), ATC '22
  * 2023 - [Filesystem Fragmentation on Modern Storage Systems](https://dl.acm.org/doi/abs/10.1145/3611386), ACM Transactions on Computer Systems
  * 2023 - [msF2FS: Design and Implementation of an NVMe ZNS SSD Optimized F2FS File System](https://repository.tudelft.nl/islandora/object/uuid:3c2b3e73-6aff-45f3-af43-31a50314b547/datastream/OBJ/download), Master thesis
    > :octocat: [GitHub](https://github.com/stonet-research/msF2FS)
  * 2023 - [ZenFS+: Nurturing Performance and Isolation to ZenFS](https://ieeexplore.ieee.org/document/10070767), IEEE Access
  * 2023 - [BlzFS: Crash Consistent Log-structured File System Based on Byte-loggable Zone for ZNS SSD](https://ieeexplore.ieee.org/document/10360948), ICCD '23
  * 2024 - [An Adaptive Zone-Grouping Scheme Enabling General-Purpose File Systems on ZNS SSDs](https://dl.acm.org/doi/10.1145/3688351.3689151), SYSTOR '24
    > * 2017 - [AutoStream: automatic stream management for multi-streamed SSDs](https://dl.acm.org/doi/10.1145/3078468.3078469), SYSTOR '17
  * 2024 - [MIDAS: Minimizing Write Amplification in Log-Structured Systems through Adaptive Group Number and Size Configuration](https://www.usenix.org/conference/fast24/presentation/oh), FAST '24
  
## 2. Host interfacing, OS and Storage I/O Stack 
  * 2021 - [ZNS+: Advanced Zoned Namespace Interface for Supporting In-Storage Zone Compaction](https://www.usenix.org/conference/osdi21/presentation/han), OSDI '21
  * 2023 - [eZNS: An Elastic Zoned Namespace for Commodity ZNS SSDs](https://www.usenix.org/conference/osdi23/presentation/min), OSDI '23
  * 2024 - [ZMS: Zone Abstraction for Mobile Flash Storage](https://www.usenix.org/conference/atc24/presentation/hwang), ATC '24
    
## 3. NVMe, Flash, PMEM, SSD  
  * 2012 - [SFS: Random Write Considered Harmful in Solid State Drives](https://dl.acm.org/doi/10.5555/2208461.2208473), FAST '12
    > :film_strip: [Presentation](https://www.youtube.com/watch?v=cBonhqDooPE)
  * 2013 - [Exploring and Exploiting the Multilevel Parallelism Inside SSDs for Improved Performance and Endurance](https://ieeexplore.ieee.org/document/6165265), IEEE Transactions on Computers
  * :octocat: [Btrfs: Do not use data_alloc_cluster in ssd mode](https://patchwork.kernel.org/project/linux-btrfs/patch/20170721114711.20229-1-hans.van.kranenburg@mendix.com/)
  
  ### 3.1 Zoned Namespaces
  * 2020 - [Exploring Performance Characteristics of ZNS SSDs: Observation and Implication](https://ieeexplore.ieee.org/document/9188086), NVMSA '20
  * 2020 - [Zone Append: A New Way of Writing to Zoned Storage](https://www.usenix.org/conference/vault20/presentation/bjorling), VAULT '20
  * 2021 - [ZNS: Avoiding the Block Interface Tax for Flash-based SSDs](https://www.usenix.org/conference/atc21/presentation/bjorling), ATC '21
  * 2021 - [Don't be a blockhead: zoned namespaces make work on conventional SSDs obsolete](https://dl.acm.org/doi/10.1145/3458336.3465300), HotOS '21
  * 2022 - [Understanding NVMe Zoned Namespace (ZNS) Flash SSD Storage Devices](https://arxiv.org/pdf/2206.01547.pdf), arXiv
  * 2022 - [Efficient Data Placement for Zoned Namespaces (ZNS) SSDs](https://dl.acm.org/doi/10.1007/978-3-031-21395-3_28), NPC '22
  * 2023 - [A Survey on the Integration of NAND Flash Storage in the Design of File Systems and the Host Storage Software Stack](https://arxiv.org/pdf/2307.11866.pdf), arXiv
  * 2022 - [What You Can’t Forget: Exploiting Parallelism for Zoned Namespaces](https://www.hotstorage.org/2022/camera-ready/hotstorage22-24/pdf/hotstorage22-24.pdf), HotStorage '22
  * 2023 - [Performance Characterization of NVMe Flash Devices with Zoned Namespaces (ZNS)](https://atlarge-research.com/pdfs/2023-cluster-zns-performance-kdoekemeijer.pdf), CLUSTER '23
    > :octocat: [GitHub](https://github.com/Krien/NVMeBenchmarks)
  * 2023 - [Understanding (Un)Written Contracts of NVMe ZNS Devices with zns-tools](https://arxiv.org/pdf/2307.11860.pdf), arXiv
  * 2024 - [zns-tools: An eBPF-powered, Cross-Layer Storage Profiling Tool for NVMe ZNS SSDs](https://atlarge-research.com/pdfs/2024-zns-tools.pdf), CHEOPS '24
    > :octocat: [GitHub](https://github.com/stonet-research/zns-tools)
  * 2024 - [Para-ZNS: Improving Small-Zone ZNS SSDs Parallelism Through Dynamic Zone Mapping](https://ieeexplore.ieee.org/document/10546863), DATE '24
  * 2024 - [Optimizing Garbage Collection for ZNS SSDs via In-storage Data Migration and Address Remapping](https://dl.acm.org/doi/10.1145/3689336), ACM Transactions on Architecture and Code Optimization
  * 2024 - [Dynamic zone redistribution for key-value stores on zoned namespaces SSDs](https://dl.acm.org/doi/10.1016/j.sysarc.2024.103159), Journal of Systems Architecture
    
## 4. Storage Virtualization, Emulation, Simulation
  * 2018 - [The CASE of FEMU: Cheap, Accurate, Scalable and Extensible Flash Emulator](https://www.usenix.org/conference/fast18/presentation/li), FAST '18
    > :clipboard:	[Slides Show](https://www.usenix.org/sites/default/files/conference/protected-files/fast18_slides_li.pdf), :octocat: [GitHub](https://github.com/MoatLab/FEMU)
  * 2023 - [ConfZNS : A Novel Emulator for Exploring Design Space of ZNS SSDs](https://dl.acm.org/doi/10.1145/3579370.3594772), SYSTOR '23
    > :octocat: [GitHub](https://github.com/DKU-StarLab/ConfZNS)
  * 2023 - [NVMeVirt: A Versatile Software-defined Virtual NVMe Device](https://www.usenix.org/conference/fast23/presentation/kim-sang-hoon), FAST '23
    > :clipboard:	[Slides Show](https://www.usenix.org/sites/default/files/conference/protected-files/fast23_slides_kim.pdf), :film_strip: [Video](https://www.youtube.com/watch?v=cBonhqDooPE),  :octocat: [GitHub](https://github.com/snu-csl/nvmevirt)
  * 2023 - [Empowering Storage Systems Research with NVMeVirt: A Comprehensive NVMe Device Emulator](https://dl.acm.org/doi/10.1145/3625006), ACM Transactions on Storage
  * 2024 - [Exploring I/O Management Performance in ZNS with ConfZNS++](https://dl.acm.org/doi/10.1145/3688351.3689160), SYSTOR '24
    > :octocat: [GitHub](https://github.com/stonet-research/systor-confznsplusplus-artifact)
    
## 5. Flash I/O Scheduling and quality-of-service/multi-tenancy 
  * 2023 - [Achieving Performance Isolation in Docker Environments with ZNS SSDs](https://ieeexplore.ieee.org/document/10254344), NVMSA '23
  * 2025 - [Does Linux Provide Performance Isolation for NVMe SSDs? Configuring cgroups for I/O Control in the NVMe Era](https://atlarge-research.com/pdfs/2025-iiswc-cgroups.pdf), IISWC '25
    > :octocat: [GitHub](https://github.com/stonet-research/isol-bench)

## 6. Database, Timeseries, VectorDB, Lookup, Indexes on Storage  
  * 2022 - [Accelerating RocksDB for Small-Zone ZNS SSDs by Parallel I/O](https://dl.acm.org/doi/10.1145/3564695.3564774), Middleware '22
  * 2023 - [WALTZ: Leveraging Zone Append to Tighten the Tail Latency of LSM Tree on ZNS SSD](https://dl.acm.org/doi/10.14778/3611479.3611495), VLDB '23
  * 2023 - [SplitZNS: Towards an Efficient LSM-Tree on Zoned Namespace SSDs](https://dl.acm.org/doi/10.1145/3608476), ACM Transactions on Architecture and Code Optimization '23
  * 2024 - [WA-Zone: Wear-Aware Zone Management Optimization for LSM-Tree on ZNS SSDs](https://dl.acm.org/doi/10.1145/3637488), ACM Transactions on Architecture and Code Optimization '24
  * 2024 - [Zone-Aware Persistent Deletion for Key-Value Store Engine](https://ieeexplore.ieee.org/document/10693671), NVMSA '24
  * 2024 - [ZWAL: Rethinking Write-ahead Logs for ZNS SSDs with Zone Appends](https://dl.acm.org/doi/10.1145/3642963.3652203), CHEOPS '24
 
## 7. Storage IO Characterization
  * 2008 - [Characterization of storage workload traces from production windows servers](https://ieeexplore.ieee.org/abstract/document/4636097), IISWC '08
  * 2010 - [Benchmarking cloud serving systems with YCSB](https://dl.acm.org/doi/10.1145/1807128.1807152), SoCC '10
    > :octocat: [GitHub](https://github.com/brianfrankcooper/YCSB)
  * 2010 - [Workload characterization of a leadership class storage cluster](https://ieeexplore.ieee.org/abstract/document/5668066), PDSW '10
  * 2018 - [I/O characteristics discovery in cloud storage systems](https://ieeexplore.ieee.org/abstract/document/8457797), CLOUD '18
  * 2020 - [Characterizing, Modeling, and Benchmarking RocksDB Key-Value Workloads at Facebook](https://www.usenix.org/conference/fast20/presentation/cao-zhichao), FAST '20
    > :octocat: [GitHub](https://github.com/facebook/rocksdb/wiki/RocksDB-Trace,-Replay,-Analyzer,-and-Workload-Generation)
  * 2022 - [Extracting and characterizing I/O behavior of HPC workloads](https://ieeexplore.ieee.org/abstract/document/9912707), CLUSTER '22
  * 2022 - [Data Storage System Requirement for Autonomous Vehicle](https://ieeexplore.ieee.org/abstract/document/10003785), ICCAS '22
  * 2023 - [Characterization of i/o behaviors in cloud storage workloads](https://ieeexplore.ieee.org/abstract/document/10089497), ToC, '23
  * 2024 - [Quantitative Analysis of Storage Requirement for Autonomous Vehicles](https://dl.acm.org/doi/abs/10.1145/3655038.3665948), HotStorage '24
  * 2025 - [IO Characterizing Study of Offloading LLM Models](https://dl.acm.org/doi/pdf/10.1145/3719330.3721230), CHEOPS '25

## 8. SNIA/NVMe weblinks   
  * [A Quick Tour of NVM Express (NVMe)](https://metebalci.com/blog/a-quick-tour-of-nvm-express-nvme/)
  * [NVMe® Computational Storage: From Addressing Ransomware to Improving Bandwidth](https://nvmexpress.org/resource/nvme-computational-storage-from-addressing-ransomware-to-improving-bandwidth/)
  * [RocksDB* db_bench Tuning Guide on 3rd Generation Intel® Xeon® Scalable Processors Based Platform](https://www.intel.com/content/www/us/en/content-details/686417/rocksdb-db-bench-tuning-guide-on-3rd-generation-intel-xeon-scalable-processors-based-platform.html)
  * 2019 - [Exploring the Impact of System Storage on AI & ML Workloads via MLPerf Benchmark Suite](https://files.futurememorystorage.com/proceedings/2019/08-08-Thursday/20190808_AIML-301-1_Vaske.pdf)
      > [MLPerf Storage Working Group](https://mlcommons.org/working-groups/benchmarks/storage)
  * 2020 - [File System Native Support of Zoned Block Devices: Regular vs Append Writes](https://www.snia.org/educational-library/file-system-native-support-zoned-block-devices-regular-vs-append-writes-2020)
  * :film_strip: 2020 - [NVMe® Zoned Namespace SSDs & The Zoned Storage Linux Software Ecosystem](https://www.youtube.com/watch?v=lcYdE_S5o8Q)
  * :film_strip: 2020 - [SDC2020: Zoned Namespaces (ZNS) SSDs: Disrupting the Storage Industry](https://www.youtube.com/watch?v=cbX3P56Jp0o)
  * :film_strip: 2021 - [Zoned NameSpaces: Bringing zones to NVMe SSDs](https://www.youtube.com/watch?v=yHpDh9M0Tuw)
  * 2023 - [FMS-2023-NVM-Express-State-of-the-Union-The-Language-of-Storage](https://nvmexpress.org/wp-content/uploads/FMS-2023-NVM-Express-State-of-the-Union-The-Language-of-Storage.pdf)
  * 2024 - [Storage for AI 101 - A Primer on AI Workloads and Their Storage Requirements](https://www.sniadeveloper.org/events/agenda/session/669)
  * 2024 - [Storage Requirements for AI Training and Checkpointing](https://www.snia.org/sites/default/files/SSSI/CMSS24/CMSS24-Cardente-Storage-Requirements-for-AI.pdf)
  * 2024 - [Storage Trends 2024: Your Questions Answered](https://sniablog.org/storage-trends-your-questions-answered/)
      > :clipboard:	[Slides Show](https://www.snia.org/sites/default/files/sta/SNIA-STA-Storage-Trends-2024-Webinar.pdf), :film_strip: [Video](https://www.youtube.com/watch?v=l8qPrFtY6qE)
      
## 9. Other applications
  * 2023 - [zCeph: Achieving High Performance On Storage System Using Small Zoned ZNS SSD](https://dl.acm.org/doi/10.1145/3555776.3577758), SAC '23
  * 2023 - [Improving Storage Systems Using Machine Learning](https://dl.acm.org/doi/10.1145/3568429), ToS '23
    
## 10. Books, Courses: 
  * [CSCI 333, Storage Systems, Williams College](https://www.cs.williams.edu/~jannen/teaching/s21/cs333/index.html)
    > [Prof. Bill Jannen](https://www.cs.williams.edu/~jannen)
    
  * [Storage Systems, MSc, VU](https://atlarge-research.com/courses/storage-systems-vu/)
    > [Reviving Storage Systems Education in the 21st Century](https://atlarge-research.com/pdfs/2024-stosys-education.pdf), CCGrid '24, :clipboard: [Slides Show](https://docs.google.com/presentation/d/1XcGmP2kTrY-OW563licFKnbG05_p-jiU8E3eGHVkFY4/edit?pli=1&slide=id.g2d25b1f337f_0_286#slide=id.g2d25b1f337f_0_286)
    
  * [Operating Systems: Three Easy Pieces](https://pages.cs.wisc.edu/~remzi/OSTEP/)
    > * [39 Files and Directories](https://pages.cs.wisc.edu/~remzi/OSTEP/file-intro.pdf)
    > * [40 File System Implementation](https://pages.cs.wisc.edu/~remzi/OSTEP/file-implementation.pdf)
    > * [42 FSCK and Journaling](https://pages.cs.wisc.edu/~remzi/OSTEP/file-journaling.pdf)
    > * [43 Log-structured File System (LFS)](https://pages.cs.wisc.edu/~remzi/OSTEP/file-lfs.pdf)
    > * [44 Flash-based SSDs](https://pages.cs.wisc.edu/~remzi/OSTEP/file-ssd.pdf)
    > * [45 Data Integrity and Protection](https://pages.cs.wisc.edu/~remzi/OSTEP/file-integrity.pdf)
  
  * [The Linux Memory Manager](https://nostarch.com/linux-memory-manager)
    > * Chapter 9: The Page Cache
    > * Chapter 10: Writeback
    > * Chapter 11: Reclaim and Memory Pressure
    > * Chapter 12: Swap Memory
***
