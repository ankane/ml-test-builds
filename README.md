# ML Builds

Pre-built shared libraries for machine learning

Library | Linux | Mac | Windows | Assets | License | Notes
--- | --- | --- | --- | --- | --- | ---
[Bling Fire](https://github.com/Microsoft/BlingFire) | ✓ | x86-64 | ✓ | [View](https://github.com/ankane/ml-builds/releases/tag/blingfire-0.1.3) | MIT |
[cmfrec](https://github.com/david-cortes/cmfrec) | ✓ | ✓ | | [View](https://github.com/ankane/ml-builds/releases/tag/cmfrec-2.4.1) | MIT |
[Faiss](https://github.com/facebookresearch/faiss) | ✓ | x86-64 | n/a | [View](https://github.com/ankane/ml-builds/releases/tag/faiss-1.6.1) | MIT |
[Interpret](https://github.com/interpretml/interpret) | ✓ | ✓ | ✓ | [View](https://github.com/ankane/ml-builds/releases/tag/interpret-0.2.0) | MIT |
[LIBMF](https://github.com/cjlin1/libmf) | ✓ | ✓ | ✓ | [View](https://github.com/ankane/ml-builds/releases/tag/libmf-master) | BSD-3-Clause | Fork, no OpenMP
[MITIE](https://github.com/mit-nlp/MITIE) | ✓ | ✓ | ✓ | [View](https://github.com/ankane/ml-builds/releases/tag/mitie-0.7) | BSL-1.0
[Multicore t-SNE](https://github.com/DmitryUlyanov/Multicore-TSNE) | ✓ | x86-64 | ✓ | [View](https://github.com/ankane/ml-builds/releases/tag/multicore-tsne-master) | BSD-3-Clause | Fork with OpenMP for Mac
[NGT](https://github.com/yahoojapan/NGT) | ✓ | ✓ | n/a | [View](https://github.com/ankane/ml-builds/releases/tag/ngt-1.12.2) | Apache-2.0 |
[SCS](https://github.com/cvxgrp/scs) | ✓ | ✓ | ✓ | [View](https://github.com/ankane/ml-builds/releases/tag/scs-2.0.2) | MIT | No blas/lapack on Windows
[ThunderSVM](https://github.com/Xtra-Computing/thundersvm) | ✓ | x86-64 | ✓ | [View](https://github.com/ankane/ml-builds/releases/tag/thundersvm-0.3.4) | Apache-2.0 |
[XGBoost](https://github.com/dmlc/xgboost) | ✓ | ✓ | ✓ | [View](https://github.com/ankane/ml-builds/releases/tag/xgboost-1.3.0) | Apache-2.0 | No OpenMP on Windows
[xLearn](https://github.com/aksnzhy/xlearn) | ✓ | x86-64 | ✓ | [View](https://github.com/ankane/ml-builds/releases/tag/xlearn-0.4.4) | Apache-2.0 |

View the [build scripts](.github/workflows)

Some projects include shared libraries as part of their releases:

- [LibTorch](https://pytorch.org/)
- [LightGBM](https://github.com/microsoft/LightGBM/releases)
- [ONNX Runtime](https://github.com/microsoft/onnxruntime/releases)
- [OR-Tools](https://developers.google.com/optimization/install/cpp)
- [OSQP](https://bintray.com/bstellato/generic/OSQP#files)

## Details

For portability:

- Linux libraries are built with `-march=x86-64` (when possible) and older `glibc` (todo: build with much older)
- Mac x86-64 libraries are built with `-march=nehalem` (same as Homebrew) and `MACOSX_DEPLOYMENT_TARGET=10.13`
- Mac arm64 libraries are built with `-march=armv8-a` and `MACOSX_DEPLOYMENT_TARGET=11.0`

[Reference](https://gcc.gnu.org/onlinedocs/gcc/x86-Options.html)

Other notes:

- Windows libraries are built with `-A x64`
- Mac x86-64 libraries that use OpenMP require `brew install libomp` (Faiss, Multicore t-SNE, NGT, ThunderSVM, XGBoost)
