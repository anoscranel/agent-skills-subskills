---
name: on-device-benchmarking
domain: software-engineering/on-device-benchmarking
trigger: "Measuring latency, memory and power on real devices."
anti_trigger: "Not for server benchmarking, and not for model quality evaluation."
scope: "Honest latency, memory and power measurement."
status: seedling
---

# On-device benchmarking

## Standard

On-device numbers are only meaningful under stated conditions. A phone throttles as it heats, so a model that hits a latency target for the first ten seconds may miss it after a minute of sustained load. Cold-start and warm inference differ by the model-load and compile cost, and both matter: the user feels the cold start, the steady state is warm. Background apps, battery level and whether the device is charging all move the result. A benchmark that ignores these is a number about the lab, not about the user's phone.

The discipline is to measure the way the feature is actually used. Report percentiles, not just the mean, because the tail is what produces the visible stalls. Measure cold and warm separately. Measure sustained load long enough for thermal throttling to appear, and report the conditions: device model, OS version, backend, battery state and ambient temperature. Measure memory peak as well as latency, since an out-of-memory kill is a harder failure than a slow inference. State the conditions next to every number, or the number is decoration.

Primary sources: <https://developer.android.com/ndk/guides/neuralnetworks> and <https://arxiv.org/abs/2106.08962>.

## Decision rules

- Report percentiles, not only the mean; the tail is the user-visible stall.
- Measure cold-start and warm inference separately and report both.
- Run sustained load long enough for thermal throttling to appear.
- Record device model, OS version, backend, battery and thermal state with every result.
- Measure peak memory as well as latency; an OOM kill outranks a slow result.
- Benchmark on the weakest supported device, not only the flagship.

## Procedure

1. Define the usage pattern to reproduce: single shot, repeated, or sustained.
2. Measure cold-start latency including model load and compile.
3. Measure warm latency over enough runs for stable percentiles.
4. Run sustained load and watch for thermal throttling and its latency effect.
5. Record peak memory and the device conditions throughout.
6. Repeat across the supported device tiers and record the full result set.

## Anti-patterns

- Quoting the mean of a few warm runs as the latency.
- Benchmarking for ten seconds and claiming sustained performance.
- Omitting the device and conditions from the reported number.
- Measuring only on the newest, fastest handset.
- Reporting latency without the memory that determines whether it runs at all.

## Done checklist

- [ ] Percentiles reported.
- [ ] Cold and warm measured separately.
- [ ] Sustained-load throttling observed.
- [ ] Conditions recorded per result.
- [ ] Peak memory measured.
- [ ] Weakest supported device benchmarked.

## Sources

- Android NNAPI and hardware acceleration: <https://developer.android.com/ndk/guides/neuralnetworks>
- Efficient deep learning survey: <https://arxiv.org/abs/2106.08962>
- TensorFlow Lite performance and delegates: <https://www.tensorflow.org/lite/performance/delegates>
