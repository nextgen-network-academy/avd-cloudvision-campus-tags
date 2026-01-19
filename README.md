# AVD Generating CloudVision Campus Tags and Static Studios

This guide demonstrates how **Arista AVD** can automatically generate **CloudVision Campus Tags** and how those tags can be consumed by a **Static Configuration Studio** using a `config_manifest`.

This workflow enables a hybrid Campus operating model where:

- **AVD** builds and maintains the campus fabric and infrastructure
- **CloudVision Studios** are leveraged for topology visualization and day-2 operations

---

## High-Level Architecture

![Campus Topology Overview](images/topology/campus-topology-overview.png)

Figure 1 – Campus fabric topology generated and tagged by AVD

---

## Overview

The `arista.avd.eos_designs` role can generate **CloudVision Tags** that are applied to devices and interfaces during fabric deployment. These tags are used by CloudVision to:

- Render accurate **Campus Topology views**
- Enable **tag-based searches and filters**
- Dynamically place devices into **Studio container hierarchies**
- Support **hybrid AVD + Studios workflows**

This functionality is supported on:

- **CloudVision as a Service (CVaaS)**
- **On-prem CloudVision 2024.3.0 or later**

---

## Documentation References

- CloudVision Tags (AVD):  
  <https://avd.arista.com/5.7/ansible_collections/arista/avd/roles/eos_designs/docs/how-to/cloudvision-tags.html>

- Static Configuration Studio Deployment:  
  <https://avd.arista.com/5.7/ansible_collections/arista/avd/roles/cv_deploy/index.html#static-configuration-studio-deployment>

---

## Enabling CloudVision Tag Generation

To globally enable CloudVision tag generation for Campus fabrics, both of the following settings must be enabled:

```yaml
generate_cv_tags:
  topology_hints: true
  campus_fabric: true
```
