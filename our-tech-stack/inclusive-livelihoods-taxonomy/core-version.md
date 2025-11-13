---
description: >-
  Our Core Taxonomy introduces important changes to ESCO to better reflect the
  livelihoods and economic realities in low- and middle-income countries, but
  avoids country-specific adaptations.
---

# Core Taxonomy

Our [Inclusive Livelihoods Taxonomy](./) introduces important changes to [ESCO](https://esco.ec.europa.eu/en) to better reflect the livelihoods and economic realities in low- and middle-income countries. This page presents our **standardized Core version, which is not country-specific.** We use our [Taxonomy Management Platform](open-taxonomy-platform/)  to manage and maintain various adapted and country-specific versions.

{% hint style="info" %}
The Core version of our taxonomy is continuously evolving. Regular updates integrate feedback, corrections, and new insights from our partners to better represent diverse economic activities.
{% endhint %}

## Version 1.0.0

Version 1.0.0 of the Core Taxonomy expands conventional job and skill classifications by changing [ESCO v.1.1.1](https://esco.ec.europa.eu/en/about-esco/escopedia/escopedia/esco-v111) in the following ways:

* **Including New Occupations:** Such as "Micro-entrepreneur," explicitly recognizing self-employed individuals and small-scale entrepreneurial activities.
* **Capturing Unseen Economic Activities:** Integrating overlooked roles and activities such as caregiving, housework, volunteer work, and informal employment, guided by the [International Classification of Activities for Time-Use Statistics (ICATUS) 2016](https://unstats.un.org/unsd/classifications/Family/Detail/2083).
* **Enhancing Accessibility:** Adding simplified alternative labels and clearer terminology, making the taxonomy more approachable and easy to use.
* **Ensuring Data Quality:** Regularly refining taxonomy entries by fixing missing labels, removing duplicate records, and standardizing formatting and textual clarity.

### Detailed Release Notes

This version builds on [ESCO v1.1.1](https://esco.ec.europa.eu/en/about-esco/escopedia/escopedia/esco-v111). The latest Tabiya Core taxonomy version includes these specific updates:

* **Added:** New Micro-entrepreneur occupation (code: 5221\_2 uuid: d76f0bac-7145-4acc-a53e-259b96a6346b).
* **Added:** Unseen economy occupations/activities from the ICATUS 2016 classification:
  * 12 Occupation Groups (I3, I31, I32, I33, I34, I35, I36, I37, I4, I41, I42, I43, I44, I5, I51, I52).
  * 60 Occupations (e.g., I31\_0..., I32\_0..., I33\_0..., etc.).
  * 72 Occupation hierarchy entries.
  * 3689 Skills Relations.
* **Fixed:** Missing preferred labels in altLabels of ISCO groups, skill groups, some occupations, and some skills.
* **Fixed:** Duplicate alternative labels.
* **Fixed:** Invisible characters such as \t, nbsp, etc., in several text fields.
* **Fixed:** Leading/trailing spaces or new lines in several text fields.
* **Fixed:** Reformatted scope notes for better readability.

## File Format and Download

### CSV File Format — Compatible with ESCO

Our taxonomy is distributed in a CSV (Comma-Separated Values) format, ensuring ease of use, integration, and compatibility with existing ESCO-based systems.&#x20;

[A Zip file with all CSV files of Version 1.0.0 can be downloaded here.](https://platform.tabiya.tech/downloads/673b3fc9b52651611ad13a80-export-673b41d2b52651611ad13be4.zip)

#### Structure of the CSV Format:

* **`conceptId`:** A unique identifier (UUID) for each occupation or skill.
* **`preferredLabel`:** The primary, official label for the occupation or skill.
* **`alternativeLabels`:** Additional labels or synonyms, improving accessibility and understanding.
* **`description`:** Concise notes providing context, scope, or detailed explanations of occupations or skills.
* **`broaderConcept`:** Links to parent classifications, creating hierarchical relationships.
* **`narrowerConcept`:** Links to subordinate classifications, detailing hierarchical depth.
* **`relatedConcept`:** Associations indicating related occupations or skills.
* **`skillRelations`:** Explicit relationships linking specific skills to relevant occupations, allowing precise mapping.
* **`iscoGroup`:** ISCO occupational group codes aligning occupations with international standards.

This format closely follows ESCO’s CSV structure, enhancing interoperability and facilitating easy integration into existing workflows. For detailed technical documentation, refer to the [Tabiya CSV Format Specification](core-version.md#csv-file-format-compatible-with-esco).

## Licensing and Availability

The Tabiya Core Taxonomy is openly available under the **Creative Commons Attribution 4.0 International (CC BY 4.0)** license, facilitating unrestricted use, adaptation, and sharing with appropriate attribution.
