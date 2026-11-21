---
name: browser-and-web-inference
domain: software-engineering/browser-and-web-inference
trigger: "Running model inference inside a web browser."
anti_trigger: "Not for native mobile deployment, and not for server-side serving."
scope: "WASM and WebGPU inference in the browser."
status: seedling
---

# Browser and web inference

## Standard

The browser is an edge target with unique properties: no install step, universal reach, and the user's data stays on their machine. Inference runs through WebAssembly, which executes on the CPU and works everywhere, and WebGPU, which exposes the device's GPU for compute and is substantially faster for suitable models. ONNX Runtime Web runs ONNX models in the browser using WASM and WebGPU backends, and other runtimes offer the same two paths.

The constraints are real. The model must be downloaded, so size directly costs the user bandwidth and time-to-first-inference, and caching strategy decides whether that cost is paid once or per visit. WASM is the compatibility floor but slow for large models; WebGPU is faster but not universally supported, and support varies by browser and version, so a WASM fallback is required. Cross-origin isolation is needed for the threading that makes WASM inference efficient, which is a deployment configuration, not a code detail. Treat the browser as a genuine target with its own budget, not as a free port of the native app.

Primary sources: <https://onnxruntime.ai/docs/tutorials/web/> and <https://www.w3.org/TR/webgpu/>.

## Decision rules

- Use WASM as the compatibility baseline and WebGPU as the accelerated path where supported.
- Ship a WASM fallback; WebGPU support is not universal and varies by browser and version.
- Budget model download size against time-to-first-inference; cache the model deliberately.
- Configure cross-origin isolation for threaded WASM inference.
- Measure on the browsers and devices the audience actually uses, not on one desktop.
- Keep a server path for models too large or too slow for the browser.

## Procedure

1. Convert and validate the model for the web runtime, as for any target.
2. Integrate the WASM path first and confirm correctness.
3. Add the WebGPU path with a runtime capability check and WASM fallback.
4. Set the cross-origin isolation headers required for threading.
5. Implement model caching and measure download and first-inference time.
6. Benchmark across the real browser and device mix; record results.

## Anti-patterns

- Requiring WebGPU with no WASM fallback.
- Shipping a huge model with no caching and no size budget.
- Forgetting cross-origin isolation and losing threaded performance.
- Benchmarking only on a fast desktop browser.
- Assuming the browser matches native on-device performance.

## Done checklist

- [ ] Model converted and validated for the web runtime.
- [ ] WASM path working as the baseline.
- [ ] WebGPU path with capability check and fallback.
- [ ] Cross-origin isolation configured.
- [ ] Caching and download budget measured.
- [ ] Real browser and device mix benchmarked.

## Sources

- ONNX Runtime Web tutorial: <https://onnxruntime.ai/docs/tutorials/web/>
- W3C WebGPU specification: <https://www.w3.org/TR/webgpu/>
- MDN WebGPU API: <https://developer.mozilla.org/en-US/docs/Web/API/WebGPU_API>
