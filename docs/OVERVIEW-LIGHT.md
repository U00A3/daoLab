# Lab DAO - how it works (for the community)

**For:** members, guests, anyone who does not want code names  
**PDF:** [`overview-light-en-reading-edition.pdf`](./overview-light-en-reading-edition.pdf)  
**Clickable map:** [dao.mynode.uk/how](https://dao.mynode.uk/how)  
**Site:** [dao.mynode.uk](https://dao.mynode.uk)

This is not an official Redbelly Network product. It is an independent lab on the test network: membership, a proposal office, and a voting urn.

---

## Three places, not three apps

In many DAOs you join in one place, file on Discord, and vote on Snapshot. Here it is one roof.

**The door.** You connect a wallet on Redbelly Testnet, the network confirms write access (CAT), you sign a declaration - and in the same step you get an **Identity**: a lasting, non-transferable membership mark. There is no separate "candidate" role and no second KYC inside the DAO. The network already checked you; the lab only opens the door.

**The office.** You write a packet and hand it to High Council. The checklist rides with the filing as a **signal**, not a gate - a hard flag does not close the queue. The author-HC thread is private. Public Discord opens only when HC is ready for daylight.

**The urn.** You vote here, not on Snapshot.org. You sign a ballot with your wallet. On-chain at the end goes the **result** (for / against / whether it passed) - not a list of who voted how. So an explorer cannot assemble a voter roll.

A guest (wallet without Identity) can read the register and the docs. **They cannot draft or vote**, even when an urn is open. Join first.

High Council works behind a PIN. A public description of that bench - without the PIN - is on the How page.

```text
Guest → Join (Identity) → member
member → draft → HC queue → public discussion → urn
member → ballot → result on-chain
```

---

## Why this beats Snapshot on ballot secrecy

On Snapshot each ballot is usually public: you see *who* and *how*. Hiding that only on the website does nothing - anyone who opens an explorer or a public API still sees the roster.

The lab splits three things Snapshot usually does not:

1. **Running tallies.** By default nobody - including HC via the public page - sees For / Against / Abstain until the window closes. Headcount ("how many have voted") can stay.
2. **Who voted how.** By default that list **is not a product at all**. HC may consciously reveal it after the end, or even during - that is a decision, not a CSS leak.
3. **Chain.** The explorer sees the result after the urn closes. It does not see your ballot.

So the urn is a **hybrid**: the ballot stays on the platform; the chain gets the finish, not every card.

**What we do not promise.** The community sees the result on-chain, but cannot alone, from an explorer, prove that the tally includes *all* valid ballots and *only* those. You trust the lab operator the same way you trust Join - that Identity is minted to your signature. Heavier crypto can give secrecy and an on-chain proof together; on this lab (decisions are still executed by hand) that cost is not worth it. Snapshot does not give that either - there the ballot simply sits in the open.

---

## The problem the network does not solve for us

CAT says: *this wallet may write on testnet*. It does not say: *this is one human*.

One person can hold many wallets. If the urn counted "one address = one vote", ten Joins would mean ten ballots.

We do not promise "one network KYC = one vote" - the network does not give us that map. The lab builds a compromise: **an honest person has one ballot**; a farm of fresh Identities should be costly or ineffective where the stakes are high.

Secrecy of "who how" is a **separate axis** from vote farming. Linking Discord does not reveal how you voted.

---

## How we defend one ballot per person

This is in the product, not on a roadmap. Stronger gates HC turns on **per vote** - not all of them on every light community signal.

**Identity votes, not the wallet.** The primary address and linked wallets share one ballot. You may sign from any of them; a second ballot from the same Identity will not pass. That is the foundation.

**Limit:** anyone who does ten separate Joins has ten Identities. That is why further layers exist.

**Link instead of a second Join.** Honest flow: one Join, then attach other wallets on Profile. A vote from any linked address is the same ballot. The platform will not let you attach an address that already has its own Identity, or Join again on an address that is already a member. Linking wallets earns a little XP (prestige) - **not** an extra ballot and not more weight.

**You do not walk into an open urn.** Even without tenure: an Identity created *after* that vote opened cannot cast. You cannot join mid-window only to swing the result. When HC turns **tenure** on, you must have been a member long enough *before* open (usually about a month) - typical for HC elections.

**An XP threshold, not a magic free-form number.** HC picks: no gate (fast lab), standard, or strict. XP today is prestige and *whether you may vote*, not a weight multiplier. Empty Identity farms fail elections if HC sets a threshold and tenure. Rank → weight multiplier is deliberately deferred.

**Discord is a social layer, not membership.** Join does not require Discord. Identity stays the source of the vote. On Profile you can link an account (one account → one active Identity). When HC turns the Discord gate on for a vote, without a link the ballot will not enter. A stolen Discord **alone** cannot cast - a wallet signature is still required. After theft HC can ban that account; the victim links a new one; Identity and reputation stay.

**Allowlist.** HC can limit a vote to named people. That is a closed / emergency mode, not a second daily urn. Off the list, even a full member with tenure, XP, and Discord cannot cast.

**Weight does not reward wallet farms.** Either one eligible Identity = one vote (member signal), or weight from RBNT on wallets of *that same* Identity at open. More linked addresses do not mean more ballots.

**The explorer is not a voter roll.** Who may vote is checked by the platform at cast. The chain sees published tallies at most. The same design gives "who how" secrecy.

---

## How tight a vote can be

Every urn uses the same panel. Tenure, XP, Discord, and allowlist are **not reserved for HC elections**. They can be turned on for a light signal, a grant, anything.

At open HC sets, among other things:

- a motion ballot (For / Against / Abstain) or a ranked ballot (elections, candidate order);
- weight: signal or RBNT;
- whether tallies show live or only after the end;
- whether who-voted-how is visible: never / after end / live;
- tenure, XP gate, Discord, optional allowlist.

Always, whatever the knobs: one Identity = one ballot; a Join after the urn opened cannot vote.

| How tight | Typical set | Why |
|-----------|-------------|-----|
| **Light lab** | motion ballot, no tenure, no XP, no Discord, who-how hidden | Fast signal; farm is cut less **on purpose** |
| **Hard** | tenure + XP + Discord + hidden tallies + secret roster | HC elections, large amounts - fresh Identity farms drop out |
| **Closed** | hard **+ named allowlist** | Named people only; tightest urn the lab has |

---

## Guardian - a brake before the result hits the chain

Hardening says *who* may cast. Guardian says: *this urn should not produce a result*.

When during a vote - or after the window closes but **before HC finalizes** - procedural facts, a forgery attempt, a security incident, or a mistaken Start come to light, High Council can **cancel the vote**.

Then:

- all ballots for that round are void;
- the packet returns to public discussion (a new urn can open);
- the chain does **not** get a "result that never was";
- an HC ops log entry remains; a short public reason is recommended.

This works because ballots live on the platform and the chain waits for finalize. If every ballot were already a transaction, Guardian could not erase the explorer list.

**There is no pause.** You do not freeze the window and resume the same round. Either cancel or finalize. After finalize, cancel no longer applies.

This is not the author withdrawing a proposal. Guardian kills the *urn*; the packet stays.

---

## Authors cannot delete a proposal at every stage

While the packet is in the HC queue (draft, submitted, in review, needs changes), the author may edit or **delete** it. That hard-deletes the row; it does not leave a "withdrawn" status.

Once HC **publishes for discussion**, the packet is no longer the author's alone. It cannot be quietly erased once the community or the urn has started.

Other brakes still apply:

- HC may defer or reject - the record stays on the register;
- an open urn is stopped by Guardian, not author Delete;
- after finalize, none of that undoes the verdict.

---

## What this lab does not promise

- That one network KYC = one vote. The network does not give us that.
- That software will auto-detect "ten Identities = one human". HC has process, not auto-ban clusters.
- That more wallets = more power. Deliberately not.
- That XP multiplies vote weight. Not now - prestige and an optional gate only.
- That Snapshot.org is the urn. It is not.
- That "who how" hidden only on the website, with votes on-chain, is a secret. That is why the hybrid exists.
- That an explorer alone can prove tally = all ballots.
- That an author can delete a proposal after publish or during an urn.
- That the same round can be paused and resumed.

A farm of ten Joins **still exists** as a cost (CAT + new Identity). The lab does not pretend it vanished. On a light vote it stays on purpose; on a hard vote fresh Identities do not enter the urn; on a closed vote only the allowlist remains. An honest person still links wallets instead of a second Join.

---

## Where to see it

| Where | What |
|-------|------|
| [How](https://dao.mynode.uk/how) | Map: guest, member, High Council |
| [Join](https://dao.mynode.uk/join) → [Profile](https://dao.mynode.uk/profile) | Entry, wallet linking, Discord |
| Proposal register | Drafts, discussion, urn, results |
| [Archive](https://dao.mynode.uk/proposals/archive) | Closed lab votes (+ Snapshot.org history, read-only) |

**In one sentence.** The lab does not know the human behind network KYC; it knows **Identity**. An honest person links wallets to one mark and has one ballot. Fresh Identity farms fail the last-minute Join block, and HC can tighten **any** vote: tenure, XP, Discord, and - tightest - an allowlist. Versus Snapshot: the ballot does not land on the explorer - you see the result, not "who how", until HC flips that. And if an urn should not produce a result - Guardian kills the round before tallies hit the chain.
