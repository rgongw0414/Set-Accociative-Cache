Set Associative Cache
=
Computer Architecture Lab1 project
---
### 目的：了解Cache Controller接受到處理器所給予的記憶體位置時，當Cache的空間大小和區塊大小不同時，如何影響到Miss Rate。

#### 說明：實作一個Set Associative機制的Cache

#### 其中，在def main可手動調整變數: <br>
    BS_BlockSize (Cache Block size, default: 16 Byte) <br>
    CS_CacheSize (Cache的大小，default: 1024
#### input (trace.txt) 說明：
trace.txt：檔案中每一行代表處理器給予Cache Controller的記憶體位置，格式如下：

```bash
0x0A985540
0x0A985548
0x0A985550
0x0A985558
0x0A985560
0x0A985568
0x11D763A0
0x11D763A0
0x13F0E838
0x13F0E840
0x13F0E848
0x186E70E0
```
cache_size：Cache的大小，單位為KByte
block_size：每個Cache Block的大小，單位為Word
set_degree：一個set中的cache block個數

輸出格式：執行完畢後，輸出Miss Rate。

input: trace.txt (16進位addresses) <br> 
output: output.txt (clock by clock status of Register_result_state, Resevation_Station, Load/Store_Buffer and Memory) <br> 

How to use: <br>
```bash
python3 trace.py 
```

and in terminal, it should be like: 
```bash
There are 65536 Cache Blocks
1-way associative cache, with 65536 sets.
The number of request: 5003, Hit_count: 2332
Miss rate: 0.533880
-

There are 65536 Cache Blocks
2-way associative cache, with 32768 sets.
The number of request: 5003, Hit_count: 2335
Miss rate: 0.533280
-

There are 65536 Cache Blocks
4-way associative cache, with 16384 sets.
The number of request: 5003, Hit_count: 2335
Miss rate: 0.533280
-

There are 65536 Cache Blocks
8-way associative cache, with 8192 sets.
The number of request: 5003, Hit_count: 2335
Miss rate: 0.533280
-
```

sample output (of output.txt):
```bash
Block size = 16 (Byte)
Cache size = 1024K (Byte)
Set degree = 1
Miss rate = 0.533880

Block size = 16 (Byte)
Cache size = 1024K (Byte)
Set degree = 2
Miss rate = 0.533280

Block size = 16 (Byte)
Cache size = 1024K (Byte)
Set degree = 4
Miss rate = 0.533280

Block size = 16 (Byte)
Cache size = 1024K (Byte)
Set degree = 8
Miss rate = 0.533280
```
