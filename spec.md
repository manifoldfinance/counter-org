# Comprehensive security monitoring process

> DRAFT

## Specification 

A comprehensive security monitoring process not only assists with the need to perform forensic analysis but can also be a proactive security measure capable of supplying information prior to, during, and after an attack. By providing a centralized repository for security reports, an attack can be detected during the probing phase, as the attack occurs, or immediately following the attack to supply responders with the information they need to react to an attack effectively, which can reduce the impact of intrusion attempts.


Understanding the range of benefits that can be gained by implementing security monitoring is important during the conceptualization phase of development so that the design and policies can take advantage of all these benefits. Some of the advantages that security monitoring provides include:

Identification and remediation of systems that do not comply with security or update policies to reduce the vulnerability profile for protocols.

Produce information that can alert staff to intrusion attempts before an actual attack occurs by identifying unusual activity to the operational team overseeing a protocol.

Create security audit information and protect it to improve forensic analysis, which not only meets regulatory requirements but also reduces the impact of any attack that might occur.

Assist with security level analysis efforts to improve overall security.

Detect activities that occur outside of established protocol/businesses processes, whether intentional or accidental.

Assist with the identification of unmanaged systems on a network or the remediation of vulnerable access methods and/or ACL policies protecting such methods (e.g. compromised EOA).


## Interpreting Audit Events

Audit events are discussed in much greater detail throughout this paper, so a basic understanding of audit event structure and the information contained in audit events is important.


## Technical Issues

To implement a security monitoring and attack detection system based on Windows security event logging, the following issues must be addressed:

**Manage high volumes of security events**. To cope with the high volume of security events that will be generated careful attention will need to be given to which specific security audit events should be tracked. These considerations are particularly important when dealing with file and object access auditing, both of which can generate very large quantities of data.

**Store and manage event information in a central repository**. Storage of event information can involve terabytes of data depending on the configuration of a monitoring system. This is most important when considering forensic analysis needs and is covered in detail under that section.

**Identify and respond to attack signatures**. In order to identify patterns of activity which can signal an attack a reviewer or configured query must be able to pick out the events associated with such activity imbedded within the information provided. Once a suspicious activity is identified there should be a mechanism in place that prompts a timely and appropriate response.


### Solution Planning
The following activities should be completed before implementing a security monitoring and attack detection system:

Review current security audit settings.

Assess administrator roles and normal user tasks.

Review business policies and procedures.

Identify vulnerable systems.

List high-value assets.

Identify sensitive or suspicious accounts.

List authorized programs.


### List High Impact Functions
Most businesses are likely to have already identified the high-impact functions that reside in their contracts, but they might not have formalized this information as a part of an organizational policy by documenting and detailing the protections in place for each such function call.

Any changes to an ACL that is used to protect such functions should be investigated, especially when ownership changes are involved because these events can indicate illicit attempts to access assets behind these functions without proper authorization. Because ownership changes of this nature should be very rare, they should be easy to detect after such high-impact functions are identified and documented.


### List Authorized Assets
By restricting what protocols/assets are permitted to run on a protocol, a protocol can significantly reduce the threat of external attack. To establish a list of authorized assets/protocols, an audit should be performed on all assets currently authorized or identified as necessary in an operational environment. Any unknown accessing assets discovered during such an audit should be considered suspect and investigated immediately.

### Identify Sensitive or Suspicious Accounts

All sensitive accounts should be reviewed to identify which accounts require a higher auditing level. Such accounts will include the default MultiSig account (if any), any members of the MultiSig, Operations, or Domain Admins groups (as example groups), and any accounts that are used by protocol services.


### Detect Policy Violations and Thresholds
Policy violations form the largest category of security issues for which businesses must plan. These types of incidents include:

Creation of user accounts outside of the established process.

Improper or unauthorized usage of administrator privileges (wrt MultiSig if applicalbe ).

Use of service accounts for interactive log on (Operations).

Function access attempts by unauthorized accounts.

Installation and execution of unapproved external function calls.

Although the most common type of policy violation is unintentional user access attempts, such as attempted access to restricted functions, such violations are usually the least significant because access limitations and well-designed rights policies address this issue. Administrative policy violations are the most significant type of event, whether deliberate or accidental, because of the very nature of administrative rights.
