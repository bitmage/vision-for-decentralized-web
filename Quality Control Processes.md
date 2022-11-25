Created On: [[2022-10-22]] 

Quality control proceeds through four phases:

* Production
* Quality Control
* Selection
* Deployment

##### Production

Assets produced need to be content addressed, with meta data stored in a [[Public Ledger]].  [[Content Addressing]] allows for additional information to be associated with the original artifact.  It also means that as we proceed through all the phases that follow, we are referring to a known artifact which has not been altered even by a single digital bit.

##### Quality Control

Quality Control can be through multiple lenses such as security, fit for purpose, and appropriate content, described more fully in [[App Auditing]].  Statements by auditors should be signed as [[Public Claims]] recorded in a [[Public Ledger]].

##### Selection

Users and observers of the app ecosystem can compose all of the available information on a particular software package, applying their own preferences and search and selection criteria.  They can find packages appropriate for a particular task, and can evaluate similar packages to find the one that best suits their needs.  They will experience a level of transparency and coherence as the packages are evaluated on common criteria that they have selected.

##### Deployment

In the context of a mobile application, this involves the user installing an app from the [[App Marketplace]].  In the context of a server, it may involve a [[Docker]] container deployed to a [[Kubernetes]] cluster.  Regardless of the format of the package, we should be able to create a standardized meta-data format to facilitate the process described here.

In addition, the person deploying the software may further contribute to the Quality Control phase, adding signed statements about their usage experience.  These should fit into the existing meta-data format without further modification.  And usage statements can then be presented and considered during the Selection process.

### Conclusions

This process essentially decouples the Producer, Auditor, App Store, and User so that each one of these roles can be fulfilled by an ecosystem, and the handoffs between each one are facilitated by a common data format.  This creates the maximum amount of trust and transparency, and should ultimately create better outcomes for the software that ends up being deployed by end users.