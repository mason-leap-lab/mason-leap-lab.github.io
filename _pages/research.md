---
title: "LeapLab - Research"
layout: textlay
excerpt: "LeapLab -- Research"
sitemap: false
permalink: /research/
---

# Serverless Computing 

Our work in serverless computing spans each layer of the stack, from
applications, middleware and infrastructure, to lower-level OSes. 

## New serverless applications

### Building a cost-effective memory cache atop serverless functions

![]({{ site.url }}{{ site.baseurl }}/images/research/infinicache_arch.png){: style="width: 40%; float: left; margin: 10px  10px"}
Internet-scale web applications are becoming increasingly
storage-intensive and rely heavily on in-memory object caching to
attain required I/O performance. We argue that the emerging
serverless computing paradigm provides a well-suited, cost-effective
platform for object caching. We present InfiniCache, a
first-of-its-kind in-memory object caching system that is completely
built and deployed atop ephemeral serverless functions. InfiniCache
exploits and orchestrates serverless functions' memory resources to
enable elastic pay-per-use caching. InfiniCache's design combines
erasure coding, intelligent billed duration control, and an efficient
data backup mechanism to maximize data availability and
cost-effectiveness while balancing the risk of losing cached state
and performance. We implement InfiniCache on AWS Lambda and show that
it: (1) achieves 31 – 96× tenant-side cost savings compared to AWS
ElastiCache for a large-object-only production workload, (2) can
effectively provide 95.4% data availability for each one hour window,
and (3) enables comparative performance seen in a typical in-memory
cache.

**paper and source code**

*InfiniCache: Exploiting Ephemeral Serverless Functions to Build a Cost-Effective Memory Cache*<br/>
Ao Wang, Jingyuan Zhang, Xiaolong Ma, Ali Anwar, Lukas Rupprecht,
Dimitrios Skourtis, Vasily Tarasov, Feng Yan, Yue Cheng<br/>
[Paper and talk](https://www.usenix.org/conference/fast20/presentation/wang-ao),
[Website](https://mason-leap-lab.github.io/infinicache/),
[GitHub](https://github.com/mason-leap-lab/infinicache),
[Hacker news](https://news.ycombinator.com/item?id=25788893).


### Serverless parallel computing

![]({{ site.url }}{{ site.baseurl }}/images/research/wukong.jpg){: style="width: 30%; float: right; margin: 10px  10px"}
Executing complex, burst-parallel, directed acyclic graph (DAG) jobs
poses a major challenge for serverless execution frameworks, which
will need to rapidly scale and schedule tasks at high throughput,
while minimizing data movement across tasks. We demonstrate that, for
serverless parallel computations, decentralized scheduling enables
scheduling to be distributed across Lambda executors that can
schedule tasks in parallel, and brings multiple benefits, including
enhanced data locality, reduced network I/Os, automatic resource
elasticity, and improved cost effectiveness. We describe the
implementation and deployment of our new serverless parallel
framework, called Wukong, on AWS Lambda. We show that Wukong achieves
near-ideal scalability, executes parallel computation jobs up to
68.17X faster, reduces network I/O by multiple orders of magnitude,
and achieves 92.96% tenant-side cost savings compared to numpywren.

**paper and source code**

*Wukong: A Scalable and Locality-Enhanced Framework for Serverless Parallel Computing*<br/>
Benjamin Carver, Jingyuan Zhang, Ao Wang, Ali Anwar, Panruo Wu, Yue Cheng<br/>
[Paper]({{ site.url }}{{ site.baseurl }}/docs/socc20-wukong.pdf),
[Talk](https://www.youtube.com/watch?v=W0tENnx_58I),
[Website](https://mason-leap-lab.github.io/Wukong/),
[GitHub](https://github.com/mason-leap-lab/Wukong/tree/socc2020).


## Optimizing FaaS platform

More to come, stay tuned...


## Rethinking the OS design for FaaS workloads

More to come, stay tuned...
<br/><br/>



# Distributed Learning

## Federated learning


![]({{ site.url }}{{ site.baseurl }}/images/research/fl_arch.jpg){: style="width: 35%; float: left; margin: 10px  10px"}
Federated Learning (FL) enables learning a shared model acrossmany
clients without violating the privacy requirements. One of the key
attributes in FL is the heterogeneity that exists in both resource
and data due to the differences in computation and communication
capacity, as well as the quantity and content of data among different
clients. We conduct a case study to show that heterogeneity in
resource and data has a significant impact on training time and model
accuracy in conventional FL systems. To this end, we propose TiFL, a
Tier-based Federated Learning System, which divides clients into
tiers based on their training performance and selects clients from
the same tier in each training round to mitigate the straggler
problem caused by heterogeneity in resource anddata quantity. To
further tame the heterogeneity caused by non-IID (Independent and
Identical Distribution) data and resources, TiFL employs an adaptive
tier selection approach to update the tiering on-the-fly based on the
observed training performance and accuracy. We prototype TiFL in a FL
testbed following Google's FL architecture and evaluate it using the
state-of-the-art FL benchmarks. Experimental evaluation shows that
TiFL outperforms the conventional FL in various heterogeneous
conditions. With the proposed adaptive tier selection policy, we
demonstrate that TiFL achieves much faster training performance while
achieving the same or better test accuracy across the board.

**paper**

*TiFL: A Tier-based Federated Learning System*<br/>
Zheng Chai, Ahsan Ali, Syed Zawad, Stacey Truex, Ali Anwar, Nathalie
Baracaldo, Yi Zhou, Heiko Ludwig, Feng Yan, Yue Cheng<br/>
[Paper]({{ site.url }}{{ site.baseurl }}/docs/hpdc20-tifl.pdf).

