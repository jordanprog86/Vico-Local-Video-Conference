
# Vico - Private Multi-User Desktop VideoConference Software

Vico is a modern, high-performance, dark-themed virtual classroom and video conferencing application built from the ground up in native C++ . 

Unlike traditional cloud-dependent streaming software (such as Zoom or Teams), Vico is engineered around a centralized **SFU (Selective Forwarding Unit) Server topology over raw UDP sockets**. This allows it to run seamlessly on Private Networks, Secure LANs, or Local Wi-Fi routers with **exactly zero internet bandwidth required**, ensuring absolute data privacy and ultra-low latency.

---
## Captures
<img width="870" height="670" alt="accueil" src="https://github.com/user-attachments/assets/ff53bb6e-5634-471c-802c-e3f21f69168e" />
<img width="870" height="670" alt="create Meeting" src="https://github.com/user-attachments/assets/2c46a997-d5a8-4ab1-a120-b98116416baa" />
<img width="870" height="670" alt="join" src="https://github.com/user-attachments/assets/06739aee-e3d6-456b-b003-9ab9ac8f816f" />



## Key Features

### 1. Intelligent Multi-Socket SFU Architecture
* **Bandwidth Demultiplexing:** Separates heavy data traffic by running dedicated outbound/inbound routes. Raw video and desktop streams run on a high-speed pipeline, while lightweight voice and control signaling run on a parallel low-traffic lane to prevent packet collisions and router freezes over Wi-Fi.
* **Asymmetric Router Traversal:** Implements a custom dynamic handshake sequence that registers client-side destination ports to the server, successfully routing traffic through home firewalls and NAT configurations.

### 2. High-DPI Aware Screen Sharing
* **Pixel-Perfect Clarity:** Detects the operating system's native hardware `devicePixelRatio` to capture true native display coordinates. This completely bypasses logical desktop font-scaling compression.
* **Crisp Presentation Quality:** Streams presentations and code editors in Full HD 1080p, utilizing smooth linear interpolation transformation filters to ensure text characters remain crystal clear on receiving monitors.

### 3. Synchronized Real-Time Voice Engine
* **Low-Latency PCM Audio:** Drives system microphone and speaker hardware natively using high-performance push-mode I/O stream buffers.
* **Network-Optimized Audio Pipeline:** Standardized to an 8kHz mono telephony voice spectrum, delivering clear vocal communication while drawing negligible network overhead.

### 4. Unlimited Lossless File & Document Sharing
* **Binary Packet Segmentation:** Overcomes the standard 65KB UDP payload boundary by automatically cutting massive documents and images into structured 8KB chunks for transmission.
* **Auto-Reassembly & External Launch:** Seamlessly mirrors and rebuilds fragments in the host operating system's native Downloads directory. Features an HTML hypertext link layout system that launches received files externally using the OS default application (e.g., Adobe Acrobat, default image viewers).

### 5. Modern Chromeless Custom UI
* **Custom Dark Theme Title Bar:** Strips away default native OS window frames (`Qt::FramelessWindowHint`) in favor of a sleek, custom-engineered dark title bar with manual mouse-coordinate drag tracking.
* **Auto-Arranging Video Grid Layout:** Features a dynamic matrix math engine that scales and shifts participant viewports automatically with strict aspect-ratio constraints as students join or leave.
* **Interactive Dashboard Widgets:** Built-in mute check box controllers, interactive "Raise Hand" neon orange highlight frame borders, and an auto-scrolling live text chat overlay panel.

---

##  Network Packet Mapping Layout

Vico wraps all media and command data into a high-utility 9-byte binary protocol header, bypassing heavy serialization frameworks like `DataStream` to eliminate alignment padding and corruption across physical Wi-Fi routers

##  Commercial Positioning & Use Cases

Vico is uniquely positioned for **High-Security, Low-Connectivity, or Private Enterprise environments** where cloud connectivity is either restricted or unavailable.

* **Air-Gapped & Corporate Environments:** Secure corporate boardrooms or government branches needing zero-data-leak virtual endpoints.
* **Remote Educational Infrastructure:** Rural training facilities or private schools utilizing a single local Wi-Fi router to support classroom networks without paying for internet data.
* **Maritime & Industrial Sites:** Internal team voice communications and document routing on remote marine vessels, mining tunnels, or offshore infrastructure hubs.

---
License: Proprietary / Commercial Close-Source

