---
layout: default 
title: Frequently Asked Questions
collection: common
permalink: common/faq/
---
 
 
- [Will my PIV credentials break or need to be updated or replaced when this change occurs](#will-my-piv-credentials-break-or-need-to-be-updated-or-replaced-when-this-change-occurs)
- [Is the Federal Common Policy CA changing?](#is-the-federal-common-policy-ca-changing)
- [When will this change happen?](#when-will-this-change-happen)
- [Which types of systems will this change affect?](#which-types-of-systems-will-this-change-affect)
- [Which operating systems will this change affect?](#which-operating-systems-will-this-change-affect)
- [What happens if I don’t distribute the FCPCA G2?](#what-happens-if-i-dont-distribute-the-fcpca-g2)
- [What errors can occur in Windows if I don’t distribute the FCPCA G2?](#what-errors-can-occur-in-windows-if-i-dont-distribute-the-fcpca-g2)
- [What errors can occur in macOS if I don’t distribute the FCPCA G2?](#what-errors-can-occur-in-macos-if-i-dont-distribute-the-fcpca-g2)
- [What errors can occur in iOS if I don’t distribute the FCPCA G2?](#what-errors-can-occur-in-ios-if-i-dont-distribute-the-fcpca-g2)
- [How can I verify that the FCPCA G2 has been successfully distributed to my workstation or device?](#how-can-i-verify-that-the-fcpca-g2-has-been-successfully-distributed-to-my-workstation-or-device)
- [My agency gets PIV cards from [Issuer Name]. I won’t be affected by this change, right?](#do-i-need-to-distribute-the-fcpca-g2-to-my-bring-your-own-device-byod-program-device)
- [Why aren't some Entrust Federal Shared Service Provider issued PIV credential certificates chaining to FCPCA G2?](#why-arent-some-entrust-federal-shared-service-provider-issued-piv-credential-certificates-chaining-to-fcpca-g2)
- [Do I need to distribute the FCPCA G2 to my Bring Your Own Device (BYOD) program device?](#do-i-need-to-distribute-the-fcpca-g2-to-my-bring-your-own-device-byod-program-device)
 
 
## Will my PIV credentials break or need to be updated or replaced when this change occurs?

No. PIV credentials will *not* be affected by this change.  For example, the graphic below shows the current and future state of certificate validation for a PIV credential issued by the USAccess Program.  Although two certificates in the chain are being updated, the PIV credential certificates are *not* affected. 
<br>
![current_and_future_state]({{site.baseurl}}/img/FCPCA_G2_Transition.jpg) 

## Is the Federal Common Policy CA changing?

Yes. In **October 2020**, the Federal Government established a new Federal Public Key Infrastructure (FPKI) Root Certification Authority (CA) known as the **Federal Common Policy CA (FCPCA) G2**. 

Between December 2020 and May 2021, CAs cross-certified by the existing FCPCA will be migrated to the FCPCA G2. Once the migration is complete, the existing FCPCA will be decommissioned (planned for May 2021). 

## When will this change happen?

Timeline:
- **October 14, 2020**: The Federal PKI Management Authority (FPKIMA) established the new FCPCA G2.
- **October 15, 2020**: The FPKIMA issued and distributed a cross certificate from the FCPCA G2 to the Federal Bridge CA G4.
- **November 18, 2020**: The FPKIMA issued and distributed certificates to migrate agency and affiliate CAs cross-certified by the existing FCPCA to the FCPCA G2.
- **December 2020 to May 2021**: All agencies transition from using the existing FCPCA as a trust anchor to the FCPCA G2.
- **May 2021**: The FPKIMA decommissions the existing FCPCA.

## Which types of systems will this change affect?

This change will affect any system that requires the ability to validate certificates issued by the Federal PKI.  This includes systems configured for Personal Identity Verification (PIV) credential authentication to government networks or web applications, systems that require the ability to verify digital signatures that leverage PIV or similar credentials, and systems that host applications or services that leverage the Federal Common Policy CA as a root CA.

Classified systems are not affected by this change.

## Which operating systems will this change affect?

All major operating systems (i.e., Microsoft Windows, macOS, iOS, *nix) will be affected.

## What happens if I don’t distribute the FCPCA G2?

1. **(*High Impact*) Authentication failures**
	- Workstations 
	- Websites  
	- Applications (internal and cross-agency)
	- Virtual Private Networks (VPNs)

2. **(*Medium Impact*) Error fatigue**
	- Unexpected application errors and system behavior for legacy and government-off-the-shelf (GOTS) products

3. **(*Low Impact*) Digital signature validation failures**
	- Email
	- Documents and files (for example, Microsoft Word)

## What errors can occur in Windows if I don't distribute the FCPCA G2?

*Sample Chrome error when a user navigates to an intranet site whose SSL/TLS certificate doesn't chain<br>to a trusted root CA:*
     <br>
     ![error_navigation]({{site.baseurl}}/img/error_navigation.png)

*Sample Chrome error when PIV authentication fails because the user’s certificate doesn't chain<br>to a trusted root CA:*
     <br>
     ![error_piv_auth]({{site.baseurl}}/img/error_piv_auth.png)

*Sample Microsoft Outlook error when a digital signature certificate for an email doesn't chain<br>to a trusted root CA:*
     <br>
     <br>
     ![error_sig_val]({{site.baseurl}}/img/error_sig_val.png)
	 
## What errors can occur in macOS if I don't distribute the FCPCA G2?

*Sample Safari error when a user navigates to an intranet site whose SSL/TLS certificate doesn't chain<br>to a trusted root CA:*
     <br>
     ![safari_untrusted_ssl]({{site.baseurl}}/img/safari_untrusted_ssl.png){:style="width:85%;"}
    
*Sample Safari error where client (PIV) authentication fails because a user’s certificate doesn't chain to a trusted root CA:*
     <br>
     ![safari_untrusted_auth]({{site.baseurl}}/img/safari_untrusted_auth.png){:style="width:85%;"}
   
*Sample Chrome error when a user navigates to an intranet site whose SSL/TLS certificate doesn't chain<br>to a trusted root CA:*
     <br>
     ![chrome_untrusted_ssl]({{site.baseurl}}/img/chrome_untrusted_ssl.png){:style="width:85%;"}

*Sample Chrome error where client (PIV) authentication fails because a user’s certificate doesn't chain to a trusted root CA:*
     <br>
     ![chrome_untrusted_auth]({{site.baseurl}}/img/chrome_untrusted_auth.png){:style="width:85%;"}

## What errors can occur in iOS if I don't distribute the FCPCA G2?

*Sample Safari error when a user navigates to an intranet site whose SSL/TLS certificate doesn't chain<br>to a trusted root CA:*
     <br>
     ![ios_safari_untrusted_ssl]({{site.baseurl}}/img/ios_safari_untrusted_ssl.png){:style="width:30%;"}

*Sample Chrome error when a user navigates to an intranet site whose SSL/TLS certificate doesn't chain<br>to a trusted root CA:*
     <br>
     ![ios_chrome_untrusted_ssl]({{site.baseurl}}/img/ios_chrome_untrusted_ssl.png){:style="width:30%;"}

## How can I verify that the FCPCA G2 has been successfully distributed to my workstation or device?

Please review the steps to [verify distribution of the FCPCA G2]({{site.baseurl}}/common/verify-os-distribution/).

## My agency gets PIV cards from [Issuer Name]. I won’t be affected by this change, right?

This change *does not* affect your PIV credential issuer, nor how agency credentials are generated or issued.

This change *does* affect how federal enterprise workstations and devices validate PIV credential certificates.  

## Why aren't some Entrust Federal Shared Service Provider issued PIV credential certificates chaining to FCPCA G2?

Entrust Federal Shared Service Provider (SSP) PIV credential certificates issued before August 13, 2019, chain through an older version of the Entrust Managed Services Root CA on their way to the Federal Common Policy CA than certificates issued since.  This older version of the Entrust Managed Services Root CA will not receive a certificate from the Federal Common Policy CA G2.

To ensure PIV credential certificates issued by the Entrust Federal SSP before August 13, 2019 validate to the Federal Common Policy CA G2, you may need to distribute [this](../../certs/Entrust_Managed_Services_Root_CA_Link.cer) "link certificate" as an intermediate CA certificate.  The link certificate allows workstations to build a path from the older Entrust Managed Services Root CA to the current version, which has been issued a certificate by the Federal Common Policy CA G2.  Review how to distribute intermediate CA certificates [here]({{site.baseurl}}/common/certificates/).

Workstations capable of performing dynamic path validation **do not** require manual distribution of the link certificate.

The graphic below shows a certificate chaining to the Federal Common Policy CA G2 through the Entrust Managed Services Root CA link certificate, denoted with a red asterisk (" <span style="color:red">*</span>.")

![Link Certificate Path]({{site.baseurl}}/img/link-cert-path.png) 

## Do I need to distribute the FCPCA G2 to my Bring Your Own Device (BYOD) program device?

As a BYOD program device user, you'll need to distribute the FCPCA G2 if you:
- use your PIV credential to log into intranet sites or VPNs,
- validate PIV digital signatures in emails or documents, or
- navigate to intranet pages whose SSL/TLS certificates chain to the FCPCA G2.
