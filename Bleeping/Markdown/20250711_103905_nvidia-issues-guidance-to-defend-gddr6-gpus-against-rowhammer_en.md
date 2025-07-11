# NVIDIA issues guidance to defend GDDR6 GPUs against Rowhammer attacks

![NVIDIA issues guidance to defend GDDR6 GPUs against Rowhammer](https://www.bleepstatic.com/content/hl-images/2022/03/01/NVIDIA___headpic.jpg)

NVIDIA is warning users to activate the System Level Error-Correcting Code mitigation to protect against Rowhammer attacks on graphical processors with GDDR6 memory.

The company is reinforcing the recommendation as new research demonstrates a Rowhammer attack against an NVIDIA A6000 GPU (graphical processing unit).

Rowhammer is a hardware fault that can be triggered through software processes and stems from memory cells being too close to each other. If one location is bombarded with enough read-write operations, the value of the adjacent data bits can be flipped from one to zero and vice-versa, and thus change the in-memory information.

The effect could be a denial-of-service condition, data corruption, or even privilege escalation.

System Level Error-Correcting Codes (ECC) can preserve the integirty of the data by adding redundant bits and correcting single-bit errors to maintain data reliability and accuracy.

In workstation and data center GPUs where VRAM handles large datasets and precise calculations related to AI workloads, ECC must be enabled to prevent crucial errors in their operation.

NVIDIA's security notice notes that researchers at the University of Toronto showed "a potential Rowhammer attack against an NVIDIA A6000 GPU with GDDR6 Memory" where System-Level ECC was not enabled.

Apart from the RTX A6000, the GPU maker also [recommends](https://nvidia.custhelp.com/app/answers/detail/a%5Fid/5671) enabling System-Level ECC for the following products:

**Data Center GPUs:**

* Ampere: A100, A40, A30, A16, A10, A2, A800
* Ada: L40S, L40, L4
* Hopper: H100, H200, GH200, H20, H800
* Blackwell: GB200, B200, B100
* Turing: T1000, T600, T400, T4
* Volta: Tesla V100, Tesla V100S

**Workstation GPUs:**

* Ampere RTX: A6000, A5000, A4500, A4000, A2000, A1000, A400
* Ada RTX: 6000, 5000, 4500, 4000, 4000 SFF, 2000
* Blackwell RTX PRO (newest workstation line)
* Turing RTX: 8000, 6000, 5000, 4000
* Volta: Quadro GV100

**Embedded / Industrial:**

* Jetson AGX Orin Industrial
* IGX Orin

The GPU maker notes that newer GPUs like Blackwell RTX 50 Series (GeForce), Blackwell Data Center GB200, B200, B100, and Hopper Data Center H100, H200, H20, and GH200, come with built-in on-die ECC protection, which does nor require an intervention from the user.

One way to check if System Level ECC is enabled is to use an out-of-band method that utilizes the system's BMC (Baseboard Management Controller) and hardware interface software, like the [Redfish API](https://www.dmtf.org/standards/redfish), to check the "ECCModeEnabled" status.

Tools like NSM Type 3 and NVIDIA SMBPBI can also be used for configuration, though they require access to the NVIDIA Partner Portal.

A second In-Band method also exists, using the nvidia-smi command-line utility from the system's CPU to check and enable ECC where supported.

Rowhammer represents a real security concern that could cause data corruption or enable attacks in multi-tenant environments like cloud servers where vulnerable GPUs may be deployed.

However, the real risk is context-dependent, and exploiting Rowhammer reliably is complicated, requiring specific conditions, high access rates, and precise control, making it an attack difficult to execute.