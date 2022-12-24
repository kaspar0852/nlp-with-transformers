# nlp-with-transformers
Transformers:
1st step
The input will go into the word embedding layer

1.Word Embedding:
Each word is maps to a vector with continuous values to represent that word. 

2.Positional Encoding:
As transformer encoder has no recurrence as RNN so we must add information about the positions of the input encodings.
This is done using positional encoding. For every Odd time step create a vector using cosine function and for every even time step create a 
vector using a sin function.Then add those vectors to their corresponding embedding vector.This process successfully gives the network information 
about the positions of the each vector. The sine and cosine function were chosen because they have linear properties which the model can easily
learn to attaen to.

3.Encoder Layer:
The encoder layers job is to map all the input sequence into an abstract continuous representation that holds the learn information
for that entire sequence.This layer contains 2 modules multi headed attention and a fully connected network.

   A.Multi headed attention: This applies a specific attention know as self attention.
   Self attention helps the module to associate each individual word to another word in the input 
   i.e if our input is ‘ Hi how are you’ then it is possible that our model will learn to associate you with are and how.
   To acheive self attention we feed the input to 3 distinct fully connected layer to create query, key and value vectors.
   (see explanation properly visually YT-the ai hacker)

   B.Residual connection,Layer Normalization and point wise Feet Forward:
   The output vector of the multi headed attention  is added to the original input this is called a residual connection.
   The output of the residual connection goes through a layer nomalization. 
   The normalized residual output goes through a point wise feet forward network for further processing.

4.Decoder: This will have 2 multi headed attention layer. 
Here for an output of I am Fine the word ‘am’ should not have access to the score of the word ‘fine’ because it will come at the future. 
So to prevent the access of the score of future word masking is done 

These are some of the layers within the transformers and is not complete as it is very hard to write in words so refer to :
https://www.youtube.com/watch?v=4Bdc55j80l8
