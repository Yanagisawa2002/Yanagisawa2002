# Chenggong (Edwin) Liu

**Graduate software engineering candidate · CPU/GPU performance · Reliable runtimes · Simulation**

I build and investigate software across CPU/GPU and asynchronous execution boundaries. My work combines implementation, profiling, complete-task measurement and reproducible validation.

I am completing an **MSc in Biomedical Engineering at the National University of Singapore**, with graduation and full-time availability expected in **December 2026**. I am based in Singapore and interested in graduate software, systems, simulation and AI infrastructure roles.

[LinkedIn](https://www.linkedin.com/in/edwin-liu-chenggong/) · [Portfolio and CVs](https://edwin-portfolio.pages.dev/)

## Selected public engineering work

### [HLSL Kernel Pipeline](https://github.com/Yanagisawa2002/hlsl-kernel-pipeline)

D3D12/HLSL primitives, native execution and GPU-driven rendering. A GPUPrefixSums-derived inclusive scan removes a redundant full-array pass: **6.376 → 2.904 ms**, versus **3.584 ms** for pinned external RTS, on an RTX 4090 at 268M uint32 elements. The frozen comparison used 18 fresh processes and full numerical checks; upstream algorithms retain their attribution.

The follow-up explains when that kernel gain does not help a complete application, then validates a GPU-resident Unity cull-to-indirect-draw path at up to **1M total agents**. Architecture execution and benchmark speedups have separate evidence; total agents are not simultaneously drawn instances.

[Scan and profiling](https://github.com/Yanagisawa2002/hlsl-kernel-pipeline/blob/cfcd8443d1c21f4df370639ea2702972dd9c4313/docs/results/RTX4090_INCLUSIVE_SCAN_PROFILE_DIAGNOSIS.md) · [Complete-task result](https://github.com/Yanagisawa2002/hlsl-kernel-pipeline/blob/cfcd8443d1c21f4df370639ea2702972dd9c4313/docs/results/CROWD_COMPLETE_TASK_2026-09-16.md)

### [ActionStream](https://github.com/Yanagisawa2002/ActionStream)

A LeRobot-compatible asynchronous runtime for chunked robot policies, with episode isolation, age-aligned action delivery, cancellation, restartable processes and real TCP inference. The maintained runtime requires reset acknowledgement before inference and rejects stale responses across reset boundaries.

The public evidence includes a two-host replication and injected disconnects. Its frozen overall replication and recovery gates remain **NO-GO**; the contribution is inspectable runtime behavior, fault analysis and explicit limits, not a claim of production-ready robot autonomy.

[Runtime hardening](https://github.com/Yanagisawa2002/ActionStream/blob/9bfd5343ae31802966a878366af1f54e9b346bf6/docs/rpc-runtime-hardening.md) · [Evidence index](https://github.com/Yanagisawa2002/ActionStream/blob/9bfd5343ae31802966a878366af1f54e9b346bf6/docs/evidence-index.md)

### [Data Layout Calibrator](https://github.com/Yanagisawa2002/data-layout-calibrator)

CPU performance work in Unity/Burst, including deterministic compensated parallel reduction and conversion/ownership/export accounting. On a Core Ultra 7 265K, BabelStream Dot fell from **29.238 → 8.244 ms**; its 100-iteration storage lifecycle improved **21.7%** versus serial Burst and remained **2.53% slower than native OpenMP**.

A separate complete SPH task found **15.7% lower mean caller latency from buffer reuse**. SoA and AoSoA8 lost to the strengthened AoS baseline, so the decision was to keep AoS plus reusable buffers.

[Engineering cases and measurement boundaries](https://github.com/Yanagisawa2002/data-layout-calibrator/blob/2dc4c27d0677b5f127641b70a2adffa8941e3e37/Docs/ENGINEERING_CASE_STUDIES.md)

### [Shader Hitch Pipeline](https://github.com/Yanagisawa2002/unity-shader-hitch-pipeline)

Unity graphics-state tracing, warmup scheduling and runtime identity checks. The merged repair reduced repeated driver-attestation checks from **about 563 ms to 0.27–0.42 ms**, retaining the initial full hash. Official Boat Attack and four URP scene routes provide the native validation. Overall scheduling speedup remains unproven.

[Repair and full-route evidence](https://github.com/Yanagisawa2002/unity-shader-hitch-pipeline/blob/55a9f168684ffc0dc538204f991a5c293fb8c8c4/Docs/EXTERNAL_BOAT_ATTACK_2026-09-14.md)

## Simulation and additional projects

At **IMMRSIV**, I work as an **Engineer Intern**, contributing to the team's SUMMIT simulation platform: GPU-driven geometry, asynchronous geospatial streaming, multi-camera integration and resource lifecycle management. My LinkedIn Featured portfolio presents the team context, my contributions and scoped historical component benchmarks.

- [SUMMIT GPU Systems](https://github.com/Yanagisawa2002/summit-gpu-systems): public GPU packages and scoped data-representation studies; a separate review surface from the employer's full platform. Complete query/consumer costs and negative comparisons are retained.
- [PolicyBridge-ROS2](https://github.com/Yanagisawa2002/PolicyBridge-ROS2): synchronized observations, ROS 2 Actions, cancellation, timeouts and late-result isolation; scripted/simulation validation, with physical-robot acceptance pending.
- [PoseLoop](https://github.com/Yanagisawa2002/PoseLoop): RGB-D instance detection to FoundationPose integration and a frozen 25-frame development evaluation, with explicit detector-to-pose failure accounting.

**Tools:** Python, C#, HLSL, Unity/URP, Burst, D3D12, RenderDoc, Nsight Graphics, PyTorch, ROS 2, Git and CI.

I use AI coding tools in implementation and investigation, and take responsibility for reviewing, testing and explaining the resulting systems. The repositories distinguish maintained implementations, frozen measurements, open PRs and unvalidated claims.

Project summaries reviewed against public default branches on **21 September 2026**. Linked reports retain their original experiment dates, hardware and measurement boundaries.
