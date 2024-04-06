This project utilized transfer learning with a pre-trained Vision Transformer (ViT) to classify satellite images from the EuroSAT dataset. By leveraging the pre-trained model's weights and biases, the final classification layer was modified to suit the specific task, significantly reducing training time. The original ViT base model, trained on ImageNet, required 3 days for training, whereas the transfer learning approach achieved model creation in 1-2 hours with 96-97% accuracy.

Multiple models were created to explore different training times and accuracy levels. Various experiments involved freezing different layers of the ViT model and fine-tuning specific layers to analyze their impact on training time and accuracy. In total, five models were evaluated, with varying results summarized as follows:

| Model Description                               | Train Accuracy    | Test Accuracy    | Training Loss    | Testing Loss    | Running Time               |
|:------------------------------------------------|------------------:|-----------------:|-----------------:|----------------:|---------------------------:|
| 1. CNN - our basic classifier model             |   74-75 %         |    77-78 %       |       0.7306     |      0.6267     |  13 mins 21 seconds        |
| 2. ViT, all layers frozen                       |   89-90 %         |    93-94 %       |       0.3233     |      0.2081     |  49 mins 56 seconds        |
| 3. ViT, finetuned encoder layer 11              |   91-92 %         |    95-96 %       |       0.2466     |      0.1377     |  53 mins 20 seconds        |
| 4. ViT, finetuned encoder layers 0 & 1          |   85-86 %         |    87-88 %       |       0.4322     |      0.3595     |  95 mins 19 seconds            |
| 5. ViT, finetuned encoder layer 10 & 11         |   93-94 %         |    96-97 %       |       0.1988     |      0.1182     |  56 mins 54 seconds        |
