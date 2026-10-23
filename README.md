# UPC_CV_Project_1
Four challenges for BP1 of CV to do with counting, classifying and normalising screws and nuts

---

### Challenge 1 — Segmentation & Part Counting (C1)
* **Goal**: Detect, isolate, and count individual fasteners against irregular wood backgrounds, handling shadows, specular reflections, and wood-chip color similarities.
* **Methodology**: Evaluates multiple distinct algorithmic families (e.g., adaptive thresholding, color space transforms, morphological watershed/clustering, active contours).
* **Rigorous Evaluation**: Isolated under unified post-processing and benchmarked via ground-truth IoU (Jaccard Index), precision, and pixel-level accuracy metrics.

### Challenge 2 — Fastener Classification: Screws vs. Nuts (C2)
* **Goal**: Categorize detected components into screws/bolts vs. nuts and tally parts per category.
* **Feature Engineering**: Extraction and analysis of rotation- and scale-invariant shape descriptors, topological genus (Euler characteristic/holes), and moment invariants (Hu/Flusser moments).
* **Statistical Modeling**: Benchmarking classifiers (e.g., Linear/Quadratic Discriminant Analysis, SVMs, k-NN, tree ensembles) alongside robustness analysis against imperfect segmentations.

### Challenge 3 — Surface Finish & Material Identification (C3)
* **Goal**: Discriminate fastener coatings (e.g., zinc-plated, yellow zinc-chromate, black-oxidized, stainless steel).
* **Feature Representation**: Texture and reflectance analysis using Local Binary Patterns (LBP), Gray-Level Co-occurrence Matrices (GLCM), Laws' texture energy filters, and color histograms.
* **Invariance & Robustness**: Explicit handling of non-uniform spatial illumination, auto-white-balance drift, high specular highlights, and low-resolution/thin fasteners.

### Challenge 4 — Canonical Pose Normalisation via Registration (C4)
* **Goal**: Re-align isolated parts into standardised reference poses for downstream automated metrology (screws vertical with head upward; nuts parallel to the horizontal axis).
* **Mathematical Formulation**: Posed as formal image registration defining moving/fixed targets, 2D rigid transformation matrices ($SE(2)$), metric similarity measures, and optimizers.
* **Symmetry & Metrology Checks**: Resolves structural symmetries ($180^\circ$ screw head/tip ambiguity, $60^\circ$ hexagonal rotational symmetry for nuts) and independently validates residual alignment errors using Hough line verification and perturbation testing.

## Evaluation & Grading Criteria

Each block is evaluated using a detailed assessment rubric across defined performance levels:

| Component | Focus Area & Assessment Criteria | Weight |
| :--- | :--- | :---: |
| **C1** | $N$ segmentation methods, evaluation, robustness, and justified method choice | **25%** |
| **C2** | Feature study, $N$ classifiers, and robustness analysis | **15%** |
| **C3** | $N$ finish methods, illumination handling, and texture analysis per finish | **20%** |
| **C4** | Registration formulation, accuracy, handling symmetries, and independent checks | **20%** |
| **Code** | Reproducibility on unseen test images, clarity, and strict adherence to `inputs/` and `outputs/` conventions | **10%** |
| **Report** | Document structure, figure quality, statistical rigor, critical discussion, and technical writing | **10%** |
