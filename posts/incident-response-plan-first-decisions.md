# An incident response plan is only as good as its first decisions

A security incident rarely arrives with a neat description of what happened, who is affected and what should happen next.

The first report might be a suspicious login, an employee who clicked a link, an unavailable service or a message from a vendor. At that point, people need to make decisions with incomplete information. They need to know who to contact, what to preserve, what can safely be contained and who has the authority to make the next call.

That is why an incident response plan should be more than a document saved in a shared folder. It should help people make the first important decisions without having to invent a process while the incident is unfolding.

## Start with clear ownership

A plan should identify who coordinates the response and who makes decisions. Those responsibilities may involve security, IT operations, business leadership, legal, privacy, communications, human resources and the teams that own affected services.

The exact structure depends on the organization. A small company may have a few people covering several responsibilities. A larger organization may have a dedicated incident response team. Either way, the plan should make clear:

- Who can declare or escalate an incident?
- Who coordinates investigation and containment?
- Who can approve actions that may interrupt a service?
- Who contacts customers, regulators, insurers or law enforcement when required?
- Who takes over if the primary contact is unavailable?

A list of names is not enough. Include roles, backup contacts and a reliable way to reach them outside normal working hours. Review the details when people or responsibilities change.

## Agree on what needs to be escalated

Not every security alert is a confirmed incident, and not every incident has the same impact. But people should not have to guess whether something deserves attention.

Set practical escalation criteria. These might include suspected exposure of sensitive information, unauthorized access to privileged accounts, malware affecting important systems, disruption of a critical service or a security event involving a key supplier.

The criteria should help staff report concerns early. They should not require someone on the front line to prove that an incident has occurred before raising it.

It is also useful to define severity levels in plain language. Explain what makes an incident urgent, who must be informed and how quickly the response team should be engaged. Avoid a complicated scoring process that people cannot use under pressure.

## Decide what to preserve before changing anything

Containment is important, but the first action should be appropriate to the situation.

People may be tempted to delete a suspicious file, wipe a device, restart a server or disable an account immediately. Some actions may be necessary to limit harm, but others can remove useful evidence or make investigation harder.

The plan should explain how to report the issue, preserve relevant records and involve the right technical people. Depending on the incident, useful evidence may include authentication logs, endpoint alerts, email headers, cloud audit events, timestamps and a record of actions already taken.

This does not mean delaying urgent containment. It means making sure that containment and evidence handling are considered together, with decisions recorded as they happen.

## Make communication part of the response

A technical team cannot manage an incident alone if other people need to make business decisions or communicate with affected parties.

Prepare a communication path for internal leaders, service owners, legal and privacy teams, customer support and external stakeholders. Decide who is allowed to send updates and who approves them.

For incidents involving a supplier, know how to reach the vendor's security or incident response contact. Understand the notification requirements in the contract, including the relevant timeframes and what information the supplier is expected to provide.

Do not assume that a vendor's response process automatically covers the customer's responsibilities. Each organization still needs to understand its own reporting, legal, contractual and customer communication obligations.

## Include recovery, not just containment

Stopping an incident is not the same as restoring a service safely.

A recovery plan should identify who decides when systems can return to operation, how integrity will be checked, which dependencies must be restored first and how the organization will monitor for signs that the incident is continuing.

For important services, confirm that backup and restoration arrangements are understood by the people who may need to use them. A backup policy alone does not show that a service can be recovered within the time the business needs.

Recovery decisions should be documented, including any remaining limitations or risks that the business has agreed to carry.

## Practise the plan before it is needed

A plan can look complete on paper and still fail in practice. A contact may have left the organization. A supplier's escalation number may be out of date. The person expected to approve containment may not be available. The team may discover that nobody knows who can communicate with customers.

A tabletop exercise helps uncover these gaps without waiting for a real incident. Bring together the people who would take part and walk through a realistic scenario. Pause at key moments and ask what each person would do, what information they need and who has the authority to decide.

A useful exercise can test questions such as:

- Who receives the first report and starts the escalation?
- What information is needed to assess the impact?
- Who approves containment if a critical service may be interrupted?
- How will the organization contact a supplier outside business hours?
- Who decides whether customers or regulators must be notified?
- What evidence needs to be retained?
- What must be confirmed before recovery is approved?

The goal is not to catch people out. It is to find unclear responsibilities and missing steps while there is still time to improve them.

## Treat lessons learned as part of the work

After an incident or exercise, record what worked, what caused delay and what needs to change. Give each improvement an owner and a target date. Update the plan, contact lists, procedures and training where necessary.

NIST's SP 800-61 Revision 3, published in April 2025, places incident response within broader cybersecurity risk management and the six functions of the Cybersecurity Framework 2.0. The useful takeaway is that preparation, detection, response, recovery and improvement should inform one another. Incident response is not an isolated activity that begins and ends with the technical team.

## A practical starting point

If an organization is reviewing its incident response plan, start with a simple test: could the people involved explain their first few actions without searching through several documents or waiting for one specific person?

Make sure the plan identifies the response lead, escalation route, decision-makers, evidence handling steps, communication responsibilities and recovery approvals. Then test those details in a tabletop exercise and fix what the exercise reveals.

No plan can predict every incident. A good one does something more useful: it gives people a clear way to coordinate, make accountable decisions and adapt as the facts become clearer.

## Further reading

- [NIST SP 800-61 Rev. 3: Incident Response Recommendations and Considerations for Cybersecurity Risk Management](https://csrc.nist.gov/pubs/sp/800/61/r3/final)
- [CISA Tabletop Exercise Packages](https://www.cisa.gov/sites/default/files/2023-01/2_-_ctep_exercise_planner_handbook_2021_final_508.pdf)
