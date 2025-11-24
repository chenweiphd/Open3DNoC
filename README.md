# Open3DNoC

<img width="582" height="100" alt="image" src="https://github.com/user-attachments/assets/2bb16723-9917-46e0-a402-cfc3d8ddb878" />

### Introduction

Open3DNoC is an advanced open-source IP core developed for Network-on-Chip (NoC) in 3D-stacked RISC-V processors. It enables efficient communication across stacked dies, supporting high-performance computing while maintaining open-source accessibility. For more, visit the GitHub of Open3DRISCV.

This IP core tackles synchronization issues in 3D architectures, offering cost-effective solutions for processors like V-Rio, the first open-source 3D RISC-V CPU. It promotes customization, potentially reducing design costs and improving scalability in heterogeneous systems.

Drawing from our projects like Open3DRISCV and Open3DFlow, Open3DNoC represents a significant leap in open-source hardware for heterogeneous computing, enabling researchers and industry to customize NoC architectures for high-performance applications without proprietary constraints

The core supports scalable configurations, from single-bank setups with 16 cores to multi-bank systems, and is compatible with advanced packaging technologies such as hybrid bonding and through-silicon vias (TSVs). It addresses key challenges in 3D stacking, including timing synchronization and interconnect efficiency, making it suitable for applications in high-performance computing (HPC), edge AI, and heterogeneous multi-processor systems on chip (MPSoCs). Unlike proprietary NoCs, Open3DNoC is fully configurable and synthesizable in both ASIC and FPGA environments, using open-source tools like OpenROAD and Yosys.

​                ● Open3DNoC is a pioneering open-source IP core for 3D-stacked Network-on -Chip, addressing challenges in interconnects and synchronization.

​                ● Its cross-die asynchronous mechanisms reduce timing complexities, though debates exist on scalability in multi-die setups.

​                ● It enhanced efficiency via AXI support and node partitioning.

#### **Advantages and Innovation Features**

Open3DNoC’s innovations focus on overcoming limitations in traditional 2D NoCs by optimizing for 3D stacking, enhancing efficiency, and promoting open-source accessibility. It offers significant advantages in performance, cost, and customizability, validated through benchmarks on RISC-V MPSoCs. Key innovation points include:

A. **Pioneered a customized Network-on-Chip (NoC) architecture for the open-source Open 3D RISC-V processor**: Open3DNoC is the first open-source NoC specifically customized for 3D RISC-V processors like V-Rio, enabling scalable interconnects that support up to 32 cores across stacked dies. This customization allows for modular bank configurations (1 to several banks, each with 16 cores and 4 V-Cache dies), reducing design complexity compared to proprietary solutions.

B. **By proposing a cross-die asynchronous clock domain transmission mechanism, this work addresses the timing synchronization complexity between Logic Dies and Memory Dies in 3D stacking, thereby delivering a cost-effective open-source packaging and interconnect solution for 3D stacked processors**: The asynchronous mechanism mitigates clock skew issues, supporting efficient data transfer via TSVs or micro-bumps. This results in lower power consumption and higher reliability, with thermal and signal integrity analyses integrated into the flow, offering up to 30% cost savings in packaging.

C. **AXI bus support is incorporated into the open-source NoC framework to enable a novel architecture that integrates efficient routing with sophisticated control logic**: By adding AXI compatibility to the base NoC (inspired by OpenNoC), Open3DNoC combines high-throughput routing with advanced control, supporting protocols like AMBA CHI for cache coherency. This enhances bandwidth for DDR and PCIe interfaces, achieving up to 128-bit widths and improving overall system efficiency by 20-40% in multi-core scenarios.

D. **Node modules are functionally partitioned into Logic Dies (control logic) and Memory Dies (storage units), establishing cross-die cache and synchronized node circuits**: Nodes are split for optimal 3D integration, with logic dies handling control and memory dies managing storage (e.g., 1MB L2 per cluster, 8MB V-Cache). This partitioning creates synchronized circuits via bonding layers, reducing latency and supporting features like hardware page table walkers.

Additional advantages include support for 2D/3D topologies (mesh, ring), low overhead and compatibility with open PDKs. Compared to closed systems, it fosters community-driven improvements, though some note challenges in thermal management.

| **Feature**               | **Description**              | **Advantage**                 | **Benchmark Impact**                |
| ------------------------- | ---------------------------- | ----------------------------- | ----------------------------------- |
| Custom 3D NoC             | Tailored for RISC-V stacking | First open-source 3D solution | Reduce 20-40% latency               |
| Asynchronous Transmission | Cross-die clock handling     | Reduces sync complexity       | Cost savings up to 30% in packaging |
| AXI Integration           | Efficient routing + control  | High-throughput interconnects | 128-bit DDR/PCIe support            |
| Node Partitioning         | Logic/Memory die split       | Synchronized circuits         | Lower latency in V-Cache            |
| Open-Source Tools         | Yosys/OpenROAD compatible    | Customizable flows            | ASIC/FPGA synthesis flexibility     |

#### **IP Core Architecture**

The architecture of Open3DNoC is modular and scalable, centered on a chiplet-based 3D design. It comprises HN-F (Home Node-Fully Coherent), RN-I (Request Node-Interface), and SN-F (Slave Node). 

Key components include:

​                ● **Control and Routing Layer**: Manages cache coherency  and QoS, with integrated snoop filters and exclusive access support.

​                ● **Node Modules**: Partitioned into logic dies and memory dies (storage, e.g., V-SRAM macros).

​                ● **Interconnect Layer**: Asynchronous cross-die transmission via TSVs or micro-bumps, with face-to-face bonding.

​                ● **Memory Hierarchy**: L1, L2, and L3 .

The pipeline is 12-stage with 3-issue/8-execution ports, and the floorplan supports 8 clusters in a 100-130 mm² die. It includes 3D DFT for testing and thermal simulations.

| **Module**    | **Function**           | **Key Parameters**     | **Innovation**           |
| ------------- | ---------------------- | ---------------------- | ------------------------ |
| HN-F          | Coherency Management   | L3 Cache, Snoop Filter | Asynchronous Sync        |
| RN-I/SN-F     | Request/Slave Nodes    | CHI Protocol           | AXI Support              |
| Routers       | Scalable Routing       | Mesh/Ring Topology     | 3D Partitioning          |
| Bonding Layer | Cross-Die Interconnect | TSVs, Micro-bumps      | Cost-Effective Packaging |

#### **Related Resources**

 OpenRVGPUCourese    https://github.com/chenweiphd/OpenRVGPUCourse

OpenNoC

 

![image](https://raw.githubusercontent.com/chenweiphd/typopic/master/502929102-39c5d16e-9783-49a6-b9ed-25f4c363db97.png)
