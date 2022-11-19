# Use diskbench to Measure IOPS

For things like etcd knowing how fast your disks are is crucial. To
measure IOPS take the number of operations and divide the total seconds
`bench` takes to run. A 2016 Mac Mini, for example, has 90 IOPS (which
is over the minimum recommended of 50).

* Hardware recommendations \| etcd  
  <https://etcd.io/docs/v3.6/op-guide/hardware/>

* GitHub - ongardie/diskbenchmark: Benchmarking utilities for measuring the latencies of disks (mostly interesting for SSDs).  
  <https://github.com/ongardie/diskbenchmark>
