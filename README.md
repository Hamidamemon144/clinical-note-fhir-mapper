# Clinical Note to FHIR Standard Mapper

An AI-driven clinical interoperability prototype designed to ingest unstructured clinical SOAP notes and parse them into standardized, EHR-ready HL7 FHIR (Release 4) JSON resources.

---

## Architecture & Repository Structure

* `main` — Core system prompts (`prompt_template.txt`), product requirements (`PRD.md`), and primary technical documentation.
* `sample_inputs` — Synthetic test data across chronic care, surgical post-operative, and pediatric domains.
* `fhir_outputs` — Validated HL7 FHIR R4 JSON `Bundle` collections corresponding to each clinical test case.

---

## Standards & Compliance

* Data Specification: HL7 FHIR Release 4 (R4)
* Clinical Terminologies: SNOMED CT (Conditions), RxNorm (Medications), LOINC (Observations & Vitals), UCUM (Units)
* Privacy & Security: Zero-retention stateless processing pipeline with automated de-identification prior to mapping

---

## System Workflow

1. Ingestion — Unstructured SOAP note text is received via the interface.
2. Parsing — System prompt rules enforce clinical entity extraction (Condition, MedicationRequest, Observation).
3. Payload Generation — Structured JSON output formatted inside a standard FHIR `Bundle` resource collection.
