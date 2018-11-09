Encryption and Authentication
https://www.ibm.com/support/knowledgecenter/SSFKSJ_7.1.0/com.ibm.mq.doc/sy10490_.htm
    * What is a three-way handshake?
    Three way handshake is the method used by TCP to set up a TCP/IP based connection
    over an Internet Protocol based network. The TCP handshaking mechanism is designed
    such that two computers attempting to communicate can negotiate the parameters of the
    network TCP socket connection before transmitting data. The 3-way handshake process
    is also designed so that both ends can initiate and negotiate separate TCP socket
    connections at the same time.

    Host A sends a TCP SYNchonize packet to Host B
    Host B receives A's SYN
    Host B sends a SYNchonize-ACKnowledgement
    Host A receives SYN-ACK
    Host A sends ACK
    Host B receives ACK
    TCP socket connection is established

    * How do cookies work?
    A cookie is a data packet attached to a web browser that maintains state and
    details about a session and user. They help with communication to a server,
    in particular for sites a user has already visited. This is how a user can,
    say, enter name/address/phone/etc. and have it repopulate after navigating
    elsewhere. The same data packets are often shared with data analytics firms.

    Cookies often contain more data than most people realize. Companies will
    often say they use cookies to deliver a better user experience and that’s
    true. But cookies also track an incredible amount of data about each user:
    their IP address, sites they visit, what items they look at, how long they
    spend on a page, etc. Some cookies will track a user’s behavior from site
    to site and not just within an organization’s own site, which is what a lot
    of privacy-minded people can’t stand.

    Cookies can be dangerous in a lot of different ways. What companies do with
    the data and how well they protect that data if they store it in a database.
    Malicious attacks by third parties using session hijacking. It’s your
    personal information that’s no longer in your control.

    One way to prevent browsers from tracking a user’s movement is to clear
    cookies. Digital Trends has a good tutorial about how to do that. Apple also
    recently released something called Intelligent Tracking Prevention within
    its Safari browser.


    * How do sessions work?
    Cookies and Sessions are ways to preserve the application's state between
    different requests the browser makes. It's thanks to them that, for instance,
    you don't need to log in every time you request a page on your bank page.

    COOKIES
    Cookies are small bits of data (usually max 4KB long), which hold data in a
    key=value pair (name=value; name2=value2)
    These are set either by the JavaScript or via the server using HTTP header.
    Cookies have an expiry datetime set, example using HTTP headers:
    Set-Cookie: name2=value2; Expires=Wed, 14 November 2018 10:00:00 GMT
    Cookies are considered highly insecure because the user can easily manipulate their
    content. That's why you should always validate cookie data. Don't assume what
    you get from a cookie is necessarily what you expect.
    Cookies are usually used to preserve login state, where a username and a special
    hash are sent from the browser, and the server checks them against the Databases
    to approve access. Cookies are also often used in sessions creation.

    SESSIONS
    Each user gets a session ID, which is sent back to the server for validation
    either by cookie or GET variable. Sessions are usually short lived, which makes
    them ideal for saving temporary state behavior in applications. Sessions also
    expire once the browser is closed.
    Sessions are considered more secure than cookies because the variables themselves
    are kept on the server. Here's how it works:
    1. Server opens a session (sets a cookie via HTTP header)
    2. Server sets a session variable
    3. Client changes page
    4. Client sends all cookies, along with the session ID from step 1
    5. Server reads session ID from cookie.
    6. Server matches session ID from a list in a database (memory)
    7. Server finds a match, reads variables which are now available on $_SESSION_$ superglobal.

    If Php does not find a match, it will start a new session and repeat steps 1-7.

    You can store sensitive information on a session because it is kept on the
    server, but be aware the session ID can still be stolen if the user, let's say,
    logged in over an insecure WiFi.(An attacker can sniff the cookie and set it
      as its own, he won't see the variables themselves, but the server will
      identify the attacker as the user.)


    * Explain how OAuth works.
    https://www.varonis.com/blog/what-is-oauth/

    * Symmetric vs Asymmetric encryption
    SYMMETRIC encryption is a conventional method of Encryption. It is also the
    simplest of two techniques. Symmetric encryption is executed by means of
    only one secret key known as ‘Symmetric Key’ that is possessed by both parties.
    This key is applied to encode and decode the information. The sender uses
    this key before sending the message and the receiver uses it to decipher
    the encoded message. This is a pretty straightforward technique and as a
    result, it doesn’t take much time. When it comes to transferring huge data,
    symmetrical keys are preferred.
    The most common form of symmetric encryption comes once an encrypted
    connection has been negotiated between a client and a server with an SSL
    certificate installed. Once the connection is negotiated, two 256-bit session
    keys are created and exchanged so that encrypted communication can occur.
    e.g. RC4, AES, DES, 3DES, QUAD, BLOWFISH


    Asymmetric Encryption is a relatively new and complex mode of Encryption.
    Complex because it incorporates two cryptographic keys to implement data security.
    These keys are called a Public Key and a Private Key. The Public key, as
    the name suggests, is available to everyone who wishes to send a message.
    On the other hand, the private key is kept at a secure place by the owner
    of the public key. The public key encrypts the information to be sent. It uses
    a specific algorithm in doing so. Whereas, the private key, which is in possession
    of the receiver, decrypts it. The Same algorithm is behind both these processes.
    e.g. RSA, DIFFIE-HELLMAN, ECC, EL GAMAL, DSA

    * What is a public key infrastructure flow and how would I diagram it?
    https://www.kyrio.com/blog/internet-of-things-security/public-key-infrastructure-explained/
    https://www.sslshopper.com/public-key-infrastructure-pki-overview.html


    * Describe the difference between symmetric and asymmetric encryption.

    https://crypto.stackexchange.com/questions/586/why-is-public-key-encryption-so-much-less-efficient-than-secret-key-encryption?noredirect=1&lq=1

    * Describe SSL handshake.
    The SSL or TLS handshake enables the SSL or TLS client and server to establish the secret keys with which they communicate.
    This section provides a summary of the steps that enable the SSL or TLS client and server to communicate with each other:
    1. Agree on the version of the protocol to use.
    2. Select cryptographic algorithms.
    3. Authenticate each other by exchanging and validating digital certificates.
    4. Use asymmetric encryption techniques to generate a shared secret key, which avoids the key distribution problem. SSL or TLS then uses the shared key for the symmetric encryption of messages, which is faster than asymmetric encryption.
    https://www.ibm.com/support/knowledgecenter/en/SSFKSJ_7.1.0/com.ibm.mq.doc/sy10660_.htm
    https://www.ibm.com/support/knowledgecenter/SSFKSJ_7.1.0/com.ibm.mq.doc/sy10670_.htm

    * How does HMAC work?
        * Why HMAC is designed in that way?
        Hash-based Message Authentication Code (HMAC) is a message authentication code that uses a cryptographic key in conjunction with a hash function.
        Hash-based message authentication code (HMAC) provides the server and the client each with a private key that is known only to that specific server and that specific client. The client creates a unique HMAC, or hash, per request to the server by hashing the request data  with the private keys and sending it as part of a request. What makes HMAC more secure than Message Authentication Code (MAC) is that the key and the message are hashed in separate steps.
        HMAC(key, msg) = H(mod1(key) || H(mod2(key) || msg))
        This ensures the process is not susceptible to extension attacks that add to the message and can cause elements of the key to be leaked as successive MACs are created.
        Once the server receives the request and regenerates its own unique HMAC, it compares the two HMACs. If they're equal, the client is trusted and the request is executed. This process is often called a secret handshake.
        https://www.quora.com/Hash-Functions-What-is-an-intuitive-explanation-of-the-HMAC-algorithm

    * What is the difference between authentication vs authorization name spaces?
    AUTHENTICATION is the process of verifying who you are. When you log on to a
    PC with a user name and password you are authenticating.
    AUTHORIZATION is the process of verifying that you have access to something.
    Gaining access to a resource (e.g. directory on a hard disk) because the permissions
    configured on it allow you access is authorization.

    * Explain how RSA works.
    https://www.geeksforgeeks.org/rsa-algorithm-cryptography/
    http://sergematovic.tripod.com/rsa1.html

    * Explain how Diffie-Hellman works.
    https://security.stackexchange.com/questions/45963/diffie-hellman-key-exchange-in-plain-english

    * What’s the difference between Diffie-Hellman and RSA?
    RSA and Diffie-Hellman are based on different but similar mathematical problems. While they both make use of modular exponentiation, exactly what they do/why they work is different. This is evident when you look at how to attack each one: RSA is threatened by integer factorization, while DH is threatened by discrete logarithms.
    Additionally: DH is a "key exchange" algorithm, which is different then "public key encryption"; It allows you and another person to mutually arrive at the same piece of information, while nobody else can. It is more or less equivalent to using public key encryption on a random message. This is in contrast to public key encryption, where you get to select the message that both parties will be aware of.

    Note that Diffie-Hellman can be turned into public key encryption (using ElGamal encryption).

    * How does Kerberos work?
    * If you're going to compress and encrypt a file, which do you do first and why?
    Neither:
    + Encrypting first and then compressing does not work.
    + Compressing first can leak information about plaintext content through
    the ciphertext length, as poncho mentioned in comments to another answer.

    Specifically, compression allows an attacker who can control parts of the
    message that is encrypted to reveal things about the other, secret parts,
    like cookies in the case of web traffic. It is most dangerous in a live protocol
    like TLS. Some forms of compression (e.g. truly constant bitrate lossy video/audio
    compression) may be immune to such attacks (but even then there might be side
    channel attacks due to the compression).

    In most cases you should just encrypt the uncompressed data and be done with it.
    Data storage and transmission is usually cheap enough. If you cannot live without
    compression, you must do it first, but then you have to really know what you are
    doing and likely accept at least some loss of security.

    * Encoding vs Encryption vs Hashing vs Obfuscation

    The purpose of ENCODING is to transform data so that it can be properly consumed
    by a different type of system (e.g. binary data being sent over email, or viewing
    special characters on a web page). The goal is not to keep the information secret,
    but rather to ensure that it's able to be properly consumed.
    Encoding transforms data into another format using a scheme that is publicly available
    so that is can easily be reversed. It does not require a key as the only thing
    required to decode it is the algorithm that was used to encode it.
    e.g. ASCII, UNICODE, URL ENCODING, BASE64

    The purpose of ENCRYPTION is to transform data in order to keep it secret from others,
    e.g. sending a password over the internet. Rather than focusing on usability, the goal
    is to ensure the data cannot be consumed by anyone other that the intended receiver.
    Encryption transforms data into another format in such a way that only specific individual
    can reverse the transformation. It uses a key, which is kept secret, in conjunction with the
    plaintext and an algorithm, in order to perform the encryption operation. As such,
    the ciphertext, the algorithm and the key are all required to return the plaintext.
    e.g. AES, BLOWFISH, RSA

    HASHING serves the purpose of  ensuring integrity, making it so that if something
    is changed you can know that it's changed. Technically, hashing takes arbitrary
    input and produce a fixed-length string that has the following attributes:
    1. the same input will always produce the same output
    2. multiple disparate inputs should not produce the same output
    3. it should not be possible to go from the output to the input
    4. any modification of the given inputs should result in drastic changes
    in the hash
    Hashing is used in conjunction with authentication to produce strong evidence that
    a given message has not been modified. This is accomplished by taking a given input,
    hashing it, and then signing the hash with the sender's private key.
    When the recipient opens the message, they can then validate the signature of the
    hash with the sender's public key and then hash the message themselves and
    compare it to the hash that was signed by the sender. If they match it is an
    unmodified message, sent by the correct person.
    e.g. SHA-3, MD5 (now obsolete)

    The purpose of OBFUSCATION is to make something harder to understand, usually
    for the purpose of making it more difficult to attack or copy. One common use
    is the obfuscation of source code so that it's harder to replicate a given
    product if it is reversed engineered. Obfuscation is not a strong control,
    but rather an obstacle.
    e.g. JavaScript obfuscation, PROGUARD


    * What is the difference between 128 and 256?
    To understand these encryption standards (128 vs 256), it’s a good idea to start with an explanation of the underlying matter of encryption. Concepts like DES (Data Encryption Standard) and AES (Advanced Encryption Standard). A good video tutorial can be found here.
    TLDR: The number refers to the length of the encryption key. DES is where we started with 56-bit encryption, computer power became cheap enough to brute force that and the industry moved on to 128.
    So is 128-bit encryption twice as good as 56-bit encryption? Actually, it’s far better: 2 to the 56th power compared with 2 to the 128th power.
    Using that logic, 256 results in an exponentially-larger number of potential keys an attacker would need to try while brute forcing your encrypted data.
    So is 256 is preferable? It depends on a lot of factors. In short, not really.
    A security engineer published a detailed explanation in which it would take about 1.3 * 10¹² * the age of the universe to check all the keys of a 128-bit encrypted data set. There’s even a StackExchange thread about how much money is would cost to crack a 256-bit password in one calendar year.
    The main arguments I’ve read against 256-bit encryption involve computation speed and overheard compared with the basic level of security already baked into 128. AgileBits (maker of 1Password) published good documentation about why they moved to 256-bit encryption. They started at 128 because of minimum hardware requirements with iPhones, then moved to 256 because… people felt safer knowing that. The article goes into a lot of depth about why 256 isn’t necessarily safer than 128. So technically there wasn’t a reason to do it.

    * How do I authenticate you and know you sent the message?
    * Should you encrypt all data at rest?

Network Level
    * What are common ports involving security, what are the risks and mitigations?
    * How does DNS work?
    * Which one for DNS?
        * AH
        * ESP
    * Describe HTTPs and how it is used.
    * What is the difference between HTTPS and SSL?
    * How does threat modeling work?
    * What is a subnet and how is it useful in security?
    * What is subnet mask?
    * Explain what traceroute is.
    * Explain how ping works.
    * Draw a network, then expect them to raise an issue and have to figure out where it happened.
    * Write out a Cisco ASA firewall configuration on the white board to allow three networks unfiltered access, 12 networks limited access to different resources on different networks, and 8 networks to be blocked altogether.
    * Explain TCP/IP concepts.
    * What is OSI model?
    * How does a router differ from a switch?
    * Describe the Risk Management Framework process and a project where you successfully implemented compliance with RMF.
    * How does a packet travel between two hosts connected in same network?
    * Explain the difference between TCP and UDP.
        * Which is more secure?
        * Why?
        * What is the TCP three way handshake?
    * What is the difference between IPSEC Phase 1 and Phase 2?
    * What are biggest AWS security vulnerabilities?
    * How do web certificates for HTTPS work?
    * What is the purpose of TLS?
    * Is ARP UDP or TCP?
    * Explain what information is added to a packet at each stop of the 7 layer OSI model.
    * Walk through a whiteboard scenario for your environment of choice (Win/Linux) in which compromising the network is the goal without use of social engineering techniques (phishing for credential harvesting, etc).
    * Explain how you would build a web site that could secure communications between a client and a server and allow an authorized user to read the communications securely.
    * How does an active directory work?
        * Do you know how Single Sign-On works?
    * What is a firewall?
        * How does it work?
        * How does it work in cloud computing?
        * Difference between IPS and IDS?
    * How do you build a tool to protect the entire Apple infra?
    * How do you harden a system?
    * How to you elevate permissions?

OWASP Top 10
    * Differentiate XSS from CSRF.
    * What do you do if a user brings you a pc that is acting 'weird'? You suspect malware.
    * What is the difference between tcp dump and FWmonitor
    * Do you know what XXE is?
    * Explain man-in-the-middle attacks

Databases
    * How would you secure a Mongo database?
    * Postgres?
    * Our DB was stolen/exfiltrated. It was secured with one round of sha256 with a static salt.
        * What do we do now?
        * Are we at risk?
        * What do we change?
    * What are the 6 aggregate functions of SQL?

Tools and Games
    * Have I played CTF?
    * How would you decrypt a steganography image?
    * You're given an ip-based phone and asked me to decrypt the message in the phone.
    * What CND tools do you knowledge or experience with?
    * What is the difference between nmap -ss and nmap -st?
    * How would you filter xyz in Wireshark?
    * Given a sample packet capture - Identify the protocol, the traffic, and the likelihood of malicious intent.
    * If left alone in office with access to a computer, how would you exploit it?
    * How do you fingerprint an iPhone like Uber did so you can monitor it even after wiping it?

Programming
    * Code review a project and look for the vulnerability.
    * How would you conduct a security code review?
    * How can Github webhooks be used in a malicious way?
    * If I hand you a repo of source code to security audit what’s the first few things you would do?
    * Can I write a tool that would search our Github repos for secrets, keys, etc.?
        * Slack?
            * https://arstechnica.com/security/2016/04/hacking-slack-accounts-as-easy-as-searching-github/
        * AWS?
        * Etc.
