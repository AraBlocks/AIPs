
Title: **AIP-0001: The Ara Improvement Proposal Process**

Short Name: `0001-aip-process`

Type: Process

Status: Draft (as of 2018-05-17)

Github PR: [Draft](https://github.com/arablocks/AIPs/pull/2)

Authors: TBD


# Summary
[summary]: #summary

The Ara Improvement Proposal ("AIP") process is inspired by the DEP
process outlined by the open source Dat project. It is how consensus
around technical enhancements and organizational process can be reached
ultimately improving Ara.


# Motivation
[motivation]: #motivation

TODO

# How To Submit a Proposal
[submit]: #submit

TODO

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

The status of a AIP can be:

* **Pre-Merge**: a well-formed AIP has been written and a PR opened. The
  "Status" line can list Draft when in this state.
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

When deciding on Draft status, at least one WG member must review the entire
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
AIP is documenting already adopted practice), a AIP can move directly to Active
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
the formality and maturity of accepted standards. The first is, does draft
status mean *could* be implemented, or *has* been implemented? We chose
"could". Secondly, for active (or "final") status, is the proposal *expected*
to be dominant in the wild, or *is it already* dominant in the wild? We chose
"expected". In both cases we are emphasizing clarification and stabilization of
new ideas, as opposed to enforcing interoperability of competing formulations
of the same idea. In short, we expect AIPs to lead (rather than tail)
implementation.

Time limits and default outcomes are used to prevent proposals could get stuck
in an ambiguous indefinite state anywhere along the process. "Draft" status is
considered a stable state to linger in.

Setting expectations for "completeness" of proposals, having an editor quickly
skim proposals before jumping in to a full review, and acknowledging an explicit
"revise and re-submit" workflow are all attempts to head off the situation of
partial proposals being submitted and then significantly revised, which places
extra (time) burden on reviewers.


# Drawbacks
[drawbacks]: #drawbacks

TODO


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


[dep-1]: https://github.com/datprotocol/DEPs/blob/master/proposals/0001-dep-process.md
[bep-1]: http://bittorrent.org/beps/bep_0001.html
[ietf]: https://www.ietf.org/about/process-docs.html


# Unresolved questions
[unresolved]: #unresolved-questions

How mutable should "Draft" Standards AIPs be over time? What about
Informational AIPs? Should there be an additional status ("Living"?) for AIPs
that are expected to evolve, or is this against the whole philosophy of having
specific stable documents to reference? This is expected to be clarified while
this AIP itself is in Draft status.

Does "Active" status mean that implementation is *mandatory*, and that features
*must* be implemented unless they are explicitly optional? How would this
expectation be enforced for third-party software? This is expected to be
clarified when concrete examples arise.

# Changelog
[changelog]: #changelog

TODO

