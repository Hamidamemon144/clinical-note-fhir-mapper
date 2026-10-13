# Product Requirements Document (PRD): Clinical Note to FHIR Standard Mapper

## 1. Executive Summary
Physicians spend up to 50% of their working hours trapped in administrative documentation, leading to severe burnout and data silos within Electronic Health Records (EHRs). The **Clinical Note to FHIR Standard Mapper** is a lightweight, AI-driven interoperability tool designed to ingest unstructured clinical SOAP notes and instantly parse them into standardized, EHR-ready HL7 FHIR (Release 4) JSON resources.

## 2. Problem Statement
* **The Clinical Burden:** Unstructured text (SOAP notes) cannot be easily queried, analyzed, or shared across disparate hospital systems.
* **The Interoperability Barrier:** Traditional healthcare mapping requires complex, expensive legacy integration engines (like Mirth Connect) and heavy engineering overhead.
* **The Opportunity:** Leveraging LLM prompting guided by clinical domain knowledge allows for rapid, zero-code structuring of clinical data.

## 3. Target Users
* **Primary Users:** Physicians, clinicians, and medical scribes looking to minimize manual data entry.
* **Secondary Users:** Health IT engineers and interoperability specialists needing clean JSON payloads for EHR testing.

## 4. Key Features & Functional Requirements
1. **Unstructured Text Ingestion:** A clean input interface allowing clinicians to paste raw SOAP text.
2. **Automated Clinical Entity Extraction:** AI-driven mapping that categorizes text into three core FHIR resource types:
   * **Condition:** Active diagnoses and medical history.
   * **MedicationRequest:** Prescriptions, dosages, and administration routes.
   * **Observation:** Vital signs, physical measurements, and lab results.
3. **Dual View Output:** 
   * *Clinical Summary Card:* Human-readable summary for quick clinical validation.
   * *FHIR JSON View:* Raw interoperable payload adhering to HL7 FHIR Release 4 standard.

## 5. Security & Compliance Strategy (HIPAA)
* **Zero-Retention Endpoints:** AI processing endpoints are configured for stateless operation (no training on patient text).
* **Automated De-Identification:** The system prompt explicitly strips direct personal identifiers (names, phone numbers, exact addresses) prior to generating resource mapping.
* **Synthetic Data Usage:** Development and testing strictly utilize synthetic clinical records to ensure zero exposure of Protected Health Information (PHI).

## 6. Tech Stack & Architecture
* **Frontend & Logic Engine:** Momen (No-Code App Builder) for live UI/UX interaction and component routing.
* **AI Parsing Engine:** Master System Prompt (`prompt_template.txt`) guiding the LLM backend.
* **Data Standard:** HL7 FHIR Release 4 specification (`Bundle` resource collection).
* **Version Control:** GitHub (`clinical-note-fhir-mapper`) for project documentation and repository setup.
