# PC Build

# High-Performance Workstation Build (2026)

## Overview

I had been using an old laptop as a lab machine (a Lenovo Ideapad 320) using KVM-QEMU in order to practice networking, directory services, and later on pentesting.  However it rapidly became clear that the hardware resources of the machine were not up to the task of running multiple Virtual Machines (VMs) simultaneously. Therefore I decided to spec and build a new PC especially for this purpose.
I wanted this to be a high performance machine capable of running multiple VMs simultaneously, in order to practice setting up and managing enterprise networks, directory services, and also practice and learn red and blue team strategies.

The system was designed with a focus on:

* High core count for parallel workloads
* Large memory capacity for virtual machines
* Fast NVMe storage for I/O-intensive tasks
* Reliability and thermal efficiency

---

## Hardware Specification

### Core Components

* CPU: AMD Ryzen 9 9950X
* Motherboard: ASUS ProArt X870E
* RAM: 128GB Corsair Vengeance DDR5 (2x64GB, 5600–6000MHz)
* GPU: XFX Swift Radeon RX 9070 16GB

### Storage

* 1TB Samsung 990 Pro NVMe
* 2TB Samsung 990 Pro NVMe
* 4TB Samsung 990 Pro NVMe

### Power Supply

* Seasonic Focus GX-850 (80+ Gold)

### Cooling & Case

* Noctua NH-D15 G2 (air cooling)
* Fractal Design Meshify 3 XL
* Rear exhaust fan configuration

---

## Design Rationale

### CPU Selection

The Ryzen 9 9950X was selected for its high core and thread count, making it suitable for:

* Running multiple virtual machines
* Parallel workloads
* Future-proofing for increasing compute demands

### Memory Configuration

128GB of DDR5 RAM was chosen to support:

* Multiple concurrent VMs
* Memory-intensive lab environments
* Reduced reliance on swap memory

This was deliberately overspecced to be future-proofed, whilst still allowing for only two RAM slots to be used. A 2x64GB kit was chosen for this reason.

### Storage Strategy

Three NVMe drives were used to separate workloads for reduced I/O contention, and to keep environments separate. Storage has been planned as follows:

* The 1TB is for holding the OS and associated applications for the virtual lab part of the machine. I'm planning on using Fedora for this purpose, as I like the Gnome desktop environment.
* The 2TB drive is for the VMs themselves to use as storage space.  Having a dedicated M.2 NVMe for VMs keeps it isolated from the OS, which is an important consideration for future work involving malware (such as Kali Linux). A dedicated drive will also improve performance for VM disk operations.
* Finally, the 4TB drive will hold a different OS for use as a daily driver machine (a task currently performed by a laptop). I have a strong interest in digital security and privacy, and so I am planning to install Qubes OS on the drive for this purpose.

External hard drives already supply ample additional bulk storage for operations where high speed is not required.

### Motherboard Choice

The ASUS ProArt X870E was selected for:

* Stability and reliability
* Strong expansion capabilities
* Support for high-speed storage and modern connectivity

### Cooling and Airflow

I chose to use a high-end air cooling system rather than liquid cooling for reliability. Despite the good reliability reputation of modern AIO solutions, I wanted a machine that, once built, would not require any ongoing maintenance and have fewer points of failure. Since this system will not be used for gaming, video editing, or other CPU or GPU intensive operations, an air cooled system should be sufficient. The large size of the Noctua cooler meant that there would be limited clearance between the top of the RAM and the front fan of the cooler. Raising the front fan to clear this would have meant that the top of the fan would have ended up extremely close to the side of the case had a mid-tower been used. For this reason I chose to use the XL version of the Fractal Meshify 3 case. This gave ample clearance for the cooler fan to be raised by about 5mm over the RAM, and as built the PC now has nearly 30cm of free space in the front half of the case, which allows for excellent airflow. The three front fans were supplemented by an additional rear-mounted exhaust fan, in order to create improved airflow whilst still allowing a certain amount of positive pressure to minimise  dust ingress.

### Power Delivery

An 850W 80+ Gold PSU provides:

* Efficient power delivery
* Headroom for peak loads
* Long-term stability under sustained usage

---

## Build Process

The build process was smooth and trouble-free. I first installed the power supply into the case, and then plugged it into the wall (keeping the wall socket turned off). Since I did not have an anti-static wrist strap, this gave me a good earth that I could touch periodically during the build in order to prevent static build up.
I then installed the CPU, RAM and M.2 drives, before applying thermal paste to the CPU and mounting the cooler. For thermal paste I followed the guidance that 'slightly too much is better than slightly too little', spreading a thin layer over the surface of the CPU, before putting a small blob in the centre and four smaller dots in the corners.
With the cooler in place the motherboard could be mounted into the case, at which point the majority of the cabling was routed. One other advantage of the larger case is that cable management proved to be extremely easy, with ample room to make sure that the air flow was entirely unimpeded. This is also aesthetically pleasing, although aesthetics did not play any role in the design choices for this build (for instance, the absence of RGB lighting in the components chosen).

A careful build process was rewarded with a successful POST on the first try.

---

## BIOS Configuration

Following the successful first boot, I set the Ai Overclock Tuner to DOCP I, which is the correct setting for an AMD system. Voltage, fan speed and CPU temperature were monitored for a while to confirm that the cooler was operating as it should be. UEFI password was set, and the motherboard firmware was updated to the newest version.



