# Topic Modeling

The process of learning, recognizing, and extracting these topics across a collection of documents is called topic modeling.

All topic models are based on the same basic assumption:

1.each document consists of a mixture of topics, and
  
2.each topic consists of a collection of words.

We are going to discuss about two Topic modeling techniques :

1. LSA(Latent Semantic Analysis)

2. LDA(Latent Dirichlet Allocation)


## -->> LSA 
The main idea is to take a matrix of documents and terms we have and decompose it into a separate document-topic matrix and a topic-term matrix.
The first step is generating document-term matrix. Given m documents and n words in our vocabulary, we can construct an m × n matrix A in which each row represents a document and each column represents a word.

We then fill document-term matrix with a tf-idf score. Tf-idf, or term frequency-inverse document frequency where the more frequently the term appears in the document, the lesser its weight and importance, and the more infrequently it appears across the corpus, the greater its weight and importance.

 Matrix A is very sparse and has many dimensions. So we want to perform dimensionality reduction on A. Dimensionality reduction can be performed using truncated SVD. SVD, or singular value decomposition, is a technique in linear algebra that factorizes any matrix M into the product of 3 separate matrices: 
                         
                         --->>M=U*S*V, 
where S is a diagonal matrix of the singular values of M.

As a result of SVD we get ,  U is our document-topic matrix, and V is our term-topic matrix. In both U and V, the columns correspond to one of our t topics. In U, rows represent document vectors expressed in terms of topics; in V, rows represent term vectors expressed in terms of topics.

With these document vectors and term vectors, we can now easily apply measures such as cosine similarity to evaluate:

1.the similarity of different documents

2.the similarity of different words
