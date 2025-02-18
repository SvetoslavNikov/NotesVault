![[Pasted image 20250130135631.png]]
		  **VM**                                            **LXC**                                                   **Docker** 


![[Pasted image 20250130201045.png]]

## Virtual machine

Software that creates whole isolated computer system, starting from the bottom with full Operating system (with Kernel and everything) , Libraries and Applications. Hardware allocation is managed by the Hypervisor.
1. Use for Legacy system that run on specific OS
2. Security research with Kali Linux
3. Scenarios where strong isolation is requaried for security reasons.

- Heavy on resources
- Slow to boot

## Containers

Containers share the operating system's kernel of the host but run in isolated user spaces. (If the OS hasn't the proper kernel Docker will run lightweight VM with it). It carries the necessary Libraries and Binaries and the Application.
1. 