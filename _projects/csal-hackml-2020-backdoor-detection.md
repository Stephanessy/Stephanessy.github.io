---
title: "CSAW HackML 2020 Backdoor detection"
collection: projects
permalink: /projects/csal-hackml-2020-backdoor-detection
excerpt: 'Detection and repair of backdoored model trained from YouTube Face dataset'
start: 2020-10-1
end: 2020-12-1
---
## I. Goal
The repaired networks take as input a YouTube Face image and outputs N+1 classes, where the N+1 class represents a backdoored inputs. Implement two method: a STRIP based method & a Fine-Prunning based method

## II. STRIPE
STRIP is a runtime detection method and its idea is based on the fact that trigger have strong effect to force result to be a fixed wrong class. For a test image, we superimpose it with random clean image for several times, if test image is poisoned, the result will be relatively static, otherwise the results will be chaos. And this is measured by entropy. Values of entropy of poison image is small and that of clean image is larger so we can compute a detection boundary.

STRIP is proposed by Yansong Gao et al, (2020). Link for the paper: [STRIP: A Defence Against Trojan Attacks on Deep Neural Networks](https://arxiv.org/pdf/1902.06531.pdf)

## III. FINE-PRUNING
We implement fine-pruning defense from paper [Fine-Pruning: Defending
Against Backdooring Attacks on Deep Neural Networks](https://arxiv.org/pdf/1805.12185.pdf). Fine-pruning defense is a combination of pruning and fine-tuning, and shows that it successfully weakens or even eliminates the backdoors.
We are able to disable a backdoor by removing neurons that are dormant for clean inputs. We refer to this strategy as the pruning defense. The pruning defense works as follows:
1. the defender exercises the DNN which received from the attacker with clean inputs from the validation dataset, <img src="https://latex.codecogs.com/svg.latex?\Large&space;x=D_{valid}" title="\Large x=\frac{-b\pm\sqrt{b^2-4ac}}{2a}" />, and records the average activation of each channel of neurons in the final convolutional layer, which is conv3 layer.
2. The defender then iteratively prunes neurons from the DNN’s final convolutional layer (conv3 layer in BadNet) in increasing order of average activations and records the accuracy of the pruned network in each iteration.

[Link for the project](https://github.com/Stephanessy/ML-project)
