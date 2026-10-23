# EMIS — Existing Systems Comparison

**Project:** Design and Development of a Privacy-Aware QR/NFC-Based Emergency Medical Information System  
**Deliverable:** Existing Systems Comparison — First Pre-Defense  


## 1. Purpose

This document compares existing approaches for making essential medical information available during emergencies. The objective is to identify useful design patterns, limitations, and requirements for the proposed Emergency Medical Information System (EMIS).


## 2. Systems Selected

1. **Apple Medical ID (Health app):** emergency medical information stored on an iPhone, with optional visibility from the lock screen. Official information: https://support.apple.com/guide/iphone/set-up-your-medical-id-iph08022b194/ios
2. **Android Emergency Information:** emergency details and contacts that can be configured on supported Android devices; presentation varies by manufacturer and Android version. Official Android help: https://support.google.com/android/
3. **MedicAlert:** medical identification jewelry linked to medical information and, in some offerings, an emergency-response service. Official website: https://www.medicalert.org/
4. **MyID:** wearable medical identification products associated with a digital medical profile. Official website: https://getmyid.com/

These four systems represent two common models: **phone-based emergency information** and **wearable identification linked to a profile or service**.

## 3. Comparison Criteria

The same nine criteria are used for every system:

1. **Emergency access mechanism:** how a responder finds the information.
2. **Dependence on the owner's phone:** whether the owner's phone is needed at the scene.
3. **Physical identification option:** whether an external item can direct responders to information.
4. **QR/NFC relevance:** whether QR or NFC is central to the access model.
5. **Medical information scope:** whether the system can present key facts such as allergies, conditions, or contacts.
6. **Information update workflow:** how an owner updates their information.
7. **Privacy/access approach:** what is publicly accessible and what needs protection.
8. **Connectivity dependence:** whether the information can be accessed without network service.
9. **Main practical limitation:** a significant constraint for emergency use.

## 4. Comparison Matrix

| Criterion | Apple Medical ID | Android Emergency Information | MedicAlert | MyID | Proposed EMIS |
|---|---|---|---|---|---|
| Emergency access | iPhone emergency/Medical ID interface, if enabled | Device emergency information interface, if supported and configured | Medical ID item and associated service/profile | Medical ID wearable and associated profile | Scan QR or tap NFC card to open limited emergency profile |
| Owner's phone required | **Yes**, for on-device access | **Yes**, for on-device access | **Not necessarily** | **Not necessarily** | **No**, if responder has a compatible device |
| Physical ID item | Not inherent to Medical ID | Not inherent to emergency information | **Yes** | **Yes** | **Planned** QR/NFC card |
| QR/NFC central | No | No | Not a universal requirement | Product-dependent; verify specific product | **Planned** dual QR/NFC entry |
| Key medical facts | Yes, if entered by owner | Yes, fields vary by device | Yes, depending on enrollment/service | Yes, depending on profile/product | **Planned** allergies, conditions, medications, contacts |
| Updates | Health app on owner's device | Device settings / safety app | Account/service workflow | Account/profile workflow | **Planned** authenticated owner dashboard |
| Privacy/access | Owner controls whether lock-screen information is shown | Device-specific controls | Service- and product-specific; verify | Service- and product-specific; verify | **Planned** minimum public data, restricted editing |
| Internet required for core access | Not generally for locally stored Medical ID | Not generally for locally stored emergency info | Depends on service and interaction | Digital profile generally needs connectivity; verify | **Planned** online profile; offline fallback under consideration |
| Principal limitation | Responder must locate and access owner's iPhone | Interface and support differ by device | May depend on membership, service, and responder process | Digital access may depend on network and product | Not yet implemented; depends on responder connectivity and safe privacy design |

**Interpretation:** “Yes” means a general capability of the identified product family, not a guarantee in every device or subscription. “Planned” means a proposed EMIS requirement, not a completed feature. Product-specific QR/NFC, pricing, emergency hotline, and access-control claims require separate verification before being presented as definitive facts.

## 5. Strengths and Limitations

### 5.1 Apple Medical ID

**Strengths:** Integrates with an existing smartphone, can display emergency details without normal device unlocking when configured, and allows the owner to maintain information in the Health app.

**Limitations for the EMIS scenario:** Availability at the scene depends on the owner's iPhone being present, accessible, and configured. It is not a separate physical medical card.

### 5.2 Android Emergency Information

**Strengths:** Offers an emergency information option on many Android phones and may make key contacts and health details accessible without normal unlocking.

**Limitations for the EMIS scenario:** Setup and access paths differ across Android devices; the owner's device must be available. The team must not assume identical behavior on every Android phone.

### 5.3 MedicAlert

**Strengths:** Physical medical identification can signal to responders that important medical information exists, without first locating the owner's phone. Some offerings support additional emergency-response workflows.

**Limitations for the EMIS scenario:** Service features and access processes depend on the selected product and plan. A physical identifier does not by itself guarantee immediate access to a full digital profile.

### 5.4 MyID

**Strengths:** Combines wearable identification with an owner-maintained digital profile, providing a useful precedent for an external emergency identifier.

**Limitations for the EMIS scenario:** Actual features depend on the product. Access to a digital profile may require an internet connection; product-specific NFC and privacy behavior need verification.

## 6. Design Gap and EMIS Rationale

The comparison suggests a practical design opportunity: a **low-friction, independently carried emergency identifier** that is not tied to the owner's phone and exposes only a carefully selected subset of self-reported medical information.

EMIS proposes to investigate the following combination:

- **Dual access:** printed QR code plus NFC tag on one card.
- **Responder-oriented public view:** concise allergies, important conditions, relevant medication information, and emergency contact actions.
- **Owner-controlled updates:** authenticated editing of profile information.
- **Privacy-aware separation:** public emergency fields separated from private account data.
- **Clear trust boundaries:** labels explaining that the information is user-provided and may not be medically verified.
- **Emergency-first usability:** readable typography, high-priority warnings, and minimal navigation.

**Important:** These are project objectives and proposed differentiators. This document does not establish that no existing commercial system offers any of them, nor does it claim that EMIS currently implements them.

## 7. Requirements Derived from the Comparison

| ID | Proposed requirement | Rationale | Suggested acceptance evidence |
|---|---|---|---|
| FR-01 | QR code opens a public emergency profile | Access without owner's phone | QR scan demonstration |
| FR-02 | NFC tag resolves to the same public profile | Alternative physical interaction | NFC tap demonstration |
| FR-03 | Public view prioritizes allergies, conditions, and emergency contact | Fast emergency reading | Usability test with representative scenarios |
| FR-04 | Owner can update profile after authentication | Keep data current | Edit-and-refresh integration test |
| NFR-01 | Only explicitly approved fields appear publicly | Reduce unnecessary disclosure | Access-control and privacy test cases |
| NFR-02 | Public profile states data is self-reported | Avoid implying clinical verification | UI content inspection |
| NFR-03 | Public profile is mobile-responsive | Responder device diversity | Responsive layout testing |
| NFR-04 | Invalid or disabled card links fail safely | Prevent unintended exposure | Negative-path test cases |

## 8. Evaluation Implications

The proposed system should be evaluated against a baseline of accessing emergency information from a configured smartphone. Suggested measurements include: time to reach critical information, success rate for identifying an allergy, number of interaction steps, readability on small screens, and whether restricted data remains inaccessible without authorization.

The team has **not yet collected experimental results**; the measures above form an initial evaluation plan.

## 9. Limitations of This Comparison

- The matrix is a **draft** and does not constitute hands-on testing of the four products.
- Device- and subscription-specific functionality may change.
- No prices, adoption rates, security guarantees, or medical effectiveness claims are inferred.
- Formal usability, security, and emergency-response validation are future work.
- Product pages should be rechecked and dated before committee submission.

## 10. Sources for Product Verification

1. Apple Support. *Set up your Medical ID in the Health app on iPhone.* https://support.apple.com/guide/iphone/set-up-your-medical-id-iph08022b194/ios
2. Google Android Help. *Android Help Center* (navigate to emergency information / safety guidance for the tested Android version). https://support.google.com/android/
3. MedicAlert Foundation. *Official product and service information.* https://www.medicalert.org/
4. MyID. *Official product information.* https://getmyid.com/


---
