# How do I use DNSChain?

__Table of Contents__

- [Using DNSChain](<#Using>)
- [Supported blockchains](<#Blockchains>)
- [Free public DNSChain servers](<#Servers>)
- [Registering blockchain domains and identities](<#Registering>)

<a name="Using"></a>
#### Using DNSChain

Use DNSChain to securely access blockchain data over HTTPS and (eventually) DNS, over a [Man-in-the-Middle Proof channel](What-is-it.md#MITMProof) to the DNSChain server (or _servers_) you trust. Remember, if you don't have access to a trustworthy DNSChain server, you should query several of them and verify that their answers match.

__Over HTTPS__

For demo purposes, we run a public DNSChain server (but you should run your own so that you don't have to trust ours!).

You can query it using [a RESTful API](What-is-it.md#API):

Query: _What's the SSL fingerprint for server at api.dnschain.net?_

- [http://api.dnschain.net/v1/dnschain/fingerprint](http://api.dnschain.net/v1/dnschain/fingerprint)

Query: _What is the GPG key for `id/example` in Namecoin?_

- [https://api.dnschain.net/v1/namecoin/key/id%2Fexample](https://api.dnschain.net/v1/namecoin/key/id%2Fexample)

Query: _What is the IP address of `example.bit`?_

- [https://api.dnschain.net/v1/namecoin/key/d%2Fexample](https://api.dnschain.net/v1/namecoin/key/d%2Fexample)

This means you can immediately begin [writing apps](Developers.md#securing-your-apps-with-dnschain) that query the blockchain over a MITM-proof channel.

| **:exclamation:** To [MITM-proof](What-is-it.md#MITMProof) these queries, you **must** verify the TLS fingerprint of the DNSChain server! |
|-------------------------------------------------------------------------------------------------------------------------------------------|

__Over DNS__

Using a DNSChain server for DNS gives you access to [blockchain TLDs](<#Blockchains>) like `.bit`. Unlike regular TLDs, access to blockchain TLDs can be done in a manner that is MITM-proof. This is the end-goal that the DNSChain project is building towards.

Try it out by changing your DNS to [one of the public DNSChain servers](<#Servers>). You should then be able to visit `.bit` domains.

Remember that the DNS server you use knows what websites you're visiting and can be used to MITM attack you, so either run your own server or use one that you trust.

<a name="Blockchains"/></a>
#### Supported blockchains

| Blockchain |  TLD   | Name used in RESTful API |
|------------|--------|--------------------------|
| Namecoin   | `.bit` | `namecoin`               |
| KeyID      | `.p2p` | `keyid`                  |
| NXT        | `.nxt` | `nxt`                    |

_Ethereum support is planned as `.eth` and `ethereum`._

__Relevant Specifications__

- Namecoin: [Specifying DNS data for domains](https://wiki.namecoin.info/index.php?title=Domain_Name_Specification)
- Openname: [Profile and RESTful resolver specifications](https://github.com/openname/openname-specifications)

<a name="Servers"/></a>
#### Free public DNSChain servers

*DNSChain is meant to be run by individuals!*

Yes, you can use a public DNSChain server, but it's far better to use your own because it gives you more privacy, makes you more resistant to censorship, and provides you with a stronger guarantee that the responses you get haven't been tampered with by a malicious server.

If you cannot run your own, you should do one or more of the following:

- Use a server that you have __good__ reason to trust (a close friend's).
- Use multiple servers that are independently run and verify that the responses you get from them all match. The more servers you query, the more likely it is the answer is accurate. Note that this only applies to using the [RESTful API](What-is-it.md#API), _not DNS._

Here are some public servers. You can [set your computer's DNS settings](https://startpage.com/do/search?q=how+to+change+DNS+settings) to one of these. Note that some of the servers must be used with [DNSCrypt](https://github.com/jedisct1/dnscrypt-proxy).

|                          IP or DNSCrypt provider                           |        [DNSCrypt](http://dnscrypt.org/) Supported?         | Logs |    Location    |                          Owner                          |     Notes      |
|----------------------------------------------------------------------------|------------------------------------------------------------|------|----------------|---------------------------------------------------------|----------------|
| 192.184.93.146 (aka [okturtles.org](https://okturtles.com))                | N/A                                                        | No   | Atlanta, GA    | [@taoeffect](https://twitter.com/taoeffect)             |                |
| 54.85.5.167 (aka [name.thwg.org](name.thwg.org))                           | N/A                                                        | No   | USA            | [id/wozz](https://api.dnschain.net/id/wozz)             |                |
| [2.dnscrypt-cert.okturtles.com](https://gist.github.com/taoeffect/8855230) | [Required Info](https://gist.github.com/taoeffect/8855230) | No   | Atlanta, GA    | [@taoeffect](https://twitter.com/taoeffect)             |                |
| [2.dnscrypt-cert.soltysiak.com](http://dc1.soltysiak.com)                  | [Required Info](http://dc1.soltysiak.com)                  | No   | Poznan, Poland | [@maciejsoltysiak](https://twitter.com/maciejsoltysiak) | IPv6 available |

Tell us about yours by opening an issue (or any other means) and we'll list it here!

Responses can be sured over HTTPS by pinning SSL certificates, and over DNS by using DNSCrypt.

<a name="Registering"/></a>
#### Registering blockchain domains and identities

[:book: Registering blockchain domains and identities](dot-bit-Domains-and-Identities.md)

You can register and use `.bit` domain names from Namecoin, and there are more blockchain based domains coming soon. Read about and secure your digital identity also, and access it using DNSChain.
