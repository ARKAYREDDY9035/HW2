AlexNet is originally proposed for 227*227 image sizes. It may be too complex for the CIFAR-10 dataset, in particular, due to the low resolution of the initial images; try simplifying the model to make the training faster while ensuring that the accuracy stays relatively high. Report the training loss, validation loss, and validation accuracy. Also, report the number of parameters in your modified version of AlexNet and compare it against the number of parameters in the original AlexNet architectures. Here is a good reference guide to AlexNet: https://www.kaggle.com/code/blurredmachine/alexnet-architecture-a-complete-guide
Links to an external site.
Explore the option of applying Dropout techniques for training your customized AlexNet. Compare the training and validation results against the baseline model without any dropout.


Notebook link -> https://colab.research.google.com/drive/1ytxqfUN2ezKpZLBE5-nPgUfl-_r5-jiV?usp=sharing


I have used AlexNet for  the CIFAR 10 to check the results . AlexNet is complicated with 11 * 11 and since CIFAR 10 being less resolution 32* 32 , the data is overfitted. We see the results are not improving. 


Epoch 1/10
1563/1563 [==============================] - 29s 14ms/step - loss: 2.3034 - accuracy: 0.0991 - val_loss: 2.3027 - val_accuracy: 0.1000
Epoch 2/10
1563/1563 [==============================] - 20s 13ms/step - loss: 2.3028 - accuracy: 0.0988 - val_loss: 2.3026 - val_accuracy: 0.1000
Epoch 3/10
1563/1563 [==============================] - 22s 14ms/step - loss: 2.3027 - accuracy: 0.0997 - val_loss: 2.3027 - val_accuracy: 0.1000
Epoch 4/10
1563/1563 [==============================] - 21s 13ms/step - loss: 2.3028 - accuracy: 0.0971 - val_loss: 2.3026 - val_accuracy: 0.1000
Epoch 5/10
1563/1563 [==============================] - 21s 13ms/step - loss: 2.3028 - accuracy: 0.0960 - val_loss: 2.3026 - val_accuracy: 0.1000
Epoch 6/10
1563/1563 [==============================] - 21s 13ms/step - loss: 2.3028 - accuracy: 0.0969 - val_loss: 2.3026 - val_accuracy: 0.1000
Epoch 7/10
1563/1563 [==============================] - 21s 13ms/step - loss: 2.3028 - accuracy: 0.0988 - val_loss: 2.3027 - val_accuracy: 0.1000
Epoch 8/10
1563/1563 [==============================] - 21s 14ms/step - loss: 2.3028 - accuracy: 0.0983 - val_loss: 2.3026 - val_accuracy: 0.1000
Epoch 9/10
1563/1563 [==============================] - 21s 13ms/step - loss: 2.3028 - accuracy: 0.1000 - val_loss: 2.3026 - val_accuracy: 0.1000
Epoch 10/10
1563/1563 [==============================] - 21s 13ms/step - loss: 2.3028 - accuracy: 0.0980 - val_loss: 2.3026 - val_accuracy: 0.1000




Below are the results from the less complicated Alexnet -  10 epochs.

Training Loss: 0.550784707069397
Training Accuracy: 0.8138999938964844
Validation Loss: 0.9350960850715637
Validation Accuracy: 0.7233999967575073
Total number of parameters in the simplified model: 842826




I have reduced the complexity of the Alexnet network by reducing the number of kernels and the kernel size. Now the accuracy has improved.






Increased Epochs to 20 


Training Loss: 0.3168511986732483
Training Accuracy: 0.8956999778747559
Validation Loss: 1.2922110557556152
Validation Accuracy: 0.70169997215271
Total number of parameters in the simplified model: 842826 

There is little improvement when epochs increased by not much

Added dropout 

Final Training Loss: 0.9678249359130859
Final Validation Loss: 0.9562284350395203
Final Training Accuracy: 0.6707199811935425
Final Validation Accuracy: 0.6825000047683716
Total number of parameters: 842826

The accuracy did not improve and the previous network without dropout performed well for 10 epochs. 




The baseline model we did in lectures is called ResNet-11. Build a new version of ResNet (ResNet-18). Train it on CIFAR-10. Plot the training loss, validation loss, and validation accuracy. Compare the classification accuracy, and model size across the two versions of ResNet (11, 18). How does the complexity grow as you increase the network depth?
You can find some references for ResNet 18 here:
https://www.kaggle.com/code/ivankunyankin/resnet18-from-scratch-using-pytorch
Links to an external site.
Explore the dropout option for the two networks and report your training results and validation accuracy.

The Resnet 18 performance in as below ,

Final Validation Accuracy: 82.57%
Total number of parameters in the model: 4903242
Below is the plot


Resnet 11 


Final Validation Accuracy: 82.57%
Total number of parameters in the model: 4903242

The accuracy and the parameters remain same 


We clearly observe that as the depth increases the model captures more features and we see that from the above graphs. The validation loss flattened after the 2nd epoch but in the Resnet 18 the validation loss kept decreasing even though it has increased for a few epochs.  

Resnet 18 with drop out 

Epoch 1, Training loss: 1.7171
Epoch 1, Validation Loss: 1.3853, Validation Accuracy: 48.51%
Epoch 2, Training loss: 1.3248
Epoch 2, Validation Loss: 1.1979, Validation Accuracy: 55.95%
Epoch 3, Training loss: 1.1361
Epoch 3, Validation Loss: 1.1316, Validation Accuracy: 59.96%
Epoch 4, Training loss: 0.9951
Epoch 4, Validation Loss: 1.0455, Validation Accuracy: 62.96%
Epoch 5, Training loss: 0.8732
Epoch 5, Validation Loss: 1.0243, Validation Accuracy: 63.96%
Epoch 6, Training loss: 0.7669
Epoch 6, Validation Loss: 1.0206, Validation Accuracy: 65.13%
Epoch 7, Training loss: 0.6578
Epoch 7, Validation Loss: 1.0658, Validation Accuracy: 65.58%
Epoch 8, Training loss: 0.5706
Epoch 8, Validation Loss: 1.0993, Validation Accuracy: 65.38%
Epoch 9, Training loss: 0.4847
Epoch 9, Validation Loss: 1.1220, Validation Accuracy: 65.40%
Epoch 10, Training loss: 0.4142
Epoch 10, Validation Loss: 1.1821, Validation Accuracy: 66.47%

The above is the validation accuracy. With dropout the accuracy went down for the same number of epochs for Resnet 18.
