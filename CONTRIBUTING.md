# Contributing #

Please ensure you take on board the notes, guidelines, and other information contained within this contribution guide. 
These assets reflect the agile ways of working for the Demo Engineering team; they allow us to rapidly develop field 
facing solutions that benefit the majority while ensuring consistency, reliability and high level of confidence 
in their functionality.

## Contribution Guidelines and Ownership ##

The code, assets, and templates stored and maintained within this Organisation are owned by the Demo Engineering team,
and they are generally maintained by them also.
However, this does not mean contributions from outside the team is unwelcome, rather it establishes a base level of 
accountability for the components stored within. There is likely to be a need or requirement for other teams or individuals
to contribute to these sets of components is welcomed with open arms, provided it takes on board the following
guidelines.

## Branching ##

The repositories within the Demo Enginnering organisation utilise a set of automations that ensure consistency and allow the 
team to focus on producing best in class solutions that make it easy to demonstrate Okta solutions and continue to evolve our 
offering to allow anyone to demonstrate even the most of complex of products.

To facilitate this automation when creating a branch to house your code your branch name should be prefixed with what the code brings to the platform

## New Features and Improvements ##

In general when there is a need and if it feels right that the new feature or improvement belongs in this repository;
the Demo Engineering team should be engaged at an early stage so they can facilitate the design, and implementation of the work.
We expect situations like this to be rare; however as the team are accountable for the code we should have a handle on the design of
anything new going in. Communication and keeping us informed is always appreciated.

## Writing tests ##

Since this is a set of common components there are no integration tests. These are left for implementation in the
respective services where the component is used, alongside suitable functional tests that exercise the different
security aspects (user types, differing roles, differing permissions, etc).

There are unit tests, component tests (across a few integral classes), and functional tests. The team prefer a high
level of code coverage, coupled with a relative high level of mutation coverage. All tests have been written in a JUnit
style - so there are no BDD tests or any cucumber framework involved. Unit tests are self explanatory.

Component tests exercise small parts of the library in isolation where mocking at a unit level becomes too heavyweight
and strenuous to maintain. Having a mix of both allows us to be more confident in the integration between the classes of
the components.

The more functional tests are used in the context of Spring Boot services (currently). A Test Controller is provided
and spun up with varying endpoints each with different access control restrictions. These endpoints are then called from
outside their container with valid or invalid JWTs (for verification testing) and with differing user types, roles, and
permissions to ensure our structures and access control validation mechanisms are working correctly.

Any tests that are introduced should be clear from their intent and follow the existing style where possible. Where
style or format of the tests needs to differ this should be communicated and agreed with members of the Customer team.

## Code Review ##

All code within this organisation will be peer-reviewed through Pull Requests (PRs). All repositories have been
restricted on both the _main_ branches to prevent direct writing (other than by CI/CD actions and Demo Engineering overrides), 
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
