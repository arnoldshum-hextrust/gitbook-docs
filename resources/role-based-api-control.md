# Role Based API Control

## Security Synopsis

\
API keys and accounts are prime suspects for hackers. Ensuring a comprehensive understanding and application of our recommended security measures for Hexsafe APIs is is vital to fortify against vulnerabilities.\
\
**Role-based Access Control** \
\
When introducing new API users, it is crucial to assign roles in alignment with the principle of least privilege. Hexsafe provides a substantial variety of roles for granular access control, and any one of these can be attributed to an API user. It's recommended to create multiple API users to effectively bifurcate responsibilities and establish clear security perimeters.

{% hint style="info" %}
Hexsafe takes an extra step in security by encrypting API keys, thereby providing an added layer of protection. Remember, a well-guarded API is your first line of defense against system intrusions.
{% endhint %}

**Best Practice**

For enhanced security management, it is advisable to maintain two distinct API users for separate functions:

1. A 'Viewer' role as an observant role dedicated to read-only actions.
2. A 'Signer' role entrusted with the authority of transaction signatures.

#### Data Encryption

Hexsafe encrypts all sensitive data, such as API keys. This offers high-level security, ensuring that even if data falls into unauthorized hands, it remains indecipherable. Additionally, always ensure that data transmission over networks occurs over secure, encrypted channels to prevent potential data interception.\

