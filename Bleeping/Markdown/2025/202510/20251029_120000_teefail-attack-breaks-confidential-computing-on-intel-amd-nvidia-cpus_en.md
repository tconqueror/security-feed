# TEE.Fail attack breaks confidential computing on Intel, AMD, NVIDIA CPUs

![TEE.Fail attack breaks confidential computing on Intel, AMD, NVIDIA CPUs](https://www.bleepstatic.com/content/hl-images/2023/11/14/CPU_attack.jpg)

Academic researchers developed a side-channel attack called TEE.Fail, which allows extracting secrets from the trusted execution environment in the CPU, the highly secure area of a system, such as Intel's SGX and TDX, and AMD's SEV-SNP.

The method is a memory-bus interposition attack on DDR5 systems that could be successfully done by computer hobbyists a cost of less than $1,000.

Trusted Execution Environments (TEEs) are “confidential computing” hardware within the main processor that ensure confidentiality and integrity of sensitive data, like cryptographic keys used for authentication and authorization.

This environment is isolated from the operating system and creates protected regions of memory where code and data can run securely.

Researchers from Georgia Tech and Purdue University note that modern implementations of Intel SGX, Intel TDX, and AMD SEV-SNP are no longer as secure as advertised, due to architectural trade-offs in recent generations.

Specifically, TEEs moved from client CPUs to server-grade hardware using DDR5 memory, which adopted deterministic AES-XTS memory encryption and stripped away memory integrity and replay protections in favor of performance and scalability.

Their experiments confirmed that it is possible to exploit these weaknesses for key extraction and attestation forgery. TEE.Fail is the first DDR5-based ciphertext attack, extending prior DDR4 work like [WireTap](https://wiretap.fail/) and [BatteringRAM](https://batteringram.eu/).

## Attack and implications

The attack requires physical access to the target as well as root-level privileges for Kernel driver modification, but no chip-level expertise.

In the technical paper, the researchers explain that they were able to capture the signal reliably by reducing the system’s memory clock to 3200 MT/s (1.6 GHz). For this, they attached a RDIMM riser and a custom probe isolation network between a DDR5 DIMM and the motherboard.

![The snooping rig (right) and the target (left)](https://www.bleepstatic.com/images/news/u/1220909/2025/October/rig.jpg)

**The snooping rig (right) and the target (left)**  
_Source: tee.fail_

With the interposer connected to a logic analyzer, the attacker records DDR5 command/address and data bursts, so they can see ciphertexts written to and read from physical DRAM locations.

![DDR5 memory bus traffic during a TEE.fail attack](https://www.bleepstatic.com/images/news/u/1220909/2025/October/analuze.jpg)

**DDR5 memory bus traffic during a TEE.fail attack**  
_Source: tee.fail_

To achieve their goal with Intel's SGX, the researchers had to force the data in virtual addresses into a single memory channel that they could observe through the interposer.

Through an interface for physical addresses that Intel exposed to the Memory Address Translation component, the researchers could "further expose this decoding interface to userspace via _sysfs._"

This let them find the info for determining the DIMM location for the physical address.

However, SGX uses the OS kernel for physical memory allocation and the researchers had to "modify the kernel’s SGX driver to accept a virtual and physical address pair as a parameter to be stored in global kernel memory."

The researchers say that they created an SGX enclave that bombarded a specific memory virtual address with read and write operations. This let them verify that the encrypted ciphertext observed on the memory interposer was a deterministic function of the physical memory address and its contents.

"To check that encryption is deterministic, we instruct our enclave to perform a series of write and read operations to a fixed virtual address in enclave memory, capturing the ciphertext read data after each step using our logic analyzer," they explain.

Because of the use of the AES-XTS encryption, where a piece of information is encrypted to the same output every time, the team wrote known values to the observable physical addresses to build a ciphertext to value mapping.

**Ciphertext from three reads of enclave data**  
_Source: tee.fail_

Then, by triggering and recording targeted crypto operations, they observe encrypted accesses to intermediate table entries and recover the per-signature nonce digits.

From the recovered nonce and the public signature, they reconstruct private signing keys, which lets them forge valid SGX/TDX quotes and impersonate genuine TEEs.

The same approach was used to extract signing keys from OpenSSL running in a virtual machine protected by AMD's SEV-SNP.

It is worth noting that the attacks against AMD SEV-SNP still work even when the “Ciphertext Hiding” security option is enabled.

The researchers showcased attacks that allowed them to:

* Forge TDX attestations on Ethereum BuilderNet to access confidential transaction data and keys, enabling undetectable frontrunning.
* Fake Intel and NVIDIA attestations to run workloads outside TEEs while appearing legitimate.
* Extract ECDH private keys directly from enclaves, recovering the network’s master key, and fully breaching confidentiality.

Through TEE.Fail, the researchers were able to demonstrate that it is possible to take control of TEE execution and observe specific virtual addresses. The researchers also targeted a Xeon server and obtained the Provisioning Certificate Key (PCK) - used for verifying the identity of a device.

TEE.Fail is a complext attack that requires physical access. This makes it less practical in a real-world scenario and its complexity is far from a threat to the average user.

The researchers reported their findings to Intel in April, to AMD in August, and to NVIDIA in June. All three vendors acknowledged the issues and stated they were working on mitigations and adaptations for the confidential computing threat model, with plans to publish official statements when the TEE.Fail paper becomes public.

BleepingComputer has asked Intel, AMD, and NVIDIA to share their statements for inclusion in this report, but we have not heard back by publication.