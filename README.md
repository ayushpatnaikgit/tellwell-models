# TellWell models

The model files the TellWell apps download on first launch, mirrored here as release assets so the apps never depend
on a third party keeping its files online. Each file is byte-for-byte the original (same SHA-256), and the apps
refuse any file whose SHA-256 doesn't match.

- [TellWell for Mac](https://github.com/ayushpatnaikgit/tellwell)
- [TellWell for Android](https://github.com/ayushpatnaikgit/tellwell-android)

## Release v1

| File | Used by | Size | SHA-256 |
|---|---|---|---|
| `parakeet-tdt-0.6b-v2-coreml.zip` | Mac: speech recognition on the Neural Engine | 450 MB | `ae3ea934db9350bf137a4768bdca27931e6ef9352df14b4c6f275aa9158df503` |
| `s1-mini-freeflow-cleanup-q4_0.gguf` | Mac and Android: cleanup | 382 MB | `ff7dfbc19d7220ac7e1f7cd88bc95da3db7e7e7893a35ea552895727605abddc` |
| `parakeet-tdt-0.6b-v2-int8-encoder.int8.onnx` | Android: speech recognition | 652 MB | `92a10bd9c23936ea0566c29f963bc57c2a5df4261b6a8921c39abea66557ca8b` |
| `parakeet-tdt-0.6b-v2-int8-decoder.int8.onnx` | Android | 7 MB | `4d097bae3bac5c96018d5293ba39f1b657296102b142affda40378f38b020f41` |
| `parakeet-tdt-0.6b-v2-int8-joiner.int8.onnx` | Android | 2 MB | `77a29f3e5ac7d37074e0af465391b80f314015d5b97f0f90c6c7767f1d56f428` |
| `parakeet-tdt-0.6b-v2-int8-tokens.txt` | Android | 9 KB | `ec182b70dd42113aff6c5372c75cac58c952443eb22322f57bbd7f53977d497d` |

## Sources and licences

- **NVIDIA Parakeet TDT 0.6B v2** (English speech recognition), [nvidia/parakeet-tdt-0.6b-v2](https://huggingface.co/nvidia/parakeet-tdt-0.6b-v2), licensed [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/).
  - Core ML conversion by FluidInference: [FluidInference/parakeet-tdt-0.6b-v2-coreml](https://huggingface.co/FluidInference/parakeet-tdt-0.6b-v2-coreml) at commit `ee09c569f73759e6d44c9bd16766f477b2b36d39`, CC BY 4.0. The zip holds `Preprocessor`, `Encoder`, `Decoder` and `JointDecision` (`.mlmodelc`) and `parakeet_vocab.json`, unchanged.
  - int8 ONNX export for sherpa-onnx: [csukuangfj/sherpa-onnx-nemo-parakeet-tdt-0.6b-v2-int8](https://huggingface.co/csukuangfj/sherpa-onnx-nemo-parakeet-tdt-0.6b-v2-int8) at commit `84b478d541cdbf0c296a7ab5f1e20a6f8f998114`, CC BY 4.0. Files are renamed with a `parakeet-tdt-0.6b-v2-int8-` prefix, otherwise unchanged.
- **S1-mini FreeFlow Cleanup** (GGUF, Q4_0), a fine-tune of **S1-mini** by **Superwhisper**: [ayushpatnaik/S1-mini-FreeFlow-cleanup-GGUF](https://huggingface.co/ayushpatnaik/S1-mini-FreeFlow-cleanup-GGUF) at commit `6665acc599d42d7adc2d55c577119e56ee22810d`. Apache 2.0 with S1-mini's naming clause: any use or distribution must continue to identify the model as "S1-mini" by "Superwhisper" (see that model card's LICENSE).
