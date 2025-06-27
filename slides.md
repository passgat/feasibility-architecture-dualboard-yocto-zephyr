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
      <div class="flex flex-row justify-around  text-4xl"> Hardware Setup   </div>
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
