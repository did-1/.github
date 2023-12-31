# Decentralized Information Distributor (DID)

DID is a novel decentralized social media infrastructure that empowers users to own and distribute their content. Think of it like a decentralized Twitter where the data is entirely in the user's hands and where everyone is free to post content and subscribe to new posts. It could be also be compared to decentralized global RSS feed.

<em>DID is decentralized, but not federated. Each user (domain) is responsible for hosting his social posts and each DID instance contains all the history of urls ever submitted to the platform.</em>

⭐ Don't like to read? Try the DEMO of DID [by publishing your first social post](https://writer.did-1.com/)

📧 We are looking for active contributors - if you want to join this project please email did@tautvilas.lt

🧠 Read more about philosophy of DID [in this blog post](https://tautvilas.medium.com/it-is-time-to-create-a-decentralized-public-social-network-128b6c11fd24)

## Architecture

DID consists of three integral repositories:

1. **demo-writer:** A user-friendly onboarding tutorial to generate keys and social posts.
2. **instance-nodejs:** The heart of the DID network. It validates, stores, and distributes the post information.
3. **demo-reader:** A platform that displays the information from the DID network in a user-friendly format.

## Repositories

### demo-writer

[Try the DID writer here](https://writer.did-1.com/)

This tutorial helps new users get started with DID:

- Generate private/public key pairs using the secp256k1 algorithm.
- Craft DID-compliant HTML documents for social posts.
- Guide on uploading the public key and post to their personal domain.
- Submit the post URL to the DID instance for publishing.

### instance-nodejs

[Go to repository](https://github.com/did-1/did-instance-nodejs)

The core of the DID p2p network:

- Receives URL submissions and validates them.
- DOES NOT save post content, only URLs, signatures, domains, and content hashes.
- Distributes validated information to other peers on the network.

### demo-reader

[Read the latest posts](https://reader.did-1.com/)

A platform to consume DID content:

- Crawls URLs from DID instance databases.
- Stores post data locally.
- Displays data in a Twitter-like interface, showing domains and "retweet" equivalents.

## How it Works

1. **Key Generation:** User creates a private/public key pair (secp256k1).
2. **Key Hosting:** User hosts the public key on their domain (e.g., `userdomain.com/did.pem`).
3. **Content Creation:** User crafts a DID-compliant HTML page with their post and hosts it on their domain.
4. **Submission:** User signs the hash of their content and URL and sends this to a DID instance.
5. **Validation:** DID instance verifies the post's signature, content, and other aspects, then saves the URL and signature.
6. **Propagation:** The URL's information is broadcasted on the p2p network for other instances to validate and store.

### Roadmap

Main planned features

1. Data synchronization algorithms for DID instances
2. Allow image/link attachments for submissions
3. Implement advanced reader features: comments, follow lists, popular posts listing etc
