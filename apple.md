# Apple's Certificate Transparency policy

Learn how to comply with Apple's Certificate Transparency policy.

​                                                                                    

Publicly trusted Transport Layer Security (TLS)  server authentication certificates issued after October 15, 2018 must  meet Apple's Certificate Transparency (CT) policy to be evaluated as  trusted on Apple platforms. Previously, only publicly trusted Extended  Validation (EV) TLS server authentication certificates were required to  meet this CT policy.

Certificates that fail to comply with our policy will result in a  failed TLS connection, which can break an app’s connection to Internet  services or Safari’s ability to seamlessly connect. 

## Policy requirements

Apple's policy requires at least two Signed  Certificate Timestamps (SCT) issued from a CT log — once-approved* or  currently approved at the time of check — and either:

- At least two SCTs from currently approved CT logs with one SCT presented via TLS extension or OCSP Stapling; or
- At least one embedded SCT from a currently approved log and at least the number of SCTs from once or currently approved logs, based on  validity period as detailed in the table below.

Number of embedded SCTs based on certificate lifetime:

| Certificate lifetime | # of SCTs from separate logs |
| -------------------- | ---------------------------- |
| Less than 15 months  | 2                            |
| 15 to 27 months      | 3                            |
| 27 to 39 months      | 4                            |
| More than 39 months  | 5                            |

\* To be considered “once-approved,” the timestamp in the SCT must  have been issued from a CT log that was in the approved CT log list at  the time of the SCT issuance.

![img](https://web.archive.org/web/20201207182124im_/https://support.apple.com/library/content/dam/edam/applecare/images/en_US/mac_apps/itunes/divider.png)

## CT logs

Download the [current CT Log list](https://web.archive.org/web/20201207182124/https://valid.apple.com/ct/log_list/current_log_list.json) and [CT Log list schema](https://web.archive.org/web/20201207182124/https://valid.apple.com/ct/log_list/current_log_list_schema.json) in JSON format.

Information about products not manufactured by Apple, or independent websites not  controlled or tested by Apple, is provided without recommendation or  endorsement. Apple assumes no responsibility with regard to the  selection, performance, or use of third-party websites or products.  Apple makes no representations regarding third-party website accuracy or reliability. [Contact the vendor](https://web.archive.org/web/20201207182124/http://support.apple.com/kb/HT2693) for additional information.

​                                                Published Date: January 23, 2019                                            