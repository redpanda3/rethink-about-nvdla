It's been 7 years since NVDLA was published, here are some common issues collected from NVDLA IP users in the industry:
## Hard to Use from the Software Perspective -- from Car Factory Side
NVDLA requires the CPU side to prepare the data(a shaped image, a layer to be sent) and send it to memory, most of the work needs to be done by the CPU side. Although NVDLA has the advantage of DSA low power, engineers in the car industry prefer to use shader cores or SIMT, rather than NPU. 
## Low Performance on the Server Side in Scalability -- from Internet Company
NVDLA Sequence Controller, which is the CSC module, 'locks up' every step to calculate. There is no way to escalate the power of calculation, maybe in the NVDLA private version, switching NHWC to NCHW might help, but none of us from the open-source world wants to modify it from cmod to rtl to dv, that costs too much.
## Costly to Build Up an NVDLA-based SOC -- from Startup Company
Although in theory, you can build up an NVDLA-based SOC without a CPU to maintain your business in some specific detection. But in reality, you need a CPU to configure each of the registers in NVDLA, and also, you will need a memory controller IP(DDR, etc...) to store the data. Mostly, I saw people use NVDLA in FPGA for demo use, but there is still a huge gap between FPGA and ASIC(peripheral IP, CPU).

## Adios to the NVDLA
I tried to expand NVDLA to common algorithms in self-driving car applications in 2020 with my own company, NProcessor(not existing anymore) and failed(in software stack, in scalability, in ASIC proof, more importantly, in my awful CEO strategy). During those years, I saw people still interested in this design, so I continued to maintain the soDLA(a chisel version of NVDLA) during my leisure time, adding more integration and verifications to it. Maybe many years later, people will say, "I like its ping-pong buffer" or "I like the completeness of cmodel, vmodel and virtual platform", but you'll admit that NVDLA's glory is gone.

## What's Next

Will it be possible for NVDLA to switch to a software-friendly, low-end-process-friendly, scalability-enabled IP?
I'm glad to hear your opinion.
