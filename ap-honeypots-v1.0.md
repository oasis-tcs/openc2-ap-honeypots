
![OASIS Logo](http://docs.oasis-open.org/templates/OASISLogo-v2.0.jpg)
-------

# Open Command and Control (OpenC2) Profile for Honeypots Version 1.0

## Working Draft 01

## 13 July 2020

#### Technical Committee:
[OASIS Open Command and Control (OpenC2) TC](https://www.oasis-open.org/committees/openc2/)

#### Chairs:
Joe Brule (jmbrule@radium.ncsc.mil), [National Security Agency](https://www.nsa.gov/) \
Duncan Sparrell (duncan@sfractal.com), [sFractal Consulting LLC](http://www.sfractal.com/)

#### Editor:
Alex Everett (alex.everett@unc.edu), [University of North Carolina at Chapel Hill](https://www.unc.edu/)

#### Additional artifacts:
This prose specification is one component of a Work Product that also includes:
* XML schemas: (list file names or directory name)
* Other parts (list titles and/or file names)
* `(Note: Any normative computer language definitions that are part of the Work Product, such as XML instances, schemas and Java(TM) code, including fragments of such, must be (a) well formed and valid, (b) provided in separate plain text files, (c) referenced from the Work Product; and (d) where any definition in these separate files disagrees with the definition found in the specification, the definition in the separate file prevails. Remove this note before submitting for publication.)`

#### Related work:
This specification is related to:
* _Open Command and Control (OpenC2) Language Specification Version 1.0_. Edited by Jason Romano and Duncan Sparrell. Latest stage: https://docs.oasis-open.org/openc2/oc2ls/v1.0/oc2ls-v1.0.html.

#### Abstract:
Open Command and Control (OpenC2) is a concise and extensible language to enable the command and control of cyber defense components, subsystems and/or systems in a manner that is agnostic of the underlying products, technologies, transport mechanisms or other aspects of the implementation. Honeypots are systems used to both detect the presence of an intruder attempting to breach a network or system, monitor the intruder's behavior, and divert the intruder from other targets. This OpenC2 Actuator Profile defines the Actions, Targets, Specifiers and Options that are consistent with the version 1.0 of the OpenC2 Language Specification ([OpenC2-Lang-v1.0]) in the context of command and control of various honeypots across one or more networks.

#### Status:
This document was last revised or approved by the OASIS Open Command and Control (OpenC2) TC on the above date. The level of approval is also listed above. Check the "Latest stage" location noted above for possible later revisions of this document. Any other numbered Versions and other technical work produced by the Technical Committee (TC) are listed at https://www.oasis-open.org/committees/tc_home.php?wg_abbrev=openc2#technical.

TC members should send comments on this specification to the TC's email list. Others should send comments to the TC's public comment list, after subscribing to it by following the instructions at the "Send A Comment" button on the TC's web page at https://www.oasis-open.org/committees/openc2/.

This specification is provided under the [Non-Assertion](https://www.oasis-open.org/policies-guidelines/ipr#Non-Assertion-Mode) Mode of the OASIS IPR Policy, the mode chosen when the Technical Committee was established. For information on whether any patents have been disclosed that may be essential to implementing this specification, and any offers of patent licensing terms, please refer to the Intellectual Property Rights section of the TC's web page (https://www.oasis-open.org/committees/openc2/ipr.php).

Note that any machine-readable content ([Computer Language Definitions](https://www.oasis-open.org/policies-guidelines/tc-process#wpComponentsCompLang)) declared Normative for this Work Product is provided in separate plain text files. In the event of a discrepancy between any such plain text file and display content in the Work Product's prose narrative document(s), the content in the separate plain text file prevails.

#### URI patterns:
Initial publication URI:  
https://docs.oasis-open.org/openc2/ap-honeypots/v1.0/csprd01/ap-honeypots-v1.0-csprd01.html

Permanent "Latest stage" URI:  
https://docs.oasis-open.org/openc2/ap-honeypots/v1.0/ap-honeypots-v1.0.html

(Note: Publication URIs are managed by OASIS TC Administration; please don't modify.)

#### Citation format:
When referencing this specification the following citation format should be used:

**[OpenC2-Honeypots-v1.0]**

_Open Command and Control (OpenC2) Profile for Honeypots Version 1.0_. Edited by Alex Everett. 13 July 2020. OASIS Committee Specification Draft 01 / Public Review Draft 01. https://docs.oasis-open.org/openc2/ap-honeypots/v1.0/csprd01/ap-honeypots-v1.0-csprd01.html. Latest stage: https://docs.oasis-open.org/openc2/ap-honeypots/v1.0/ap-honeypots-v1.0.html.

-------

## Notices
Copyright © OASIS Open 2020. All Rights Reserved.

All capitalized terms in the following text have the meanings assigned to them in the OASIS Intellectual Property Rights Policy (the "OASIS IPR Policy"). The full [Policy](https://www.oasis-open.org/policies-guidelines/ipr) may be found at the OASIS website.

This document and translations of it may be copied and furnished to others, and derivative works that comment on or otherwise explain it or assist in its implementation may be prepared, copied, published, and distributed, in whole or in part, without restriction of any kind, provided that the above copyright notice and this section are included on all such copies and derivative works. However, this document itself may not be modified in any way, including by removing the copyright notice or references to OASIS, except as needed for the purpose of developing any document or deliverable produced by an OASIS Technical Committee (in which case the rules applicable to copyrights, as set forth in the OASIS IPR Policy, must be followed) or as required to translate it into languages other than English.

The limited permissions granted above are perpetual and will not be revoked by OASIS or its successors or assigns.

This document and the information contained herein is provided on an "AS IS" basis and OASIS DISCLAIMS ALL WARRANTIES, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO ANY WARRANTY THAT THE USE OF THE INFORMATION HEREIN WILL NOT INFRINGE ANY OWNERSHIP RIGHTS OR ANY IMPLIED WARRANTIES OF MERCHANTABILITY OR FITNESS FOR A PARTICULAR PURPOSE.

OASIS requests that any OASIS Party or any other party that believes it has patent claims that would necessarily be infringed by implementations of this OASIS Committee Specification or OASIS Standard, to notify OASIS TC Administrator and provide an indication of its willingness to grant patent licenses to such patent claims in a manner consistent with the IPR Mode of the OASIS Technical Committee that produced this specification.

OASIS invites any party to contact the OASIS TC Administrator if it is aware of a claim of ownership of any patent claims that would necessarily be infringed by implementations of this specification by a patent holder that is not willing to provide a license to such patent claims in a manner consistent with the IPR Mode of the OASIS Technical Committee that produced this specification. OASIS may include such claims on its website, but disclaims any obligation to do so.

OASIS takes no position regarding the validity or scope of any intellectual property or other rights that might be claimed to pertain to the implementation or use of the technology described in this document or the extent to which any license under such rights might or might not be available; neither does it represent that it has made any effort to identify any such rights. Information on OASIS' procedures with respect to rights in any document or deliverable produced by an OASIS Technical Committee can be found on the OASIS website. Copies of claims of rights made available for publication and any assurances of licenses to be made available, or the result of an attempt made to obtain a general license or permission for the use of such proprietary rights by implementers or users of this OASIS Committee Specification or OASIS Standard, can be obtained from the OASIS TC Administrator. OASIS makes no representation that any information or list of intellectual property rights will at any time be complete, or that any claims in such list are, in fact, Essential Claims.

The name "OASIS" is a trademark of [OASIS](https://www.oasis-open.org/), the owner and developer of this specification, and should be used only to refer to the organization and its official outputs. OASIS welcomes reference to, and implementation and use of, specifications, while reserving the right to enforce its marks against misleading uses. Please see https://www.oasis-open.org/policies-guidelines/trademark for above guidance.

-------

# Table of Contents
[[TOC will be inserted here]]

-------

# 1 Introduction

The text in this section may all be replaced, but the following three sections (1.1, 1.2, and 1.3) are required for OASIS publications. Section 1.1 (IPR Policy) must not be changed by the TC. Section 1.2 (Terminology) may be modified to include other terminology-related information used in this specification. Section 1.3 (Normative References) should be modified to include additional references, as needed. Section 1.4 (Non-Normative References) is not required, but should be modified to include additional references, as needed.

Here is a customized command line which will generate HTML from this markdown file (named ap-sbom-v1.0-wd01.md):

pandoc -f gfm -t html ap-sbom-v1.0-wd01.md -c styles/markdown-styles-v1.7.3.css --toc --toc-depth=5 -s -o ap-sbom-v1.0-wd01.html --metadata title="Open Command and Control (OpenC2) Profile for Software Bill of Materials Retrieval Version 1.0"

We are currently using pandoc 2.6 from https://github.com/jgm/pandoc/releases/tag/2.6.

This also requires the presence of a .css file containing the HTML styles (like styles/markdown-styles-v1.7.3.css).

Note this command generates a Table of Contents (TOC) in HTML which is located at the top of the HTML document, and which requires additional editing in order to be published in the expected OASIS style. This editing will be handled by OASIS staff during publication.

## 1.1 IPR Policy
This specification is provided under the [Non-Assertion](https://www.oasis-open.org/policies-guidelines/ipr#Non-Assertion-Mode) Mode of the [OASIS IPR Policy](https://www.oasis-open.org/policies-guidelines/ipr), the mode chosen when the Technical Committee was established. For information on whether any patents have been disclosed that may be essential to implementing this specification, and any offers of patent licensing terms, please refer to the Intellectual Property Rights section of the TC's web page ([https://www.oasis-open.org/committees/openc2/ipr.php](https://www.oasis-open.org/committees/openc2/ipr.php)).

## 1.2 Terminology
The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as described in [[RFC2119](#rfc2119)] and [[RFC8174](#rfc8174)] when, and only when, they appear in all capitals, as shown here.

## 1.3 Normative References

(Reference sources:
For references to IETF RFCs, use the approved citation formats at:  
http://docs.oasis-open.org/templates/ietf-rfc-list/ietf-rfc-list.html.  
For references to W3C Recommendations, use the approved citation formats at:  
http://docs.oasis-open.org/templates/w3c-recommendations-list/w3c-recommendations-list.html.  
Remove this note before submitting for publication.)

###### [OpenC2-Lang-v1.0]
_Open Command and Control (OpenC2) Language Specification Version 1.0_. Edited by Jason Romano and Duncan Sparrell. Latest stage: https://docs.oasis-open.org/openc2/oc2ls/v1.0/oc2ls-v1.0.html.
###### [OpenC2-HTTPS-v1.0]
_Specification for Transfer of OpenC2 Messages via HTTPS Version 1.0_. Edited by David Lemire. Latest stage: http://docs.oasis-open.org/openc2/open-impl-https/v1.0/open-impl-https-v1.0.html
###### [OpenC2-SLPF-v1.0]
_Open Command and Control (OpenC2) Profile for Stateless Packet Filtering Version 1.0_. Edited by Joe Brule, Duncan Sparrell, and Alex Everett. Latest stage: http://docs.oasis-open.org/openc2/oc2slpf/v1.0/oc2slpf-v1.0.html
###### [RFC2119]
Bradner, S., "Key words for use in RFCs to Indicate Requirement Levels", BCP 14, RFC 2119, DOI 10.17487/RFC2119, March 1997, http://www.rfc-editor.org/info/rfc2119.
###### [RFC8174]
Leiba, B., "Ambiguity of Uppercase vs Lowercase in RFC 2119 Key Words", BCP 14, RFC 8174, DOI 10.17487/RFC8174, May 2017, http://www.rfc-editor.org/info/rfc8174.

## 1.4 Non-Normative References

###### [RFC3552]
Rescorla, E. and B. Korver, "Guidelines for Writing RFC Text on Security Considerations", BCP 72, RFC 3552, DOI 10.17487/RFC3552, July 2003, https://www.rfc-editor.org/info/rfc3552.

## 1.5 Some markdown usage examples

**Text.**

Note that text paragraphs in markdown should be separated by a blank line between them -

Otherwise the separate paragraphs will be joined together when the HTML is generated.
Even if the text appears to be separate lines in the markdown source.

To avoid having the usual vertical space between paragraphs,  
append two or more space characters (or space-backslash) to the end of the lines  
which will generate an HTML break tag instead of a new paragraph tag  
(as demonstrated here).

### 1.5.1 Figures and Captions

FIGURE EXAMPLE:
<note caption is best placed ABOVE figure, to allow a link to it to display image - same for table captions>

###### Figure 1 -- Title of Figure
![image-label should be meaningful](images/image_0.png) (this image is missing)

###### Figure 2 -- OpenC2 Message Exchange
![message exchange](images/image_1.png)


### 1.5.2 Tables

#### 1.5.2.1 Basic Table
**Table 1-1. Table Label**

| Item | Description |
| :--- | :--- |
| Item 1 | Something<br>(second line) |
| Item 2 | Something |
| Item 3 | Something<br>(second line) |
| Item 4 | text |

#### 1.5.2.2 Table with Three Columns and Some Bold Text
text.

| Title 1 | Title 2 | title 3 |
| :--- | :--- | :--- |
| something | something | something else that is a long string of text that **might** need to wrap around inside the table box and will just continue until the column divider is reached |
| something | something | something |

#### 1.5.2.3 Table with a caption which can be referenced

###### Table 1-5. See reference label construction

| Name | Description |
| :--- | :--- |
| **content** | Message body as specified by content_type and msg_type. |

Here is a reference to the table caption:
Please see [Table 1-5 or other meaningful label](#table-1-5-see-reference-label-construction) 


### 1.5.3 Lists

Bulleted list:
* bullet item 1.
* **Bold** bullet item 2.
* bullet item 3.
* bullet item 4.

Indented or multi-level bullet list - add two spaces per level before bullet character (* or -):
* main bullet type
  * Example second bullet
    * See third level
      * fourth level

Numbered list:
1. item 1
2. item 2
3. item 3

Left-justified list without bullets or numbers:
To list multiple items without full paragraph breaks between items, add space-backslash after each item except the last.

### 1.5.4 Reference Label Construction

REFERENCES and ANCHORS
- in markdown source, format the Reference tags as level 6 headings like: `###### [RFC2119]`
###### [RFC2119]
Bradner, S., "Key words ..."

- reference text has to be on a separate line below the tag

- format cross-references (citations of the references) like: `see [[RFC2119](#rfc2119)]`  
"see [[RFC2119](#rfc2119)]"  
(note the outer square brackets in markdown will appear in the visible HTML text)

- The text in the Reference tag (following ###### ) will become an HTML anchor using the following conversion rules:  
-- punctuation marks will be dropped (including "[" )  
-- leading white spaces will be dropped  
-- upper case will be converted to lower  
-- spaces between letters will be converted to a single hyphen

- The same HTML anchor construction rules apply to cross-references and to section headings.  
-- Thus, a section heading like "## 1.3 Normative References"  
-- becomes an anchor in HTML like `<a href="#13-normative-references">`  
-- referenced in the markdown like: see [Section 1.3](#13-normative-references)  
-- (in markdown: `"see [Section 1.3](#13-normative-references"`)  
-- similar HTML anchors are also used in constructing the TOC

### 1.5.5 Code Blocks

Text to appear as an indented code block with grey background and monospace font - use three back-ticks before and after the code block).

Note the actual backticks will not appear in the HTML format. If it's necessary to display visible backticks, place a back-slash before them like: \``` .

```
{   
    "target": {
        "x_kmip_2.0": {
            {"kmip_type": "json"},
            {"operation": "RekeyKeyPair"},
            {"name": "publicWebKey11DEC2017"}
        }
    }
}
```

Text to be highlighted as code can also be surrounded by a single "backtick" character: 
`code text`

## 1.6 Page Breaks
Add horizontal rule lines where page breaks are desired in the PDF - before each major section
- insert the line rules in markdown by inserting 3 or more hyphens on a line by themselves:  ---
- place these before each main section in markdown (usually "#" - which generates the HTML `<h1>` tag)

-------
# 2 OpenC2 Language Binding

_This section is normative_

This section defines the set of Actions, Targets, Specifiers, and Arguments that are meaningful in the context of Honeypots. This section also describes the appropriate format for the status and properties of a Response frame. This section is organized into three major subsections; Command Components, Response Components and Commands.

Extensions to the Language Specification are defined in accordance with [[OpenC2-Lang-v1.0]](#openc2-lang-v10), Section 3.1.5, where:

1. The unique name of the SLPF schema is `oasis-open.org/openc2/v1.0/ap-honeypots`
2. The namespace identifier (nsid) referring to the SLPF schema is:  `honeypots`
3. The definitions of and conformance requirements for these types are contained in this document

## 2.1 OpenC2 Command Components
The components of an OpenC2 Command include Actions, Targets, Actuators and associated Arguments and Specifiers. Appropriate aggregation of the components will define a Command-body that is meaningful in the context of Honeypots.

This specification identifies the applicable components of an OpenC2 Command. The components of an OpenC2 Command include:

* Action:  A subset of the Actions defined in the OpenC2 Language Specification that are meaningful in the context of Honeypots.
    * This profile SHALL NOT define Actions that are external to Version 1.0 of the [OpenC2 Language Specification](#openc2-lang-v10)
    * This profile MAY augment the definition of the Actions in the context of Honeypots
    * This profile SHALL NOT define Actions in a manner that is inconsistent with version 1.0 of the OpenC2 Language Specification
* Target:  A subset of the Targets and Target-Specifiers defined in Version 1.0 of the OpenC2 Language Specification that are meaningful in the context of Honeypots and one Target (and its associated Specifier) that is defined in this specification
* Arguments:  A subset of the Arguments defined in the Language Specification and a set of Arguments defined in this specification
* Actuator:  A set of specifiers defined in this specification that are meaningful in the context of Honeypots

### 2.1.1 Actions
Table 2.1.1-1 presents the OpenC2 Actions defined in version 1.0 of the Language Specification which are meaningful in the context of Honeypots. The particular Action/Target pairs that are required or are optional are presented in [Section 2.3](#23-openc2-commands).

**Table 2.1.1-1. Actions Applicable to Honeypots**

**_Type: Action (Enumerated)_**

| ID | Name | Description |
| :--- | :--- | :--- |
| 3 | **query** | Initiate a request for information. Used to retrieve information about one or more honeypots |
| 9 | **start** | Initiate a process, application, system, or activity. Used to start one or more honeypots|
| 10 | **stop** | Halt a system or end an activity. Used to stop one or more honeypots|
| 11 | **restart** | Stop then start a system or an activity. Used to restart one or more honeypots|
| 15 | **set** | Change a value, configuration, or state of a managed entity. Used to set a configuration value |
| 16 | **update** | Instruct a component to retrieve, install, process, and operate in accordance with a software update, reconfiguration, or other update. Used to update one or more honeypots via a small text file|
| 19 | **create** | Add a new entity of a known type (e.g., data, files, directories). Used to create one or more honeypots |
| 20 | **delete** | Remove an entity (e.g., data, files, flows). Used to remove one or more honeypots |

### 2.1.2 Targets
Table 2.1.2-1 summarizes the Targets defined in Version 1.0 of the [[OpenC2-Lang-v1.0]](#openc2-lang-v10) as they relate to Honeypots functionality. Table 2.1.2-2 summarizes the Targets that are defined in this specification.

#### 2.1.2.1 Common Targets
Table 2.1.2-1 lists the Targets defined in the OpenC2 Language Specification that are applicable to Honeypots. The particular Action/Target pairs that are required or are optional are presented in [Section 2.3](#23-openc2-commands).

**Table 2.1.2-1. Targets Applicable to Honeypots**

**_Type: Target (Choice)_**

| ID | Name | Type | Description |
| :--- | :--- | :--- | :--- |
| 3 | **device** | Device | The properties of a hardware device. Used to identify one or more honeypots|
| 9 | **features** | Features | A set of items such as Action/Target pairs, profiles versions, options that are supported by the Actuator. The Target is used with the query Action to determine an Actuator's capabilities |
| 10 | **file** | File | Properties of a file |

#### 2.1.2.2 Honeypots Targets
The list of common Targets is extended to include the additional Targets defined in this section and referenced with the honeypots namespace.

**Table 2.1.2-2. Targets Unique to Honeypots**

**_Type: Target (Choice)_**

| ID | Name | Type | Description |
| :--- | :--- | :--- | :--- |
| 1024 | **hit_count** | Number | Represents the number of hits against one or more honeypots over a time period |
| 1025 | **hit_details** | Hit-Details | Represents details regarding a hits against one or more honeypots over a time period |

### 2.1.3 Command Arguments
Arguments provide additional precision to a Command by including information such as how, when, or where a Command is to be executed. Table 2.1.3-1 summarizes the Command Arguments defined in Version 1.0 of the [[OpenC2-Lang-v1.0]](#openc2-lang-v10) as they relate to Honeypots functionality. Table 2.1.3-2 summarizes the Command Arguments that are defined in this specification.

#### 2.1.3.1 Common Arguments
Table 2.1.3-1 lists the Command Arguments defined in the [[OpenC2-Lang-v1.0]](#openc2-lang-v10) that are applicable to Honeypots.

**Table 2.1.3-1. Command Arguments applicable to Honeypots**

**_Type: Args (Map)_**

| ID | Name | Type | # | Description |
| :--- | :--- | :--- | :--- | :--- |
| 1 | **start_time** | Date-Time | 0..1 | The specific date/time to initiate the Action |
| 2 | **stop_time** | Date-Time | 0..1 | The specific date/time to terminate the Action|
| 3 | **duration** | Duration | 0..1 | The length of time for an Action to be in effect |
| 4 | **response_requested** | Response-Type | 0..1 | The type of Response required for the Action: `none`, `ack`, `status`, `complete` |

**_Type: Hit-Details_**

| Type Name | Type | Description |
| :--- | :--- | :--- |
| **Hit-Details** | ArrayOf(String) | Details regarding a subset of hits to one or more honeypots for a given time |

### 2.1.4 Actuator Specifiers
An Actuator is the entity that provides the functionality and performs the Action. The Actuator executes the Action on the Target. In the context of this profile, the Actuator is the Honeypots and the presence of one or more Specifiers further refine which Actuator(s) shall execute the Action.

Table 2.1.4-1 lists the Specifiers that are applicable to the Honeypots Actuator. [Annex A](#annex-a-sample-commands) provides sample Commands with the use of Specifiers.

The Actuator Specifiers defined in this document are referenced under the honeypots namespace.

**Table 2.1.4-1. Honeypots Specifiers**

**_Type: Specifiers (Map)_**

| ID | Name | Type | # | Description |
| :--- | :--- | :--- | :--- | :--- |
| 1 | **hostname** | String | 0..1 | [[RFC1123]](#rfc1123) hostname (can be a domain name or IP address) for a particular device with Honeypots functionality |
| 2 | **named_group** | String | 0..1 | User defined collection of devices with Honepots functionality |
| 3 | **asset_id** | String | 0..1 | Unique identifier for a particular honeypot |
| 4 | **asset_tuple** | String | 0..10 | Unique tuple identifier for a particular honeypot consisting of a list of up to 10 strings |

## 2.2 OpenC2 Response Components
Response messages originate from the Actuator as a result of a Command.

Responses associated with required Actions MUST be implemented. Implementations that include optional Actions MUST implement the RESPONSE associated with the implemented Action. Additional details regarding the Command and associated Response are captured in [Section 2.3](#23-openc2-commands). Examples are provided in [Annex A](#annex-a-sample-commands).

### 2.2.1 Common Results
Table 2.2.1-1 lists the Response Results properties defined in the [[OpenC2-Lang-v1.0]](#openc2-lang-v10) that are applicable to Honeypots.

**Table 2.2.1-1. Response Results Applicable to Honeypots**

**_Type: Results (Map [1..*])_**

| ID | Name | Type | # | Description |
| ---: | :--- | :--- | ---: | :--- |
| 1 | **versions** | Version | 0..* | List of OpenC2 language versions supported by this Actuator |
| 2 | **profiles** | ArrayOf(Nsid) | 0..1 | List of profiles supported by this Actuator |
| 3 | **pairs** | Action-Targets | 0..* | List of targets applicable to each supported Action |
| 4 | **rate_limit** | Number | 0..1 | Maximum number of requests per minute supported by design or policy |

### 2.2.3 Response Status Codes
Table 2.2.1-2 lists the Response Status Codes defined in the OpenC2 Language Specification that are applicable to Honeypots.

**Table 2.2.1-2. Response Status Codes**

**_Type: Status-Code (Enumerated.ID)_**

| Value | Description |
| :--- | :--- |
| 102 | Processing. Command received but action not necessarily complete. |
| 200 | OK. |
| 400 | Bad Request. Unable to process Command, parsing error. |
| 500 | Internal Error. For "response_requested" value "complete", one of the following MAY apply:<br> * Cannot access file or path<br> * Rule number currently in use<br> * Rule not updated |
| 501 | Not implemented. For "response_requested" value "complete", one of the following MAY apply:<br> * Target not supported<br> * Option not supported<br> * Command not supported |

## 2.3 OpenC2 Commands

An OpenC2 Command consists of an Action/Target pair and associated Specifiers and Arguments. This section enumerates the allowed Commands and presents the associated Responses.

Table 2.3-1 defines the Commands that are valid in the context of the SLPF profile. An Action (the top row in Table 2.3-1) paired with a Target (the first column in Table 2.3-1) defines a valid Command. The subsequent subsections provide the property tables applicable to each OpenC2 Command.

**Table 2.3-1. Command Matrix**

|   | Query | Start | Stop | Restart | Set | Update | Create | Delete |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **devices** | | valid | valid | valid |   | valid | valid | valid |
| **features** | valid | |   |   |   |   |   |   |
| **files** |  |  |   |   | valid | valid |   |   |
| **hit_count** | valid |  |   |   | |  |   |   |
| **hit_details** | valid |  |   |   | |  |   |   |

Table 2.3-2 defines the Command Arguments that are allowed for a particular Command by the SLPF profile. A Command (the top row in Table 2.3-2) paired with an Argument (the first column in Table 2.3-2) defines an allowable combination. The subsection identified at the intersection of the Command/Argument provides details applicable to each Command as influenced by the Argument.

**Table 2.3-2. Command Arguments Matrix**

|   | Query features | Update file |
| :--- | :---: | :---: | 
| **response_requested** | [2.3.1](#231-allow) | [2.3.2](#232-deny) | 
| **start_time** | [2.3.1](#231-allow)| [2.3.2](#232-deny) |   
| **stop_time** | [2.3.1](#231-allow) | [2.3.2](#232-deny) |  

### 2.3.1 Allow
Table 2.3.1-1 summarizes the Command Arguments that apply to all of the Commands consisting of the 'allow' Action and a valid Target type.

Upon receipt of an unsupported Command Argument, SLPF Consumers

* MUST NOT respond with a OK/200
* SHOULD respond with the 501 status code.
* SHOULD respond with "Option not supported" in the status text
* MAY respond with the 500 status code

OpenC2 Producers that send 'allow target' Commands and support the 'delete slpf:rule_number' Command:

* MUST support the slpf:rule_number Target type as defined in [Section 2.1.2.2](#2122-slpf-targets)
* SHOULD populate the Command Arguments field with "response_requested" : "complete"
* MAY populate the Command Arguments field with the "insert_rule" : <integer> option
* MUST populate the Command Arguments field with "response_requested" : "complete" if the insert_rule Argument is populated

OpenC2 Consumers that receive and successfully parse 'allow <target>' Commands but cannot implement the 'allow <target>' :

* MUST NOT respond with a OK/200
* SHOULD respond with the 501 status code
* SHOULD respond with 'Rule not updated' in the status text
* MAY respond with the 500 status code

OpenC2 Consumers that receive 'allow <target>' Commands and support the 'delete slpf:rule_number' Command:

* MUST support the slpf:rule_number Target type as defined in [Section 2.1.2.2](#2122-slpf-targets)
* Upon successful implementation of the 'allow <target>', MUST return the rule_number associated with the rule if the "response_requested" : "complete" option is populated.

OpenC2 Consumers that receive 'allow target' Commands and support the 'insert_rule' Command Argument:

* MUST assign the rule number provided if the "insert_rule" : <integer> option is populated.
* If the rule number is currently in use, then
    * MUST NOT respond with a OK/200.
    * SHOULD respond with the 501 status code.
    * SHOULD respond with 'Rule number currently in use' in the status text.
    * MAY respond with the 500 status code.

The valid Target types, associated Specifiers, and Options are summarized in [Section 2.3.1.1](#2311-allow-ipv4_connection) and [Section 2.3.1.2](#2312-allow-ipv6_connection). Sample Commands are presented in [Annex A](#annex-a-sample-commands).

#### 2.3.1.1 'Allow ipv4_connection'

The 'allow ipv4_connection' Command is OPTIONAL for Openc2 Producers implementing the SLPF.
The 'allow ipv4_connection' Command is OPTIONAL for Openc2 Consumers implementing the SLPF.

The Command permits traffic that is consistent with the specified ipv4_connection. A valid 'allow ipv4_connection' Command has at least one property of the ipv4_connection populated and may have any combination of the five properties populated. An unpopulated property within the ipv4_connection Target MUST be treated as an 'any'.

Products that receive but do not implement the 'allow ipv4_connection' Command:

* MUST NOT respond with a OK/200
* SHOULD respond with the 501 Response code
* SHOULD respond with 'Target type not supported' in the status text
* MAY respond with the 500 status code

#### 2.3.1.2 'Allow ipv6_connection'
The 'allow ipv6_connection' Command is OPTIONAL for Openc2 Producers implementing the SLPF.
The 'allow ipv6_connection' Command is OPTIONAL for Openc2 Consumers implementing the SLPF.

The Command permits traffic that is consistent with the specified ipv6_connection. A valid 'allow ipv6_connection' Command has at least one property of the ipv6_connection populated and may have any combination of the five properties populated. An unpopulated property within the the ipv4_connection Target MUST be treated as an 'any'.

Products that receive but do not implement the 'allow ipv6_connection' Command:

* MUST NOT respond with a OK/200
* SHOULD respond with the 501 Response code
* SHOULD respond with 'Target type not supported' in the status text
* MAY respond with the 500 status code

#### 2.3.1.3 'Allow ipv4_net'
The 'allow ipv4_net' Command is OPTIONAL for Openc2 Producers implementing the SLPF.
The 'allow ipv4_net' Command is OPTIONAL for Openc2 Consumers implementing the SLPF.

The Command permits traffic as specified by the range of IPv4 addresses as expressed by CIDR notation. If the mask is absent (or unspecified) then it MUST be treated as a single IPv4 address (i.e., an address range of one element). The address range specified in the ipv4_net MUST be treated as a source OR destination address.

Products that receive but do not implement the 'allow ipv4_net' Command:
* MUST NOT respond with a OK/200
* SHOULD respond with the 501 Response code
* SHOULD respond with 'Target type not supported' in the status text
* MAY respond with the 500 status code

#### 2.3.1.4 'Allow ipv6_net'
The 'allow ipv6_net' Command is OPTIONAL for Openc2 Producers implementing the SLPF.
The 'allow ipv6_net' Command is OPTIONAL for Openc2 Consumers implementing the SLPF.

The Command permits traffic as specified by the range of IPv6 addresses as expressed by CIDR notation. If the mask is absent (or unspecified) then it MUST be treated as a single IPv6 address (i.e., an address range of one element). The address range specified in the ipv6_net MUST be treated as a source OR destination address.

Products that receive but do not implement the 'allow ipv6_net' Command:
* MUST NOT respond with a OK/200
* SHOULD respond with the 501 Response code
* SHOULD respond with 'Target type not supported' in the status text
* MAY respond with the 500 status code

### 2.3.2 Deny
'Deny' can be treated as the mathematical complement to 'allow'. With the exception of the additional 'drop_process' Actuator-Argument, the Targets, Specifiers, Options and corresponding Responses are identical to the four 'allow' Commands. Table 2.3-2 summarizes the Command Arguments that apply to all of the Commands consisting of the 'deny' Action and valid Target type.

Upon receipt of a Command with an Argument that is not supported by the Actuator:

* MUST NOT respond with OK/200
* SHOULD respond with the 501 status code
* SHOULD respond with 'Option not supported' in the status text
* MAY respond with the 500 status code

OpenC2 Producers that send 'deny target' Commands and support the 'delete slpf:rule_number' Command:

* MUST support the slpf:rule_number Target type as defined in [Section 2.1.2.2](#2122-slpf-targets)
* SHOULD populate the Command Arguments field with '"response_requested" : "complete"
* MAY populate the Command Arguments field with the "insert_rule" : <integer> option
* MUST populate the Command Arguments field with "response_requested" : "complete" if the insert_rule Argument is populated

OpenC2 Consumers that receive 'deny <target>' Commands and support the 'delete slpf:rule_number' Command:

* MUST support the slpf:rule_number Target type as defined in [Section 2.1.2.2](#2122-slpf-targets)
* MUST return the rule number assigned in the slpf object if the "response_requested" : "complete" Argument is populated.

OpenC2 Consumers that receive 'deny target' Commands and support the 'insert_rule' Command Argument:

* MUST assign the rule number provided if the "insert_rule" : <integer> Argument is populated
* If the rule number is currently in use, then
    * MUST NOT respond with a OK/200
    * SHOULD respond with the 501 status code
    * SHOULD respond with 'Rule number currently in use' in the status text
    * MAY respond with the 500 status code

### 2.3.3 Query
The valid Target type, associated Specifiers, and Options are summarized in [Section 2.3.3.1](#2331-query-features). Sample Commands are presented in [Annex A](#annex-a-sample-commands).

#### 2.3.3.1 Query features
The 'query features' Command MUST be implemented in accordance with Version 1.0 of the [[OpenC2-Lang-v1.0]](#openc2-lang-v10).

### 2.3.4 Delete
The slpf:rule_number is the only valid Target type for the delete Action. The associated Specifiers, and Options are summarized in [Section 2.3.4.1](#2341-delete-slpfrule_number). Sample Commands are presented in [Annex A](#annex-a-sample-commands).

#### 2.3.4.1 delete slpf:rule_number
The 'delete slpf:rule_number' Command is used to remove a firewall rule rather than issue an allow or deny to counteract the effect of an existing rule. Implementation of the 'delete slpf:rule_number' Command is OPTIONAL. Products that choose to implement the 'delete slpf:rule_number' Command MUST implement the slpf:rule_number Target type described in [Section 2.1.2.2](#2122-slpf-targets).

OpenC2 Producers that send the 'delete slpf:rule_number' Command:

* MAY populate the Command Arguments field with 'response_requested" : "complete"
* MUST NOT include other Command Arguments
* MUST include exactly one rule_number

OpenC2 Consumers that receive the 'delete slpf:rule_number' Command:

* but cannot parse or process the 'delete slpf:rule_number' Command:
    * MUST NOT respond with a OK/200
    * SHOULD respond with status code 400
    * MAY respond with the 500 status code
* but do not support the slpf:rule_number Target type:
    * MUST NOT respond with a OK/200
    * SHOULD respond with the 501 status code
    * SHOULD respond with 'target not supported' in the status text
    * MAY respond with the 500 status code
* MUST respond with Response code 200 upon successful parsing of the 'delete slpf:rule_number' Command and subsequent removal of the corresponding rule
* upon successful parsing but failure to remove the corresponding rule:
    * MUST NOT respond with OK/200
    * MUST respond with Response code 500
    * SHOULD respond with 'firewall rule not removed or updated' in the status text

Refer to [Annex A](#annex-a-sample-commands) for sample Commands.

### 2.3.5 Update
The 'file' Target as defined in Version 1.0 of the Language Specification is the only valid Target type for the update Action. The associated Specifiers, and Options are summarized in [Section 2.3.5.1](#2351-update-file). Sample Commands are presented in [Annex A](#annex-a-sample-Commands).

#### 2.3.5.1 Update file
The 'update file' Command is used to replace or update files such as configuration files, rule sets, etc. Implementation of the update file Command is OPTIONAL. OpenC2 Consumers that choose to implement the 'update file' Command MUST include all steps that are required for the update file procedure such as retrieving the file(s), install the file(s), restart/ reboot the device etc. The end state shall be that the firewall operates with the new file at the conclusion of the 'update file' Command. The atomic steps that take place are implementation specific.

Table 2.3-2 presents the valid options for the 'update file' Command. OpenC2 Producers and Consumers that choose to implement the 'update file' Command MUST NOT include options other than the options identified in Table 2.3-2.

OpenC2 Producers that send the 'update file' Command:

* MAY populate the arguments field with the "response_requested" argument. Valid values for "response_requested" for 'update file' are "complete", "ack", and "none"
* MUST NOT include other Command Arguments
* MUST populate the name Specifier in the Target
* SHOULD populate the path Specifier in the Target

OpenC2 Consumers that receive the 'update file' Command:

* but cannot parse or process the Command
    * MUST NOT respond with a OK/200
    * SHOULD respond with status code 400
    * MAY respond with the 500 status code
* but do not support the 'update file' Command
    * MUST NOT respond with a OK/200
    * SHOULD respond with status code 501
    * SHOULD respond with 'Command not supported' in the status text
    * MAY respond with status code 500
* but cannot access the file specified in the file Target
    * MUST respond with status code 500
    * SHOULD respond with 'cannot access file' in the status text
* upon successful parsing and initiating the processing of the 'update file' Command, OpenC2 Consumers MAY respond with Response code 102
* upon completion of all the steps necessary to complete the update and the Actuator commences operations functioning with the new file, OpenC2 Consumers SHOULD respond with Response code 200

Refer to [Annex A](#annex-a-sample-commands) for sample Commands.

---

# 3 Safety, Security, and Data Protection Considerations
(Note: OASIS strongly recommends that Technical Committees consider issues that might affect safety, security, privacy, and/or data protection in implementations of their specification and document them for implementers and adopters. For some purposes, you may find it required, e.g. if you apply for IANA registration.

While it may not be immediately obvious how your specification might make systems vulnerable to attack, most specifications, because they involve communications between systems, message formats, or system settings, open potential channels for exploit. For example, IETF [[RFC3552](#rfc3552)] lists “eavesdropping, replay, message insertion, deletion, modification, and man-in-the-middle” as well as potential denial of service attacks as threats that must be considered and, if appropriate, addressed in IETF RFCs.

In addition to considering and describing foreseeable risks, this section should include guidance on how implementers and adopters can protect against these risks.

We encourage editors and TC members concerned with this subject to read _Guidelines for Writing RFC Text on Security Considerations_, IETF [[RFC3552](#rfc3552)], for more information.

Remove this note before submitting for publication.)

-------

# 4 Conformance
(Note: The [OASIS TC Process](https://www.oasis-open.org/policies-guidelines/tc-process#wpComponentsConfClause) requires that a specification approved by the TC at the Committee Specification Public Review Draft, Committee Specification or OASIS Standard level must include a separate section, listing a set of numbered conformance clauses, to which any implementation of the specification must adhere in order to claim conformance to the specification (or any optional portion thereof). This is done by listing the conformance clauses here.
For the definition of "conformance clause," see [OASIS Defined Terms](https://www.oasis-open.org/policies-guidelines/oasis-defined-terms-2017-05-26#dConformanceClause).

See "Guidelines to Writing Conformance Clauses":  
http://docs.oasis-open.org/templates/TCHandbook/ConformanceGuidelines.html.

Remove this note before submitting for publication.)


-------

# Appendix A. Acknowledgments

(Note: A Work Product approved by the TC must include a list of people who participated in the development of the Work Product. This is generally done by collecting the list of names in this appendix. This list shall be initially compiled by the Chair, and any Member of the TC may add or remove their names from the list by request.  
Remove this note before submitting for publication.)

The following individuals have participated in the creation of this specification and are gratefully acknowledged:

**OpenC2 TC Members:**

| First Name | Last Name | Company |
| :--- | :--- | :--- |
Philippe | test | Arbor Networks

-------

# Appendix B. Revision History
| Revision | Date | Editor | Changes Made |
| :--- | :--- | :--- | :--- |
| ap-honeypots-v1.0-wd01 | 2020-07-13 | Alex EVerett | Initial working draft |
