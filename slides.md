---
theme: ./slidev-theme-amarula
background: https://cover.sli.dev
title: "Feasibility and Architecture of a Dual-Board Embedded System: Yocto & Zephyr Integration"
author: Andrea Ricchi & Dario Binacchi
event: ELCE 2025
drawings:
  persist: false
transition: slide-left
mdc: true
fonts:
  sans: Roboto
  serif: Roboto Slab
  mono: Fira Code
---

<!-- The content of the slide is handled by the layout -->

---

::title::

About Us

::body::

<div class="flex flex-row justify-around">
   <div class="flex flex-col justify-center items-center">
      <div class="text-3xl font-semibold">
         Andrea Ricchi
      </div>
      <a href="mailto:andrea.ricchi@amarulasolutions.com" class="text-xl text-blue-500 underline">andrea.ricchi@amarulasolutions.com</a>
      <a href="https://github.com/AndreaRicchi" class="text-xl text-blue-500 underline">
      https://github.com/AndreaRicchi
      </a>
      <hr class="my-4">
      </hr>
      <ul class="text-l">
         <li>C</li>
         <li>C++ & Qt</li>
         <li>Dart & Flutter</li>
         <li>Yocto & Buildroot</li>
      </ul>
   </div>
   <div class="flex flex-col justify-between space-y-2">
      <div>
         <img src="./assets/andrea_avatar.jpg" alt="Ricchi-avatar" class="w-54 h-54 rounded-xl shadow" />
      </div>
      <iframe
         src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d45313.59690505175!2d10.876755850000011!3d44.77877055!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x477f8d2da31002a3%3A0xe3b13d5ff519c63f!2s41012%20Carpi%20MO!5e0!3m2!1sit!2sit!4v1750767724786!5m2!1sit!2sit"
         class="w-54 h-54 rounded-xl shadow"
         loading="lazy"
         referrerpolicy="no-referrer-when-downgrade"
         >
      </iframe>
   </div>
</div>

<!--
A quick introduction about myself: I’m Andrea Ricchi, from Carpi, Italy. At Amarula Solutions, I work as an embedded developer. My focus is on GUI applications using C++/Qt or Dart/Flutter, as well as user-space applications and services written in C/C++ and Rust. I actively contribute to open-source software projects, collaborating with the community on real-world challenges, including work on ConnMan, libraries, and UI components. I also have experience with Yocto and Buildroot, contributing recipes and packages to support embedded Linux development.
-->

---

::title::

About Us

::body::

<div class="flex flex-row justify-around">
   <div class="flex flex-col justify-center items-center">
      <div class="text-3xl font-semibold">
         Dario Binacchi
      </div>
      <a href="mailto:dario.binacchi@amarulasolutions.com" class="text-xl text-blue-500 underline">dario.binacchi@amarulasolutions.com</a>
      <a href="https://github.com/passgat" class="text-xl text-blue-500 underline">
      https://github.com/passgat
      </a>
      <hr class="my-4">
      </hr>
      <ul class="text-l">
         <li>Embedded Linux Engineer at Amarula Solutions</li>
         <li>
            Open Source contributor
            <ul>
               <li>Buildroot</li>
               <li>Yocto</li>
               <li>
                  Linux
                  <ul>
                     <li>Maintainer for bxCAN and slCAN driver</li>
                  </ul>
               </li>
               <li>
                  U-Boot
                  <ul>
                     <li>Custodian for NAND sub-system with Michael Trimarchi</li>
                  </ul>
               </li>
               <li>Zephyr</li>
            </ul>
         </li>
      </ul>
   </div>
   <div class="flex flex-col justify-between space-y-2">
      <div>
         <img src="" alt="Binacchi-avatar" class="w-54 h-54 rounded-xl shadow" />
      </div>
      <iframe
         src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d2822.7545496510397!2d10.669070376736789!3d44.96898086634357!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x47802f14b2f0bbd7%3A0xfe1866464beb4f0b!2sLido%20Po%20Luzzara!5e0!3m2!1sen!2sit!4v1750770011439!5m2!1sen!2sit"
         class="w-54 h-54 rounded-xl shadow"
         loading="lazy"
         referrerpolicy="no-referrer-when-downgrade"
         >
      </iframe>
   </div>
</div>

<!--
I’m Dario Binacchi and at Amarula, I mainly take care of the operating system side of the boards we work on.
I’m an open source contributor for projects like Buildroot, U-boot, Linux and Zephyr. Together with my colleague Michael Trimarchi, I am a custodian of the NAND subsystem in U-Boot, and in the Linux kernel, I maintain the BxCAN and SLCAN drivers for the CAN subsystem.
I live in a small town in the Po valley, north of Italy.
-->

---

::title::

About Us

::body::

<div class="flex flex-row justify-around">
   <div class="flex flex-col justify-center items-center">
      <div class="text-3xl font-semibold">
         Amarula Solutions
      </div>
      <a href="mailto:info@amarulasolutions.com" class="text-xl text-blue-500 underline">info@amarulasolutions.com</a>
      <a href="www.amarulasolutions.com" class="text-xl text-blue-500 underline">
      www.amarulasolutions.com
      </a>
      <hr class="my-4">
      </hr>
      <ul class="text-l">
         <li>
            Software Consulting Across Europe
            <ul>
               <li>Offices in multiple European countries</li>
               <li>Focused on mobile apps, cloud platforms, and embedded systems</li>
            </ul>
         </li>
         <li>
            Full-Stack Embedded Expertise
            <ul>
               <li>From bootloaders & kernels to UI applications</li>
               <li>Deep knowledge of Android & Linux OS</li>
            </ul>
         </li>
         <li>
            Open Source at Our Core
            <ul>
               <li>Active upstream contributions</li>
               <li>Solutions built for security and long-term maintainability</li>
            </ul>
         </li>
      </ul>
   </div>
   <div class="flex flex-col justify-center">
      <div>
         <img src="./slidev-theme-amarula/assets/logo-small-dark.svg" class="block dark:hidden w-54 h-54 rounded-xl shadow p-2" alt="Dark logo" />
         <img src="./slidev-theme-amarula/assets/logo-small-white.svg" class="hidden dark:block w-54 h-54 rounded-xl shadow p-2" alt="White logo" />
      </div>
   </div>
</div>

<!--
We work at Amarula Solutions, a software consulting company with multiple offices across Europe. Our expertise spans mobile applications, cloud platforms, and embedded systems based on Android and Linux OS. We operate in a highly vertical organisation, covering everything from bootloaders and kernels all the way up to user interface applications.

A core principle that guides our work is our open-source-oriented mindset. We actively contribute upstream, prioritising both security and long-term maintainability in the solutions we build.
-->

---

::title::

Agenda

::body::

 <v-switch>
   <template #0>
      <div class="flex flex-row justify-around text-4xl"> Hardware Setup </div>
   </template>
   <template #1>
      <div class="flex flex-row justify-around">
         <div class=" flex flex-col justify-center grid-cols-2 text-4xl">
            <ul>
               <li>Hardware Setup</li>
            </ul>
         </div>
         <div class=" flex flex-col justify-center grid-cols-2 text-4xl">
            Yocto
         </div>
      </div>
   </template>
   <template #2>
      <div class="flex flex-row justify-around">
         <div class=" flex flex-col justify-center grid-cols-2 text-4xl">
            <ul>
               <li>Hardware Setup</li>
               <li>Yocto</li>
            </ul>
         </div>
         <div class=" flex flex-col justify-center grid-cols-2 text-4xl">
            Zephyr
         </div>
      </div>
   </template>
   <template #3>
      <div class="flex flex-row justify-around">
         <div class=" flex flex-col justify-center grid-cols-2 text-4xl">
            <ul>
               <li>Hardware Setup</li>
               <li>Yocto</li>
               <li>Zephyr</li>
            </ul>
         </div>
         <div class=" flex flex-col justify-center grid-cols-2 text-4xl">
            Flutter
         </div>
      </div>
   </template>
   <template #4>
      <div class="flex flex-row justify-around">
         <div class=" flex flex-col justify-center grid-cols-2 text-4xl">
            <ul>
               <li>Hardware Setup</li>
               <li>Yocto</li>
               <li>Zephyr</li>
               <li>Flutter</li>
            </ul>
         </div>
         <div class=" flex flex-col justify-center grid-cols-2 text-4xl">
            LVGL
         </div>
      </div>
   </template>
   <template #5>
      <div class="flex flex-row justify-around">
         <div class=" flex flex-col justify-center grid-cols-2 text-4xl">
            <ul>
               <li>Hardware Setup</li>
               <li>Yocto</li>
               <li>Zephyr</li>
               <li>Flutter</li>
               <li>LVGL</li>
            </ul>
         </div>
         <div class=" flex flex-col justify-center grid-cols-2 text-4xl">
            Demo - Q&A
         </div>
      </div>
   </template>
</v-switch>

<!--
In this presentation will detail the journey of our idea, from its initial concept to its development, including the challenges encountered. We will also provide an overview and comparison of the core components: the hardware setup (boards and sensors), the operating systems (Linux Yocto vs. Zephyr), and the UI frameworks (Flutter vs. LVGL).
-->

---
preload: false
---

::title::

Why

::body::

<script setup>
import { ref, onMounted } from 'vue'

const icons = [
  './assets/flutter_logo.svg',
  './assets/lvgl_logo.svg',
  './assets/yocto_logo.svg',
  './assets/zephyr_logo.svg',
]

const rotation = ref(0)

onMounted(() => {
  const animate = () => {
    rotation.value = (rotation.value + 0.2) % 360
    requestAnimationFrame(animate)
  }
  animate()
})
</script>

<div class="h-screen pr-32">
  <div class="relative  w-64 h-64 mx-auto">
    <template v-for="(icon, i) in icons">
      <div
        class="absolute top-1/2 left-1/2"
        :style="{
          transform: `rotate(${rotation}deg) rotate(${(360 / icons.length) * i}deg) translate(0, -150px) rotate(-${rotation + (360 / icons.length) * i}deg)`
        }"
      >
        <img :src="icon" class="w-54 h-54" />
      </div>
    </template>
  </div>
</div>

<!--
-->

---

::title::

Hardware Setup

::body::

<!--
-->

---

::title::

The Yocto Project

::body::

<div class="flex flex-row items-center justify-center space-x-24 text-3xl">
   <div class="font-semibold max-w-xs leading-relaxed">
      Flexible, scalable and <span class="text-indigo-600 font-bold">reproducible</span>...
   </div>
   <v-clicks>
      <ul class="list-disc list-inside space-y-3 max-w-xs">
         <li class="font-semibold hover:text-indigo-600 transition-colors duration-300 cursor-pointer">Customizable</li>
         <li class="font-semibold hover:text-indigo-600 transition-colors duration-300 cursor-pointer">Reproducible</li>
         <li class="font-semibold hover:text-indigo-600 transition-colors duration-300 cursor-pointer">Package-based</li>
         <li class="font-semibold hover:text-indigo-600 transition-colors duration-300 cursor-pointer">Toolchain control</li>
         <li class="font-semibold hover:text-indigo-600 transition-colors duration-300 cursor-pointer">Community-driven</li>
      </ul>
   </v-clicks>
</div>

<!--
-->

---

::title::

Our Setup

::body::

## Yocto folder structure

<br>

````md magic-move

```bash
ricchi@maratona:~/work/ew_2025_stmp2_demo$ ls -l
bitbake
openembedded-core
meta-openembedded
[...]
```

```bash
ricchi@maratona:~/work/ew_2025_stmp2_demo$ ls -l
[...]
meta-st-openstlinux
meta-st-scripts
meta-st-stm32mp
meta-st-stm32mp-addons
[...]
```

```bash
ricchi@maratona:~/work/ew_2025_stmp2_demo$ ls -l
[...]
meta-engicam-st
[...]
```

```bash
ricchi@maratona:~/work/ew_2025_stmp2_demo$ ls -l
[...]
meta-clang
meta-flutter
[...]
```

```bash
ricchi@maratona:~/work/ew_2025_stmp2_demo$ ls -l
[...]
meta-amarula-demo
[...]
```

````

<!--
-->

---

::title::

The challanges

::body::

<v-switch>

  <!-- Step 0 -->
  <template #0>

  ## meta-flutter
  <br></br>
  `* bf37f37 - (HEAD -> scarthgap, origin/scarthgap) Rename CI (2 weeks ago) <Joel Winarske>`

  </template>

  <!-- Step 1 -->
  <template #1>

  ## meta-flutter
  <br></br>
  `* bf37f37 - (HEAD -> scarthgap, origin/scarthgap) Rename CI (2 weeks ago) <Joel Winarske>`

  <br></br>
  <br></br>

  ## meta-engicam-st (engicam-stable)
  <br></br>
  `* 3143970 - (HEAD -> mickledore-6.1_v24.06, origin/mickledore-6.1_v24.06) stm32mp2 MicroGEA: added support for spi1 (2 weeks ago)`

  </template>

  <!-- Step 2 -->
  <template #2>

  ## meta-flutter
  <br></br>
  `* bf37f37 - (HEAD -> scarthgap, origin/scarthgap) Rename CI (2 weeks ago) <Joel Winarske>`

  <br></br>
  <br></br>

  ## meta-engicam-st (amarula)
  <br></br>
  `* d3ff59d - (HEAD -> scarthgap, origin/scarthgap) Update conf machine configuration to use newest components (2 weeks ago) <Michael Trimarchi>`

  </template>

</v-switch>


<!--
In our project, we initially faced a version incompatibility between the official meta-engicam-st layer and the meta-flutter layer. The meta-engicam-st was based on an older Yocto release, which made it incompatible with the dependencies required by meta-flutter. To resolve this, we updated the meta-engicam-st layer to align with the latest Yocto LTS release, Scarthgap. This allowed us to successfully build both the board support package and the Flutter engine using the most recent and stable Yocto version, ensuring long-term maintainability and access to the latest features and security updates.
-->

---

::title::

Our configuration

::body::

## local.conf

<br>

````md magic-move

```bash
ricchi@maratona:~/work/ew_2025_stmp2_demo$ cat build/conf/local.conf
[...]
   BB_NUMBER_THREADS ?= "12"
   PARALLEL_MAKE ?= "-j 6"
[...]
```

```bash
ricchi@maratona:~/work/ew_2025_stmp2_demo$ cat build/conf/local.conf
[...]
   MACHINE ??= "stm32mp25-icore"
   DISTRO ??= "openstlinux-weston"
[...]
```

```bash
ricchi@maratona:~/work/ew_2025_stmp2_demo$ cat build/conf/local.conf
[...]
   EULA_FILE_ST = "1"
   ACCEPT_EULA_stm32mp25-icore = "1"
   GLIBC_GENERATE_LOCALES = "en_GB.UTF-8 en_US.UTF-8"
   IMAGE_LINGUAS ?= "en-gb"
   INHERIT += "devshell"
   RM_OLD_IMAGE = "1"
[...]
```

```bash
ricchi@maratona:~/work/ew_2025_stmp2_demo$ cat build/conf/local.conf
[...]
   PACKAGE_CLASSES = "package_deb"
[...]
```

```bash
ricchi@maratona:~/work/ew_2025_stmp2_demo$ cat build/conf/local.conf
[...]
   SDK_EXT_TYPE = "minimal"
   SDK_INCLUDE_TOOLCHAIN = "1"
[...]
```

```bash
ricchi@maratona:~/work/ew_2025_stmp2_demo$ cat build/conf/local.conf
[...]
   PRSERV_HOST = "localhost:0"
[...]
```

```bash
ricchi@maratona:~/work/ew_2025_stmp2_demo$ cat build/conf/local.conf
[...]
   IMAGE_INSTALL:append = " \
      flutter-engine \
      flutter-wayland-client \
      ew-2025-flutter-demo-can-lib \
      ew-2025-flutter-demo \
      connman \
      connman-client \
   "
   TOOLCHAIN_HOST_TASK:append = " nativesdk-flutter-sdk"
[...]
```

````

<!--
To ensure a smooth and consistent build process, we customised our Yocto local.conf. We optimised build performance with parallelism settings (BB_NUMBER_THREADS and PARALLEL_MAKE), and enabled STMicroelectronics-specific licensing by accepting the EULA required for STM32MP25-based platforms. For localisation, we specified UTF-8 locales and language support. We chose the Debian package format (package_deb) for improved integration with Flutter and system updates, and enabled reproducible builds by controlling root file system timestamps. The configuration also supports extensible SDK generation and sets up the PR server to prevent version rollback issues in packaged recipes. Finally, we extended the image with key components for our Flutter-based UI, including the Flutter engine, Wayland client, and our custom application demos, ensuring that everything needed for development and deployment is included out of the box.
-->

---

::title::

Meet KAS

::body::

<div class="flex flex-row items-center justify-center space-x-24 text-2xl">
   <div class="font-semibold max-w-xs leading-relaxed">
      This tool provides an easy mechanism to setup bitbake based projects.
   </div>
   <v-clicks class="text-xl">
      <ul class="list-disc list-inside space-y-3 max-w-xs">
         <li class="font-semibold hover:text-indigo-600 transition-colors duration-300 cursor-pointer">Clone and checkout bitbake layers</li>
         <li class="font-semibold hover:text-indigo-600 transition-colors duration-300 cursor-pointer">Create default bitbake settings (machine, arch, …)</li>
         <li class="font-semibold hover:text-indigo-600 transition-colors duration-300 cursor-pointer">Launch minimal build environment, reducing risk of host contamination</li>
         <li class="font-semibold hover:text-indigo-600 transition-colors duration-300 cursor-pointer">Initiate bitbake build process</li>
      </ul>
   </v-clicks>
</div>

<!--
As you have seen until now, managing Yocto can be tricky. Layers, configs, dependencies…

KAS make it too easy, almost boring…

KAS is a tool that simplifies working with the Yocto Project by managing configurations and build environments through a single YAML file. Instead of manually setting up multiple layers, repositories, and local configurations, KAS lets you define everything in a structured, version-controlled format, making your builds reproducible and team-friendly. With just one command, kas build, you can go from a clean environment to a fully built Linux image. It's especially useful in collaborative or CI/CD setups, where consistency and ease of setup are crucial. Think of it as a lightweight project manager that keeps your Yocto-based workflows clean, reliable, and repeatable.

With the power of Yocto and the simplicity of KAS, our result is this YAML file that contains all the building blocks that we analysed earlier.
-->

---

::title::

Our KAS config

::body::

## .config.yaml

<div class="h-2" />

````md magic-move

```bash
ricchi@maratona:~/work/ew_2025_stmp2_demo$ cat .config.yaml
[...]
machine: stm32mp25-icore
distro: openstlinux-weston
target: st-image-weston
[...]
```

```bash
ricchi@maratona:~/work/ew_2025_stmp2_demo$ cat .config.yaml
[...]
repos:
    bitbake:
        url: "https://git.openembedded.org/bitbake"
        branch: "2.10"
        layers:
            .: excluded

    openembedded-core:
        url: "https://git.openembedded.org/openembedded-core"
        commit: 236ac1b43308df722a78d3aa20aef065dfae5b2b
        layers:
            meta:

    meta-openembedded:
        url: "https://github.com/openembedded/meta-openembedded"
        commit: 1235dd4ed4a57e67683c045ad76b6a0f9e896b45
        layers:
            meta-gnome:
            meta-multimedia:
            meta-networking:
            meta-oe:
            meta-python:
            meta-webserver:
[...]
```

```bash
ricchi@maratona:~/work/ew_2025_stmp2_demo$ cat .config.yaml
[...]
    meta-st-openstlinux:
        url: "https://github.com/STMicroelectronics/meta-st-openstlinux"
        commit: a25d4806880cdc73471e3c1824a87901b5a4e44f

    meta-st-stm32mp:
        url: "https://github.com/STMicroelectronics/meta-st-stm32mp"
        commit: dd13b8318b78f956086efade81de9c72c0e97187

    meta-st-stm32mp-addons:
        url: "https://github.com/STMicroelectronics/meta-st-stm32mp-addons"
        commit: 97617f888513d89c4070f59bfdfa2a91e8175d5c

    meta-st-scripts:
        url: "https://github.com/STMicroelectronics/meta-st-scripts"
        commit: 27b8b0df3b2f3515d5e51de65f54eff00ddacb82
        layers:
            .: excluded
[...]
```

```bash
ricchi@maratona:~/work/ew_2025_stmp2_demo$ cat .config.yaml
[...]
    meta-engicam-st:
        url: "https://github.com/amarula/meta-engicam-st"
        branch: "scarthgap"
[...]
```

```bash
ricchi@maratona:~/work/ew_2025_stmp2_demo$ cat .config.yaml
[...]
    meta-clang:
        url: "https://github.com/kraj/meta-clang"
        branch: "scarthgap"

    meta-flutter:
        url: "https://github.com/meta-flutter/meta-flutter"
        branch: "scarthgap"
        layers:
            .:
[...]
```

```bash
ricchi@maratona:~/work/ew_2025_stmp2_demo$ cat .config.yaml
[...]
    meta-amarula-demo:
        url: "https://github.com/amarula/meta-amarula-demo.git"
        commit: 611f500415bd9f141b8b4bc6782c8b596f9b56ad
[...]
```

```bash
ricchi@maratona:~/work/ew_2025_stmp2_demo$ cat .config.yaml
[...]
local_conf_header:
    standard: |
        BB_NUMBER_THREADS ?= "12"
        PARALLEL_MAKE ?= "-j 6"
        EULA_FILE_ST = "1"
        ACCEPT_EULA_stm32mp25-icore = "1"
        GLIBC_GENERATE_LOCALES = "en_GB.UTF-8 en_US.UTF-8"
        IMAGE_LINGUAS ?= "en-gb"
        INHERIT += "devshell"
        RM_OLD_IMAGE = "1"
        PACKAGE_CLASSES = "package_deb"
        REPRODUCIBLE_TIMESTAMP_ROOTFS = ""
        SDK_EXT_TYPE="minimal"
        SDK_INCLUDE_TOOLCHAIN="1"
        PRSERV_HOST = "localhost:0"
        HOSTTOOLS += "xz truncate"
        IMAGE_INSTALL:append = " \
            flutter-engine \
            flutter-wayland-client \
            ew-2025-flutter-demo-can-lib \
            ew-2025-flutter-demo \
            connman \
            connman-client \
        "
        TOOLCHAIN_HOST_TASK:append = " nativesdk-flutter-sdk"
[...]
```

````

<!--
-->
