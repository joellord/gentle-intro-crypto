Today, we’ll go back all the way to some of the first records of secret messages which date back all the way to Ancient Greece. In _“The Histories”_, _Herodotus_ chronicled the conflicts between _Persia and Greece in the fifth century BC_. According to Herodotus, this confrontation between freedom and slavery opposed the _independent Greece states and the oppressive Persians_.

_Xerxes_ was building a city at _Persepolis_, the new capital for his kingdom. Tributes and gifts arrived from all over the empire and neighboring states, with the notable exception of Athens and Sparta.
Xerxes was determined to avenge this insolence. He mobilized a force declaring that “_we shall extend the empire of Persia such that its boundaries will be God’s own sky, so the sun will not look down upon any land beyond the boundaries of what is our own_.
I guess megalomaniac country leaders are not just a modern thing…
So he spent five years to secretly assemble the greatest fighting force in history and in _480 BC, he was ready_ to launch his attack.

But one does not simply build a giant army without having some witnesses. _Demaratus_, a Greek who had been expelled from his homeland and who lived in the Persian city of Susa, still felt loyalty to Greece, despite being exiles.
So he decided to send a message to warn the _Spartans_.

Now he had to find a way to send the message without the Persians discovering it along the way. So instead of writing the message in the wax, as they would normally do, he scraped the wax and wrote the message on the wood underneath. He then covered the message with wax again.
When the message reached its destination, _Cleomene’ daughter Gorgo, wife of Leonidas_ divined and told the other to scrape the wax off. This was done, revealing the secret message.

Because they knew what was going to happen, the Spartians were able to ambush the Persians and ultimately won this battle.
_Demaratus simply hid the message_. Many other examples of hidden messages are described by Herodotus. Some of them involve shaving the head of a messenger, writing on his scalp and then waiting for the hair to grow back…  Wouldn’t be very efficient if I would be the messenger but I guess it worked in those days.

_If one of the guards would’ve also had a revelation_ and decided to look under the wax, his plans would’ve failed and the Greeks would’ve been defeated.

That’s where _cryptography comes into play_. Examples of encryption are found in many places. Encryption can be done as transposition. This is a _scytale_. It was known to be used by the _Spartans in 400 BC_. A strip of leather contained letters and when it was wrapped around this device, it would reveal the message.
It was _practical and very easy to use but also very easy to crack_.

This is where _encryption by substitution_ is practical. It’s also been used for quite a while but the form evolved through time.

But before we jump into this topic, let me introduce myself.

Intro

Agenda

Back to our topic…
The first documented use of substitution cipher for military purposes appears in _Julius Caesar’s Gallic Wars_. He describes how he sent messages to Cicero _substituting Roman letters with Greek letters_, making the message unintelligible to the enemy.
Caesar was known to use secret writings in a lot of his communications. His most famous cipher is often called the _Caesar shift cipher_.

Caesar Cipher

Vigenere Square

After the war, a lot of efforts were put on trying to find a way to secure communications. It was obvious that the outcomes of many battles during the first world war had been determined by how well secured the communications were.  It was also obvious that a lot of money could be made if you could solve this issue.
In _1918_, German inventor _Artur Scherbius_ came up with the idea of the Enigma machine.
This would let the _radio operators leave behind the manual encryption_ using a pen and paper and use a machine to make it easier.

https://www.polygon.com/2015/1/20/7861901/imitation-game-alan-turing-james-bond
If you are unfamiliar with Alan Turing’s story, I recommend watching the movie “The Imitation Game”.
Turing was fascinated by puzzles and the idea of finding a way to crack a machine that had 159 million million million possibilities was just so great. In order to do so, he had to build a machine based on _Rejewski’s design and Babbage ideas_. Unfortunately, the machine was simply _too slow_ to find the codes in a single day which made it useless.
But, thanks to some _repetitions and patterns_, he was actually able to decipher the messages.
 This was a dealbreaker and played a decisive role in the Allies victory of World War II.
Sadly, Turing was _arrested_ after it naively revealed that he was having a homosexual relationship to the police when he reported a burglary.
His security clearance was withdrawn by the British government and he suffured from severe depression.
He _commited suicide in 1954_, before anyone knew the contributions that he did to the world of cryptanalysis.

In the 1960’s with the apparition of computers as we know them now, and more specifically, the creation of the _ASCII codes_, appeared a new type of cryptography.  _Horst Feistel_, a German immigrant, recently moved in the US came up with an idea to encrypt data. After being shut down two times by the NSA he eventually moved to _IBM’s Watson laboratories_ where he was able to pursue his research without being harrassed.
It is there that he came with the _Lucifer encryption_ system.
First, the plain text message is tranlated into a long string of binary digits.
Then, the string is split in blocks on 64 digits.
The digits are split in two half blocks of 32.
The Right block is then put through a mangler function which arranges the digits according to a complex substution.
This is done again 16 times. Kinda like kneading some dough where you stretch it and fold it onto each other again and again.
The mangler function uses a key to encrypt the data in a unique way.
The opposite process is then executed to decrypt the message

_Meet Alice & Bob_
Alice sends a message to Bob in a secured suitcase with a padlock. This way, Eve cannot view the content. But Bob also can’t read the message.
So Alice needs to give the key to Bob somehow. Now if at any point Eve can get that key, she could read the message.
_Diffie and Hellman_ had this idea.
What if Alice sent the suitcase to Bob.  Then Bob would also add a padlock to it and ship it back to Alice. Alice can then remove her padlock, ship the suitcase to Bob who can finally open it. This was all done without ever sharing a key and Eve was never able to see the content of the suitcase.
This seemed like a step in the right direction but it still had a major flaw. Encryption was a first in last out (_FiLo_) algorithm. So in our example, we would encrypt the message with Alice’s padlock, then encrypt it with Bob’s, but we try to decrypt with Alice’s key before Bob’s. That is a problem.

_Diffie and Hellman_ were trying to find a _one-way function_ that could work to encrypt the data. A one-way function is a function that is easy to calculate in one direction but really hard to find in the other direction. They decided to look into modular mathematics. You know, that mod operator that we only use in fizzbuzz interview questions? Turns out it’s actually very practical in cryptology. Let’s take a simple function 3^x = y. If we know that y = 81, x is relatively easy to guess. If you try with x = 2, you get 9, so you know x > 2. Let’s try 6, we get 729. So we know that x < 6. So we can guess 4 and find the right answer.
Now if our function is a modular function, say 3^x mod 7 and we know that y = 4. If we guess 2, we get 9 mod 7 = 2. If we try a higher number like 6, we get 729 mod 7, which is 1. So you never get warmer or colder, you just have to guess numbers until you actually find one that matches. And if you use higher numbers, the probabilities become quite high!
In the _spring of 1976_, Diffie and Hellman came up with a _solution_.

First, Alice comes up with a secret number.
Bob also picks a secret number.
Then Alice and Bob agree on a secret one-way function
Because they’re shouting it, Eve can actually get ahold of this function.
Alice and Bob uses this function with their secret number.
Now they both share their results publicly
Eve can listen in, it doesn’t matter
Now if they use the other’s result with their secret, they will have the same key
Eve can spy as much as she wants over the public channel, she can’t make sense of those!

The paper caught the attention of _Ron Rivest_, a computer scientist at the MIT. He discussed it with his colleague _Leonard Adleman_ who professedly didn’t really care about it. He didn’t have a lot of interest in cryptography but was a very strong mathematician. They were later joined by another colleague, _Adi Shamir_, also from the MIT Laboratory for Computer Science. The dynamics of the trio were typically Rivest and Shamir coming up with ideas and Adleman tearing them apart.But one morning of April 1977, Rivest came up with an idea. When he shared with Adleman, he couldn’t find any faults in it. Rivest and Shamir continued elaborating on it and finally found the perfect math function for encryption. They published a joint paper. The paper was supposed to be by _Adleman, Rivest and Shamir_ as the convention usually goes but Adleman insisted that he didn’t have anything to do with the idea and asked to be put at the end. So the paper was published by Rivest, Shamir and Adleman… who later created the company RSA to hold the patent.

Here is how the function works (Appendix J, page 387)
First, Alice picks two large prime numbers. They should be very large, up to _10^150_ but let’s make our math easier and pick something smaller
She then multiplies those numbers to get N
Alice then publishes N and e somewhere
Now Bob wants to send a message to Alice. He’s secretly in love with Alice and wants to send her hugs and kisses.
Actually, let’s make that easier, and just send one kiss
We can convert this into an ASCII code
And then to it’s numerical decimal value for us humans to understand.
To encode the message, Bob will need to use the following mathematical function
Now Bob can shout the encoded message… 11
Eve doesn’t have the prime numbers so she can’t decrypt the message. Finding the prime numbers p and q would take massive computational power.
Alice, on the other hand, knows what to do with this message
First, she’ll need to find d such that
And to decrypt the message, she will use the following formular
