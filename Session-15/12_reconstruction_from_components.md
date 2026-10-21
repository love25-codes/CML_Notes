# 12. Reconstruction from k Components

PCA can compress data by keeping only the first `k` components. We can also approximately reconstruct the original data from those components.

If many components are kept, the reconstruction is usually closer to the original. If only a few are kept, details are lost.

For example, the lecture discusses reconstructing a 64-feature image of a digit:
- 5 components: more information is lost, so the image may look blurry.
- 20 components: more details return.
- 40 components: the reconstruction is usually clearer.
- 64 components: in this example, keeping all available components can preserve the full representation, subject to the data setup.

This shows the trade-off: fewer components need less storage and computation, but can lose detail. Sometimes performance improves after reduction because low-variance noise is removed; this is not guaranteed.
