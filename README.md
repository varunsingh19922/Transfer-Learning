This project aims to build a model using transfer learning. I used a pre trained Vision transformer to build a model by transfer learning which can be used to classify satellite images belonging to different terrains, the EuroSAT dataset. By using transfer learning techniques, we can use the weights and biases of a pre trained transformer model and change the final classification layer based on the current requirement. And this helps us build a model that takes considerably less time to train, we utilize knowledge that the Vision transformer already possesses from training over the ImageNet dataset. The original training time of the ViT base model was 3 days, by using transfer learning I built models in 1-2 hours with 96-97% accuracy. 

In this project I created multiple models to investigate how different models perform based on the training time and the accuracy of model predictions on test data. I also froze the weights of different layers and finetuned some layers which were upstream or downstream in the architecture of the transformer to investigate how the train times and accuracy were affected. In total I created 5 models to analyse, 

Model Description	                        Train Accuracy	  Test Accuracy	  Training Loss	  Testing Loss  	Running Time
1. CNN - our basic classifier model	        74-75 %	          77-78 %	        0.7306	        0.6267	      13 mins 21 seconds
2. ViT, all layers frozen	                  89-90 %	          93-94 %	        0.3233	        0.2081	      49 mins 56 seconds
3. ViT, finetuned encoder layer 11	        91-92 %	          95-96 %	        0.2466	        0.1377	      53 mins 20 seconds
4. ViT, finetuned encoder layers 0 & 1	    85-86 %	          87-88 %	        0.4322	        0.3595	      95 mins 19 seconds
5. ViT, finetuned encoder layer 10 & 11	    93-94 %	          96-97 %	        0.1988	        0.1182	      56 mins 54 seconds
