# Fall 2013 Midterm

1. Because of the hassles of installing cryptographic software that works everywhere, some secure email
web sites (e.g., hushmail.com) offer “downloadable crypto”: a web page with Java or Javascript that implements the necessary functions to send and receive secure email. There’s a serious risk, though: you don’t know what you’re executing. Is it the real crypto code, or does it have a back door installed by the provider because the government ordered them to?

    (a) (10 points) To avoid this problem, a new site decides to offer digitally-signed crypto. That is, the
code they send your browser will be digitally signed and will be accompanied by a certificate. This does not solve the problem. Explain why it fails. (Assume that the browser is in fact capable of verifying such signatures. This question is about security architecture, not implementation
limitations.)
