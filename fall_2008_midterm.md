# Fall 2008 Midterm

## 1
(10 points) The web site I mentioned that describes how to build a Geiger counter-based random number generator contains the following text:

"If you don’t know what you’re doing, radioactive material of any kind is better left strictly alone. I am not encouraging you to fool around with hot stuff-especially when there’s no need to, since you can get all the random bits you need from the Fourmilab generator."

Why do I disagree with this advice? (Note 1: you do not need any other material from that site to answer this question, so don’t regret not printing it out. Note 2: if you think you need knowledge of physics to answer it, your answer is wrong.)

> You don’t know if the operator of that site is competent or honest. What if the numbers really aren’t random? Maybe he’s using a pseudo-random number generator. Maybe his hardware
generator isn’t working properly. Maybe he’s making a copy of the random numbers he’s handing out. Maybe someone has hacked his site and is making a copy.

## 2
(15 points) You are designing a computer security procedure for laptops for a top secret intelligence agency. Someone proposes the following scheme. The files on the laptop’s disk drive are encrypted. The only copy of the key is on the employee’s badge, encrypted with the employee’s fingerprint. To log in, the employee must insert the badge into the computer and supply a fingerprint. Then and only then will the files be decrypted.

There are several things wrong with this idea. Name at least two.

> If the badge is lost, so is the data. If the employee dies, the data is lost. It’s hard toget a key from a fingerprint or other biometric. Badges tend to travel with people; there’s no security
redundancy against, say, an armed enemy — remember that we’re talking about intelligence agencies.



