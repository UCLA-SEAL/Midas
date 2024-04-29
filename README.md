# Midas
Harvesting Idle Memory for Application-managed Soft State with Midas ([NSDI 2024](https://www.usenix.org/conference/nsdi24/presentation/qiao))

## Summary
Many applications can benefit from data that increases performance but is not required for correctness (commonly referred to as soft state). Examples include cached data from backend web servers and memoized computations in data analytics systems. Today's systems generally statically limit the amount of memory they use for storing soft state in order to prevent unbounded growth that could exhaust the server's memory. Static provisioning, however, makes it difficult to respond to shifts in application demand for soft state and can leave significant amounts of memory idle. Existing OS kernels can only spend idle memory on caching disk blocks—which may not have the most utility—because they do not provide the right abstractions to safely allow applications to store their own soft state.

To effectively manage and dynamically scale soft state, we propose soft memory, an elastic virtual memory abstraction with unmap-and-reconstruct semantics that makes it possible for applications to use idle memory to store whatever soft state they choose while guaranteeing both safety and efficiency. We present Midas, a soft memory management system that contains (1) a runtime that is linked to each application to manage soft memory objects and (2) OS kernel support that coordinates soft memory allocation between applications to maximize their performance. Our experiments with four real-world applications show that Midas can efficiently and safely harvest idle memory to store applications' soft state, delivering near-optimal application performance and responding to extreme memory pressure without running out of memory.

## Team
This project is done in collaboration with Professor [Harry Xu](http://web.cs.ucla.edu/~harryxu/)'s group at UCLA and Professor [Adam Belay](http://www.abelay.me/)'s group at MIT. Please visit [Midas project at UCLA Systems](https://github.com/uclasystem/midas). If you encounter any problems, please open an issue or feel free to contact us:

[Yifan Qiao](https://web.cs.ucla.edu/~yifan/): PhD student, [yifanqiao@ucla.edu](mailto:yifanqiao@ucla.edu).

## How to cite 
Please refer to our NSDI'24 paper, **[Harvesting Idle Memory for Application-managed Soft State with Midas](https://www.usenix.org/system/files/nsdi24-qiao.pdf)** for more details.

### Bibtex  
```txt
@inproceedings {qiao2024midas,
author = {Yifan Qiao and Zhenyuan Ruan and Haoran Ma and Adam Belay and Miryung Kim and Harry Xu},
title = {Harvesting Idle Memory for Application-managed Soft State with Midas},
booktitle = {21st USENIX Symposium on Networked Systems Design and Implementation (NSDI 24)},
year = {2024},
isbn = {978-1-939133-39-7},
address = {Santa Clara, CA},
pages = {1247--1265},
url = {https://www.usenix.org/conference/nsdi24/presentation/qiao},
publisher = {USENIX Association},
month = apr
}
```
