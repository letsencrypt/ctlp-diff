# Apple's Certificate Transparency policy

Learn how to comply with Apple's Certificate Transparency policy.

​                                                                                    

Publicly trusted Transport Layer Security (TLS)  server authentication certificates must meet Apple's Certificate  Transparency (CT) policy to be evaluated as trusted on Apple platforms.

Certificates that fail to comply with our policy will result in a  failed TLS connection, which can break an app’s connection to Internet  services or Safari’s ability to seamlessly connect. 

## Policy requirements

Apple's policy requires at least two Signed Certificate Timestamps (SCT) issued from a CT log — once-approved1 or currently approved2 at the time of check — and either:

- At least two SCTs from currently approved CT logs with one SCT presented via TLS extension or OCSP Stapling; or
- At least one embedded SCT from a currently approved log and at least the number of SCTs from once or currently approved logs, based on  validity period as detailed in the table below.

For certificates with a notBefore value greater than or equal to  April 21, 2021 (2021-04-21T00:00:00Z), the Number of embedded SCTs based on certificate lifetime3:

| Certificate lifetime | # of SCTs from separate logs | Maximum # of SCTs per log operator which count towards the SCT requirement |
| -------------------- | ---------------------------- | ------------------------------------------------------------ |
| 180 days or less     | 2                            | 1                                                            |
| 181 to 398 days      | 3                            | 2                                                            |

For certificates with a notBefore value less than April 21, 2021  (2021-04-21T00:00:00Z), the Number of embedded SCTs based on certificate lifetime:

| Certificate lifetime | # of SCTs from separate logs |
| -------------------- | ---------------------------- |
| Less than 15 months  | 2                            |
| 15 to 27 months      | 3                            |
| 27 to 39 months      | 4                            |
| More than 39 months  | 5                            |

For certificates with a notBefore value equal to or greater than  20210421T00:00:00Z, log operators MAY reject leaf certificates which  don’t contain the serverAuth EKU. 

Log operators MUST provide a minimum of 45 days’ advance written  notice to certificate-transparency-program@group.apple.com of any  changes to the accepted set of leaf certificates their log(s) accepts.

![img](https://support.apple.com/library/content/dam/edam/applecare/images/en_US/mac_apps/itunes/divider.png)

## CT logs

Download the [current CT Log list](https://valid.apple.com/ct/log_list/current_log_list.json) and [CT Log list schema](https://valid.apple.com/ct/log_list/current_log_list_schema.json) in JSON format.

\1. To be considered  "once-approved", the timestamp in the SCT must have been issued from a  CT log with a "Qualified" or "Usable" status at the time of the SCT  issuance.

\2. For CT log status definitions, please refer to Apple’s Certificate Transparency log program: https://support.apple.com/kb/HT209255

\3. A certificate's validity period (or lifetime)  is defined in line with RFC 5280, Section 4.1.2.5, as "the period of  time from notBefore through notAfter, inclusive."

a. Validity period is  measured with a day being equal to 86,400 seconds. Any time greater than this indicates an additional day of validity. 

 

Information about products not manufactured by Apple, or independent websites not  controlled or tested by Apple, is provided without recommendation or  endorsement. Apple assumes no responsibility with regard to the  selection, performance, or use of third-party websites or products.  Apple makes no representations regarding third-party website accuracy or reliability. [Contact the vendor](http://support.apple.com/kb/HT2693) for additional information.

​                                                Published Date: March 05, 2021                                            