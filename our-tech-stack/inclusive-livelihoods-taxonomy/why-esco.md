---
description: >-
  The European Skills, Competences, Qualifications, and Occupations taxonomy
  provides a comprehensive - albeit improvable - taxonomy of skills and
  occupations, on which our work builds.
---

# Why ESCO?

## Our Challenge

As explained [here](methodology.md), Tabiya's work builds upon widely used taxonomies of skills and competences to ensure that our inclusive taxonomy is compatible with existing intermediation tools used by governments and organisations. However, there exist multiple taxonomies serving as basis for national matching platforms and public policies, among which ISCO (International Standard Classification of Occupations), ESCO, O\*NET (Occupation Information Network) or OFO (Organising Framework for Occupations in South Africa).&#x20;

The challenge when picking a taxonomy is the following. On the one hand, the taxonomy needs to be broad enough to account for the occupations and human capital of job-seekers on the whole African continent and elsewhere. On the other hand, it needs to be adaptable to local contexts, which implies using a language understandable by local users, and encompassing context-specific skills and occupations. Finally, it needs to be open-source and regularly updated, to account for the rapid evolution of labour markets, as well as the integration of new skills and occupations, such as the ones linked to AI or the green economy. Based on these considerations and discussions with our localised partners, ESCO appeared as the most appropriate taxonomy.&#x20;



## The Advantages of ESCO

#### Accessibility to job-seekers:&#x20;

1. When it comes to user experience, one of our main concerns is to make sure that demographics who may be traditionally marginalised from labour markets et intermediation solutions can use our inclusive taxonomy. In some contexts, the mastery of official languages, such as English in South Africa, is limited. Compared to O\*NET, ESCO relies on skill tags that are easier to understand.&#x20;
2. ESCO contains a list of ‘similar titles’ for each occupation – making it easier to search for an occupation from a broad starting point. For instance, "data engineer" is saved as an alternative title for "data scientist", which ensures that one may use the platform by typing out "data engineer". &#x20;

#### Highlighting job seekers' skills

1. Contrary to O\*NET, ESCO includes "attitudes and values", which are soft-skills missing in O\*NET. Therefore, it covers a broader range of skills that are sought after by employers.&#x20;
2. ESCO is a European Commission project administered by the Directorate General Employment, Social Affairs and Inclusion. This ensures that the taxonomy is frequently updated and will be used by major actors in the long run. On the contrary, the last update of ISCO was made in 2008, and the last update of OFO happened in 2013. Frequent updates of ESCO allow it to include skills and occupations associated with major evolutions in labour markets worldwide, such as the greening of economies and, in the next few years, the predictable growing reliance and AI.&#x20;

#### Compatibility with Compass

1. Technically, ESCO is designed to be used by third-party organisations. ESCO is specifically built for others to use and embed the taxonomy in their own technologies.&#x20;
2. Other developing countries in [Latin America have also adopted ESCO as their skills framework rather than ONET](https://publications.iadb.org/publications/english/document/A-Skills-Taxonomy-for-LAC-Lessons-Learned-and-a-Roadmap-for-Future-Users.pdf), and they are contributing to the open-source tools around ESCO which can be leveraged (for instance,  ML-classification models which take in free-text job-titles and assign the ESCO occupations).
3. [ESCO provides a Local API in addition to their web-based API](https://ec.europa.eu/esco/portal/api). This means that Tabiya can host this API locally and adjust it as need be without depending on third-party performance when the volumes of requests are scaled up. This also gives Tabiya the ability to edit and adapt the framework freely.
