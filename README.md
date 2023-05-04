Download Link: https://assignmentchef.com/product/solved-cs5348-assignment-3
<br>



<ol>

 <li>Consider the page reference sequence for a program P: 0 1 2 3 0 1 2 4 0 1 2 5 3 5 6 3. Load the pages following the page replacement policies given below. Also, compute the number of page faults incurred in each policy. Assume that the working set size is 4.

  <ul>

   <li>LRU</li>

   <li>Clock</li>

   <li>Aging: Assume that the page reference is for the entire system, not from a single program and the memory has only 4 pages. Apply aging policy to the access scenario above and give the aging vectors for all 4 pages. Assume that the system maintains 8 aging bits and before the above accesses the aging vectors for all 8 pages were 0. Also, assume that the background scanning and updating of aging vectors happened after every 2 accesses.</li>

  </ul></li>

</ol>




<ol start="2">

 <li>Consider a Unix-like file system with the I-node structure to index file blocks. The I-node data structure is given in the following: Each I-node contains 7 direct addresses, 2 single indirect address pointers, and one double indirect address pointer. (There is no triple indirect address pointer.) Assume that each address is 32 bits long. Also assume that each logical file block is of size 8KB. Given a file of size 100MB, is the inode sufficient to address all the blocks of the file.</li>

</ol>




<ol start="3">

 <li>Consider a Unix-like file system. It has file block size 4KB. Each inode is of size 128B and its format is as defined in Question 2. The plan is to support the storage of 1M files in the system. The average file size is 16KB.</li>

</ol>

A disk is used to host the file system, which has 512 sectors on each track and each sector is 512B.

The file system starts at track 0. Also, the disk uses the C-Scan algorithm for its arm scheduling. Currently, the disk head is at track 600 with a forward direction.




<ul>

 <li>What is the rough number of file data blocks to be allocated for the file system?</li>

 <li>How many blocks are needed for the file block map?</li>

 <li>How many inode blocks are needed for the file system?</li>

 <li>How many blocks are needed for the inode map?</li>

 <li>How many blocks total are required in the file system?</li>

 <li>How many tracks are required to host the file system?</li>

 <li>Assume that a file F was nonexisting and a command was just issued to created F in the given file system. F got an inum 1024 and its inode is as shown in the figure below after it is created. Assume that the pointers in the i-node is the block offset from the beginning of the file blocks. Also assume that the OS, upon creating a file, will calculate all the required updates to the disk and issue all the updates to the disk manager (arm scheduler) all together. Which tracks have been visited during the creation of F? Give these tracks in the order they are visited.</li>

</ul>

file direct direct direct direct direct direct direct single single double attributes pointer pointer pointer pointer pointer pointer pointer indirect indirect indirect

3500 1000 8000 null null null null pointer pointer pointer null null null




<ul>

 <li>Question (g) can be extended to compute the total disk access time. But I will not give it as a homework question because there are already a lot of questions. You can use any set of disk parameters in the notes to practice access time computation for this one. But it is just for your own practice and it is not a part of this assignment.</li>

</ul>




<ol start="4">

 <li>Consider a 500GB, 7200rpm disk. Each track on the disk has 128 sectors and each sector is 1KB. The disk arm traverses the tracks at 0.1 msec per track and requires a start up time 0.2msec. A file system is built on top of this disk and the size of each file block is 8KB. Note that a file block is always allocated contiguously on the disk. Consider a file of size 80KB. The file is allocated on the disk using indexed allocation scheme and the index table is kept in memory. The file contains 10 file blocks, which are allocated on tracks 105, 120, 112, 101, 113, 106, 116, 108, 111, and 115. Assume that the disk has a 1MB buffer and it uses the Scan algorithm for disk arm scheduling. Compute the time required to access the entire file. (Assume that there are no other disk access requests in the system and the current disk arm is at track 0.)</li>

</ol>







<ol start="5">

 <li>Consider a log-structured file system with each file block of size 4KB. Now we are updating file F1, and a new segment is started just before this update. The segment starts at block 10000 in the file system. The inode design and F1’s inode content are as given in Q3. We add 3 data blocks to F1 at offset 4KB. We also created a new file F2 with 4 data blocks. Now a flush occurred and the current part of the segment is written to disk. The inum for F1 and F2 are 87 and 233, respectively.

  <ul>

   <li>Give the current layout of the new segment (at a high level), indicating the data blocks for each file, the inode blocks, and the imap locations.</li>

   <li>Give the inodes for F1.</li>

   <li>Describe the imap content at a high level, no need to worry about the specific format.</li>

  </ul></li>

</ol>







<ol start="6">

 <li>Consider the clock device in Unix system.

  <ul>

   <li>Assume that the current time is March 4, 1971, 10:00:00 a.m. What would be the value in the clock register?</li>

   <li>Assume that current time is 10:22:30. Also, assume that the clock timer unit is 1 second. Consider the following timer requests being issued to the clock earlier. Show the timer data structure.

    <ul>

     <li>Process A issued command “sleep (100)” at time 10:22:00.</li>

    </ul></li>

  </ul></li>

</ol>

(O) OS set time quantum for current process at time 10:22:10. Time quantum is 30seconds.

<ul>

 <li>Process B issued command “set_timer (10:25:00)” at time 10:22:20.</li>

</ul>







<ol start="7">

 <li>Consider the following set of jobs.</li>

</ol>




<table width="498">

 <tbody>

  <tr>

   <td width="114">Job Number</td>

   <td width="64">1</td>

   <td width="64">2</td>

   <td width="64">3</td>

   <td width="64">4</td>

   <td width="64">5</td>

   <td width="64">6</td>

  </tr>

  <tr>

   <td width="114">Arrival Time</td>

   <td width="64">0</td>

   <td width="64">1</td>

   <td width="64">4</td>

   <td width="64">7</td>

   <td width="64">17</td>

   <td width="64">18</td>

  </tr>

  <tr>

   <td width="114">Service Time</td>

   <td width="64">6</td>

   <td width="64">2</td>

   <td width="64">4</td>

   <td width="64">2</td>

   <td width="64">4</td>

   <td width="64">2</td>

  </tr>

 </tbody>

</table>




Clearly show the scheduling of these jobs using the following algorithms (refer to the notes).

<ul>

 <li>Shortest job first (non-preemptive)</li>

 <li>Highest response ratio first (non-preemptive)</li>

 <li>Multilevel feedback queue (number of queue levels = 4, time quantum = 1)</li>

</ul>







<ol start="8">

 <li>Consider a real time system with the periodical jobs specified in the following table. A real time CPU scheduling algorithm, the rate monotonic algorithm, is used. Clearly show the scheduling of the jobs.</li>

</ol>




<table width="330">

 <tbody>

  <tr>

   <td width="108">Job name</td>

   <td width="60">A</td>

   <td width="54">B</td>

   <td width="54">C</td>

   <td width="54">D</td>

  </tr>

  <tr>

   <td width="108">Period</td>

   <td width="60">6</td>

   <td width="54">4</td>

   <td width="54">12</td>

   <td width="54">6</td>

  </tr>

  <tr>

   <td width="108">Service time</td>

   <td width="60">1</td>

   <td width="54">1</td>

   <td width="54">2</td>

   <td width="54">1</td>

  </tr>

 </tbody>

</table>







<ol start="9">

 <li>Consider RAID level 4 disk array with a configuration as shown below.</li>

</ol>




<ul>

 <li>If a sequence of read requests retrieve data blocks 1, 6, 8, 9, 13, 15, 16, how many rounds of parallel accesses will need to be performed? Which blocks will be accessed in each round?</li>

</ul>




<ul>

 <li>If a sequence of write requests access data blocks 1, 3, 4, 6, 7, how many rounds of parallel accesses will need to be performed? Which blocks will be accessed in each round? Give an answer that will require the least number of block accesses.</li>

</ul>