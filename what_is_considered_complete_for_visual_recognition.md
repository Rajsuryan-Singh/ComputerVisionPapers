**Link to Paper:** https://arxiv.org/pdf/2105.13978.pdf

### Summary

Opinionated paper on the completeness of visual recognition. Proposes that effective compression (i.e. a high compression to recovery ratio) be considered as a metric for completeness of visual recogniton as visual data is immensely complex. By "complete", the authors refer to a vision algorithm that has the the ability to recognise all visual information that a human can recognise. 

A human can recognise rich and hierarchical information upon request. For example, both humans and CV algorithms perform well on identifying a person in a image, but humans, if prompted, can easily go on to identifying more fine-grained features like arms, fingers, knuckles, to even single cells if provided with the necessary resolution. This stems from "understanding" images rather than pure recognition. When a human sees a person, we already have a mental representation of the anatomy, a template so to speak, and we fill that template up with the information we see. Which is fundamentally different from the way a CV algorithm "sees" an image. 

The authors argue that the learning-by-annotation paradigm has a fundamental flaw - "complete" annotations are impossible as annotations form an open set (one can keep adding elements to the set of all annotations) and incomplete annotations have a negative impact on learning. The empirical proof of this is that richer annotations improve model performance (bounding boxes improve classification accuracy, pixel wise segmentation improves object detection etc.). Additionally, as performance on benchmarks goes up, it raises the question of the model overfitting the training data, or even the evaluation protocol built upon incomplete annotations. 


**The Solution:** A learning-by-compression framework, where a pair of encoder and decoder networks aim to achieve a high compression ratio along with a high resolution of recovery. The idea here is that if you can effectively compress something, you have an understanding of the building blocks. The authors propose this as a pretraining task for vision, where the encoder network captures features at different levels of resolution. 