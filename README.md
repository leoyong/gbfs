# General Bikeshare Feed Specification
Documentation for the General Bikeshare Feed Specification, a standardized data feed for shared mobility system availability.

## What is GBFS?
The General Bikeshare Feed Specification, known as GBFS, is the open data standard for shared mobility. GBFS makes real-time data feeds in a uniform format publicly available online, with an emphasis on findability. GBFS is intended to make information publicly available online; therefore information that is personally identifiable is not currently and will not become part of the core specification.

GBFS was created in 2014 by Mitch Vars (@mplsmitch) with collaboration from public, private sector and non-profit shared mobility system owners and operators, application developers, and technology vendors. The [North American Bikeshare Association’s](http://www.nabsa.net) endorsement, support, and hosting was key to its success starting in 2015. In 2019, NABSA chose MobilityData to govern and facilitate the improvement of GBFS. MobilityData hosts a [GBFS Resource Center](https://gbfs.mobilitydata.org/) and a [public GBFS Slack channel](https://mobilitydata-io.herokuapp.com/) - you are welcome to contact us there or at <specifications@mobilitydata.org> with questions.  

GBFS is intended as a specification for real-time, read-only data - any data being written back into individual shared mobility systems are excluded from this spec.

The specification has been designed with the following concepts in mind:
*	Provide the status of the system at this moment
*	Do not provide information whose primary purpose is historical

The data in the specification contained in this document is intended for consumption by clients intending to provide real-time (or semi-real-time) transit advice and is designed as such.

## Read the spec & version history
* [v1.0](https://github.com/NABSA/gbfs/blob/v1.0/gbfs.md)
  * 2019 December 20 - GBFS copyright [transfered to NABSA](https://github.com/NABSA/gbfs/commit/b1260b9c59eeff810a62e0aedc72ce1d4fb8f3ab)
  * 2015 November 05 - GBFS V1.0 Adopted by NABSA board - [Original draft spec in a Google doc](https://docs.google.com/document/d/1BQPZCKpem4-n6lUQDD4Mi8E5hNZ0-lhY62IVtWuyhec/edit#heading=h.ic7i1m4gcev7) (reference only)
  * 2015 August - Latest changes incorporated and name change to GBFS (comments from Motivate, 8D, others)
  * 2015 June - Proposed refinements (prepared by Jesse Chan-Norris on behalf of Motivate)
  * 2015 January - NABSA Draft (prepared by Mitch Vars)
* [v1.1-RC (Release Candidate)](https://github.com/NABSA/gbfs/blob/v1.1-RC/gbfs.md)
  * [#25](https://github.com/NABSA/gbfs/pull/25) - Add deep links for iOS, Android, and web apps
  * [#181](https://github.com/NABSA/gbfs/pull/181) - Add `feed_contact_email` field to `system_information.json`
  * [#188](https://github.com/NABSA/gbfs/pull/188) - GBFS documentation versioning and and feed conformance (adds `gbfs_versions.json`)
* [v1.1](https://github.com/NABSA/gbfs/blob/v1.1/gbfs.md)
  * [#25](https://github.com/NABSA/gbfs/pull/25) - Add deep links for iOS, Android, and web apps
  * [#181](https://github.com/NABSA/gbfs/pull/181) - Add `feed_contact_email` field to `system_information.json`
  * [#188](https://github.com/NABSA/gbfs/pull/188) - GBFS documentation versioning and and feed conformance (adds `gbfs_versions.json`)
* [v2.0-RC (Release Candidate)](https://github.com/NABSA/gbfs/blob/v2.0-RC/gbfs.md)
  * [#182](https://github.com/NABSA/gbfs/pull/182) - Require `license_url`, add attribution fields 
  * [#189](https://github.com/NABSA/gbfs/pull/189) - Require autodiscovery gbfs.json file, define feed names
  * [#195](https://github.com/NABSA/gbfs/pull/195) - Clarify `num_bikes_available` and `num_docks_available`
  * [#196](https://github.com/NABSA/gbfs/pull/196) - Change boolean from 1/0 to true/false
  * [#147](https://github.com/NABSA/gbfs/pull/147) - Rotate `bike_id` on `free_bike_status`
* **[v2.0: Current version](https://github.com/NABSA/gbfs/blob/v2.0/gbfs.md)**
  * [#189](https://github.com/NABSA/gbfs/pull/189) - Require autodiscovery gbfs.json file, define feed names
  * [#195](https://github.com/NABSA/gbfs/pull/195) - Clarify `num_bikes_available` and `num_docks_available`
  * [#196](https://github.com/NABSA/gbfs/pull/196) - Change boolean from 1/0 to true/false
  * [#147](https://github.com/NABSA/gbfs/pull/147) - Rotate `bike_id` on `free_bike_status`
* [v2.1-RC (Release Candidate)](https://github.com/NABSA/gbfs/blob/v2.1-RC/gbfs.md)
  * [#136](https://github.com/NABSA/gbfs/pull/136) - Add vehicle type definitions
  * [#219](https://github.com/NABSA/gbfs/pull/219) - Add geofencing, virtual station, and dockless support
* [v2.1-RC2 (Release Candidate)](https://github.com/NABSA/gbfs/blob/v2.1-RC2/gbfs.md)
  * [#261](https://github.com/NABSA/gbfs/pull/261) - Aggregate available vehicle_types at a station
  * [#252](https://github.com/NABSA/gbfs/pull/252) - Extend system_pricing_plans.json
* [v3.0-RC (Release Candidate)](https://github.com/NABSA/gbfs/blob/master/gbfs.md)
  * [#182](https://github.com/NABSA/gbfs/pull/182) - Require `license_url`, add attribution fields 

## Governance & Overview of the Change Process
GBFS is an open specification, developed and maintained by the community of producers and consumers of GBFS data.
The specification is not fixed or unchangeable. As the shared mobility industry evolves, it is expected that the specification will be extended by the GBFS community to include new features and capabilities over time. If you are new to engaging with the community on this repository, firstly welcome! Please identify which organization you represent when posting. 

To manage the change process, the following guidelines have been established.

* Anyone can propose a change.
* A change is proposed by opening a Pull Request at the GBFS GitHub repository. The proposer becomes “The Advocate”. Comments and feedback from the GBFS community are received to iterate on the proposed change. Discussion lasts for as long as necessary to address questions and revisions, but must be at least 7 calendar days.
* After 7 calendar days, The Advocate can call for a vote. Should The Advocate not call a vote or respond to comments from the community for a period of 30 full calendar days, anyone in the community can call for a vote. Vote lasts the minimum period sufficient to cover 10 full calendar days. Voting ends at 23:59:59 UTC. The vote announcement must conform to this template: 
  * *I hereby call a vote on this proposal. Voting will be open for 10 full calendar days until 11:59PM UTC on X.<br /> Please vote for or against the proposal, and include the organization for which you are voting in your comment. <br /> Please note if you can commit to implementing the proposal.*
* The person calling for the vote should announce the vote in the [GBFS Slack channel](https://mobilittydata-io.slack.com) with a link to the PR. The message should conform to this template:
  * *A vote has been called on PR # [title of PR] (link to PR). This vote will be open for 10 full calendar days, until 11:59PM UTC on X. Please vote for or against the proposal on GitHub.*
* MobilityData will both comment on the PR on GitHub and send a reminder in the GBFS Slack channel when there are 2 calendar days remaining on the vote. The reminder should conform to this template: 
  * Slack: <br />*Voting on PR # [title of PR] (link to PR) closes in 2 calendar days. Please vote for or against the proposal on GitHub.* 
  * GitHub:<br />*Voting on this PR closes in 2 calendar days. Please vote for or against the proposal, and include the organization for which you are voting in your comment. Please note if you can commit to implementing the proposal.*
* Once a vote is called, a "Vote Open" label will be added to the PR. After the 2 day reminder, the label will be replaced with "Vote Closing Soon", once the vote is closed, the label will become either “Vote Passed” or “Voted Failed” depending on the vote outcome.
* At least 3 votes in favor, in addition to the author of the Pull Request, are required for a proposal to pass. At least one of these votes must be from a producer and at least one from a consumer.
* The advocate should cancel a vote if significant changes are made to the proposal after stakeholders have already voted.
* Should the vote fail, the advocate can choose to continue work on the proposal with the feedback received and restart the governance process, or abandon the proposal by closing the Pull Request. Another interested member of the community can take over the proposal if they feel the addition is valuable. 
* Implementation requirements are that both 1 producer and 1 consumer commit to implementing the changes. A change is placed into RC status pending implementation. Once implemented successfully, the change is merged into an official release.
* Editorial changes as well as items that are not found in gbfs.md do not need to be voted on. Extensions that include new capabilities and features must be voted on.
* Issues and pull requests will be considered stale after 120 days, at which point participants will be notified via comment. Should they wish to keep the discussion open, it is the responsibility of the participants to re-engage in the conversation. If there is no re-engagement, the issue or pull request will be closed 60 days after the stale date. 
 

## Specification Versioning
To enable the evolution of GBFS, including changes that would otherwise break backwards-compatibility with consuming applications, GBFS documentation is versioned. Semantic versions are established by a git tag in the form of `vX.Y` where `X.Y` is the version name. Multiple changes (commits) may be batched into a single new release.

A whole integer increase is used for breaking changes (MAJOR changes). A decimal increase is used for non-breaking changes (MINOR changes or patches).

Examples of breaking changes include:

* Adding or removing a required endpoint or field
* Changing the data type or semantics of an existing field

Examples of non-breaking changes include:
 
* Adding or removing an optional endpoint or field
* Adding or removing enum values
* Modifying documentation or spec language in a way that clarifies semantics or recommended practices

### Version Release Cycles
* There is no strict limitation on the frequency of MAJOR releases, but the GBFS community aims to limit the MAJOR releases to 2 or fewer every 12 months. To limit releases, breaking changes can be batched together.
* MINOR changes may be applied at any time. There is no guideline to limit the number of MINOR changes. MINOR changes may be batched or released immediately, at the discretion of the pull request author and advocate.
* GBFS documentation will include a designated long-term support (LTS) branch. The LTS branch would maintain its LTS status for at least 2 years, after which a new LTS release and branch would be designated. The LTS branch will be determined according to the GBFS voting process. Non-breaking changes (MINOR) will be applied to the LTS branch when relevant.


## Guiding Principles
To preserve the original vision of GBFS, the following guiding principles should be taken into consideration when proposing extensions to the spec:

* **GBFS is a specification for real-time or semi-real-time, read-only data.**
The spec is not intended for historical or archival data such as trip records.
The spec is about public information intended for shared mobility users.

* **GBFS is targeted at providing transit information to the shared mobility end user.**
 Its primary purpose is to power tools for riders that will make shared mobility more accessible to users.  GBFS is about public information. Producers and owners of GBFS data should take licensing and discoverability into account when publishing GBFS feeds.

* **Changes to the spec should be backwards-compatible, when possible.**
Caution should be taken to avoid making changes to the spec that would render existing feeds invalid.

* **Speculative features are discouraged.**
Each new addition to the spec adds complexity. We want to avoid additions to the spec that do not provide additional value to the shared mobility end user.

## Systems Implementing GBFS
This list contains all known systems publishing GBFS feeds and is maintained by the GBFS community. If you have or are aware of a system that doesn’t appear on the list please add it.

* [systems.csv](systems.csv)

If you would like to add a system, please fork this repository and submit a pull request. Please keep this list alphabetized by country and system name.

## GBFS and Other Shared Mobility Resources
Including APIs, datasets, validators, research, and software can be found [here](https://github.com/NABSA/micromobility-tools-and-resources).

## Copyright
The copyright for GBFS is held by the [North American Bikeshare Association](https://nabsa.net/). 
