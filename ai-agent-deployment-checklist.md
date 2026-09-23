# AI Agent Deployment Checklist for Small Businesses

A practical checklist for introducing an AI agent into a real business process without turning a useful automation into an uncontrolled system.

## 1. Pick one useful job

Start with a task that is repetitive, measurable and easy to review.

Good first candidates:
- sorting or summarising incoming information;
- preparing draft replies for human review;
- extracting structured fields from documents;
- updating internal records from approved sources;
- generating routine reports or checklists;
- monitoring a defined system and raising an alert.

Avoid starting with a broad "run the business" brief.

## 2. Define the boundary before connecting tools

Write down:
- what the agent may read;
- what it may change;
- which applications it may access;
- which actions always require a person;
- the maximum spend or transaction size;
- which customer or staff data is allowed;
- where its logs and outputs will be stored.

A useful agent should have fewer permissions than the person supervising it.

## 3. Keep irreversible actions behind approval

Require explicit human approval before:
- sending customer messages;
- publishing content;
- deleting or overwriting records;
- changing billing or payment details;
- buying services;
- changing security settings;
- creating or removing user accounts;
- signing agreements.

Automate preparation and verification first. Automate irreversible execution only when the process is proven.

## 4. Test with representative examples

Create a small test set containing:
- normal cases;
- incomplete inputs;
- conflicting instructions;
- malformed documents;
- duplicate requests;
- requests containing sensitive information;
- deliberately misleading instructions.

Record the expected result for each example and compare the agent's output.

## 5. Check failure behaviour

For each connected tool, ask:

**What happens when it fails halfway through?**

The workflow should be able to tell the difference between:
- never attempted;
- attempted but failed;
- completed;
- completed with uncertain confirmation.

Do not automatically repeat an action when the first attempt may already have reached an external system.

## 6. Preserve evidence

For important actions record:
- time;
- request or job identifier;
- input source;
- tool used;
- result;
- external receipt or URL where available;
- person who approved it when approval was required.

Logs should make it possible to reconstruct what happened without trusting the agent's summary alone.

## 7. Protect secrets

Do not put passwords, API secrets, recovery codes or payment credentials into prompts, public logs or customer emails.

Prefer scoped credentials, short-lived tokens and provider-native authorization where available.

## 8. Measure business value

Track outcomes rather than model activity:
- minutes saved;
- errors prevented;
- jobs completed;
- customer response time;
- accepted quotes;
- support issues resolved;
- revenue received;
- cost per completed task.

Token counts and agent counts are operating metrics, not business results.

## 9. Start small, then expand

A sensible rollout is:

1. observe;
2. draft;
3. recommend;
4. execute reversible actions;
5. execute bounded external actions with approval;
6. automate only the parts that have reliable evidence.

## 10. Review regularly

Recheck permissions, prompts, connected tools and failure cases whenever the workflow changes.

Remove unused access and retire automations that no longer create measurable value.

---

Linux Stewards helps small businesses design and implement practical AI, automation and IT workflows with clear scope and human control.

- AI & automation services: https://www.linuxstewards.com/services/ai-business
- AI agents: https://www.linuxstewards.com/services/ai-agents
- Business automation: https://www.linuxstewards.com/services/business-automation
- Contact: https://www.linuxstewards.com/contact

UK-based, with remote work available worldwide where suitable.
