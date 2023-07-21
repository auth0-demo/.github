# Contributing #

Please ensure you take on board the notes, guidelines, and other information contained within this contribution guide. 
These assets reflect the agile ways of working for the Demo Engineering team; they allow us to rapidly develop field 
facing solutions that benefit the majority while ensuring consistency, reliability and a high level of confidence 
in their functionality.

## Contribution Guidelines and Ownership ##

The code, assets, and templates stored and maintained within this Organisation are owned by the Demo Engineering team,
and they are generally maintained by them also.
However, this does not mean contributions from outside the team is unwelcome, rather it establishes a base level of 
accountability for the components stored within. There is likely to be a need or requirement for other teams or individuals to contribute to these sets of components and those contributions are welcomed with open arms, provided they take on board the following guidelines.

Demo Engineering is not able to support or take ownership of every component that falls under demo.okta; our solutions are focused on providing the building blocks to enable the field to build and distribute amazing meaningful demonstrations to anyone, anywhere, anytime. Our solutions outside of these building blocks cater for what we call 'the 80%', that being that the usage of these solutions will encapsulate 80% of all demo needs. As a result we have created various soltions (each detailed in the relevant README) that replicate our solutions or accelerate the time it takes the field to develop and deploy their own contributions. These include but are not limited to;

 * Community Applications
 * Community Resources
 * Node Quickstart
 * Resources Quickstart
 * Unified Labs

Support for field developed solutions lies with the owner or collaborators of the solution; as does the code ownership. Demo Engineering will supply best endeavours support where possible. 

Demo Engineering is responsible for oversight of the code developed into these repositories, as well as the on going support for the solution as a whole. Final sign off on code commit to these repositories is owned by Demo Engineering.

## Branching ##

The repositories within the Demo Enginnering organisation utilise a set of automations that ensure consistency and allow the team to focus on producing best in class solutions that make it easy to demonstrate Okta solutions and continue to evolve our offering to allow anyone to demonstrate even the most of complex of products.

To facilitate this automation when creating a branch to house your code your branch name should be prefixed with what the code brings to the platform. This allows automation to automatically categorise Pull Requests, and generate relase notes for each code release. The following conventions should generally be used;

* Branches prefixed with `feature/` or `feat/` will be labelled as features
* Branches prefixed with `fix/` will be labelled as defects
* Branches prefixed with `docs/` or `documentation/` will be labelled as documentation
* Branches prefixed with `chore/`, `test/` or `ci/` will be labelled as chores
* Branches prefixed with `refactor/` will be labelled as a refactor

## New Features and Improvements ##

In general when there is a need and if it feels right that the new feature or improvement belongs in a repository;
the Demo Engineering team should be engaged at an early stage so they can facilitate the design, and implementation of the work. We expect situations like this to be rare; however as the team are accountable for the code we should have a handle on the design of anything new going in. Communication and keeping us informed is always appreciated.

The exceptions to this are currently anticipated to be in the areas of community resources and labs. 

Community Resources that wish to use Demo Engineering infrastructure for running can be added the `managed-resources` repository without engaging Demo Engineering at the start. As usual Demo Engineering will have final sign off and can provide support with how to structure the development and code for success.

## Writing tests ##

Demo Engineering employ a pyramid strategy for testing core solutions; testing where necessary to give confidence in our solutions as early as possible (aslo known as a 'shift left strategy'). Our solutions use automated testing strategies with;
* large amounts of unit tests (prodominently written in Jest) to test individual functions in Isolation.
* several solutions employ component testing; testing a set of functions that are linked together with mocking either side. This is usually because testing at a functional level in costly and not practical.
* functional tests that test our solutions outside of any environment end to end with mocked external dependencies; written as BDD style tests in Cucumber. These tests allow us to exercise our solutions with assumed integration of other components.
* integration tests that exercise our solution end to end in a near live environment; written as BDD style tests in Cucumber. These tests allow us to exercise our solutions with real integration in real enviromments.

The team prefer a high level of code coverage, coupled with a relative high level of mutation coverage. All unit tests have been written in Jest. Unit tests should be self explanatory and self documenting.

Component tests exercise small parts of the library in isolation where mocking at a unit level becomes too heavyweight
and strenuous to maintain. Having a mix of both allows us to be more confident in the integration between the functions of the components.

Any tests that are introduced should be clear from their intent and follow the existing style where possible. Where
style or format of the tests needs to differ this should be communicated and agreed with members of the Demo Engineering team.

## Code Review ##

All code within this organisation will be peer-reviewed through Pull Requests (PRs). All repositories have been
restricted on the _main_ branch to prevent direct writing (other than by CI/CD actions and Demo Engineering overrides), 
and as such PRs will be required to merge to this branch. 

All Pull Requests require approval at minimum from at least one 'code owner' which is derived from the CODEOWNERS file. 
The Demo Engineering Team are by default the code owners; but this will vary depending on the repository and the files being altered. 

Raising a PR will automatically add the relevant code owners and notify them. There is nothing additional required.

## Other Guidelines ##

The Demo Engineering team have specific ways of working that can be found [here](https://oktawiki.atlassian.net/wiki/spaces/DemoEng/pages/2790066663/Agile+Charter). As such the team have several artifacts around their agile process;
 * [Definition of Ready](https://oktawiki.atlassian.net/wiki/spaces/DemoEng/pages/2790132059/Definition+of+Ready)
 * [Definition of Done](https://oktawiki.atlassian.net/wiki/spaces/DemoEng/pages/2790066643/Definition+of+Done)
 * [Bug Triage](https://oktawiki.atlassian.net/wiki/spaces/DemoEng/pages/2735934308/Bug+Triage)

Please take these into consideration - most notably the Definition of Done and Bug Triage before raising Pull Requests
or Defects against components in this organisation.

## Getting Help ##

The Demo Engineering team are always available and happy to lend their expertise. Our internal team slack channel is
[#demo-okta](https://okta.slack.com/archives/CE676UAUS) where we are happy to answer questions or help
investigate issues. To facilitate issue investigation we prefer having as much information as possible to make this
quick, easy and seamless for all involved. We ask that as many of the details listed [here](https://oktawiki.atlassian.net/wiki/spaces/DemoEng/pages/2735934308/Bug+Triage) are given when
asking for help with issue investigation.
