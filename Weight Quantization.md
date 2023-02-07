
Quantization of a floating-point number to a fixed-point number involves mapping a range of continuous values to a range of discrete values. The number of bits used for quantization determines the number of discrete values in the output.

For example, if we want to quantize 0.43 to a 4-bit integer, we can first multiply it by 2^4 (16) to get 6.88, and then round it to the nearest integer, which is 7 in this case. The 4-bit integer representation of 0.43 is 7.

If we want to quantize 0.43 to an 8-bit integer, we can multiply it by 2^8 (256) to get 110.08, and then round it to the nearest integer, which is 110 in this case. The 8-bit integer representation of 0.43 is 110.

If we want to quantize 0.43 to a 16-bit integer, we can multiply it by 2^16 (65536) to get 28268.48, and then round it to the nearest integer, which is 28268 in this case. The 16-bit integer representation of 0.43 is 28268.

Similarly, we can quantize 1.2 to 4-bit, 8-bit, and 16-bit integers using the same process.

Quantization of weights involves converting the model's weights from floating-point representation to fixed-point representation, which can reduce the memory footprint and computation costs of the model. The conversion process can cause significant changes to the model's parameters, so it's important to train the model with a smaller learning rate when quantizing the weights to ensure that the changes are gradual and the model's accuracy is not significantly affected.

The learning rate should be small enough that the updates to the model's parameters during training are small compared to the original values, but not so small that the training process takes
(Learning rate 0.001 - 0.0001)