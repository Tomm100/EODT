# EoDT: Encoder-only Detection Transformer

**Author:** Tommaso Centonze

Object detection is a fundamental computer vision task focused on localizing and classifying objects within images. The introduction of the DEtection TRansformer (DETR) transformed this field by framing detection as a direct set prediction problem. To do so, DETR and its successors leverage an encoder-decoder structure: a Transformer encoder processes image features, while a specialized decoder refines object queries. 

Over time, object detection architectures have grown increasingly complex, adding multi-scale feature extractors and heavy task-specific decoder heads. The segmentation domain, by contrast, has recently moved toward radical simplification. Architectures like EoMT showed that the task-specific decoder can be dropped entirely: by injecting learnable queries into the final layers of a plain Vision Transformer (ViT), the model handles the full predictive process inside the encoder alone, relying on the strong inductive biases of large pre-trained models.

This thesis explores whether this encoder-only paradigm can be successfully applied to object detection. We propose EoDT (Encoder-only Detection Transformer), an architecture that entirely eliminates the traditional decoder. By injecting learnable queries directly into a standard pre-trained Vision Transformer (DINOv2), the full detection pipeline is resolved within the encoder. 

We evaluate this solution on established benchmarks such as COCO to assess whether an encoder-only architecture can match the accuracy of complex decoder-based models at a fraction of the architectural complexity, mirroring the simplification recently brought to segmentation.
