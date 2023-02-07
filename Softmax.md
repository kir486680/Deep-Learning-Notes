Assuming a suitable loss function, we could try, directly, to minimize the difference between o and the labels y. While it turns out that treating classification as a vector-valued regression problem works surprisingly well, it is nonetheless lacking in the following ways:

-   There is no guarantee that the outputs $o_i$ sum up to 1 in the way we expect probabilities to behave.
    
-   There is no guarantee that the outputs $o_i$ are even nonnegative, even if their outputs sum up to 1, or that they do not exceed 1.

![[Pasted image 20230202193459.png]]