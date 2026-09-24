# Hana — AI voice receptionist

A Retell AI voice agent that answers inbound calls for my studio, qualifies the caller in Serbian, and books a discovery call on Cal.com. This repo is the agent config — prompt, tools, call settings — with real credentials replaced by placeholders.

There's no application code here; the interesting part is the prompt, not software. Hana collects information in a fixed order — name, company, what they do, the problem, a time slot — one question at a time. Letting the model free-associate through a qualification call meant it sometimes jumped straight to booking without actually qualifying anyone, so the order is enforced explicitly in the prompt rather than left to the model's judgment.

To reuse it: clone the repo, open `horizen-ai-recepcionista.json`, replace the placeholders (`YOUR_CAL_API_KEY`, `YOUR_TRANSFER_PHONE_NUMBER`, and the rest) with your own Cal.com and Retell values, then recreate the agent from that config in the Retell dashboard. MIT-licensed.

## What's not great

There's no way to test this outside making an actual phone call — no simulator, no unit tests, nothing that catches a broken prompt before a real caller hits it. And the whole language, tone and business logic lives in one long prompt string, which works but is a pain to review a diff of.

---

Matija Radulović · [horizen.rs](https://horizen.rs)
