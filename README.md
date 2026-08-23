<div align="center">
  <img src="logo.png" alt="Anyone-Hub Logo" width="220"/>

  # Anyone-Hub: V2.1 RC Documentation

  **Desktop-Grade IDE & Terminal Native to Android. Production-Ready. Zero Compromise.**

  <p>
    <img src="https://img.shields.io/badge/Build-Alpha_Release-orange.svg?style=for-the-badge" alt="Alpha Release" />
    <img src="https://img.shields.io/badge/Stack-Pure_Kotlin-7F52FF.svg?style=for-the-badge&logo=kotlin" alt="Pure Kotlin" />
    <img src="https://img.shields.io/badge/IPC-FlatBuffers-FF9900.svg?style=for-the-badge" alt="FlatBuffers" />
    <img src="https://img.shields.io/badge/Play_Safety-Compliant-brightgreen.svg?style=for-the-badge" alt="Play Safety Compliant" />
  </p>

  <p><em>Official distribution hub for pre-compiled alpha binaries, technical documentation, and issue tracking.</em></p>
</div>

---

## 📌 Welcome to the Alpha

Welcome to the official testing and distribution repository for **Anyone-Hub**. This workspace hosts pre-compiled APK binaries, integration documentation, and active issue tracking for early adopters and enterprise testers.

Anyone-Hub is not a web wrapper or a slow hybrid container. It is a colossal, **46-module, pure Kotlin developer platform** engineered to execute desktop-grade workloads, on-device runtime compilation, and advanced terminal workflows directly on Android—requiring **zero root access** and operating in strict compliance with Google Play Safety standards.

---

## ⚡ Core Architecture & Capabilities

* **Vendored Android JediTerm Implementation:** The first and only working hard-fork of JetBrains' desktop JediTerm engine deployed natively on Android. Delivers full-spec TTY terminal emulation, native PTY control, and direct shell execution without third-party Linux deployers.
* **Exclusive FlatBuffers Zero-Copy IPC:** Inter-process communication between the UI, background daemons, and language servers runs entirely over **FlatBuffers**, guaranteeing $O(1)$ zero-copy serialization and minimal memory footprints.
* **The ABL (Annotated Build Language) Compiler Engine:** A self-contained, on-device runtime compiler pipeline integrating `K2JVMCompiler` (Kotlin), embedded `ECJ 3.36.0` (Java), pinned CMake (`4.1.2`), and `libaapt2.so` for split-second on-device builds.
* **Universal Plugin System (UPS) & Custom Marketplace:** Dynamically provisions runtimes and language servers on the fly via `ups-runtime-loader`. Test our **14 active extensions** and **6 premium pro add-on tools** natively within the sandbox.
* **Proprietary Language Engines:** Features **ANTLR4** for dynamic syntactic analysis, **EmmyLuaCore** for ultra-fast Lua LSP support, and the **Reactor Engine** for reactive flow node graph management.

---

## 🚀 Installation & Sideloading Guide

Because Anyone-Hub executes local compiler toolchains and on-device native terminal daemons, alpha releases must be sideloaded:

1. **Download the Binary:** Head to the [Releases](../../releases) tab and download the latest `app-debug.apk` or `app-release.apk`.
2. **Enable Unknown Sources:** On your Android device, navigate to:
   `Settings > Apps > Special app access > Install unknown apps`
   Grant installation permission to your browser or file manager.
3. **Install & Initialize:** Tap the APK to install.
4. **Grant Permissions:** Launch the app and grant the necessary storage and workspace execution permissions to initialize the local build caches.

---

## 🧪 Alpha Testing Objectives

We need aggressive, real-world stress testing across our core subsystems:

### 1. Terminal & PTY Stress Testing
* Launch `anyones-Terminal` and execute high-frequency I/O tasks.
* Test full-spec ANSI escape sequences, text reflow, and long-running interactive shell scripts.
* Validate that PTY session management remains intact across rapid app backgrounding/resuming.

### 2. ABL On-Device Compilation
* Trigger dynamic builds using the `@AblModule`, `@AblCompile`, `@AblEntryPoint`, and `@AblInject` annotations.
* Benchmark split-second compilation speeds across mixed Kotlin/Java source sets.
* Verify that cache cleanups cleanly flush memory via `resetWorkspace()`.

### 3. UPS Plugin & Marketplace Lifecycle
* Install, hot-reload, and teardown plugins dynamically via the `ups-runtime-loader`.
* Ensure that dynamic dependency injection hooks execute without corrupting the sandbox boundary.

---

## 🐛 Submitting Issues & Stack Traces

We operate on zero tolerance for unhandled exceptions. If you hit a crash, deadlock, or unexpected state:

1. **Capture Logs:** Capture the raw logcat output immediately:
   ```bash
   adb logcat -d > crash_log.txt
File an Issue: Open an issue under the Issues tab using the appropriate label:

[BUG] for runtime exceptions, JEDI PTY failures, or FlatBuffers serialization faults.

[ABL-COMPILER] for on-device compilation errors.

[ENHANCEMENT] for UI/UX adjustments or feature requests.

Include Reproduction Steps: Provide exact device specs (Android OS version, chipset architecture, RAM) along with reproducible steps.

⚖️ Legal & Contact
EULA & Disclaimers: Anyone-Hub executes local compilers and native terminal binaries within the official Android application sandbox. Users retain full responsibility for scripts and binaries executed inside their local workspace.

Contact: anyone-hub.dev@zohomail.com

Copyright: © Copyright 2024 Anyone-Hub. All rights reserved.


***
