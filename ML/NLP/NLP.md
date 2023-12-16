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
- We use cosine rather than the angle itself because cosine is positive in the 1st and 4th quadrants and is in a convenient range, $[-1, 1]$
- Euclidean distance is not in the range $[-1, 1]$, it's in units that don't mean anything
	- The Euclidean distance between two vectors produced by one encoder can't be compared to another encoder's vectors' distance, because different units

## TF-IDF

Can represent each word using its [TF-IDF](TF-IDF.md) (term frequency-inverse document frequency)
