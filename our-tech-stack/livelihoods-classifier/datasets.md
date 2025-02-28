# Datasets

## Reference Sets

#### Occupations

* **Location**: inference/files/occupations\_augmented.csv
* **Source**: [ESCO dataset - v1.1.1](https://esco.ec.europa.eu/en/use-esco/download)
* **Description**: ESCO (European Skills, Competences, Qualifications and Occupations) is the European multilingual classification of Skills, Competences, and Occupations. This dataset includes information relevant to the occupations.
* **License**: Creative Commons Attribution 4.0 International see DATA\_LICENSE for details.
* **Modifications**: The columns retained are `alt_label`, `preferred_label`, `esco_code`, and `uuid`. Each alternative label has been separated into individual rows.

#### Skills

* **Location**: inference/files/skills.csv
* **Source**: [ESCO dataset - v1.1.1](https://esco.ec.europa.eu/en/use-esco/download)
* **Description**: ESCO (European Skills, Competences, Qualifications and Occupations) is the European multilingual classification of Skills, Competences and Occupations. This dataset includes information relevant to the skills.
* **License**: Creative Commons Attribution 4.0 International see Data License for details.
* **Modifications**: The columns retained are `preferred_label` and `uuid`.

#### Qualifications

* **Location**: inference/files/qualifications.csv
* **Source**: [Official European Union EQF comparison website](https://europass.europa.eu/en/compare-qualifications)
* **Description**: This dataset contains EQF (European Qualifications Framework) relevant information extracted from the official EQF comparison website. It includes data strings, country information, and EQF levels. Non-English text was ignored.
* **License**: Please refer to the original source for [license information](https://europass.europa.eu/en/node/2161).
* **Modifications**: Non-English text was removed, and the remaining information was formatted into a structured database.

For the French version of the tool, we use the French version of ESCO v1.1.1, as well as, a translation of the qualifications, using the Google Translation API.&#x20;

## Training Sets

#### **Entity Extraction**

* **Location:** [ job\_ner\_dataset](https://huggingface.co/datasets/tabiya/job_ner_dataset)
* **Source:** [Green Benchmark corpus](https://github.com/acp19tag/skill-extraction-dataset)
* **Description:** This dataset provides a comprehensive benchmark suite for Entity Recognition (ER) in job descriptions. Developed to fill the significant gap in resources for extracting key entities like skills from job descriptions, the dataset features 18.6k annotated entities across five categories: Skill, Qualification, Experience, Occupation, and Domain.
* **License:** CC-BY-NC-4.0
* **Modifications:** No modifications were made to the original dataset. It was only converted to HuggingFace format.

#### **Entity Similarity**

* **Location:** TBD
* **Source:**[ hahu-occupation-titles](https://huggingface.co/datasets/tabiya/occupation_titles_esco)
*   **Description:**&#x20;

    The `hahu_test.csv` file is the original file provided by Hahu Jobs with the following fields:

    * title: The title of the job position, indicating the specific role and/or position within the organization.
    * esco\_label: The preferred or alternative label provided by ESCO, matching the corresponding ESCO code.
    * esco\_code: The ESCO code associated with the job, facilitating standardized classification and comparison across different job listings.
* **License:** CC-BY-NC-4.0
* **Modifications:** Extracted Occupation title and relevant ESCO code and matched with preferred and alternative labels.

## Evaluation Sets

#### Hahu Test

* **Location**: inference/files/eval/redacted\_hahu\_test\_with\_id.csv
* **Source**: [hahu\_test](https://huggingface.co/datasets/tabiya/hahu_test)
* **Description**: This dataset consists of 542 entries chosen at random from the 11 general classification system of the Ethiopian hahu jobs platform. 50 entries were selected from each class to create the final dataset.
* **License**: Creative Commons Attribution 4.0 International see Data License for details.
* **Modifications**: No modifications were made to the selected entries.

#### House and Tech

* **Location**:
  * inference/files/eval/house\_test\_annotations.csv
  * inference/files/eval/house\_validation\_annotations.csv
  * inference/files/eval/tech\_test\_annotations.csv
  * inference/files/eval/tech\_validation\_annotations.csv
* **Source**: Provided by [Decorte et al.](https://arxiv.org/abs/2209.05987)
* **Description**: The dataset includes the HOUSE and TECH extensions of the SkillSpan Dataset. In the original work by Decorte et al., the test and development entities of the SkillSpan Dataset were annotated into the ESCO model.
* **License**: MIT, Please refer to the original source.
* **Modifications**: The datasets were used as provided without further modifications.

#### Qualification Mapping

* **Location**: inference/files/eval/qualification\_mapping.csv
* **Source**: Extended from the [Green Benchmark](https://github.com/acp19tag/skill-extraction-dataset) Qualifications
* **Description**: This dataset maps the Green Benchmark Qualifications to the appropriate EQF levels. Two annotators tagged the qualifications, resulting in a Cohen's Kappa agreement of 0.45, indicating moderate agreement.
* **License**: Creative Commons Attribution 4.0 International see Data License for details.
* **Modifications**: Extended the dataset to include EQF level mappings and the annotations were verified by two annotators.

#### Access and Usage

To use these datasets, ensure you comply with the original dataset's license and terms of use. Any modifications made should be documented and attributed appropriately to your project.

{% hint style="info" %}
For datasets requiring access tokens, such as those from HuggingFace 🤗, please contact the maintainers.
{% endhint %}

