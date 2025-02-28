# Introduction

The Tabiya Livelihoods Classifier provides an easy-to-use implementation of the entity-linking paradigm to support job description heuristics. &#x20;

Using state-of-the-art transformer neural networks this tool can extract 5 entity types: Occupation, Skill, Qualification, Experience, and Domain. For the Occupations and Skills,  ESCO-related entries are retrieved.  The procedure consists of two discrete steps, entity extraction and similarity vector search.

### Model's Architecture

<figure><img src="../../.gitbook/assets/entity_linker (1).png" alt=""><figcaption><p>Job Entity Linking Pipeline</p></figcaption></figure>

### Target Audience

The tool is intended for specialists in workforce analytics, recruitment technologies, and human capital management, as well as researchers focused on labor markets and job data. It caters to organizations and professionals who deal with analyzing, categorizing, and optimizing job descriptions or resumes at scale. Ideal users include those in HR technology, career advisory services, and data-driven talent solutions, particularly those seeking to enhance precision in identifying roles, skills, and qualifications for improved decision-making in hiring or workforce planning. Technical users interested in integrating standardized frameworks into their analysis will also find this tool highly relevant.

{% hint style="info" %}
You can find all related code on [Tabiya's GitHub page](https://github.com/tabiya-tech/tabiya-livelihoods-classifier/tree/main).
{% endhint %}
