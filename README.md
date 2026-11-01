<div align="center">
  <img src="logo.png" alt="Anyone-Hub Logo" width="220"/>

  # Dev.io: RC Documentation

  **Desktop-Grade IDE & Terminal Native to Android. Built for Production with a Zero Compromise Mindset.**

  <p>
    <img src="https://shields.io" alt="Production Release" />
    <img src="https://img.shields.io/badge/Stack-Pure_Kotlin-7F52FF.svg?style=for-the-badge&logo=kotlin" alt="Pure Kotlin" />
    <img src="https://img.shields.io/badge/IPC-FlatBuffers-FF9900.svg?style=for-the-badge" alt="FlatBuffers" />
    <img src="https://img.shields.io/badge/Play_Safety-Compliant-brightgreen.svg?style=for-the-badge" alt="Play Safety Compliant" />
  </p>

  <p><em>Official distribution hub for production-ready signing binaries, technical documentation, and issue tracking.</em></p>
</div>

---

## 📌 Introduction

Welcome to the official repository for **Dev.io**. This workspace hosts our core documentation, integration guides, and issue tracking parameters for our high-performance mobile ecosystem.

Dev.io is not a web wrapper or a slow hybrid container. It is a colossal, **46-module, pure Kotlin developer platform** engineered to execute desktop-grade workloads, on-device runtime compilation (A.B.L.), and advanced native terminal workflows directly on Android—requiring **zero root access** and operating in strict compliance with Google Play Console specifications.

---

## ⚡ Core Architecture & Capabilities

* **Vendored Android JediTerm Implementation:** The first and only working hard-fork of JetBrains' desktop JediTerm engine deployed natively on Android. Delivers full-spec TTY terminal emulation, native PTY control (`pty_linux_arm64.S`), and direct shell command multitasking.
* **Exclusive FlatBuffers Zero-Copy IPC:** Inter-process communication between the UI layout layer, background compiler daemons, and language servers runs entirely over **FlatBuffers**, guaranteeing $O(1)$ zero-copy serialization and non-allocating memory footprints.
* **The ABL (Annotated Build Language) 1.2.0 Compiler Engine:** An annotation-driven, on-device runtime compiler pipeline integrating `K2JVMCompiler` (Kotlin), embedded Java bytecode compilation (`javac`), pinned CMake (`3.22+`), and 16KB-page-size aligned binary modules for seamless on-device builds.
* **Universal Plugin System (UPS) & Secure Marketplace:** Dynamically provisions runtimes and language servers via an Android 14+ read-only dynamic code loading (DCL) pipeline. Loads our **14 active marketplace extensions** and **6 premium Pro add-on tools** (`devio-agile`, `devio-mock`, `devio-request`, `devio-schema`, `devio-snippets`, `devio-timeline`) securely on-demand.
* **Proprietary Language Engines:** Features **ANTLR4** for real-time syntactic analysis, **EmmyLuaCore** for ultra-fast Lua semantic highlighting, and a lock-free `ConcurrentHashMap` caching engine to eliminate editor thread synchronization latency.

---

## 🚀 Deployment & App Store Readiness

Dev.io is fully hardened for production deployment under the strict **\< 200 MB compressed download ceiling** mandated by Google Play Console:

1. **Compilation Configuration:** Code optimization, resource stripping, and dead-code elimination are handled via R8 (`isMinifyEnabled = true`, `isShrinkResources = true`).
2. **Release Artifacts:** Generates official signed Android App Bundles (`.aab`) and direct device installation packages (`.apk`) using our dedicated production PKCS12 certificate store (`devio-release.jks`).
3. **Distribution Path:**
   - **Google Play App Bundle (.aab):** Located at `app/build/outputs/bundle/release/app-release.aab`
   - **Local Installation Package (.apk):** Located at `app/build/outputs/apk/release/app-release.apk`

---

## 🧪 Operational System Testing

Our diagnostic integration suites comprehensively validate all internal engine subsystems:

### 1. Terminal & PTY Line Discipline
* Verifies горизонталь text overwrite and staircase layout protections via explicit `\r\n` (CRLF) sequence mapping inside a synchronized `outputLock` block.
* Confirms native execution routing for whitelisted developer utilities (`./gradlew`, `gradle`, `abl`, `mvn`, `deps`, `ups`, `sh`, `bash`, `touch`, `clear`).

### 2. ABL On-Device Compilation & Inlay Providers
* Validates dynamic compilation passes triggered by the `@AblModule`, `@AblCompile`, `@AblInject`, and `@AblRuntimeAsset` annotations.
* Renders real-time editor semantic text maps and virtual DI inlay badges (`«Tool: jar-silo»`, `«SDK: ide-assets»`).

### 3. UPS Plugin & Pro Module Activation Loop
* Tracks on-demand fetch requests targeting the secure `pro_module_assets` and `plugin_payloads` Supabase Storage buckets.
* Evaluates cryptographic SHA-256 validation checks and verifies `0400` read-only container flags before loading modules via `PreviewClassLoaderDeck`.

---

## 🐛 Submitting Issues & Stack Traces

We operate on a zero-tolerance policy for unhandled exceptions or thread lock conditions. If you encounter a compilation fault, layout regression, or network sync boundary block:

1. **Capture Diagnostic Logs:** Extract raw device records via adb immediately:
   ```bash
   adb logcat -d > devio_crash_log.txt
   ```
2. **File a Structured Report:** Submit an issue on our tracker using the appropriate catalog token:
   - `[BUG]` for runtime thread exceptions, PTY stream corruption, or JSON serialization errors.
   - `[ABL-COMPILER]` for on-device toolchain errors or missing SDK classpaths.
   - `[ENHANCEMENT]` for workspace ergonomic optimizations or layout refactoring requests.

---

## ⚖️ Legal, Privacy & Contact

* **EULA & Privacy Terms:** Dev.io runs local compilers and native shell binaries within the official Android isolated application sandbox. Users retain exclusive ownership of, and full operational responsibility for, all code, scripts, or assets executed within their local workspaces. Public metadata reads are secured via column-level security and `profiles_public` database views.
* **Primary Contact Address:** tomslinkard@anyonehub.tech
* **Developer Legal Support:** anyone-hub.dev@zohomail.com
* **Official Web Platform:** [https://info-dev.io](https://info-dev.io)

**Copyright:** © Copyright 2024–2026 Anyone-Hub LLC. All rights reserved.
