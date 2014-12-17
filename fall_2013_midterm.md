# Fall 2013 Midterm

1. Because of the hassles of installing cryptographic software that works everywhere, some secure email
web sites (e.g., hushmail.com) offer “downloadable crypto”: a web page with Java or Javascript that implements the necessary functions to send and receive secure email. There’s a serious risk, though: you don’t know what you’re executing. Is it the real crypto code, or does it have a back door installed by the provider because the government ordered them to?

    (a) (10 points) To avoid this problem, a new site decides to offer digitally-signed crypto. That is, the
code they send your browser will be digitally signed and will be accompanied by a certificate. This does not solve the problem. Explain why it fails. (Assume that the browser is in fact capable of verifying such signatures. This question is about security architecture, not implementation
limitations.)

    (b) (10 points) Design a better scheme that in principle can work. (Again, ignore the question of what
browsers can or cannot do.)

2. (20 points) The MTA wants to replace the Metrocard used to pay subway and bus fares in New York. Suppose that someone suggested using iris scans: when you board a bus or enter a turnstile, something scans your eye and deducts the appropriate fare from your account. Is this a good architecture or not?
Explain.



3. Suppose I want to build an online exam server: students take the exam via their own web browsers on their own computers. Also assume that for some reason I’m not worried about students collaborating via their computers; consider only the questions I’m explicitly asking.

    (a) (10 points) What sort of authentication should be used? Justify your choice.
    
    > Any solution has to rely on existing hardware. It’s not possible to use biometrics or smart card readers, since (a) most students’ computers don’t have such things, and (b) remote, unobserved biometrics aren’t a good idea. This means we’re back to passwords, client side certificates, or some form of two-factor authentication. This could be done with client-side software or with a hardware token (If you specify this latter, you need to state this explicity.)
Note that this isn’t the weak link: the risk is someone else taking the exam with the cooperation of the student who should take it; such a student could share any necessary authentication details.

    (b) (5 points) Discuss other sorts of programming precautions you should take in building the server.
    
    > Apart from the usual, the big risk here is someone seeing another student’s answers. The best solution is to encrypt all answers in the instructor’s public key.

    > The usual attacks, such as bad input values and buffer overflows, must be considered.

4. (20 points) There’s a new multiplayer game out that runs on distributed systems that share a file system, e.g., something like the CLIC Lab. There several different roles here:

    * The game company, which is constantly adding new features to the already-installed game
    * The local game administrator
    * The game itself, with secret files, score files, etc.
    * Many individual players; new ones can join at any time
plus of course the site’s usual system administrators. Describe the access control and permission architecture
you would use.
    
> If you use message-passing, the game should run as its own service with its own user id, to prevent hacks from affecting anyone else. If you use setuid, it should have its userid and groupid; per below, the game is probably best run setgid, not setuid.

> All score files should be writable only by this group. Depending on the game needs, score files may be restricted to being readable only by that group. The game administrator needs to have the ability to overwrite the game program, and probably to modify the score files and other administrative files. This suggests that the administrator should be in the game’s group and in the group that owns the programs; those in turn should be group-writable.

> If there are some resources accessible only by players, either all players can be in a some group, or there should be some game program—setgid to the game’s group—that reads those resources. There are three ways to handle updates to the game. 

> First, the game can auto-install those. Second,
the game administrator can download them and manually install them. Third, the game company can do it directly. In the first two cases, the updates should be digitally signed. In the third situation, the game company should be in the appropriate group to overwrite those files.