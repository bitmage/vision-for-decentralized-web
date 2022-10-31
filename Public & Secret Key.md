Public & Secret Keys are the foundation of all private storage, communications, and provable signatures.

There are two main types of cryptographic keys:  symmetric and asymmetric.

Public & Secret Key refers specifically to asymmetric keys.  These have the property that when data is encoded with the Public key, it can only be decoded with the Secret key, and when data is encoded with the Secret key, it can only be decoded with the Public Key.  This creates two different data flows like so:

```
some text -> secret_key -> asla3425hsfa00y -> public_key -> some text
other text -> public_key -> h03480hseglse4d -> secret_key -> other text
```

Typically we refer to encoding with the Secret key as "signing" and decoding with the Public key as "verification".  And encoding with the Public key is "encryption" and decoding with the Secret key is "decryption".  It's the same mathematical operation, just a different intention.

```
sign('some text', secret_key) -> 'asla3425hsfa00y'
verify('asla3425hsfa00y', public_key) -> some text

encrypt('other text', public_key) -> 'h03480hseglse4d'
decrypt('h03480hseglse4d', secret_key) -> 'other text'
```

Now typically a person does not reveal their Secret key to anyone else, but in contrast will publish their Public key to their website, their email signature, or other visible, discoverable places.

Why is that useful?  Well:

1. Using my Public key, anyone can send encrypted messages which only I can read.
2. Using my Secret key, I can sign a message, and anyone can use my Public key to verify that that message indeed originated from someone possessing my Secret key.

What can be built with that?  Glad you asked!

* [[Crypto Wallet]]
* [[User Keychain]]
* [[Device Constellation]]
* [[Self-Sovereign Identity]]

### Is anyone using this now?

Asymmetric keys have a long history of use, going back at least to the 70's when we had the invention of the [Diffie-Hellman key exchange](https://en.wikipedia.org/wiki/Diffie%E2%80%93Hellman_key_exchange) upon which the modern [SSH](https://en.wikipedia.org/wiki/Secure_Shell) and [TLS](https://en.wikipedia.org/wiki/Transport_Layer_Security) protocols are based.

Any time you visit a website in your browser where you see the little lock in the URL bar?  You are connecting over an encrypted channel.  The Diffie-Hellman key exchange was used to set up that channel, resulting in a shared symmetric key which can facilitate the conversation at high speeds without taxing the CPU of the involved computers.

Cryptocurrencies also rely upon a Public & Secret Key for creating a new wallet, and for "signing" transactions which result in a transfer of funds recorded on a [[Public Ledger]].

SSH is another common use.  IT professionals use it to connect to servers and transfer files or issue commands.  A lot of datacenter management is occuring through SSH connections.  It means we can access resources on the other side of the world safely, knowing that our connection would be difficult to compromise.

##### Can it be broken or hacked?

Both symmetric and assymetric cryptography was designed such that if a person uses an appropriate key length, brute force breaking the encryption would require massive computing resources.  But as computing technology continues to increase in power and decrease in price, the bar of what "safe" means gets pushed further out.  We employ newer algorithms and longer keys in order to keep our data safe.

Quantum computing also presents a threat to many algorithmic approaches.  As this technology becomes more available, it will be important to use algorithms that are resistant to quantum analysis.  Currently the elliptical curve cryptography (ECC) algorithms are believed to be quantum resistant, but it's very possible that 1) a new vulnerability will be published 2) that intelligence communities around the world have already found vulnerabilities and have simply not published that knowledge.

In any case, using encryption significantly increases the level of effort that an adversary would need to apply.  And it prevents blanket data trawling approaches, such as was [revealed by Edward Snowden](https://blokt.com/guides/edward-snowden-leaks).

If a person is using encrypted communication properly, the most likely reason for compromise at that point will be coming from another angle, such as when the secretary opens an email attachment ([[Phishing]]), or when someone pretending to be IT or maintenance is let in the building ([[Social Engineering]]), or when someone picks up a thumb-drive from the parking lot and plugs it into their computer, thinking they will do a good deed, discover the owner and hand it back to them (also [[Social Engineering]]).

If a person wants to be comprehensively secure, it is recommended to study [OPSEC](https://opsec101.org/).

##### Additional History and Context

The first computing devices were built to break the German Enigma codes, revealing the content of military communications.  This development is [credited as a major contributing factor to the allies winning World War II](https://www.iwm.org.uk/history/how-alan-turing-cracked-the-enigma-code).  The history of computers and cryptography are deeply interlinked, and it has long been understood by militaries and nations that the ability to communicate securely while (ideally) revealing the communications of adversaries is a crucial advantage.

For the same reasons, anyone who wishes to pursue life, liberty and happiness and avoid interference with these goals should consider the value of private communications.  There will always be those whose goals are in conflict with your own, and discretion and trust are foundations of an intact social contract.  Weaponization of information and taking information out of context have become the norm.

Businesses also understand this implicitly, and create strategies and policies for what information they will release and when.  Most businesses require that employees and business partners sign Non Disclosure Agreements precisely because they understand the damage that untimely information leakage can cause.  This goes for all businesses, regardless of whether they consider themselves as having "something to hide".  It's simply the precautionary principle in action.

### Implementations

There are more implementations than you can shake a stick at.

Some that may be useful for [[Password Manager]]:

* [[Holochain Research & Prototype]] contains a Public & Secret Key implementation, amongst many other things.  This is a "kitchen sink" which may be able to comprehensively address the [[Public Ledger]] portion of the architecture, but which may be less useful for the [[Private Data]] side of things.
* [[Ockam]] contains a Public & Secret Key implementation along with communication channel primitives, which look like they may be very useful for implementing [[Private Data]] and [[Private Communication]]

