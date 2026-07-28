# GateWeavers

> **Modernizing VHDL & FPGA Engineering through Hermetic Build Systems and Modular IP Cores.**

GateWeavers develops open-source tools based on bazel and VHDL IP cores designed to bring software engineering best practices such as CI/CD, hermetic integration, and dependency management to the digital hardware world.

---

## The Ecosystem

We focus on hardware build reproducibility, VHDL simulation automation, and modular IP distribution powered by **Bazel (Bzlmod)**.

### Build Tools & Rules

* **[`gateweavers_rules_vhdl`](https://github.com/GateWeavers/gateweavers_rules_vhdl)**  
  Bazel rules for hardware development. Handles compilation, hermetic simulation (**GHDL**, **NVC**, **VUnit**), for VHDL projects with zero complex global toolchain configuration.

* **[`gateweavers_rules_fpga`](https://github.com/GateWeavers/gateweavers_rules_fpga)**  
  Bazel rules for fpga development to manage synthesis and implementation toolchain from several vendors. **WIP**

### IP Core Registry (BCR)

* **[`gateweavers-ip-registry`](https://github.com/GateWeavers/gateweavers-ip-registry)**  
  The official GateWeavers public Bazel Central Registry (BCR). It hosts our ready-to-use IP cores, allowing single-line integration into any FPGA project.

### IP Cores (VHDL)

* **[`spacewire`](https://github.com/GateWeavers/spacewire)**  
  VHDL core for the high-speed **SpaceWire** communication protocol (ECSS-E-ST-50-52C), packaged and Bzlmod-ready out of the box. **WIP**
* **`axi_lib`** *(and more to come)*  
  Standard axi lite and axi stream library using vhdl2008 or vhdl2019 interfaces as an option. **WIP**

---

## Quickstart with Bazel

To use our rules and IP cores in your own FPGA project, add the GateWeavers registry to your `.bazelrc` file:

```ini
# .bazelrc
common --registry=[https://raw.githubusercontent.com/GateWeavers/gateweavers-ip-registry/main/](https://raw.githubusercontent.com/GateWeavers/gateweavers-ip-registry/main/)
common --registry=[https://bcr.bazel.build](https://bcr.bazel.build)
```
