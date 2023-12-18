One way to turn text into vectors using [one-hot encoding](../Feature%20Engineering/One%20Hot%20Encoding.md)

> [!warning]
> This is a bad approach

Max encoded whole *sentences* as vectors, not individual words
- If a word appears twice, put a 2 in its column rather than 1

Produces very sparse vectors

> [!note]
> Max also refers to this as the "unigram" approach. Not sure if "unigram" approach will refer to bag-of-words specifically on the exam

Problem: Bag of words loses information about ordering of words within sentence
- Partial solution: Use bigrams to keep some of the order
- Now "School has homework" and "Homework has school" no longer the same vector
- But now dimensionality is way bigger
	- Some people use trigrams, but no one uses anything past that because too much memory required

