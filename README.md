# CC-Experiment-01: Performance Analysis of Type-1 and Type-2 Hypervisors

## 1. Experiment Title

**Performance Analysis of Type-1 and Type-2 Hypervisors**

---

## 2. Aim

To deploy similarly configured Ubuntu virtual machines on a **Type-1 hypervisor (Proxmox VE)** and a **Type-2 hypervisor (VMware Workstation)** and evaluate their CPU performance using the **Sysbench CPU benchmark**.

---

## 3. Objectives

The main objectives of this experiment are:

* To study the basic concept of virtualization and hypervisor technology.
* To identify the architectural differences between Type-1 and Type-2 hypervisors.
* To create and configure an Ubuntu virtual machine using **Proxmox VE**.
* To create and configure another Ubuntu virtual machine using **VMware Workstation**.
* To assign equivalent CPU, memory, and other VM resources to both virtual machines.
* To execute the **Sysbench CPU benchmark** in both virtualized environments.
* To record important performance parameters such as:

  * Total execution time
  * Number of events completed
  * Events processed per second
  * Average latency
* To analyze the CPU performance obtained from both hypervisor types.
* To study how the underlying virtualization architecture can influence benchmark results.
* To maintain proper experimental documentation with screenshots, configurations, and benchmark results.

---

## 4. Introduction

### 4.1 Virtualization

Virtualization is a technology that enables a single physical computer to run multiple **virtual machines (VMs)**.

The physical resources of a system, such as the **CPU, RAM, storage, and network interfaces**, are abstracted and assigned to individual virtual machines according to their requirements.

Each virtual machine operates as an independent computing environment and can have its own operating system, virtual processor, memory, storage, and network configuration.

This approach improves hardware utilization and allows multiple operating environments to coexist on the same physical system.

---

### 4.2 Hypervisor

A **hypervisor**, also known as a **Virtual Machine Monitor (VMM)**, is the virtualization layer responsible for creating, running, and managing virtual machines.

It controls the allocation of physical resources to VMs and provides isolation between different guest operating systems.

Based on where the hypervisor operates in relation to the host operating system, hypervisors are commonly categorized into:

1. **Type-1 Hypervisor (Bare-Metal)**
2. **Type-2 Hypervisor (Hosted)**

---

# 5. Types of Hypervisors

## 5.1 Type-1 Hypervisor

A **Type-1 hypervisor**, commonly referred to as a **bare-metal hypervisor**, operates directly on the physical hardware.

It does not require a conventional desktop operating system underneath it. The hypervisor itself manages the hardware resources and provides the virtualization layer required by the guest virtual machines.

**Proxmox VE** is used as the Type-1 virtualization platform in this experiment.

### Architecture

```text
┌─────────────────────────────────┐
│         Virtual Machines        │
│   ┌────────┐     ┌────────┐     │
│   │  VM 1  │     │  VM 2  │ ... │
│   └────────┘     └────────┘     │
├─────────────────────────────────┤
│        Type-1 Hypervisor        │
│           Proxmox VE             │
├─────────────────────────────────┤
│          Physical Hardware      │
│       CPU / RAM / Storage       │
│            / Network            │
└─────────────────────────────────┘
```

### Characteristics

* Runs directly on physical hardware.
* Does not depend on a traditional host OS for virtualization.
* Provides direct management of hardware resources.
* Commonly used in servers and data-center environments.
* Can support multiple virtual machines simultaneously.

---

## 5.2 Type-2 Hypervisor

A **Type-2 hypervisor**, also known as a **hosted hypervisor**, operates as an application within an existing host operating system.

In this architecture, the host OS controls the physical hardware, while the hypervisor uses the resources provided by the host OS to create and operate virtual machines.

**VMware Workstation** is used as the Type-2 virtualization platform in this experiment.

### Architecture

```text
┌─────────────────────────────────┐
│         Virtual Machines        │
│   ┌────────┐     ┌────────┐     │
│   │  VM 1  │     │  VM 2  │ ... │
│   └────────┘     └────────┘     │
├─────────────────────────────────┤
│        Type-2 Hypervisor        │
│       VMware Workstation        │
├─────────────────────────────────┤
│        Host Operating System    │
├─────────────────────────────────┤
│          Physical Hardware      │
│       CPU / RAM / Storage       │
│            / Network            │
└─────────────────────────────────┘
```

### Characteristics

* Runs on top of a host operating system.
* The host OS manages the underlying physical hardware.
* Easy to install and use on desktop or laptop systems.
* Suitable for development, testing, learning, and software experimentation.
* The virtualization layer depends on the host operating system and its resource management.
