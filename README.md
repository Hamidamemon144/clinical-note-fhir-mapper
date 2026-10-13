# clinical-note-fhir-mapper
AI-powered clinical note parser converting unstructured SOAP notes into HL7 FHIR JSON resources to support EHR interoperability and reduce physician documentation burden.

## 📁 Repository Structure
* **`main` Branch**: Contains core system prompts (`prompt_template.txt`), product requirements (`PRD.md`), and overall architectural documentation.
* **`sample_inputs` Branch**: Includes synthetic test cases across chronic, surgical, and pediatric domains.
* **`fhir_outputs` Branch**: Contains fully compliant, pre-mapped HL7 FHIR R4 JSON `Bundle` outputs corresponding to each sample case.

## 🛠️ Interoperability Standards
* **Data Format**: HL7 FHIR Release 4 (R4)
* **Terminologies**: SNOMED CT (Conditions), RxNorm (Medications), LOINC (Observations/Vitals), UCUM (Units)
* **Compliance**: Zero-retention stateless processing & automated de-identification.
