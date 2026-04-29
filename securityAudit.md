# Scenario

Botium Toys is a small U.S. business that develops and sells toys. The business has a single physical location, which serves as their main office, a storefront, and warehouse for their products. However, Botium Toy’s online presence has grown, attracting customers in the U.S. and abroad. As a result, their information technology (IT) department is under increasing pressure to support their online market worldwide.

The manager of the IT department has decided that an internal IT audit needs to be conducted. She's worried about maintaining compliance and business operations as the company grows without a clear plan. She believes an internal audit can help better secure the company’s infrastructure and help them identify and mitigate potential risks, threats, or vulnerabilities to critical assets. The manager is also interested in ensuring that they comply with regulations related to internally processing and accepting online payments and conducting business in the European Union (E.U.).

The IT manager starts by implementing the National Institute of Standards and Technology Cybersecurity Framework (NIST CSF), establishing an audit scope and goals, listing assets currently managed by the IT department, and completing a risk assessment. The goal of the audit is to provide an overview of the risks and/or fines that the company might experience due to the current state of their security posture.

Your task is to review the IT manager’s scope, goals, and risk assessment report. Then, perform an internal audit by completing a controls and compliance checklist.

## Checklists

Yes = X
No = Empty

### Controls Assessment

Control,Yes,No

- [ ] Least Privilege
- [ ] Disaster recovery plans
- [ ] Password policies (needs improvement)
- [ ] Separation of duties
- [ X ] Firewall
- [ ] Intrusion detection system (IDS)
- [ ] Backups
- [ X ] Antivirus software
- [ ] Manual monitoring, maintenance, and intervention for legacy systems (needs improvement: schedule and intervention methods)
- [ ] Encryption
- [ ] Password management system
- [ X ] Locks (offices, storefront, warehouse)
- [ X ] Closed-circuit television (CCTV) surveillance
- [ X ] Fire detection/prevention (fire alarm, sprinkler system, etc.)

### Compliance Checklist: PCI DSS

Best Practice Yes No

- [ ] Only authorized users have access to customers’ credit card information.
- [ ] Credit card information is stored, accepted, processed, and transmitted internally, in a secure environment.
- [ ] Implement data encryption procedures to better secure credit card transaction touchpoints and data.
- [ ] Adopt secure password management policies.

### Compliance Checklist: GDPR

Best Practice Yes No

- [ ] E.U. customers’ data is kept private/secured.
- [ X ] There is a plan in place to notify E.U. customers within 72 hours if their data is compromised/there is a breach.
- [ ] Ensure data is properly classified and inventoried.
- [ X ] Enforce privacy policies, procedures, and processes to properly document and maintain data.

### Compliance Checklist: SOC (Type 1 & Type 2)

Best Practice Yes No

- [ ] User access policies are established.
- [ ] Sensitive data (PII/SPII) is confidential/private.
- [ X ] Data integrity ensures the data is consistent, complete, accurate, and has been validated.
- [ ] Data is available to individuals authorized to access it. (needs improvement: accessible by everyone)

## Recommendations

Recommendations (optional): In this section, provide recommendations, related to
controls and/or compliance needs, that your IT manager could communicate to
stakeholders to reduce risks to assets and improve Botium Toys’ security posture.

## Immediate policies to implement:

- Least privilege and separation of duties
  - Company stores both PII and possibly SPII. Currently, this data is accessible by all employees. Immediate action must be taken to ensure that only those who require access to such data for their daily duties have access. Malicious or accidental access or spread of this data can cause irreperable harm to the company's reputation and result in identity theft, or IP becoming public.
- Backups
  - Loss of data will likely result in loss of business continuity and revenue.
- Encryption
  - Sensitive information, such as but not limited to SSNs and payment data, must be stored safely. This information should not be human readable by default. If a threat actor gains access to this information, there is a high risk of loss of reputation and identity theft. There might also be fines due to lack of compliance with regulations.
  - Ensure PCI DSS compliance by implementing end-to-end encryption for all credit card transaction touchpoints to avoid the risk of losing the ability to process payments.
- Secure password management
  - All passwords should meet minimum requirements, e.g. 8 characters or more with a combination of uppercase and lowercase letters, at least one number and special character. This centralized policy should apply to all users. Threat actors can easily break weak passwords, putting SPII and PII, systems, and other data at risk.
- Comply with GDPR
  - GDPR compliance is mandatory and hefty fines and loss of business may occur for lack of compliance. Ensure E.U. customer data is secured, properly classified, and inventoried.
- Add Intrusion Detection (IDS)
  - Implement an Intrusion Detection System (IDS) to provide real-time alerts on suspicious activity, allowing the IT team to respond to threats before they become full-scale breaches.
- Disaster Recovery (DR)
  - Develop a formal Disaster Recovery Plan to document the specific steps and roles required to restore operations after a critical failure or cyberattack.
