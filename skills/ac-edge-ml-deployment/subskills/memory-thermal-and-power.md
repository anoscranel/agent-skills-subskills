---
name: memory-thermal-and-power
domain: software-engineering/memory-thermal-and-power
trigger: "Fitting the model within the device's resource envelope."
anti_trigger: "Not for compressing the model artifact, and not for server capacity."
scope: "The resource envelope: size, RAM, heat, battery."
status: seedling
---

# Memory, thermal and power

## Standard

A device gives the model a fixed envelope, and exceeding any wall stops the feature. Size has two costs: the model may ship inside the app bundle, where it inflates download and may hit store size limits, or download on first run, where it costs bandwidth and a wait. RAM is the hard wall — the runtime, the model and its working tensors must fit in the memory the OS grants the app, and an over-budget model is killed, not slowed. Heat is the sustained-load wall: continuous inference warms the device and triggers throttling, which cuts throughput exactly when the user is using the feature most.

Power is the quiet cost that decides whether users keep the feature. Sustained inference drains the battery, and a feature that noticeably shortens battery life gets disabled. The craft is to fit the whole envelope, not just latency: choose bundled versus downloaded size deliberately, keep peak memory under the per-app budget with headroom, bound sustained load to stay under the thermal cliff, and measure battery impact per unit of work. Where the envelope cannot be met at the required quality, that is the signal to use a smaller model or a cloud path, not to ship and hope.

Primary sources: <https://arxiv.org/abs/2106.08962> and <https://www.tensorflow.org/lite/guide>.

## Decision rules

- Choose bundled versus downloaded size deliberately; each has a distinct user cost.
- Keep peak memory under the per-app budget with headroom for the rest of the app.
- Bound sustained inference to stay below the thermal-throttling cliff.
- Measure battery drain per unit of work, not only per session.
- Treat an envelope that cannot meet the quality floor as a signal for a smaller model or cloud path.
- Re-check the envelope on the weakest supported device.

## Procedure

1. Measure the model's size and decide bundled versus downloaded delivery.
2. Measure peak RAM during inference on the target device.
3. Run sustained load and find the point where throttling begins.
4. Measure battery consumption over a representative workload.
5. Compare each against the envelope and resolve any breach.
6. Record the envelope figures per device tier.

## Anti-patterns

- Bundling a huge model and blowing the store size limit or install rate.
- Treating memory as unlimited until the OS kills the app.
- Ignoring thermal throttling that halves throughput under real use.
- Shipping a feature users disable because it drains the battery.
- Fitting the envelope on a flagship and assuming low-tier devices match.

## Done checklist

- [ ] Size measured and delivery mode chosen.
- [ ] Peak RAM within budget with headroom.
- [ ] Thermal cliff identified and avoided.
- [ ] Battery impact measured per workload.
- [ ] Envelope breaches resolved by model or path change.
- [ ] Envelope recorded per device tier.

## Sources

- Efficient deep learning survey: <https://arxiv.org/abs/2106.08962>
- TensorFlow Lite guide: <https://www.tensorflow.org/lite/guide>
- Apple CoreML framework: <https://developer.apple.com/documentation/coreml>
