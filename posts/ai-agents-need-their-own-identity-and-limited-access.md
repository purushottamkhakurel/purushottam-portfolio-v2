# AI agents need their own identity, not your admin access

AI tools are moving beyond answering questions. Some can now read tickets, search files, update records, write code or trigger workflows through connected tools.

That changes the security question.

When an AI system can take action, it is not enough to ask whether its answers are accurate. We also need to ask what it is allowed to access, whose authority it is using and how we would stop it if something goes wrong.

An agent should not quietly inherit the permissions of the person who connected it. It needs a clear identity and a narrow set of permissions for the work it is meant to do.

## Why an agent's access matters

Imagine an internal support agent that can read customer tickets and update account records. Reading a ticket may be appropriate. Changing account details or issuing a refund is a different level of action.

If the agent uses a shared administrator account or a broad service credential, a mistake or manipulated instruction could have a much wider impact than the original task required.

This is not just a theoretical governance concern. In its October 2026 roundup of selected incidents from the previous quarter, the OWASP GenAI Security Project described cases where agent activity crossed intended boundaries, used unintended network access or exposed credentials and expanded access into connected systems. The report is not an exhaustive list, but it is a useful reminder that permissions and infrastructure boundaries matter as much as model instructions.

The lesson is simple: do not rely on the agent being told to behave. Design the surrounding system so that it cannot easily do more than it is authorized to do.

## Give each agent a clear identity

An AI agent should be identifiable in the same way an organization identifies a service account or other non-human identity.

At a minimum, teams should be able to answer:

- What is this agent called, and who owns it?
- Which business task is it approved to perform?
- Which applications, data and environments can it access?
- Is it acting on behalf of a person, a workflow or the organization?
- How can its access be reviewed, suspended or revoked?

Avoid using a person's everyday account or a shared administrator credential as the agent's identity. Where the platform supports it, use a dedicated identity with permissions scoped to the task. Prefer short-lived or task-limited credentials over long-lived secrets, and keep development, testing and production access separate.

NIST's work on software-agent identity and authorization highlights the need to apply identification and authorization practices to agents as they interact with data, tools and applications. This is an important area for identity and access management teams to include in their existing processes.

## Limit what the agent can do

A named identity is useful, but it does not make an overpowered agent safe.

Start with the smallest set of permissions needed for the use case. If the task is to summarize support tickets, the agent may only need read access. It should not automatically receive permission to close accounts, change billing details or export customer records.

A practical design separates actions by impact:

- **Read:** retrieve only the records needed for the task.
- **Prepare:** draft a change or recommendation without applying it.
- **Write:** make a limited change within an approved scope.
- **High impact:** require a separate approval before actions such as payments, permission changes, deletion or external communication.

The application or tool that performs the action should enforce authorization. Do not depend on a prompt that says “only update approved records.” Check the user's authority, the agent's scope, the target resource and the requested action in the system that actually executes it.

This also helps with prompt injection. A document, email or ticket may contain text that tries to redirect an agent. Treat that content as data to be assessed, not as permission to change the agent's goal or access. Even if the model follows an unsafe instruction, the tool should still reject an action outside its approved scope.

## Keep a useful record of actions

If an agent changes a record, sends a message or accesses sensitive information, the organization should be able to reconstruct what happened.

Useful audit details include:

- The agent identity and the person or workflow that initiated the task
- The requested task and the tool or application used
- The resource or record the agent tried to access
- Whether the action was allowed, denied or sent for approval
- Who approved a high-impact action
- The time, result and any relevant error

Logs should be protected and should not unnecessarily store passwords, access tokens or sensitive content. The aim is to make decisions and actions traceable without creating another place where confidential information can leak.

Teams also need a practical stop mechanism. If an agent behaves unexpectedly, they should know how to disable the workflow, revoke its credentials and disconnect the relevant tools. A control that exists only in a policy document will not help much during an incident.

## Include the vendor and the full lifecycle

Many agents depend on external models, connectors, plugins or other services. A security review should cover the complete path, not just the model provider's name.

Ask vendors how identities are assigned, how permissions are limited, whether customer data is retained, what subprocessors are involved, what activity is logged and how access can be revoked. Understand which party is responsible for investigating and notifying customers if an agent or connected service is compromised.

The review should not end at launch. Agent capabilities, connected tools and business use cases can change. Reassess access when a connector is added, the workflow changes, the agent receives new responsibilities or the underlying service is updated.

## A practical review checklist

Before approving an agent for business use, I would want clear answers to these questions:

1. Is the agent inventoried, with a named business and technical owner?
2. Does it have its own identifiable account or workload identity?
3. Are its permissions limited to the specific task and resources?
4. Are high-impact actions checked by an independent authorization control or human approval?
5. Can untrusted documents and messages influence what the agent is allowed to do?
6. Are its actions logged in a way that supports investigation?
7. Can the organization quickly suspend the agent and revoke its access?
8. Have the vendor, connected tools and data handling arrangements been reviewed?

If several answers are unclear, that is a reason to pause and understand the exposure before expanding the agent's access.

## Autonomy needs boundaries

AI agents can make useful workflows faster, but granting access is a business and security decision. The more an agent can do, the more important it becomes to know exactly whose authority it uses and where that authority ends.

For GRC and security teams, this is a practical extension of familiar work: inventory the system, identify the owner, assess the data and access, verify safeguards, document exceptions and keep reviewing changes.

The goal is not to prevent every use of AI agents. It is to make sure that when an agent acts, its permissions are deliberate, its actions are visible and someone remains accountable.

An AI agent may be able to act on our behalf. It should never be allowed to act without boundaries.

## Further reading

- [NIST: New Concept Paper on Identity and Authority of Software Agents](https://www.nist.gov/news-events/news/2026/02/new-concept-paper-identity-and-authority-software-agents)
- [OWASP Top 10 for Agentic Applications 2026](https://genai.owasp.org/resource/owasp-top-10-for-agentic-applications-for-2026/)
- [OWASP: Securing Agentic Applications V2](https://genai.owasp.org/resource/securing-agentic-applications-v2/)
- [OWASP GenAI and Agentic AI Exploit Roundup Q3 2026](https://genai.owasp.org/2026/10/08/genai-and-agentic-ai-exploit-roundup-q3-2026/)
