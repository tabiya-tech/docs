---
description: >-
  The European Skills, Competences, Qualifications, and Occupations (ESCO)
  taxonomy provides a comprehensive - albeit improvable - taxonomy of skills and
  occupations, on which our work builds.
---

# Why ESCO?

## Our Challenge: Picking the Correct Base Taxonomy

As explained [here](methodology.md), Tabiya's work enhances widely used skill and competence taxonomies to ensure that our inclusive taxonomy aligns with existing tools employed by governments and organizations. Several key taxonomies serve as the foundation for job matching platforms and public policies, among which the ILO's International Standard Classification of Occupations (ISCO), the European Commission's European Skills, Competences, Qualifications and Occupations (ESCO; built on top of ISCO), and the United States' Occupation Information Network (O\*NET) are the most widely-accepted globally standardized taxonomies. Many countries have their own established taxonomies, built independently or based on these global frameworks such as South Africa's Organizing Framework for Occupations (OFO) and Singapore's SkillsFuture.&#x20;

Tabiya's challenge when picking a base taxonomy is the following: we were trying to pick a comprehensive base of the "seen" economy with which to be able to expand for the "unseen" economy.  This fundamental expansion of how global labor taxonomy is applied and can be used requires that the base taxonomy is -&#x20;

1. Broad enough to account for the occupations and human capital of individuals all over the world.&#x20;
2. Adaptable to local contexts, which implies using a language understandable by local users, and encompassing context-specific skills and occupations.&#x20;
3. Open-source and regularly updated, to account for the rapid evolution of labor markets, as well as the integration of new skills and occupations, such as the ones linked to AI or the green economy.&#x20;

Based on these considerations and discussions with our local implementing partners, ESCO was deemed the most appropriate taxonomy.&#x20;

## The Advantages of ESCO

### Accessibility to Job Seekers

1. When it comes to user experience, one of our main concerns is to make sure that demographics who may be traditionally marginalized from labor market intermediation solutions can use our inclusive taxonomy. In some contexts, the mastery of official languages, such as English in South Africa, is limited. Compared to O\*NET, ESCO relies on skill tags that are easier to understand.&#x20;
2. ESCO contains a list of ‘similar titles’ or what they call, "alternative labels" for each occupation – making it easier to search for an occupation from a broad starting point. For example, "data engineer" and "data expert" are saved as alternative labels for "data scientist".  &#x20;

### Highlighting the Market's and Job Seekers' (Updated) Skills

1. Contrary to O\*NET, ESCO includes "attitudes and values", which are soft-skills missing in O\*NET. Therefore, it covers a broader range of skills that are sought after by employers.&#x20;
2. ESCO is a European Commission project administered by the Directorate General Employment, Social Affairs and Inclusion. This ensures that the taxonomy is frequently updated and will be used by major actors in the long run. On the contrary, the last update of ISCO was made in 2008. Frequent updates of ESCO allow it to include skills and occupations associated with major evolutions in labor markets worldwide - for example, the ESCO taxonomy already contains designated skill trees for green and digital skills.  &#x20;

### Compatibility with Compass and Other Open-Source Tools

1. From a technical standpoint, ESCO is designed to be used by third-party organizations. It is specifically built for others to use and embed the taxonomy in their own technologies.&#x20;
2. ESCO is arguably more widely adopted across countries. Developing countries in [Latin America have also adopted ESCO as their skills framework rather than ONET](https://publications.iadb.org/publications/english/document/A-Skills-Taxonomy-for-LAC-Lessons-Learned-and-a-Roadmap-for-Future-Users.pdf), and they are contributing to the open-source tools around ESCO which can be leveraged (for instance,  ML-classification models which take in free-text job-titles and assign the ESCO occupations).
3. [ESCO provides a Local API in addition to their web-based API](https://ec.europa.eu/esco/portal/api). This means that Tabiya can host this API locally and adjust it as need be without depending on third-party performance when the volumes of requests are scaled up. This also gives Tabiya the ability to edit and adapt the framework freely.
