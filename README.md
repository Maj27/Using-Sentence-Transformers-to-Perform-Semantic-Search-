# Using-Sentence-Transformers-to-Perform-Semantic-Search-

I am showing here how Sentence Transformers can be used to perform semantic search. I have created a small corpus with example sentences of descriptions of top 20 startups in Canada taken from https://www.foundersbeta.com/tech-companies/20-tech-companies-to-watch-for-in-2021/  website to demonstrate how this could work.
I search for 3 queries (included in the notebook) and found the similarity using two methods (cosine similarity using the semantic search in sentence transformers and FAISS by Facebook).


Sentence Transformers Framework provides an easy method to compute dense vector representations of
document, sentences and images. There are many versions of Sentence Transformers that fine-tune various pretrained models such as BERT, RoBERTa and smaller versions like distill-BERT and distill-Roberta. A well known model on our platform is
sentence-transformers/paraphrase-multilingual-MiniLM-L12-v2 that maps sentences &
paragraphs to a 384 dimensional dense vector space. You can also fine-tune these using your
own data. You should generate embeddings for all of your items that you have in the inventory.

You can then encode your search query using the same model and find the similarity between
the generated vector against the pre-constructed vectors. To do this you can use Faiss, a library developed by Facebook AI Research for efficient similarity search of dense vectors. If you are concerned about the linearity cost of the retrieval and if you have a
huge database to search, Faiss also provides fast indexes too but you will need to index your
catalog first. With Faiss, you can even scale up to huge vector space using GPU and you don't
need to have everything in RAM.
