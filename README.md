# Meltdown Proof-of-Concept - look closely

We have added one more test to the PoC from the authors of the meltdown-paper: The same secret.c but with removed endless fetching of the target data into the memory: 

![Diffs](https://meltdown-core-catcher.com/diff.png)

In our tests this makes the PoC completly unusable - what should not be the case if the meltdown-paper would be exhaustive.

You can help if you try the official PoC from the paper writer, and our modified version which removes the endless fetching of the target data into the memory, which gives the illusion that this would work on any machine in any case.

See: [Realworld testing meltdown](https://meltdown-core-catcher.com/testing.html)
