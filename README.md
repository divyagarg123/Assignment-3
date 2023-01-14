# S-3

## Part-1
1. Below is the image of simple neural network with 1 input layer , 1 hidden layer and 1 output layer. We have two inputs and two outputs. 
Truth values t1, t2 are the real outputs. E1 is loss from first output and E2 is loss from second output. E_total is sum of E1 and E2.
We need to train this neural network such that E_total is minimized. For this E1 and E2 needs to be minimized.
w1....w8 are the weights which will be learned while training this neural network. Their initial values are given in below image.

![image](https://user-images.githubusercontent.com/109232157/212311429-bd95b046-4315-42c3-bc0c-7a32f9cec857.png)

2. In Ist image, Forward propagation equations are written, i1 and i2 are the inputs. Then they are multiplied with weights to form h1, h2 . Then activations are applied on h1 and h2 to form a_h1 and a_h2. Sigmoid activation is used to introduce non linearity. Then a_h1 and a_h2 are inputs to output layer. they are multiplies with weights to form o1 and o2 . Again same activation is applied to form a_o1 and a_o2 .These are the outputs from network. Now to find loss, E1, E2, square of differences between the network and real outputs are taken. E_total is sum of E1 and E2.

3. Now we need to minimize the less. For that, we will backpropagate this loss, and make the network learn the weights which will help us to minimize the loss. 
For that, we need to find the partial derivatives of E_total w.r.t all weights(w1, w2....w8).

4. In second image, we are finding the partial derivative of E_total w.r.t w5, There is only path to w5 which is through E1, a_o1, o1, a_h1. Hence we have used chain rule to find the partial derivative.

5. Similarly In third image, we have derivatives w.r.t w5, w6, w7, w8.

![image](https://user-images.githubusercontent.com/109232157/212311846-8bf68cfb-39ce-441d-8dc5-85ca86897047.png)

6. Now we need to find the derivatives w.r.t to w1, w2, w3, w4. Lets understand w.r.t w1 first. Now , from E_total to w1, we have two paths. One is E_total->E1->a_o1->o1>w5->a_h1->h1->w1 and second is E_total->E2->a_o2->o2>w8->a_h2->h2->w1. 

7. In 5th image, We have shown how can we find partial derivatives using chain rule. So we need E_total w.r.t to a_h1 and a_h1 w.r.t to h1 and h1 w.r.t w1. Similarly for others.

8. In 4th image, we have shown how can we find derivative of E_total w.r.t a_h1 and a_h2

9. In 6th image, we have combined these and shown the derivatives of E_total w.r.t w1, w2, w3, w4.

![image](https://user-images.githubusercontent.com/109232157/212311978-92316dc3-fa0e-49ac-b207-ca4a387e8df3.png)

10. Below are the loss curves at different learning rates for about ~100 iterations of above algorithm. As we are decreasing the learning rate, convergence rate decreases. 

![image](https://user-images.githubusercontent.com/109232157/212312507-7e8d16c4-50ac-42d6-8f56-9d1912c1cca9.png) ![image](https://user-images.githubusercontent.com/109232157/212312320-d3d05bc7-9754-4606-a076-8db58038080c.png) 
![image](https://user-images.githubusercontent.com/109232157/212312785-c8f15078-0811-433f-a06f-92f8d21cc49a.png) ![image](https://user-images.githubusercontent.com/109232157/212312924-16a3ee61-31e4-4747-b4c6-ab032f909d0c.png)
![image](https://user-images.githubusercontent.com/109232157/212313118-d0f00b54-410d-497e-9875-bd4f26961cb0.png) ![image](https://user-images.githubusercontent.com/109232157/212313198-a2458368-feb6-4580-82ce-a2e7206b8866.png)


## Part-2

Below is the network, layers i have used to bring mnist accuracy to 99.4%.
Dropouts(5%) and batch norms are used after every layer except last.
Maxpoolings used in second and 4th block.
1*1 convolutions are used in 5th block just to filter information.
Average pooling is used and after that fully connected layer is used.

![image](https://user-images.githubusercontent.com/109232157/212445621-c5fa0a96-5773-4cbf-9a62-2900b1e73c1b.png)

In below picture, parameters are shown and how receptive field is increasing with image size decreasing.
Input size = 28(input size)->28(first conv layer, padding-1)->26(second conv)->13(max pool)->11(third conv)->9(fouth conv)->4(max pooling)->2(fifth conv)->1(avg pooling)
Receptive fields: 1------------------->2------------------------------->4--------------> 8----------->10------------>12------------>24--------------->26------------>28

![image](https://user-images.githubusercontent.com/109232157/212445464-4477831c-7561-472d-a47d-5f13c51f56c5.png)

![image](https://user-images.githubusercontent.com/109232157/212445477-983c5126-568a-40e2-aabb-5d999b725cc5.png)




