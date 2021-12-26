# erx-prescription-generate

# Dev Notes
    1. Not for Dispensing - When you generate e Prescription and still you want a paper copy of prescription then it will generate prescription with water mark states that not for dispensing.
    
    2. NON-PBS - When you generate prescription with NON_PBS item, then it will have cross marks on PBS/RPBS fields on left hand and right hand sides.

    3. NON-PBS-E-Prescription - When you want to generate NON_PBS item prescription but still want to generate e-prescription then it will have a water mark states that not for dispensing.

    4. If You want to generate e-prescription directly then you can provide erx QR Code URL to prescription then it will add that barcode.

    5. Please refer to data and validation section.

## Data Options & Validations

    1. isEPrescription - boolean - default: false
    2. isPBS - boolean - default false
    3. doctorName - string - required - Ex. Dr. Vatsaly Patel
    4. clinicAddressLine1 - string - required - Ex. Unit/StreetNo StreetName
    5. clinicAddressLine2 - string - required - Ex. Suburb STATE PostCode
    6. clinicPhNo - string - required - Ex. 1800 000 000
    7. docPrescriberNumber - string - required - Ex. 0000000
    8. scriptNumber - string - required - Random number - Ex. Math.floor(100000 + Math.random() * 900000);
    9. eRxQRCodeUrl - string - optional - allow empty however is you have the eRX barcode url then you can pass it and package will implement that
    10. patientMedicareNumber - string - optional, however it will required for e-Prescription - default: ''
    11. patientMedicareRefrenceNumber - string - optional, however it will be required for e-Prescription - default: ''
    12. pharmecyEntitlementNumber - string - optional - not in use for now - default: ''
    13. pbsSafetyCardholder - boolean - optional - not in use for now - default: false
    14. pbsSafetyNetConcessionHolder - boolean - optional - not in use for now - default: false
    15. patientName - string - required - Ex. FirstName LastName
    16. patientAddressLine1 - string - required - Ex. Unit/StreetNo StreetName
    17. patientAddressLine2 - string - required - Ex. Suburb STATE Postcode
    18. dateOfPrescription - string - optional - Default: DD/MM/YYYY
    19. brandSubstitution - boolean - required - Ex. true/false - Brand Substitution Not Permitted
    20. drugName - string - required
    22. drugStrength - string - required
    23. drugFormType - string - required - Ex. Tablets
    24. drugDose - string - required - Ex. 20mg
    25. drugFrequency - string - required - Ex. 2 Daily
    26. medicationTakeWith - string - required - Ex. with food/on an empty stomach
    27. medicationQty - string - required - Ex. [20] Twenty
    28. repeats - string - required - Ex. 0/1/2
    29. isUnusualDose - boolean - Default: false - Ex. flag as unusual dose
    30. streamlinedAuthorityCode - string - If authorityRequiredPBS then we will have StreamlinedAuthorityCode (SAC) from MIMS
    33. APN - Authority Approval Number - this is depends on SAC
    34. prescriptionNumber - authorityRequiredPBS is true then we will have a prescriptionNumber required
    35. doctorQualification - string - required
    36. doctorSignature - string - requried - url of signature
    37. erxBarCodeUrl - string - required if you want to generate ePrescription
    38. otherPrescriptionDetails - string - max char 200 allowed - optional