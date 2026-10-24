# cocoon-llm-guard

> **Status: concept — RFC stage. There is no code in this repository yet, and no published
> package.** This README describes an intended design. Our working code is in
> [harm-signal-api](https://github.com/The-Cocoon-Collective/harm-signal-api).

A wrapper layer for LLM APIs that intercepts and flags age-inappropriate generation attempts
before they reach a child.

## The idea

It would sit between an application and any LLM provider, apply an age-band profile to both
the request and the response, and block or sanitise what fails the check — so that a product
for children does not depend on each provider's own safety settings being configured
correctly, and the same rules apply whichever model is behind it.

Intended provider coverage: Anthropic, Google Gemini, OpenAI, and open-weight models served
locally.

## The open question we would rather settle before writing it

A guard layer is a **second** safety system, and second systems have a habit of becoming the
excuse for weakening the first. If a product can only be safe for a six-year-old because a
filter is catching what the model produces, the product is not safe — it is supervised.

So the question this RFC is really asking is: what belongs in a guard layer, and what should
never have been generated near a child in the first place? We would rather answer that in
public before shipping something that makes the question easier to avoid.

Age bands, when this is built, will be the product's real bands — `6-7` and `8-9`, plus
whatever the separate older platform turns out to need — not a single "under-13" flag.

## Licence

MIT. See [LICENSE](LICENSE).
