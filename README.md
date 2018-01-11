# Meltdown Proof-of-Concept - look closely

We have added one more test to the [PoC from the authors of the meltdown-paper](https://github.com/IAIK/meltdown):

The secret.c from Demo #4, the program which gets attackt in the offical PoC, has code in it which leads to the illusion that this would work on any machine in any case. This works by reading the attacked memory endless in a loop, and running a call for changing thread scheduling, [sched_yield](http://man7.org/linux/man-pages/man2/sched_yield.2.html). We believe this is not a real-world scenarion, but very relevant for getting the data to be attacked into the cache, which seems to be an precondition to let meltdown work.

In our tests, the attack do not work anymore if you remove this</b> - what should not be the case if the meltdown-paper would be exhaustive.

![Diffs](https://meltdown-core-catcher.com/diff.png)

In our tests this makes the PoC completly unusable - what should not be the case if the meltdown-paper would be exhaustive.

You can help if you try the official PoC from the paper writer, and our modified version which removes the endless fetching of the target data into the memory, which gives the illusion that this would work on any machine in any case.

See: [Realworld testing meltdown](https://meltdown-core-catcher.com/testing.html)
