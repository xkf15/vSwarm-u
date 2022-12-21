<!-- # **vSwarm-&mu;:** Microarchitectural Research for Serverless -->
![vSwarm-u Header](docs/figures/vSwarm-u-hdr.png)


[![Build Linux Kernel](https://github.com/vhive-serverless/vSwarm-u/actions/workflows/build_kernel.yml/badge.svg)](https://github.com/vhive-serverless/vSwarm-u/actions/workflows/build_kernel.yml)
[![Build Gem5](https://github.com/vhive-serverless/vSwarm-u/actions/workflows/build_gem5.yml/badge.svg)](https://github.com/vhive-serverless/vSwarm-u/actions/workflows/build_gem5.yml)
[![Build base disk image](https://github.com/vhive-serverless/vSwarm-u/actions/workflows/create_base_disk.yml/badge.svg)](https://github.com/vhive-serverless/vSwarm-u/actions/workflows/create_base_disk.yml)
[![Function CI for gem5 Simulator](https://github.com/vhive-serverless/vSwarm-u/actions/workflows/function_ci.yml/badge.svg)](https://github.com/vhive-serverless/vSwarm-u/actions/workflows/function_ci.yml)

[![doc](https://img.shields.io/badge/doc-latest-green)](https://vhive-serverless.github.io/vSwarm-u/)
![GitHub release (latest by date)](https://img.shields.io/github/v/release/vhive-serverless/vSwarm-u)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
<a href="https://twitter.com/intent/follow?screen_name=ease_lab" target="_blank">
<img src="https://img.shields.io/twitter/follow/ease_lab?style=social&logo=twitter" alt="follow on Twitter"></a>

<!-- ![GitHub Workflow Status](https://img.shields.io/github/workflow/status/vhive-serverless/vSwarm-u/function_ci.yml?logo=Build%20kernel) -->

<!-- ![](https://img.shields.io/static/v1?label=&message=documentation&color=green) -->

<!-- ![vSwarm-u Header](docs/figures/vhive_hdr.jpg) -->


Serverless computing represent a new class of workloads, challenging the microarchitecture of modern CPU's. The mission of vSwarm-&mu; is to provide microarchitect's with the tools they need to address those challenges in next generation CPU's. As such vSwarm-&mu; is part of the [vHive Ecosystem](https://vhive-serverless.github.io/) and allow cycle accurate simulations of containerized serverless benchmarks from [vSwarm](https://github.com/vhive-serverless/vSwarm) using [gem5](https://www.gem5.org/)


<!-- <span style="color:green;font-weight:700;font-size:20px">
    markdown color font styles
</span> -->


## Challenges of Serverless Host Simulation

Serverless computing has emerged as a widely used paradigm for deploying services in the cloud. However, with their unique characteristics of short execution times and infrequent invocation of function instances serverless workloads set new demands on both the microarchitecture of modern server CPU’s as well as the research tools built to design this microarchitecture.

gem5 is the state-of-the-art research platform for system- and microarchitecture but does not support key layers of the serverless software stack in its reference setup. Moreover, the common way of ignoring large parts of the system stack and simplifying test scenarios in favour of simulation speed is not applicable to serverless. Due to its significant part faction of execution time spend in communication and system stack components such simplifications may result in wrong experimental data and, consequently, mislead research.


## The vSwarm-&mu; Framework

| Serverless software stack on gem5 | Serverless Test infrastructure |
|---|---|
| <img src="./docs/figures/serverless-stack.jpg" title="Serverless Stack"/> | <img src="./docs/figures/serverless-system.jpg" title="vSwarm-u design"/> |

vSwarm-&mu; offers two main components to address the challenges of serverless host simulation. A full serverless software stack including kernel, OS and packages compatible with gem5. Furthermore, the infrastructure to drive function instances running on the simulated serverless host server without interfering or simplifying the complexity of the test system.

That will equip microarchitect's and researchers with the tools they need to identify the real bottlenecks in modern hardware when running serverless workloads.

Interested? Find more information why and how we build vSwarm-&mu; from its first [presentation](https://vhive-serverless.github.io/vSwarm-u/methodology/) and the remaining documentation.

## Key features of vSwarm-&mu;

To enable microarchitectural innovation, vSwarm-&mu; provides a ready-to-use serverless simulation platform based on the gem5 simulator. 
With vSwarm-&mu;, 20 functions from the [vSwarm](https://github.com/vhive-serverless/vSwarm) benchmark suite are ready to run in gem5 unmodified from their deployment on real hardware – i.e., in the same OS environment and containerization.

This is enabled through a set of tools, configurations and documentation to facilitate the necessary multi-node ([client-server](https://vhive-serverless.github.io/vSwarm-u/simulation/systems/#two-machine-model)) setup in gem5, [load generation](https://github.com/vhive-serverless/vSwarm-u/tree/main/tools/client), [function deployment](https://vhive-serverless.github.io/vSwarm-u/simulation/basics/#workflow),
and [results analysis](https://vhive-serverless.github.io/vSwarm-u/analysis/basic_analysis/). Uniquely, because function execution times are relatively short, vSwarm-&mu; affords simulation of end-to-end function execution without the need for sampling or workload subsetting.


## Referencing our work

If you decide to use vSwarm-&mu; for your research and experiments, we are thrilled to support you by offering
advice for potential extensions of vSwarm-&mu; and always open for collaboration.

Please cite our [paper](https://ease-lab.github.io/ease_website/pubs/JUKEBOX_ISCA22.pdf) that has been recently accepted to ISCA 2022:


```
@inproceedings{schall:lukewarm,
  author    = {Schall, David and
               Margaritov, Artemiy and
               Ustiugov, Dmitrii and
               Sandberg, Andreas and
               Grot, Boris},
  title     = {Lukewarm Serverless Functions: Characterization and Optimization},
  year      = {2022},
  isbn      = {9781450386104},
  publisher = {Association for Computing Machinery},
  address   = {New York, NY, USA},
  doi       = {10.1145/3470496.3527390},
  booktitle = {Proceedings of the 49th Annual International Symposium on Computer Architecture},
  pages     = {757–770},
  numpages  = {14},
  keywords  = {characterization, instruction prefetching, microarchitecture, serverless},
  location  = {New York, New York},
  series    = {ISCA '22}
}
```



## Getting started with vSwarm-&mu;

vSwarm-&mu; can be deployed on premises or in the cloud, with support for nested virtualization. We provide [a quick-start guide](https://vhive-serverless.github.io/vSwarm-u/quick_start/)
that describes the initial setup, as well as how to set up benchmarking experiments.


### Getting help and contributing

We would be happy to answer any questions in GitHub Issues and encourage the open-source community to submit new Issues, assist in addressing existing issues and limitations, and contribute their code with Pull Requests.


## License and copyright

vSwarm-&mu; is free. We publish the code under the terms of the MIT License that allows distribution, modification, and commercial use.
This software, however, comes without any warranty or liability.

The software is maintained by the [vHive Ecosystem](https://vhive-serverless.github.io/) as well as the [EASE lab](https://easelab.inf.ed.ac.uk/) as part of the University of Edinburgh.


### Maintainers

* David Schall: [GitHub](https://github.com/dhschall), [web page](https://dhschall.github.io/)



## Directory Structure

- `simulation` contains everything related to run simulations.
- `setup` contains all scripts and makefiles to setup vSwarm-&mu;
- `tools` includes a client that can be instrumented for gem5
- `runner` is for setting up self-hosted GitHub Actions runners.
- `docs` contains the documentation on a number of relevant topics.



## Known problems

Sometimes the simulator get stuck during while running with the detailed core model. We are working on it and try to make the setup more stable.
In the meantime the best is to kill the process and restart the simulation for this particular function.
Use
```bash
make -f simulation/Makefile kill_gem5
```
to kill all currently running simulations at once.


