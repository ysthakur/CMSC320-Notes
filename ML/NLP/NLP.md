# Natural Language Processing

Natural language is not as structured as tabular data, but it's more structured than images

Vocab:
- Document: A collection of words
- Corpus: A collection of documents

## Topic Modeling

[Topic Modeling](Topic%20Modeling.md)


## Turning Text Into Vectors

Ways to encode words or sentences as vectors:
- [Bag of Words](Bag%20of%20Words.md)

## Preprocessing

[Preprocessing (NLP)](Preprocessing%20(NLP).md)

## Similarity

Can't use Euclidean distance because:
- Suppose you're doing topic modeling, and one book has the word "dragon" 10 times and another has the word "dragon" 100 times
	- They are both probably the same genre (fantasy), but their Euclidean distance says they're far apart

Solution: Use **cosine similarity**
- Cosine similarity is the cosine of the angle between the two vectors

## Term Frequency

**Term Frequency:** How many times a word appears in a specific document
**Document Frequency:** How many documents a word appears in

We want to downweight words with a high document frequncy, because words that are very common are not as useful to us
- For topic modeling, if only two books have the word "dragon," that's probably an important word for determining the genre
- On the other hand, every book has the word "they," so it doesn't give you much information about the book's genre

So we weight words using **TF-IDF**:
- TF-IDF is term frequency times inverse document frequency
- IDF (inverse document frequency) is *logarithm* of 1/(document frequency)
	- Logarithm because you want the extremes to be the same (don't care if a word appears in 100 documents or 110 documents, both are bad)