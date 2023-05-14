# HINT

[Password-protect URLs using AES in the
browser.](https://mikrodinet.github.io/hint)

Link Lock now supports secure, hidden bookmarks via bookmark knocking! Read
more [here](https://mikrodinet.github.io/hint/hidden-bookmarks).



## About

Link Lock is a tool for encrypting and decrypting URLs. When a user visits an
encrypted URL, they will be prompted for a password. If the password is
correct, Link Lock retrieves the original URL and then redirects there.
Otherwise, an error is displayed. Users can also add hints to display near the
password prompt.

Each encrypted URL is stored entirely within the link generated by the
application. As a result, users control all the data they create with Link
Lock. Nothing is ever stored on a server, and there are no cookies, tracking,
or signups.

Link Lock has many uses:

- Store private bookmarks on a shared computer
- Encrypt entire web pages (via [URL
  Pages](https://github.com/wahyu9kdl/))
- Send sensitive links over public or insecure channels (e.g., posting links
  to a public website that require a password to access)
- Implement simple CAPTCHAs – particularly effective against basic web scrapers
  that do not respect `robots.txt`
- Add a password to shared Dropbox or Google Drive links
- Share password-protected magnet links and torrents
- [Evade censorship](#evading-censorship)

Link Lock uses AES in GCM mode to securely encrypt passwords, and PBKDF2 and
salted SHA-256 (100,000 iterations) for secure key derivation. Encryption,
decryption, and key derivation are all performed by the [`SubtleCrypto`
API](https://developer.mozilla.org/en-US/docs/Web/API/SubtleCrypto). The
initialization vector is randomized by default, but the salt is not.
Randomization of both the initialization vector and salt can be enabled or
disabled by the user via "advanced options." The salt and initialization vector
are sent with the encrypted data if they are randomly generated. The API is
versioned such that old encrypted links will always work, even if later
versions of Link Lock are updated to be more secure. Please read the code
([`api.js`](https://github.com/mikrodinet/hint/blob/main/api.js) in
particular) for more information.

Read the Hacker News discussion [here](https://wahyu9kdl.github.io/).

# Instalation

 Clone HTTP/HTTPS
 ```
https://github.com/mikrodinet/hint.git
```
 Clone GitHub CLI
 ```
gh repo clone mikrodinet/hint
```
 LIVE PAGE 
 ```
https://mikrodinet.github.io/hint/create/
```
 EXAMPLE 
 Link Excample
 ```
https://mikrodinet.github.io/hint
```
 hint (optional)
 ```
admin alhikmah 🎨🖥🛡♥️ password: alhikmah
```
 password
 ```
alhikmah
```
Link Live
 ```
https://mikrodinet.github.io/hint/#eyJ2IjoiMC4wLjEiLCJlIjoiL2RLTGZyOUIzRit6RmQwU1RxQ2dCVk1YeWlWWU4zMTZVZjlTTTkrVFVxeDdkOVdqQm1SN1E0WUFHTjUyIiwiaCI6ImFkbWluIGFsaGlrbWFoIPCfjqjwn5al8J+boeKZpe+4jyBwYXNzd29yZDogYWxoaWttYWgiLCJzIjoiSEk2Qkhzc3ZMTDcrUXZ6dE95YTdsdz09IiwiaSI6ImdSVHg1cnM0a2IxRG5JQ20ifQ==
```
 
 # macOS

Architecture x64

- Download

```
# Create a folder
$ mkdir actions-runner && cd actions-runner# Download the latest runner package
$ curl -o actions-runner-osx-x64-2.291.1.tar.gz -L https://github.com/actions/runner/releases/download/v2.291.1/actions-runner-osx-x64-2.291.1.tar.gz# Optional: Validate the hash
$ echo "1ed51d6f35af946e97bb1e10f1272197ded20dd55186ae463563cd2f58f476dc  actions-runner-osx-x64-2.291.1.tar.gz" | shasum -a 256 -c# Extract the installer
$ tar xzf ./actions-runner-osx-x64-2.291.1.tar.gz
```

- Configure

```
# Create the runner and start the configuration experience
$ ./config.sh --url https://github.com/mikrodinet/hint --token AUB55YBFCW7GBJLQAOMT7G3CTBEWE# Last step, run it!
$ ./run.sh
```

- Using your self-hosted runner

```
# Use this YAML in your workflow file for each job
runs-on: self-hosted
```

For additional details about configuring, running, or shutting down the runner, please check out our product docs.


#  Windows

Architecture x64

- Download 

We recommend configuring the runner under "\actions-runner". This will help avoid issues related to service identity folder permissions and long path restrictions on Windows.


```
# Create a folder under the drive root
$ mkdir actions-runner; cd actions-runner# Download the latest runner package
$ Invoke-WebRequest -Uri https://github.com/actions/runner/releases/download/v2.291.1/actions-runner-win-x64-2.291.1.zip -OutFile actions-runner-win-x64-2.291.1.zip# Optional: Validate the hash
$ if((Get-FileHash -Path actions-runner-win-x64-2.291.1.zip -Algorithm SHA256).Hash.ToUpper() -ne '2a504f852b0ab0362d08a36a84984753c2ac159ef17e5d1cd93f661ecd367cbd'.ToUpper()){ throw 'Computed checksum did not match' }# Extract the installer
$ Add-Type -AssemblyName System.IO.Compression.FileSystem ; [System.IO.Compression.ZipFile]::ExtractToDirectory("$PWD/actions-runner-win-x64-2.291.1.zip", "$PWD")
```

- Configure

```
# Create the runner and start the configuration experience
$ ./config.cmd --url https://github.com/mikrodinet/hint --token AUB55YDZ2E6RMNHZ4MG4FTDCTBENE# Run it!
$ ./run.cmd
```

- Using your self-hosted runner

```
# Use this YAML in your workflow file for each job
runs-on: self-hosted
```


For additional details about configuring, running, or shutting down the runner, please check out our product docs.


# Linux

Architecture x64

- Download

```
# Create a folder
$ mkdir actions-runner && cd actions-runner# Download the latest runner package
$ curl -o actions-runner-linux-x64-2.291.1.tar.gz -L https://github.com/actions/runner/releases/download/v2.291.1/actions-runner-linux-x64-2.291.1.tar.gz# Optional: Validate the hash
$ echo "1bde3f2baf514adda5f8cf2ce531edd2f6be52ed84b9b6733bf43006d36dcd4c  actions-runner-linux-x64-2.291.1.tar.gz" | shasum -a 256 -c# Extract the installer
$ tar xzf ./actions-runner-linux-x64-2.291.1.tar.gz
```

- Configure

```
# Create the runner and start the configuration experience
$ ./config.sh --url https://github.com/mikrodinet/hint --token AUB55YBFCW7GBJLQAOMT7G3CTBEWE# Last step, run it!
$ ./run.sh
```

- Using your self-hosted runner

```
# Use this YAML in your workflow file for each job
runs-on: self-hosted
```

For additional details about configuring, running, or shutting down the runner, please check out our product docs.


# Linux

Architecture ARM

- Download

```
# Create a folder
$ mkdir actions-runner && cd actions-runner# Download the latest runner package
$ curl -o actions-runner-linux-arm-2.291.1.tar.gz -L https://github.com/actions/runner/releases/download/v2.291.1/actions-runner-linux-arm-2.291.1.tar.gz# Optional: Validate the hash
$ echo "a78e86ba6428a28733730bdff3a807480f9eeb843f4c64bd1bbc45de13e61348  actions-runner-linux-arm-2.291.1.tar.gz" | shasum -a 256 -c# Extract the installer
$ tar xzf ./actions-runner-linux-arm-2.291.1.tar.gz
```

- Configure

```
# Create the runner and start the configuration experience
$ ./config.sh --url https://github.com/mikrodinet/hint --token AUB55YBFCW7GBJLQAOMT7G3CTBEWE# Last step, run it!
$ ./run.sh
```

- Using your self-hosted runner

```
# Use this YAML in your workflow file for each job
runs-on: self-hosted
```

For additional details about configuring, running, or shutting down the runner, please check out our product docs.



# Linux
Architecture ARM64

- Download

```
# Create a folder
$ mkdir actions-runner && cd actions-runner# Download the latest runner package
$ curl -o actions-runner-linux-arm64-2.291.1.tar.gz -L https://github.com/actions/runner/releases/download/v2.291.1/actions-runner-linux-arm64-2.291.1.tar.gz# Optional: Validate the hash
$ echo "c4823bd8322f80cb24a311ef49273f0677ff938530248242de7df33800a22900  actions-runner-linux-arm64-2.291.1.tar.gz" | shasum -a 256 -c# Extract the installer
$ tar xzf ./actions-runner-linux-arm64-2.291.1.tar.gz
```

- Configure

```
# Create the runner and start the configuration experience
$ ./config.sh --url https://github.com/mikrodinet/hint --token AUB55YBFCW7GBJLQAOMT7G3CTBEWE# Last step, run it!
$ ./run.sh
```

- Using your self-hosted runner

```
# Use this YAML in your workflow file for each job
runs-on: self-hosted
```

For additional details about configuring, running, or shutting down the runner, please check out our product docs.






## Disclaimer

The code was written to be read. Please read it, especially if you don't trust
me to build a secure encryption application. In particular:

- ~~I am a college student, not a security professional – there may be best
  practices I am not aware of.~~ I have graduated college, and now work for a
  cybersecurity company. 
- Once someone decrypts a link, they can share the original URL as much as they
  want. Only share encrypted links with trusted people.
- I am not comfortable using JavaScript, and I don't have a firm grasp of the
  nuances of the language – there may be bugs that I don't even know to check
  for.
- This is the first project I have ever done using encryption – there is likely
  a subtle mistake somewhere.
- Most of the encryption/decryption code is based on [MDN
  tutorials](https://developer.mozilla.org/en-US/docs/Web/API/SubtleCrypto/deriveKey#PBKDF2_2)
  for the `SubtleCrypto` API.



## Usage

- Create a locked link here: [https://mikrodinet.github.io/hint](https://mikrodinet.github.io/hint).
- Once you have a locked link, create a hidden bookmark here:
  <https://mikrodinet.github.io/hint/hidden>.
- Use the advanced options when creating a link to make the encryption more
  secure (at the cost of a longer link).
    - By default, the initialization vector is randomized for security, but
      this can be disabled, even though doing so is a vulnerability.
    - By default, the salt used to hash the password during key derivation is
      not randomized, but this can be enabled.
- To bookmark a locked link, drag it from the output box to the bookmarks bar.
  Alternatively, visit the locked link and bookmark it before entering the
  password.
- If you lose the password, it is almost impossible to recover the original
  link. The strong security guaranteed by encryption can be a blessing or a
  curse if you are not careful!
- Currently, the only way to recover a lost password is by trying all possible
  options (very slowly) by brute force. An example application to brute force
  Link Lock URLs in the browser can be found here:
  <https://mikrodinet.github.io/hint/bruteforce>.
- A parallelized, cross-platform, CPU-based brute forcer can be found here:
  <https://mikrodinet.github.io/hint/bruteforce/>
- If you receive a Link Lock URL that you do not trust, decrypt it using this
  interface that does not automatically redirect:
  <https://mikrodinet.github.io/hint/decrypt>.
- Get Started On Link Lock
  <https://mikrodinet.github.io/hint/index.html>

### Evading Censorship

Link Lock can be used to evade censorship. If you are concerned that sending
links with the [mikrodinet.github.io](https://mikrodinet.github.io) domain name will put you at risk, just
replace the domain with another. For example, share

```
https://wikipedia.org/#eyJ2IjoiMC4wLjEiLCJlIjoiYUgrNDhISkpBWWhkeFFMc0l0VlIzeFlma21mYlZCOFJ5Zz09In0=
```

instead of

```
https://mikrodinet.github.io/hint/#eyJ2IjoiMC4wLjEiLCJlIjoiYUgrNDhISkpBWWhkeFFMc0l0VlIzeFlma21mYlZCOFJ5Zz09In0=
```

Any domain can be used in place of `wikipedia.org`. That way, a malicious
third-party who clicks the altered link will be taken to a valid page, which
helps alleviate suspicion. When sharing the password to unlock the link,
explain how to switch out the domain name with either
[mikrodinet.github.io/hint](https://mikrodinet.github.io/hint), or with the path to a local clone of Link Lock.
Using a local copy is particularly recommended for evading censorship, since no
request to my domain is ever made.

Alternatively paste the altered link directly into the [decrypt
page](https://mikrodinet.github.io/hint/decrypt/). This page does not check
the domain name of the pasted link, only the "fragment" (the part after the
`#`). So, for example, the Wikipedia link above can be pasted directly in there
and decrypted without changing the domain.

Using a local copy of [URL Pages](https://github.com/mikrodinet/hint/) is also
recommended. Entire web pages can be shared safely and secretly this way.



## Project Status

This project is actively maintained. If there are no recent commits, it means
that everything has been running smoothly! Even if the link storage protocol
is updated, Link Lock is designed to be 100% backwards-compatible, so your
locked links will never break.

Even if something were to happen to me, and I could not continue to work on
the project, Link Lock will continue to work as long as my GitHub account is
open and the [mikrodinet.github.io](https://mikrodinet.github.io) domain is online.



## Other Versions & Related Projects

- Jawa translation: [Java.site](https://Java.site)
- Indonesia translation:
  [Indonesion.github.io/hint](https://mikrodinet.github.io/hint/)
- Polish translation: 
  [your<example>.github.io/link-lock](https://mikrodinet.github.io/hint/)




## Acknowledgments

Thank you to those who offered feedback on this program before its release.
Thanks also to the Hacker News second-chance pool.

Thanks to [@mikrodinet](https://www.mikrodinet.eu.org) for discovering a
reflected XSS vulnerability resulting from allowing non-hypertext protocols in
the URL. The vulnerability has since been fixed.

Thank you to ([@mikrodinet](https://github.com/mikrodinet)) for
translating Link Lock into French, and hosting a translated version. 


 
# Support the Project

There are a few things you can do to support the project:

- Star the repository and follow me on GitHub
- Share and upvote on sites like Twitter, Reddit, and Hacker News
- Report any bugs, glitches, or errors that you find
- Translate into other languages

These things motivate me to to keep sharing what I build, and they provide
validation that my work is appreciated! They also help me improve the project.
Thanks in advance!

If you are insistent on spending money to show your support, I encourage you to
instead make a generous donation to one of the following organizations. By
advocating for Internet freedoms, organizations like these help me to feel
comfortable releasing work publicly on the Web.

<p align="center">
<i>Loved the tool? Please consider <a href="https://www.paypal.com/signin?returnUri=https%3A%2F%2Fwww.paypal.com%2Fmyaccount%2Ftransfer%2Fhomepage%2Fexternal%2Fprofile%3FflowContextData%3DdnQz6co9bTO3dXsoaSQoXrylmBBr7Z4w4NgW64GB_WDfmLR52ffZouE7E54etjPgewijP0OxmZksVyVuBbZSxh7v9r8PWndQTi1eJUMZCCj7rrJftUv11NTxekLdOnVJT8vh6pE128RXl6Lq4yOTwu0f2kutdDCQ_qZkx2CTsh1Z3f_OGWFAvKJiKVMHbhq3dn4SWoaIs2dY-I1dSekSdPbZuEHLmCfV3kIA3MpjsPC9xVmmiRxgIY0fsKhMIEnZZQdCZUSJTpNWAnvYDIc-pUIdstyJJzGtqMk0TeqjSG7LnM5jOZufDLI4W8Jbk14B1O-3rAfdL66TgrgjcVRK35l6WhQzVDZEWvimVxtUMuqCgf8gboCEKwLD3ywxApHbM23LBMJY9KBXh6ILB3oZCmB0wYYJxSwmpLiIEW%26amount%3D25%26currencyCode%3DAUD&onboardData=%7B%22country.x%22%3A%22ID%22%2C%22locale.x%22%3A%22id_ID%22%2C%22intent%22%3A%22paypalme%22%2C%22redirect_url%22%3A%22https%253A%252F%252Fwww.paypal.com%252Fmyaccount%252Ftransfer%252Fhomepage%252Fexternal%252Fprofile%253FflowContextData%253DdnQz6co9bTO3dXsoaSQoXrylmBBr7Z4w4NgW64GB_WDfmLR52ffZouE7E54etjPgewijP0OxmZksVyVuBbZSxh7v9r8PWndQTi1eJUMZCCj7rrJftUv11NTxekLdOnVJT8vh6pE128RXl6Lq4yOTwu0f2kutdDCQ_qZkx2CTsh1Z3f_OGWFAvKJiKVMHbhq3dn4SWoaIs2dY-I1dSekSdPbZuEHLmCfV3kIA3MpjsPC9xVmmiRxgIY0fsKhMIEnZZQdCZUSJTpNWAnvYDIc-pUIdstyJJzGtqMk0TeqjSG7LnM5jOZufDLI4W8Jbk14B1O-3rAfdL66TgrgjcVRK35l6WhQzVDZEWvimVxtUMuqCgf8gboCEKwLD3ywxApHbM23LBMJY9KBXh6ILB3oZCmB0wYYJxSwmpLiIEW%2526amount%253D25%2526currencyCode%253DAUD%22%2C%22sendMoneyText%22%3A%22Anda%2520mengirimkan%2520Ahmad%2520wahyudi%22%7D">donating</a>  💸 to help it improve!</i>
</p>
<a href="https://www.paypal.com/signin?returnUri=https%3A%2F%2Fwww.paypal.com%2Fmyaccount%2Ftransfer%2Fhomepage%2Fexternal%2Fprofile%3FflowContextData%3DdnQz6co9bTO3dXsoaSQoXrylmBBr7Z4w4NgW64GB_WDfmLR52ffZouE7E54etjPgewijP0OxmZksVyVuBbZSxh7v9r8PWndQTi1eJUMZCCj7rrJftUv11NTxekLdOnVJT8vh6pE128RXl6Lq4yOTwu0f2kutdDCQ_qZkx2CTsh1Z3f_OGWFAvKJiKVMHbhq3dn4SWoaIs2dY-I1dSekSdPbZuEHLmCfV3kIA3MpjsPC9xVmmiRxgIY0fsKhMIEnZZQdCZUSJTpNWAnvYDIc-pUIdstyJJzGtqMk0TeqjSG7LnM5jOZufDLI4W8Jbk14B1O-3rAfdL66TgrgjcVRK35l6WhQzVDZEWvimVxtUMuqCgf8gboCEKwLD3ywxApHbM23LBMJY9KBXh6ILB3oZCmB0wYYJxSwmpLiIEW%26amount%3D25%26currencyCode%3DAUD&onboardData=%7B%22country.x%22%3A%22ID%22%2C%22locale.x%22%3A%22id_ID%22%2C%22intent%22%3A%22paypalme%22%2C%22redirect_url%22%3A%22https%253A%252F%252Fwww.paypal.com%252Fmyaccount%252Ftransfer%252Fhomepage%252Fexternal%252Fprofile%253FflowContextData%253DdnQz6co9bTO3dXsoaSQoXrylmBBr7Z4w4NgW64GB_WDfmLR52ffZouE7E54etjPgewijP0OxmZksVyVuBbZSxh7v9r8PWndQTi1eJUMZCCj7rrJftUv11NTxekLdOnVJT8vh6pE128RXl6Lq4yOTwu0f2kutdDCQ_qZkx2CTsh1Z3f_OGWFAvKJiKVMHbhq3dn4SWoaIs2dY-I1dSekSdPbZuEHLmCfV3kIA3MpjsPC9xVmmiRxgIY0fsKhMIEnZZQdCZUSJTpNWAnvYDIc-pUIdstyJJzGtqMk0TeqjSG7LnM5jOZufDLI4W8Jbk14B1O-3rAfdL66TgrgjcVRK35l6WhQzVDZEWvimVxtUMuqCgf8gboCEKwLD3ywxApHbM23LBMJY9KBXh6ILB3oZCmB0wYYJxSwmpLiIEW%2526amount%253D25%2526currencyCode%253DAUD%22%2C%22sendMoneyText%22%3A%22Anda%2520mengirimkan%2520Ahmad%2520wahyudi%22%7D"/><img align="center"  src="https://img.shields.io/badge/support-PayPal-blue?logo=PayPal&style=flat-square&label=Donate" alt="sponsor github profile readme generator"/>
</a>  
<a href="https://trakteer.id/awfanspage/tip "><img align="center" src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" height="30" width="100" alt="Support" /></a>

