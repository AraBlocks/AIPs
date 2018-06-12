
Title: **AIP-0000: The ARA Improvement Proposal Process**

Short Name: `0000-aip-process`

Type: Process

Status: Draft (as of 2018-06-12)

Github PR: [Draft](https://github.com/arablocks/AIPs/pull/2)

Authors: TBD


# Summary
[summary]: #summary

The ARA Improvement Proposal ("AIP") process is inspired by the DEP
process outlined by the open source Dat project. It is how consensus
around technical enhancements and organizational process can be reached
ultimately improving ARA.


# Motivation
[motivation]: #motivation

The ARA platform and its protocols are open standards aimed to serve and be upheld by an active developer community. This document outlines a transparent and standardized process for submitting proposals to enhance the platform.

AIPs will serve as the primary means of introducing new features, documenting design thought processes and decisions, and tracking community progress. They should follow a streamlined and coordinated method for communication necessary both to accomodate the variety of projects that are expected to use the platform and to improve their overall technical quality.


# How To Submit a Proposal
[submit]: #submit

The AIPs repository will have a Working Group (WG) responsible for maintaining the proposal workflow and upholding proposal standards. Importantly, the WG does not make judgments based on a proposal's likelihood of acceptance, but rather on its level of completeness, adherence to the process, technical soundness, and document preparation. The WG is expected to perform all work related to repository management, including active communication with proposal authors as well as merging pull requests.

Each AIP must have a _champion_ who is responsible for vetting the idea, ensuring its feasibility and relevance to the community, and leading public discussions. It may be helpful for the _champion_ to gauge community interest and support on ARA's public forums—including [Github issues][issues-1], the [ARA subreddit][subreddit-1], and the [ARA Telegram][telegram-1] channel—before committing too much time to an AIP. In general, the more community interest and consensus there is around an AIP, the more likely it is to be ultimately accepted.

AIPs should strive to outline a single, focused responsibility. If a new idea entails multiple functional changes, each change should be documented in a separate AIP. It is better to err on the side of too narrowly describing a new proposal or idea than to describe it in a too broad or unfocused way. AIPs should describe ideas that are applicable to a substantial subset of the community.

Each proposal should abide by the following procedure:

1. Fork the arablocks/aips repository using git https://github.com/AraBlocks/aips
2. Copy `0000-template.md` to `proposals/0000-my-proposal.md` (Don't choose a number here; leave it as `0000`. `my-proposal` should be descriptive)
3. Fill in the AIP template. Be sure to include a Type and Status as described in the section below. Each proposal's Status should start off as `WIP`.
4. When the proposal is ready, submit a pull request to signal the WG that the AIP is ready for review. At this point, the WG will determine whether the AIP is at an acceptable level of completion. If so, the AIP will be assigned a number and merged with `Draft` status. Otherwise, the AIP is declined. The WG may request revisions and a resubmission and/or provide feedback.
5. Once in `Draft` status, the AIP can be ammended with small changes, clarifications, and corrections through additional PRs. Large changes will warrent a `Superceding` proposal.
6. When the AIP reaches a finalized state, a PR should be submitted to promote the status to `Active`. Again, the PR should not include any major changes, but may include small updates.

[subreddit-1]: https://www.reddit.com/r/AraBlocks/
[issues-1]: https://github.com/AraBlocks/AIPs/issues
[telegram-1]: https://t.me/arablocks

# Details
[reference-documentation]: #reference-documentation

## Types and Statuses
[types]: #types

AIPs should have a type:

* **Standard** for technical changes to the protocol, on-disk formats, or
  public APIs. These are intended to be *proscriptive*, and to clearly
  delineate which features and behaviors are mandatory or optional.
* **Process** for formalizing community processes or other (technical or
  non-technical) decisions. For example, a security vulnerability reporting
  policy, a process for handling conflicts of interest, or procedures for
  mentoring new developers.
* **Informative** for describing conventions, design patterns, existing norms,
  special considerations, etc.

The status of an AIP can be:

* **Work in progress (WIP)**: The idea has gained significant community support and is being prepared for `Draft` review.
* **Draft**: PR has been merged and a number assigned, but additional time is
  needed for deeper discussion or more implementation before being "normative"
  and expected for implementation. It is acceptable to have "competing"
  proposals in this state at the same time.
* **Active**: adopted or intended for implementation in mainline libraries and
  clients as appropriate. Again, AIPs should clarify which aspects of
  themselves are optional or required for well-behaved clients.
* **Closed**: either consensus was against, a decision was postponed, or the
  authors withdrew their proposal. This could apply to any of: a proposal PR
  that was never merged, a merged Draft (which was never Active), or an Active
  AIP which there is now consensus against without a specific new AIP to
  replace it.
* **Superseded**: a formerly Active AIP has been made obsolete by a new
  Active AIP; the new AIP should specify specific old AIPs that it would
  supersede.

## Content and Structure
[content]: #content

A changelog should be kept in the AIP itself giving the date of any changes of
status.

A template file is provided, but sections can be added or removed as
appropriate for a specific AIP.

The AIP text itself should be permissively licensed; the convention is to use
the Creative Commons Attribution License (CC-BY), with attribution to the major
contributing authors listed.

For appropriate AIPs (including *all* Standards AIPs), authors should
explicitly consider and note impacts on:

* Privacy and User Rights. Consider reading IETF [RFC 6973] ("Privacy
  Considerations for Internet Protocols") and [RFC 8280] ("Research into Human
  Rights Protocol Considerations")
* Backwards compatibility of on-disk archives and older network clients. If a
  backwards-incompatible change is proposed, a migration plan should be
  sketched out in the proposal
* Security

[CC-BY]: https://creativecommons.org/licenses/by/3.0/us/
[RFC-6973]: https://tools.ietf.org/html/rfc6973
[RFC-8280]: https://tools.ietf.org/html/rfc8280


## Acceptance Criteria
[criteria]: #criteria

The criteria for a proposal being accepted as a Draft are, at a minimum, that
the proposal is complete, understandable, unambiguous, and relevant. There is a
good faith assumption that the submitter believes that the proposal could
actually be adopted and put to beneficial use. An editor may screen proposals
before passing on to the group for review.

For Standards and Process AIPs, Draft proposals should be specific enough that
they can be prototyped and experimented with (eg, in a pilot program or test
network), but it isn't expected that all details have been worked out. Working
code is helpful but not required.

For a Draft to migrate to Active, there is an expectation that the proposal has
been demonstrated (eg, in working code, though not necessarily in "official"
libraries yet), that the proposal will be the "new normal" and expected
behavior going forward, and that the chance of unforeseen issues arising during
complete adoption is low.


## Decision Making Process
[power]: #power

There exists a [Protocol Working Group (WG)][wg] (WG) which makes AIP status
decisions; see the Github repository for a list of current members and the
governance process.

By no means should working group members be the only people reviewing or giving
feedback on proposals.

When deciding on `Draft` status, at least one WG member must review the entire
proposal in detail, give feedback, and give informed approval. If no detailed
review takes place in the fixed time window, the default is to close (reject)
until a member is willing to commit to review. Any WG member can request
revisions or clarifications (blocking acceptance until addressed), and any
member can block. In other words, consensus requires that at least one member
actively approve, and any member can block, but it isn't required to have every
member review and actively given an opinion. This is referred to as the "loose
consensus" model.

For Active status, the expectation is that all working group members will
review the proposal and actively participate in consensus. In the event that
not all members can participate, the default is again negative. Any member can
block. This is referred to as the "complete consensus" model.

For all other status changes, at least one WG member must vouch for or approve
the change ("loose consensus"). If there is unambiguous consensus (or, eg, a
AIP is documenting already adopted practice), an AIP can move directly to Active
status (following the "complete consensus" process).

In all cases, if there is a deadlock (a block can not be overcome after
further discussion), there is an option to override the block by a vote. The
details of this process are left to description in the Working Group
repository, and are expected to be used only in exceptional cases (eg, are not
invoked by default if a member blocks).

Proposals are expected to be open for at least three days (72 hours) for
comment (and longer to accommodate special circumstances, like holidays). Vetoes
(blocks) can happen up to a week after initially being submitted for review,
which might be retroactive if the proposal was accepted (by other WG members)
very quickly.


# Rationale
[rationale]: #rationale

In the design space of RFC processes, there are two decision points determining
the formality and maturity of accepted standards. The first is, does `Draft`
status mean *could* be implemented, or *has* been implemented? We chose
"could". Secondly, for `Active` (or `Final`) status, is the proposal *expected*
to be dominant in the wild, or *is it already* dominant in the wild? We chose
"expected". In both cases we are emphasizing clarification and stabilization of
new ideas, as opposed to enforcing interoperability of competing formulations
of the same idea. In short, we expect AIPs to lead (rather than tail)
implementation.

Time limits and default outcomes are used to prevent proposals from getting stuck
in an ambiguous indefinite state anywhere along the process. `Draft` status is
considered a stable state to linger in.

Setting expectations for "completeness" of proposals, having an editor quickly
skim proposals before jumping in to a full review, and acknowledging an explicit
"revise and re-submit" workflow are all attempts to head off the situation of
partial proposals being submitted and then significantly revised, which places
extra (time) burden on reviewers.


# Background and References
[references]: #references


The following standards processes were referenced and considered while
designing the AIP process:

* **Dat Enhancement Proposals** as described in [DEP 1][dep-1].
* **BitTorrent Enhancement Process** as described in [BEP 1][bep-1]. The
  Bittorrent protocol has a lot of technical similarities to Dat, and as a
  single protocol family (not a language or full-stack system) is one of the
  most similar in scope. The de facto BEP model is that Drafts are very stable
  and widely adopted; only the most universal core components are Final. The
  AIP process bases it's type categories on the BEP process. There is a single
  editor and an explicit BDFL in the BEP process.
* **[IETF RFC Process][ietf]**: perhaps the oldest and best known RFC process,
  under the motto of "rough consensus and working code". The process is very
  bespoke (involving custom file formats and software) and heavy on process
  (with working groups and in-person meetings).
* The **W3C** is a paid membership organization which, like the IETF, is made
  up of entities large and small, for-profit and altruistic, with decent
  regional diversity. W3C standards are often rather large and verbose
  documents, and tend to tail (rather than lead) implementation.
* **Ethereum Improvement Proposals** as described in [EIP 1][eip-1].

[eip-1]: https://github.com/ethereum/EIPs/blob/master/EIPS/eip-1.md
[dep-1]: https://github.com/datprotocol/DEPs/blob/master/proposals/0001-dep-process.md
[bep-1]: http://bittorrent.org/beps/bep_0001.html
[ietf]: https://www.ietf.org/about/process-docs.html


# Unresolved questions
[unresolved]: #unresolved-questions

How mutable should `Draft` Standards AIPs be over time? What about
Informational AIPs? Should there be an additional status ("Living"?) for AIPs
that are expected to evolve, or is this against the whole philosophy of having
specific stable documents to reference? This is expected to be clarified while
this AIP itself is in `Draft` status.

Does `Active` status mean that implementation is *mandatory*, and that features
*must* be implemented unless they are explicitly optional? How would this
expectation be enforced for third-party software? This is expected to be
clarified when concrete examples arise.