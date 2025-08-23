# Malicious npm package using steganography downloaded by hundreds

![NPM](https://www.bleepstatic.com/content/hl-images/2022/07/05/NPM_head_pic.jpg)

A malicious package in the Node Package Manager index uses invisible Unicode characters to hide malicious code and Google Calendar links to host the URL for the command-and-control location.

The package, named _os-info-checker-es6_, appears as an information utility and has been downloaded more than 1,000 times since the beginning of the month.

Researchers at [Veracode](https://www.veracode.com/resources/sophisticated-npm-attack-leveraging-unicode-steganography-and-google-calendar-c2), a code security assessment company, found that the first version of the package was added to the Node Package Manager (NPM) index on March 19 and was benign, as it only collected operating system information from the host.

The author added modifications a few days later to include platform-specific binaries and obfuscated install scripts.

On May 7, a new version of the package was published, which featured code for "a sophisticated C2 (command-and-control) mechanism" that delivers the final payload.

The latest version of '[os-info-checker-es6](https://www.npmjs.com/package/os-info-checker-es6)' available on npm at the time of writing is v1.0.8 and it is malicious, Veracode warns.

Furthermore, the package is listed as a dependency for four other NPM packages: [skip-tot](https://www.npmjs.com/package/skip-tot), [vue-dev-serverr](https://www.npmjs.com/package/vue-dev-serverr), [vue-dummyy](https://www.npmjs.com/package/vue-dummyy), and '[vue-bit](https://www.npmjs.com/package/vue-bit) \- all pose as accessibility and developer platform engineering tools.

It is unclear if or how these packages are promoted by the threat actor.

## Unicode steganography

In the malicious version, the attacker embedded data in what appeared to be a '|' string. However, the vertical bar is followed by a long sequence of invisible Unicode characters from the Variation Selectors Supplement range (U+E0100 to U+E01EF).

These Unicode characters are normally modifiers, typically used "to provide specific glyph variations in complex scripts." In this case, their role is to facilitate text-based steganography - hiding information in other data.

Veracode decoded and deobfuscated the string to find a payload for a sophisticated C2 mechanism that relied on a Google Calendar short link to reach the location hosting the final payload.

The researcher explain that after fetching the Google Calendar link, a set of redirects are checked until it receives a HTTP 200 OK response for the request.

It then scrapes a _data-base-title_ attribute from the event's HTML page, which holds a base64-encoded URL pointing to the final payload.

Using a function called _ymmogvj,_ the URL is decoded to get a malware payload. The researchers say that the request expects a base- encoded stage-2 malware payload in the response body, and likely an initialization vector and a secret key in the HTTP headers - an indication of possible encryption of the final payload.

Veracode also found that the payload is also executed using _eval()._ The script includes a simple persistence mechanism in the system's temporary directory, which prevents multiple instances running at the same time.

At the time of analysis, the researchers could not retrieve the final payload, suggesting that the campaign could be on hold or still in an early stage.

Despite Veracode reporting its findings to NPM, the suspicious packages are still present on the platform.