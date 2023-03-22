# Ximira NOVA Version Management

## Version Labeling

### Software

For all *software* releases, including all documentation referencing the requirements, design or use of a software version, Ximira will use the following:

Scheme      |   Description
---         |   ---
YY.MM       |   Major Release
YY.MM-A     |   Revision
YY.MM-A.B   |   Minor Revision or Patch

`YY` will represent the year of the release. `MM` will represent the approximate month of the release. `A` will be a sequential number beginning with `0` and `B` will be a sequential number beginning with `1`. `YY.MM` is assumed to be short for `YY.MM-0`, meaning that minor revisions or patches made to a Major Release will be of the form `YY.MM-0.B`. For example, the first minor patch to version `23.10` will be version `23.10-0.1`.

Ximira will target a `10-4` release cadence, meaning a Fall `10` release around October and a Spring `04` release around April.

Revisions and patches will be released as needed to improve performance, fix bugs, and patch security vulnerabilities. Unless it is otherwise unavoidable due to a major functional flaw or security issue, no breaking changes should be introduced with revisions.

At present, Ximira has defined no product support windows. Therefore, there is currently no provision for "rolling" or "interim" or "long-term support" releases. This will be revisited in time.

### Hardware

For all *hardware* releases, including all documentation and other artifacts referencing the requirements, design or use of the hardware and any firmware, Ximira will use the following scheme:

Scheme  |   Description
---     |   ---
vN      |   Product Version
vN-A    |   Major Revision
vN-A.B  |   Minor Revision or Patch

`vN` represents the version of the product. A change here will represent a major redesign that might render the product incompatible with prior versions or other related peripheral hardware. For example, a new CU design that necessitates and entirely new Sling and PU design. Multiple hardware versions may remain supported and updated in parallel.

As with the software version standards defined above, major `A` revisions are integer values starting with an *assumed* `0`. Minor `B` revisions should be sequential integers beginning with 1. For hardware consisting of multiple components (e.g., case, PCB, wiring diagram, firmware, etc.), these may increment independently. Every effort should be made to insure that the backwards compatibility is maintained and/or clear upgrade paths defined between revisions.

### Other Documentation and Miscellaneous Artifacts

For all documents, diagrams, etc. that are not specifically targeting a software or hardware release, Ximira maintains no explicit version labeling standards. Such items should simply be maintained using Ximira's version control standards.



## Version Control Standards

TBD
