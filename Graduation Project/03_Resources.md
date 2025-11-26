
[UNET Segmentation of OC/OD](https://www.kaggle.com/code/arnavjain1/unet-segmentation-of-oc-od)
[My code](https://www.kaggle.com/code/ahmedalnile/glaucoma-diagnosing/)

#### Segmentation Guide
- [what is image segmentation](https://huggingface.co/tasks/image-segmentation)
- [Transformer-based image segmentation](https://huggingface.co/learn/computer-vision-course/en/unit3/vision-transformers/vision-transformers-for-image-segmentation)
- [Making Sense of Segmentation Metrics: A Clear Guide for Beginners](https://medium.com/@sabrina.jorgenson/making-sense-of-segmentation-metrics-a-clear-guide-for-beginners-33bf6789f41d)
- [Fine-Tune a Semantic Segmentation Model with a Custom Dataset](https://huggingface.co/blog/fine-tune-segformer)


## Library

[Segmentation_models.pytorch](https://github.com/qubvel-org/segmentation_models.pytorch): Python library with Neural Networks for Image Semantic  
Segmentation based on [PyTorch](https://pytorch.org/)

- [PyTorch Segmentation Models — A Practical Guide](https://medium.com/@heyamit10/pytorch-segmentation-models-a-practical-guide-5bf973a32e30)



#### [Attention U-Net: Learning Where to Look for the Pancreas](https://www.kaggle.com/code/truthisneverlinear/attention-u-net-pytorch)


#### [Med-Adpt Zoo Map 🐘🐊🦍🦒🦨🦜🦥](https://huggingface.co/KidsWithTokens/Medical-Adapter-Zoo)

Here are the pre-trained Adapters to transfer [SAM](https://segment-anything.com/) (Segment Anything Model) for segmenting various organs/lesions from the medical images. Check our paper: [Medical SAM Adapter](https://arxiv.org/abs/2304.12620) for the details.

SAM (Segment Anything Model) is one of the most popular open models for image segmentation. Unfortunately, it does not perform well on the medical images. An efficient way to solve it is using Adapters, i.e., some layers with a few parameters to be added to the pre-trained SAM model to fine-tune it to the target down-stream tasks. Medical image segmentation includes many different organs, lesions, and abnormalities as the targets. So we are training different adapters for each of the targets, and sharing them here for the easy usage in the community.

### [TransAttUne](https://arxiv.org/pdf/2107.05274)

The **Transferable Attention U-Net (TAU-Net or TAU)** is a deep learning model, typically used for medical image segmentation, that integrates attention mechanisms with a U-Net architecture to address the challenge of **domain shift**. It is designed to perform accurately on new, unseen datasets without extensive re-annotation or retraining.

- **Domain Adaptation:** The primary goal of TAU is to enable models pretrained on one set of data (source domain) to perform well on data from different sources (target domains) that may have variations in resolution, contrast, or field-of-view. This is particularly useful in medical imaging, where data acquisition methods can vary significantly.
- **Attention Mechanisms:** Attention modules are incorporated into the U-Net backbone to help the model automatically focus on relevant target structures and suppress irrelevant regions, improving performance and interpretability.
- **Adversarial Training:** The original TAU model uses two discriminators (feature domain discriminator and attention domain discriminator) during training to encourage the network to learn features that are invariant across different datasets.



### [Segformer for optic disc cup segmentation (don't use this you can use it for comprsion)](https://huggingface.co/pamixsun/segformer_for_optic_disc_cup_segmentation#model-card-for-model-id)


This SegFormer model has undergone specialized fine-tuning on the [REFUGE challenge dataset](https://refuge.grand-challenge.org/), a public benchmark for semantic segmentation of anatomical structures in retinal fundus images. The fine-tuning enables expert-level segmentation of the optic disc and optic cup, two critical structures for ophthalmological diagnosis.
#### Bias, Risks, and Limitations

The model has undergone specialized training and fine-tuning exclusively using retinal fundus images, with the objective to perform semantic segmentation of anatomical structures including the optic disc and optic cup. Therefore, in order to derive optimal segmentation performance, it is imperative to ensure that only fundus images are entered as inputs to this model.