INFO:__main__:Processed response from llama_scout API : The encoders in this picture are:

1. **Multi-head attention**: allows the model to attend to different parts of the input sequence simultaneously and weigh their impor
tance.
2. **Add & normalize**: adds the output of the multi-head attention mechanism to the input sequence and normalizes the result.
3. **Fully connected network**: a neural network layer that is fully connected, meaning every input is connected to every output.

These encoders are stacked 6 times, as indicated by the "6x" label on the left side of the diagram. The encoder takes in
 **input text**, which is first **tokenized** and then embedded into a vector space using **embeddings**. The embedded input sequence is then added to **positional encoding**, which provides information about the position of each token in the sequence.

INFO:__main__:Processed response from llama_maverick API : 
The image illustrates a Transformer model architecture, which is a type of
 neural network used primarily for natural language processing tasks. The diagram is divided into two main components: the Encoder and the Decoder.

**Encoder:**

The Encoder is represented on the left side of the diagram. It consists of a stack of identical layers, with the number of layers den
oted as "6x" on the left. Each layer comprises two sub-layers:

1.  **Multi-head attention**: This sub-layer allows the model to attend to different parts of the input sequence simultaneously and w
eigh their importance.
2.  **Fully connected network (Feed Forward Network)**: This sub-layer transforms the output from the multi-head attention mechanism.


Both sub-layers are followed by an **Add & normalize** operation, which adds the input to the output of the sub-layer and applies lay
er normalization.

**Decoder:**

The Decoder is depicted on the right side of the diagram. Similar to the Encoder, it consists of a stack of identical layers, with th
e number of layers also denoted as "6x". Each layer comprises three sub-layers:

1.  **Masked Multi-head attention**: This sub-layer is similar to the multi-head attention in the Encoder but with a mask to prevent
the model from attending to future tokens in the output sequence.
2.  **Multi-head attention**: This sub-layer attends to the output of the Encoder.
3.  **Fully connected network (Feed Forward Network)**: This sub-layer is identical to the one in the Encoder.

Again, both sub-layers are followed by an **Add & normalize** operation.

**Input and Output:**

The input to the Encoder is a sequence of tokens (e.g., words or subwords) represented as **Tokenized text**, which is then embedded
into a vector space using **Embeddings**. The input to the Decoder is also a sequence of tokens, represented as **Target text**, whic
h is similarly embedded.

The output of the Decoder is passed through a **Fully connected layer** to produce the final output.

In summary, the encoders in this picture are the left part of the diagram, which is labeled "Encoder". The Encoder takes in input tex
t, tokenizes it, embeds it, adds positional encoding, and then passes it through a stack of identical layers, each consisting of mult
i-head attention and a fully connected network, with add and normalize operations in between. There are 6 such encoder layers stacked
 together.
{'llama_scout': 'The encoders in this picture are:\n\n1. **Multi-head attention**: allows the model to attend to different parts of t
he input sequence simultaneously and weigh their importance.\n2. **Add & normalize**: adds the output of the multi-head attention mec
hanism to the input sequence and normalizes the result.\n3. **Fully connected network**: a neural network layer that is fully connect
ed, meaning every input is connected to every output.\n\nThese encoders are stacked 6 times, as indicated by the "6x" label on the le
ft side of the diagram. The encoder takes in **input text**, which is first **tokenized** and then embedded into a vector space using
 **embeddings**. The embedded input sequence is then added to **positional encoding**, which provides information about the position
of each token in the sequence.', 

'llama_maverick': 'The image illustrates a Transformer model architecture, which is a type of neural
 network used primarily for natural language processing tasks. The diagram is divided into two main components: the Encoder and the Decoder.\n\n**Encoder:**\n\nThe Encoder is represented on the left side of the diagram. It consists of a stack of identical layers, wi
th the number of layers denoted as "6x" on the left. Each layer comprises two sub-layers:\n\n1.  **Multi-head attention**: This sub-l
ayer allows the model to attend to different parts of the input sequence simultaneously and weigh their importance.\n2.  **Fully connected network (Feed Forward Network)**: This sub-layer transforms the output from the multi-head attention mechanism.\n\nBoth sub-lay
ers are followed by an **Add & normalize** operation, which adds the input to the output of the sub-layer and applies layer normaliza
tion.\n\n**Decoder:**\n\nThe Decoder is depicted on the right side of the diagram. Similar to the Encoder, it consists of a stack of
identical layers, with the number of layers also denoted as "6x". Each layer comprises three sub-layers:\n\n1.  **Masked Multi-head a
ttention**: This sub-layer is similar to the multi-head attention in the Encoder but with a mask to prevent the model from attending
to future tokens in the output sequence.\n2.  **Multi-head attention**: This sub-layer attends to the output of the Encoder.\n3.  **Fully connected network (Feed Forward Network)**: This sub-layer is identical to the one in the Encoder.\n\nAgain, both sub-layers are
 followed by an **Add & normalize** operation.\n\n**Input and Output:**\n\nThe input to the Encoder is a sequence of tokens (e.g., words or subwords) represented as **Tokenized text**, which is then embedded into a vector space using **Embeddings**. The input to the
 Decoder is also a sequence of tokens, represented as **Target text**, which is similarly embedded.\n\nThe output of the Decoder is passed through a **Fully connected layer** to produce the final output.\n\nIn summary, the encoders in this picture are the left part
of the diagram, which is labeled "Encoder". The Encoder takes in input text, tokenizes it, embeds it, adds positional encoding, and then passes it through a stack of identical layers, each consisting of multi-head attention and a fully connected network, with add an
d normalize operations in between. There are 6 such encoder layers stacked together.'}