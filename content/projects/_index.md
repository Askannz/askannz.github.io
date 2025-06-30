+++
title = "Personal projects"
+++

## Munal OS

<a class="github-button" href="https://github.com/Askannz/munal-os" data-color-scheme="no-preference: light; light: light; dark: dark;" data-icon="octicon-star" data-size="large" data-show-count="true" aria-label="Star Askannz/munal-os on GitHub">Github stars</a>

[https://github.com/Askannz/munal-os](https://github.com/Askannz/munal-os)

**Hacker News:** [https://news.ycombinator.com/item?id=44226879](https://news.ycombinator.com/item?id=44226879)

By far my biggest project, a full OS written from scratch in Rust. Has a fully graphical interface and window manager, PCI driver, QEMU drivers for mouse, keyboard, network and GPU, and a few custom-made applications including a basic web browser and a Python terminal.

I tried to do something new with the kernel architecture: instead of running inside of a virtual address space like on most OSes, applications are compiled to WebAssembly and run within an embedded WASM interpreter. See the README for more details.

![Munal OS screenshot](munal-os.png "The Munal OS desktop with a few apps open")


## optimus-manager

<a class="github-button" href="https://github.com/Askannz/optimus-manager" data-color-scheme="no-preference: light; light: light; dark: dark;" data-icon="octicon-star" data-size="large" data-show-count="true" aria-label="Star Askannz/optimus-manager on GitHub">Github stars</a>

[https://github.com/Askannz/optimus-manager](https://github.com/Askannz/optimus-manager)

This is a Python CLI utility I wrote to solve a very specific problem: for power management reasons, some laptops (mostly gaming ones) have two GPUs, a small one for lightweight desktop usage and a large one for heavy applications such as games. Until recently this dual-GPU config was very poorly supported by Linux distributions, so this Python tool aims at providing easy commands for switching the active GPU or turn the big one off to save power.

I had originally written it for myself but decided to publish it as an [Archlinux package](https://aur.archlinux.org/packages/optimus-manager-git) and it blew up in popularity, climbing to over 2000 stars on Github over the years ([someone even made a 3rd-party GUI for it](https://github.com/Shatur/optimus-manager-qt)). It has gone through multiple major versions since, to add features and try to improve stability and compatibility.

I don't maintain it anymore (due to lacking a recent dual-GPU laptop), so I have handed that project over to someone else to continue development (shootout to [es20490446e](https://github.com/es20490446e)).


## msi-perkeyrgb

<a class="github-button" href="https://github.com/Askannz/msi-perkeyrgb" data-color-scheme="no-preference: light; light: light; dark: dark;" data-icon="octicon-star" data-size="large" data-show-count="true" aria-label="Star Askannz/msi-perkeyrgb on GitHub">Github stars</a>

[https://github.com/Askannz/msi-perkeyrgb](https://github.com/Askannz/msi-perkeyrgb)

This was a fun holiday project aiming to reverse-engineer the protocol that controls the RGB lighting of keyboards on an MSI laptop. It involved peeking at USB traffic using Wireshark, analyzing packet data and playing detective to figure out which pattern did what and how to toggle various lighting effects.

## OxyDICOM

[https://github.com/Askannz/oxydicom](https://github.com/Askannz/oxydicom)

This is a little application to open and read DICOM images.

DICOM is a standardized data format for medical applications, which I have become very acquainted with during my time at See-Mode Technologies. It can store images and videos in a variety of encodings, and also stores tables of metadata ("DICOM tags") for patient information and the like.

OxyDICOM supports a subset of DICOM image encodings and is capable of extracting and displaying the tags. It is written in Rust with the [iced](https://github.com/iced-rs/iced) toolkit (or, well, an early version of it).

![OxyDICOM screenshot 1](oxydicom-1.png "OxyDICOM displaying the US scan image embdedded into the DICOM")
![OxyDICOM screenshot 2](oxydicom-2.png "OxyDICOM showing the extracted DICOM tag metadata tree")

## Nag

[https://github.com/Askannz/nag](https://github.com/Askannz/nag)

A Telegram bot that can send reminder at a given date or frequency given in natural language. For example, "every day at 3pm", "on March 13th", etc.
