Glaucoma remains one of the primary causes of irreversible blindness, characterized by gradual damage to the optic nerve, which often goes undetected until advanced stages. Accurate and  early diagnosis depends heavily on precise segmentation of the optic disc and optic cup in retinal fundus images, as this enables reliable calculation of the cup-to-disc ratio.

To address these issues, this study introduces DB-SegNet, an advanced diagnostic framework designed to enhance both segmentation accuracy and glaucoma detection

However many current deep learning approaches struggle with generalization because of challenges such as variable image quality, blood vessel occlusion, and structural ambiguities, leading to reduced segmentation and classification accuracy.


These challenges underscore the necessity of a unified end-to-end diagnostic framework that seamlessly combines segmentation, feature optimization, and classification within a single architecture. Such an approach should not only achieve high segmentation precision and robustness across diverse imaging conditions but also deliver clinically reliable classification outcomes while maintaining computational efficiency. To address these gaps, this work introduces `DB-SegNet`, an optimized framework designed for glaucoma detection and optic structure segmentation.

Built on the SegNet backbone, the model is enhanced with:
- a `Dilated Atrous Context Module (DACM)` for multi-scale context extraction and 
- a `Bidirectional Feature Calibration Unit (BFCU)` to refine boundary accuracy.
- Beyond segmentation, the framework integrates `Bitterling Fish Optimization (BFO)` for effective dimensionality reduction, ensuring the preservation of the most discriminative features while minimizing redundancy.
- `A Multi-Scale Attention Transformer (MSAT)` further enriches the network by capturing long-range dependencies and hierarchical structural relationships, enabling accurate recognition of subtle optic variations.