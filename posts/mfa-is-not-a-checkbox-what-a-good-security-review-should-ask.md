# MFA is not a checkbox: what a good security review should ask

A common security questionnaire asks a simple question: is multi-factor authentication enabled?

A clear “yes” is a good start, but it does not tell us enough to understand how well accounts are protected. Which systems require it? Which methods are allowed? Can a user bypass it during account recovery? Are administrators covered in the same way as everyone else?

These details matter because multi-factor authentication (MFA) is not one single setting. The protection depends on how it is configured and how people actually use it.

## Start with coverage, not just the policy

First, understand where MFA is required. A policy may say that MFA is mandatory, while the actual configuration applies only to certain applications or groups.

For a useful review, look at:

- Employee access to business applications and cloud services
- Remote access, such as VPN or remote administration
- Administrator and other privileged accounts
- Contractors and third parties who can access company systems
- Any documented exceptions, including who approved them and when they expire

It is also worth checking whether the scope matches the service being assessed. A vendor might enforce MFA for its corporate email but have a different arrangement for the platform that stores a customer's data.

The goal is not to assume a gap exists. It is to confirm what the control covers.

## Ask which authentication methods are allowed

Not every MFA method offers the same level of protection.

SMS codes and voice calls can be better than relying on a password alone, but they can still be exposed to phishing, phone-number takeover and social engineering. Push notifications and authenticator codes also need to be considered in the context of how they are configured and used.

Passkeys and FIDO2 security keys are designed to resist phishing by using public-key cryptography and binding authentication to the legitimate service. They can reduce the risk of a user handing a reusable code to a fake login page.

NIST's current Digital Identity Guidelines, SP 800-63B-4, make phishing resistance an explicit part of stronger authentication assurance. For example, applications assessed at AAL2 must offer a phishing-resistant option, while AAL3 requires a phishing-resistant authenticator with a non-exportable key. These are NIST assurance requirements for their stated scope, not a blanket rule that every organization must apply to every system.

For an assessment, ask the vendor to explain which methods are permitted, which are preferred, and whether weaker methods remain as fallbacks.

## Treat account recovery as part of MFA

A strong sign-in process can be undermined by a weak recovery process.

Consider what happens when an employee loses a phone or security key. Can the help desk reset MFA after asking a few basic questions? Is identity checked through a separate trusted process? Does another person approve the change? Are recovery events logged and reviewed?

These are not minor operational details. An attacker who cannot get through the normal sign-in process may try to persuade support staff to reset the account instead.

Ask for the recovery procedure and, where possible, evidence that it is followed. A well-written policy is useful, but a sample of a properly reviewed recovery event can provide more confidence.

## Pay attention to changes already underway

Passkeys are moving into mainstream enterprise identity platforms. Microsoft announced that passkeys would become the default phishing-resistant authentication method in Microsoft Entra ID, with a staged rollout beginning on 1 September 2026. Microsoft also says its own SMS and voice delivery for Entra ID public cloud will end on 1 February 2027. These dates apply to the public cloud service, so organizations using other environments should check the guidance that applies to them.

This is a useful reminder for vendor reviews: a control that was acceptable in a previous assessment may be changing. If a provider uses Microsoft Entra ID, ask whether the change affects its users, what migration has been planned, and how access will be maintained during the transition.

A planned move to passkeys is positive, but it should not be recorded as completed until there is evidence of implementation.

## What evidence should you request?

The right evidence depends on the service and the level of access involved. A practical starting point could include:

- The MFA or authentication-method policy, including its scope
- A configuration view or export showing which applications and user groups are covered
- A summary of enrolled authentication methods, with sensitive details removed
- Confirmation that privileged accounts are included
- The exception register, including approvals and expiry dates
- The account recovery procedure and a redacted example of a recovery review
- A sample of sign-in or authentication logs that demonstrates enforcement

You do not need to collect every configuration file. Ask for enough evidence to connect the vendor's statement to the actual service being assessed.

## Write down what the evidence really confirms

A useful assessment conclusion is more specific than “MFA is enabled.”

For example, it might say that MFA is enforced for staff and administrators accessing the assessed service, while SMS remains an allowed fallback for a defined group. It might also note that the vendor has documented a passkey migration but has not yet provided evidence that recovery controls have been tested.

That kind of wording is fair. It recognizes what is working, identifies what remains unclear and gives the customer something concrete to consider.

MFA is an important control, but the checkbox is only the beginning. A good review looks at coverage, method strength, recovery and evidence together. That is how we move from collecting a yes-or-no answer to understanding the protection behind it.

## Further reading

- [NIST SP 800-63B-4: Authentication and Authenticator Management](https://pages.nist.gov/800-63-4/sp800-63b/introduction/)
- [Microsoft: Passkeys are the default authentication method in Entra ID](https://www.microsoft.com/en-us/security/blog/2026/07/13/microsoft-entra-id-security-updates-passkeys-are-the-default-authentication-method-in-entra-id/)
