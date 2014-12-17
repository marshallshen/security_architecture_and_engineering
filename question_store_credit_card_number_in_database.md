# Question: store credit card number in database?

> I want to allow my customer users to enter their credit card information so that I can charge them every month. I wonder how one should save this information?

> Should it be saved in the MySQL database ("user" table) or is this kind of information too sensitive and need to be stored in another place?
 I have no experience of this and would be glad if someone could advice me how to accomplish this.


As mentioned above, do not store credit card information in a database. It's a recipe for trouble. Doing so will make you a very attractive target for hackers and, if they are successful in retrieving them, end your business and potentially ruin your life as well as the lives of those whose credit card numbers are stolen.

Having said that here are three things to consider:

1) Your best bet is to use a payment processor/payment gateway that offers recurring billing. An example of this is [Authorize.Net's Automated Recurring Billing][1] service. Once you set up the subscription they will automatically bill the user every month for you automatically and let you know the results of the transaction. It saves you a ton of work and relieves you of the liability of storing credit card information.

2) If you do store store credit card numbers you must follow [PCI guidelines][2]. These guidelines are set by the payment card industry and define what you can and cannot do. It also defines how credit card information must be stored. You will need to encrypt the credit card numbers and you should, but are not required to, encrypt related information (expiration date, etc). You will also be required for ensuring that your web server and network are secure. Failing to meet PCI compliance will result in losing your merchant account and being banned from having a true merchant account forever. That would limit you to using third party processors which are less flexible. Keep in mind that PCI guidelines are a good start but hardly a "how to" when it comes to online security. Your goal would be to exceed the recommendation (by a lot).

3) States laws supersede PCI compliance. If you suffer a breach and credit card numbers are stolen you risk criminal prosecution. The laws vary from state to state and are constantly in flux as lawmakers are only just beginning to realize how serious of a matter this is.

As far as encryption goes make sure you read up on which encryption algorithms are secure and have not been broken yet. [Blowfish][3] is a good start and if you use PHP the [mcrypt library][4] is recommended ([example][5]).


  [1]: http://www.authorize.net/solutions/merchantsolutions/merchantservices/automatedrecurringbilling/
  [2]: https://www.pcisecuritystandards.org/index.shtml
  [3]: http://en.wikipedia.org/wiki/Blowfish_%28cipher%29
  [4]: http://us3.php.net/manual/en/book.mcrypt.php
  [5]: http://stackoverflow.com/questions/2448256/php-mcrypt-encrypting-decrypting-file/2448441#2448441