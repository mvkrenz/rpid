## Overview and Introduction

The expansion of the research community’s ability to collect and store data has expanded more
rapidly than its ability to catalog, make accessible, and make use of data. Major challenges facing the
scientific research enterprise are the basic problems of making data discoverable, accessible, and reusable
at Internet scales; and making it possible to use data to replicate analyses done in published
research [1]. The importance of this issue is at the center of many recent initiatives in Open Science [2]
and Open Data [3] and many technical articles, position papers, and even books [4]. To address these
deficiencies and to enable more reusable data options in the current research data landscape, we
propose to integrate a set of preexisting and newly designed software solutions into the previously funded
Robust Persistent Identification of Data (RPID) [5] testbed. These additional software components will
provide an end-to-end fabric of data services built on the Digital Object Architecture (DOA) [6] framework
and the core principles of making data findable, accessible, interoperable, and reusable.

The goal of the DOA is to specify an architecture that would implement principles of data discovery,
access, and reuse at Internet scales. The ongoing development of DOA has been led since the late
1980s by the US-based Corporation for National Research Initiatives [7], and by the DONA foundation [8].
The DOA consists of the following [9]: A Digital Object (DO) is a sequence of bits, or a set of sequences
of bits, in which there is value and having as an essential element an associated unique persistent
identifier. The Identifier/Resolution Protocol (IRP) “is a rapid-resolution protocol for creating, updating,
deleting, and resolving identifiers that are globally managed and allotted.” The Digital Object Interface
Protocol (DOIP) is “a protocol for software applications (‘clients’) to interact with ‘services’ which could be
either the digital objects or the information systems that manage those digital objects.” The
Identifier/Resolution Service enables allotment of unique identifiers to digital objects regardless of the
location or technology used to access the object, and the resolution of the identifiers to current state
information about the corresponding digital object. The Repository Service manages digital objects
including the provision of access to such objects based on the use of identifiers, and with integrated
security. Together with the DOIP, the Repository Service enables a long-lived mechanism for depositing
and accessing digital objects. Finally, The Registry Service is a specialized repository system that stores
metadata about digital objects that are managed by one or more repository systems. Figure 1 provides a
high-level view of the DOA. At the core of the DOA is the Persistent ID (PID), which provides unique, long
lasting identifiers that resolve to the digital object (DO) they identify. In recent years it has become good
data practice to use PIDs not only for publications but also for data products. PIDs have been used for
many years to uniquely identify publication data in the form of Digital Object Identifiers [10], Handles [11],
Archive Resource Keys (ARKs) [12], and URNs [13].

Since the initial development of the DOA, the International Council for Science - World Data Systems
(ICSU-WDS) [14] have developed principles for access and use of data at scale: data must be Findable,
Accessible, Interoperable, and Reusable (FAIR) [15]. The DOA may be implemented in a way that
supports FAIR access principles, dependent of course on individual authors providing rights to use data
they generate and make them available.

Various software components specific to the DOA have been built by CNRI, DONA, and others, and
in some cases software that implements elements of the DOA are in relatively widespread use. We make
two observations. First, there are several interesting early projects - many focused on a particular domain
or type of data. Second, however, is that there is not yet a multi-purpose, scalable, and generally usable
implementation of the DOA for research data. The current state is that a general purpose DOA is just
beyond the fingertips of researchers, not quite obtainable due to multiple inconsistent data management
mechanism implementations, widely varying data access solutions, and no common interaction protocol
for preforming standard operations on digital objects.

![alt text](https://github.com/rpidproject/rpid/blob/master/docs/ERPID-Figure1.png "Digital Object Cloud")

We are currently leading a two-year pilot effort to create a testbed to implement some foundational
elements of the DOA - funded by NSF award 1659310 - “CC* Storage: Robust Persistent Identification of
Data (RPID)” [16]. Current information about this project and its code repository are available online in the
RPID Project Github repository [17]. The specific elements of the Digital Object Architecture and our
progress in implementing those elements under the existing RPID grant award are described in Table 1
below, along with the new steps we propose to take in this project in implementing an Enhanced RPID as
a full reference implementation of the DOA. All development proposed here is new work and not included
in the scope of work of the current NSF award. Ongoing RPID work will be completed according to plan.

![alt text](https://github.com/rpidproject/rpid/blob/master/docs/ERPID-Table1.png "Core Element Comparison")

During the RPID project we built the two most important foundational elements of a DOA
implementation. A Handle Service issues PIDs and provides resolution services, which consist of taking a
PID and resolving it to current state information about the digital object contained in a registry in the form
of user defined key-value pairs. The second major component is a Data Type Registry [20] (DTR), which
provides type information for each registry field. This allows consistent and programmatic interaction with
the state information. The Data Type Registry is a component of the Resolution System of the overall
DOA and an output of the Research Data Alliance [21]. We also developed and evaluated existing APIs
for use by the use cases that are already users of the existing testbed: PRAGMA Rice Genomics and
SEADTrain environmental sensors.

**Proposed Work:** We propose to complete the end-to-end DOA environment that is both a full
reference implementation of the entire DOA as currently specified by CNRI and DONA, and fully
embodies FAIR principles. We will do this by adding two new components to the existing RPID testbed.
   * Digital Object Interface Protocol [22] (DOIP), which defines common operations that can be
carried out on digital objects. This protocol defines standard operations (CREATE, GET,
UPDATE, DELETE) and would allow tools utilizing E-RPID to interact directly with data objects.
   * Repository Mapping Service, which would allow existing repositories to remain unchanged while
mapping their content to the DOA environment. This would allow E-RPID (or other DOA system)
to operate with a homogeneous digital object view across heterogeneous systems.

We further propose to take steps that will lead to the broader adoption of our reference
implementation. Data interoperability tools are a challenge to create because they become meaningful
and useful only when widely adopted. We will be guided in our work by best current understandings in the
sociology of technology adoption - specifically that technology adoption choices are driven by
performance expectancy (perceived value), effort expectancy (perceived ease of use), social influence,
and facilitating conditions (including knowledge of a technology and the belief that end users will find it
accessible) [23]. One of the things we understand from our own experiences in creating technology as
well the sociological literature is that a perceived high amount of effort to adopt a new technology can
take precedence over the potential benefit of adoption. That is, high cost of adoption can trump value of a
new tool even when that new tool might be widely valuable. Thus, in our work we will focus on lowering
the real and perceived barriers to adoption and use. The implementation of a DOIP will lower barriers to
development of data access and use tools. The Repository Mapping Services will lower the barriers for
adoption effort of existing and future repositories, and educational materials that we will develop will
provide a clear value statement and core knowledge needed for interacting with a DOA environment.
These components will stimulate data tool development, entice good data management practices
including emphasizing the utility of early assignment of PIDs to data products, and fuel future work on the
core of a new data-centric research cyberinfrastructure.

This E-RPID testbed will promote high-level data filtering, programmatic interoperability mechanisms,
computational workflow provenance information recording, and the ability to assign long-term identities to
each of these aspects. Each of these aspects could have a transformative impact on scientific data reuse.
The proposed E-RPID testbed will be, as far as we know, the first full implementation of the DOA in a
research environment. Because of the capabilities for repository mapping, adoption of the technology we
are developing can be done by other projects without giving up their existing work and implemented code.
The proposed E-RPID testbed will be housed on the NSF-funded Jetstream system, led by the Indiana
University Pervasive Technology Institute. While results have not been published CNRI technicians report
the software underlying E-RPID will have capacity to create PIDs at a rate of over 1000 per second and
resolve PIDs at a rate of 10,000 per second (when hosted on an Amazon Web Services m3.large
instance [24]). If this technology does in fact gain substantial adoption, then we will either pursue
additional funding from the NSF to operate this as a national service or look to other large NSF-funded
cyberinfrastructure projects for ways to implement the services we are developing as production-quality
services suitable for serving the entire population of NSF-funded researchers.

## Use Cases

In this section we describe a number of projects that have agreed to the value of this work and to
participate in the E-RPID testbed. Additional E-RPID use cases will be recruited and supported based on
the limited availability of effort. We anticipate the support capacity to bring 5-10 new use cases into the E4
RPID testbed environment, supplemented by documentation and outreach materials. New use case will
be reviewed by the PI team based on diversity of data (as compared to existing use cases), availability of
technical assistance from the client, and benefit of the work to the testbed and existing stakeholders.

**PRAGMA Rice Genomics:** The PRAGMA Rice Genomics Project [25] mines data from the
International Rice Genebank Collection with the goal of developing sustainable rice varieties to support
future population growth. To achieve this goal, current data collections must be highly interoperable.
During the original RPID project PRAGMA used the testbed to assign PIDs, resolve state data and gather
typing information. In the process of making the RPID useful to the PRAGMA Rice Genomics projects,
some functionality called for in the DOA - in particular the DOIP - was implemented in non-scalable ways
through custom APIs. The needs faced by the PRAGMA Rice Genomics project and not met by existing
RPID project include reducing effort for future dataset adoption. This use case is also interested in
evaluating the new components of the E-RPID testbed and researching provenance information as part of
the PID Kernel Information.

**SEADTrain:** The SEADTrain [26] project provides a cloud-based API for researchers and students to
analyze environmental data collected by sensors throughout Taiwan. This service is implemented on
Microsoft Azure resources. SEADTrain uses RPID to assign PIDs early in the data lifecycle allowing highlevel
time-based data filtering. SEADTrain has also adopted the work of the RDA PID Kernel Information
Interest Group [27] and implemented it through the RPID services. This kernel information allows general
metadata and provenance information to be stored in the state data with the RPID Handle resolution
service. The needs faced by the SEADTrain project and not met through the work on the existing RPID
project include reducing effort levels for future DOA adoption. The implementation of the DOIP and
repository mapping services will ease the learning curve for developers and eliminate the need for custom
software implementations. This use case will also evaluate representing collections with PIDs.

**Galaxy Bioinformatics Workflow and Jetstream:** The Galaxy bioinformatics workflow system is
one of the most widely used bioinformatics workflow systems in the world, with tens of thousands of
current users [28]. Galaxy promotes re-use of pre-defined bioinformatics workflows to enable replication
and expansion of analyses of data sets that underlie research in biology, biochemistry, and biomedical
research. The Galaxy project currently maintains a list of commonly used workflows [29], but there is no
way to access these workflows save by human perusal of this web page.

Enhancing replicability of scientific data analysis and in particular improving ease of access to
bioinformatics tools are goals of the Jetstream project. At present, it is possible to publish a Virtual
Machine image, including data and scripts, with a DOI, through IU’s Scholarworks digital repository [30].
We propose to create a set of tools that will allow a person to discover a Galaxy workflow through use of
E-RPID tools, and then if that person has an account on Jetstream, invoke that workflow on Jetstream
using input data set(s) also specified via PIDs issued through the E-RPID project. We will work with the
Galaxy Project leaders at Johns Hopkins University to implement this capability for the most widely used
workflows by their community. We will work with the Jetstream team (another subunit of the IU Pervasive
Technology Institute) to make sure that potential users of this capability are easily able to create accounts
on Jetstream and make use of that system.

**Science Gateway Platform as a Service (SciGaP):** The SciGaP project, led by E-RPID Co-PI
Pierce, develops the open source Apache Airavata software framework for science gateways and
operates this platform as a service for over thirty client gateways. Science gateways [31], including
Galaxy described previously, provide user environments and middleware that help expand the use of
scientific computing resources. Gateways target communities of users and help them manage, share, and
replicate computational experiments. Publishing data and metadata about user sessions, workflows, and
outputs in a way that is independent of a particular gateway is a much needed capability. We will
integrate the protocol mechanisms proposed here into Apache Airavata middleware’s development track
and will use it to both evaluate and act as a driving use case for E-RPID. We will also incorporate the
work described here into our Science Gateway Architectures course [32], which we teach each semester
to Computer Science graduate students at Indiana University.

## Testbed Description and Architecture

Figure 2 below describes the core elements we plan to implement as part of the E-RPID project,
building on work already done in the RPID project and other software created by other projects. The
overriding principle that each object on a given network, in this case the Internet, is addressable as an
independent entity, regardless of its current location, composition, owner, or other changeable attributes.
This puts identifiers at the heart of the architecture. To address an object, it must have a resolvable
identifier that provides the information clients need to address and interact with the object. Further, the
architecture provides a middleware approach to normalizing the great variety of existing information
management structures and processes, focusing on the digital object layer, a level of abstraction above
the existing structures and processes, such that each identified object can be associated with a set of
possible operations and both the operations and the identity of the object remain fixed over lower level
changes of process implementation or structure details.

Creating and leveraging this object layer requires 1) a set of mapping and brokering tools and
processes to create the virtual object level over the existing information structures, and 2) an object
interface protocol that optimizes interaction with the object layer by understanding how to query each
object for the set of operations that apply to it. The mapping and brokering tools would be specific to the
underlying data structures. Done correctly, the added layer of indirection would insulate clients executing
the common operations from the details of those underlying structures. The Digital Object Interface
Protocol (DOIP), which is currently in beta testing, is available open source [33]. An available reference
implementation is embedded in server software [34] that can provide access to the digital object layer
while providing multiple client interfaces, including the common web protocols as well as the native DOIP.
Figure 2 above gives a high-level graphical view of the entire architecture. Moving right to left, the basic
storage (in the form of digital objects) and existing information system environment is fronted by a series
of brokering and mapping services to create the DO layer, accessible by clients, both human and
machine, at the far left. The RPID project deployed many of the components shown here, while E-RPID
will introduce the remaining elements, specifically DOIP, and create the data specific mapping routines
needed to create the DO layer.

**Testbed Implementation:** The RPID testbed currently consists of a set of services hosted at IU on a
standard Linux cluster, with backup services running on Amazon Web Services to provide for 7 x 24
uptime of the testbed. As part of our E-RPID work we plan to move the entire primary testbed from its
existing cluster home at IU to the Jetstream cloud system - meaning that it will have as its primary
development platform the open source OpenStack cloud environment. This will promote re-use and
portability of the tools we are creating. We will retain AWS as our backup environment for hosting the ERPID
testbed components. Indiana University will maintain the testbed for two years beyond the grant
period allowing continued testing. While the RPID testbed components have proved stable, during this
extended lifetime support and maintenance will be done at best effort levels.

![alt text](https://github.com/rpidproject/rpid/blob/master/docs/ERPID-Figure2.png "ERPID Core Elements")

**Comparison to Related Work:** The work we propose is distinct from other, ongoing projects. Unlike
the current CNRI- and DONA-led work [35], we focus on extending, deploying, operating existing software
to create a full, end-to-end implementation of DOA. CNRI and DONA are focused on improving key
specific software elements at the core of the DOA model. Our proposed work can be distinguished from
the Dryad [36] project in two major ways. Dryad is a data repository for publication related data whereas
RPID interacts with data repositories but does not hold data, eliminating the need for additional data
movement and replication. RPID also encourages the use of PIDs early in the data lifecycle not after
publication this allowing researcher to interact with their data the same before and after publication. The
Named Data Networking [37] project proposes changing the underlying networking itself, whereas we
utilize the existing networking infrastructure with a middleware approach. The Globus Online [38] project
focuses on the movement of data in the form of files across the network. Our proposed work focuses on
the underlying information management needed for making decisions prior to network transfers.

## Milestones and Evaluation
The proposed project milestones are given in Table 2.

![alt text](https://github.com/rpidproject/rpid/blob/master/docs/ERPID-Table2.png "Project Milestones")

**Project Evaluation:** The project will be considered a success if the following goals are accomplished:
(1) The current RPID is updated with the components necessary to create an end-to end DOA testbed.
This will be evaluated by the use case participants to determine if the functionality of the testbed meets
their needs. (2) The E-RPID testbed demonstrates the performance required to scale. This will be done
by simulating load in a controlled E-RPID environment and monitoring performance. (3) We determine
that the DOIP is suitable for common research data interactions. We will report these finding to the RDA
Data Fabric Interest Group [40]. (4) We successfully demonstrate a generic mapping service for research
data and document usage, releasing prototype software in publicly available repository. (5) We engage
and support at least five additional use cases that do full evaluations of the E-RPID testbed.

## Project Management and Dissemination Plans

The project will be led by Rob Quick, Deputy Director of the Science Gateways Research Center,
which is itself a part of the IU Pervasive Technology Institute. Quick currently serves as PI of the RPID
project. He will be assisted in the proposed E-RPID project by Co-PIs Lawrence Lannom and Marlon
Pierce. Lannom is a Co-PI of the RPID project and brings experience in the development and operations
of the DOI system, data type registries, and other aspects of DOAs. Pierce is director of the Science
Gateways Research Center and will bring science gateway use cases to E-RPID. More information on
project leaders and their roles can be found in the attached CVs and budget justification. This project will
be advised by a Stakeholder Advisory Board (SAB), which will include representatives from each of the
projects listed as use cases. Beth Plale will represent the Pragma Rice Genomic and SEADTrain use
cases, James Taylor and Dave Hancock will represent the Galaxy and Jetstream use case and Marlon
Pierce will represent the SciGaP use case, additional members will include Mark Parsons from the Deep
Carbon Observatory [41] and Eric Nienhouse from the National Center for Atmospheric Research [42].
The latter two are potential adopters of E-RPID. The SAB’s function is to offer advice leading to greater
adoption of E-RPID. We plan one “in person” SAB meeting per year, with one additional SAB meeting
conducted as a teleconference.

Dissemination of information about E-RPID will leverage the existing dissemination activities of the IU
Pervasive Technology Institute and partner organizations, which reach more than 20,000 people per year,
typically including booth displays and tutorials at conferences such as the IEEE/ACM Supercomputing
conference, the Galaxy User Conference, and the Plant and Animal Genome Conference. As a sponsor
of Science Node [43], IUPTI can include sponsor-contributed content that is seen by over 80,000 readers.
Finally, we will create and publish training videos online through YouTube and supplement these with
written educational materials, making it straightforward for researchers and educators to implement the
tools we are creating in their research and teaching work.

## Intellectual Merit

The proposed project will create a realization of both the Digital Object Architecture and the FAIR
data principles, providing a full, end-to-end reference implementation that demonstrates how such
projects should be designed, implemented, and operated and also how to make such systems attractive
to and usable by a broad range of scientific clients. Such systems increase the publication, discovery, and
reuse of data, thus contributing to the greater integrity of the scientific enterprise. This reference
implementation will be based on a combination of third party software, prior work by the proposal team as
part of the predecessor RPID project, and new work. The resulting Enhanced RPID (E-RPID) testbed will
contribute to knowledge across the fields of computer science and cyberinfrastructure. This work will be
performed in the context of the Research Data Alliance (RDA), particularly the RDA Kernel Information,
the Data Type Registry, Data Fabric, and PID working groups to form reciprocally beneficial
implementation feedback loops. The work proposed here will finally realize ideas that are years or even
decades old. A full implementation of the DOA, embodying the FAIR principles, could potentially
transform the way many scientific disciplines conduct their research. There is a particular opportunity to
transform the reusability of data collected with federal funding and transform the ease with which
analyses of experimental or simulation data can be replicated and extended.

## Broader Impacts

We have already seen tremendous advances in research in many fields made possible by
implementation of pieces of the DOA and FAIR-based systems for data accessibility and reuse. A full
implementation of the DOA could truly revolutionize inter- and multi-disciplinary research, particularly in
areas where use and reuse of similar data sets over time are important. This could lead to new research
in and societal benefits from many fields, particularly biology and its many related sub-fields, earth
science, and astronomy. E-RPID also has the potential to trigger new work on data analysis tools along
with services that allow repositories to easily overlay DOA and FAIR-based systems on existing repository
structures. The work we propose could also lead to a significant new service for the national (open)
research community. The proposed research and development will also have an impact on Science,
Technology, Engineering, and Mathematics (STEM) training and education. The educational materials we
will create will make it straightforward for educators to adopt or adapt the technologies we propose to
create. This project will support a Ph.D. student working on this project for the two-year proposed period
of activity, and the work will be incorporated into the Science Gateway Architectures class taught at IU.

## Risks and Rewards: Relevance to EAGER Requirements

This project is clearly high risk: if this problem were simple to solve, it would be solved already.
Scaling and adoption by scientists are two difficult problems that impede DOAs and FAIR systems; we
request exploratory funds to see if solutions are possible. While there are obvious challenges to anyone
proposing a full implementation of the DOA, so doing would achieve goals stated by the Research Data
Alliance of “...building the social and technical bridges that enable open sharing of data.” While proposed
project is risky, it also has the potential to be widely adopted. A first-of-a-kind full implementation of the
DOA should accelerate adoption and use of this architecture in practice, nationally and internationally. A
demonstration of a DOA implementation capable of operating at Internet scales would change the way
scientists publish and interact with data objects. We will test both scaling and scientific usability directly
through the large scale of the projects we are working with (particularly Galaxy), giving us a “built in”
audience of tens of thousands of potential users. The proposed work is a good match for the EAGER
mechanism because it is high-risk, potentially high-reward, and because it will be possible to judge
success or failure within the EAGER mechanism’s time and budget constraints. The proposed work is not
well suited for other potential solicitations such as the CISE CNS solicitation. There is too much “it’s just
implementation” and not enough “interesting discovery research in computer science” for this work to
match the CNS solicitation.

Perhaps most importantly, the proposed work is directly relevant to the “socio-technical infrastructure”
track of NSF DCL 18-060 [44], which specifically calls for proposals that address the “technical barriers
that limit the findability, accessibility, and interoperability of research data in the US and internationally”
and will specifically address the suggested topic of “persistent identifiers early in the data lifecycle that
facilitate discovery, filtering, indexing, and routing of the data objects.” Our work is inclusive of this
specific topic and also goes beyond it, creating technologies that stand to enhance the value of persistent
identifiers to data objects and the creation of tools that facilitate use and reuse of data objects throughout
the data lifecycle.

## Results of Prior Funding
**Robert Quick (PI)** is the Principle Investigator of NSF award #1659310, “CC* Storage: Robust
Persistent Identification of Data (RPID)” Award period: 1 Mar 2017 - 28 Feb 2019; award amount:
$199,847. Intellectual Merit: RPID has architected a robust persistent ID testbed, prototype PID types,
and study approaches to mapping PIDs to CTSURNs. Broader Impact: RPID engages with the research
data community by participating in RDA events. Research Products: The RPID Testbed implementation
[45], integrated PID Kernel Information into the PRAGMA Rice Genomics project and SEADTrain project
CTSURN to PID mapping recommendations [46]. Resulting Publications: No publications have resulted
from this project yet, however, there is project information and a code repository available online in the
RPIDProject Github repository [17].

**Laurence Lannom** is the Co-PI of NSF award #1349002, "RCN: Building the Research Data Alliance
Community through US and International Engagement (RDA 2)". Award Period: 1 Oct 2013 - 30 Sep
2018; award amount: $6M. Intellectual Merit: RDA has shown enormous growth over the period of this
grant and has become the primary organizational venue for the development and sharing of scientific
data management infrastructure. Broader Impact: RDA’s success has helped create a stronger network
among data-enabled researchers, data practitioners, students and data professionals within the U.S.,
benefiting the both the national and international data community. Resulting Publications: The RDA
website [21] contains references to all of the formal and supporting outputs.

**Marlon Pierce** is Principal Investigator of NSF award #1339774, “Collaborative Research: SI2-SSI:
Open Gateway Computing Environments Science Gateways Platform as a Service (OGCE SciGaP)”.
Award period: 1 Oct 2013 - 30 Sep 2018; award amount: $2.5M. Intellectual Merit: Funding supports
development of Apache Airavata and its deployment as a platform service capable of supporting multiple
gateway clients. Broader Impact: funding supports the Science Gateway Architectures graduate course
at Indiana University, which has been taken by over 65 students since 2016. In addition, the proposal
team has mentored over 30 Google Summer of Code students using Apache Airavata-based projects.
Research Products: Apache Software Foundation’s GitHub organization [47]. Resulting Publications:
Apache Airavata is described in the following publications: the API [48], distributed components [49],
security model [50,51], and sharing capabilities [52].
