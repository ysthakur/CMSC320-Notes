**Term Frequency:** How many times a word appears in a specific document
**Document Frequency:** How many documents a word appears in

Motivation: We want to downweight words with a high document frequency, because words that are very common are not as useful to us

- For topic modeling, if only two books have the word "dragon," that's probably an important word for determining the genre
- On the other hand, every book has the word "they," so it doesn't give you much information about the book's genre

So we weight words using **TF-IDF**:
- TF-IDF is term frequency times inverse document frequency
- IDF (inverse document frequency) is *logarithm* of 1/(document frequency)
	- Logarithm because you want the extremes to be the same (don't care if a word appears in 100 documents or 110 documents, both are bad)
