---
description: >-
  Extending the ESCO taxonomy by including the unseen economy while adapting our
  methodology to the challenges met gave us valuable lessons.
---

# Lessons Learned

## ESCO vs O\*Net

{% hint style="danger" %}
This section will be filled promptly.&#x20;
{% endhint %}

## ICATUS Level Choice

As discussed [here](./), the ICATUS taxonomy comprises three levels that represent different levels of disaggregation, namely the major division, division and group levels. For Tabiya’s matching procedure, the group level activities pertaining to the unseen economy are matched to ESCO Occupations. There are a total of 60 ICATUS group level activities that comprise the Framework’s ICATUS input. The group level is chosen, rather than the major division or division level primarily due to the fact that the group level attains the highest level of precision in the ICATUS taxonomy. Thus, we are able to glean the most detail when matching from this level, relative to the major division and division levels.&#x20;

The challenge, though, has been in the matching of group level activities to ESCO occupations that occasionally define activities and occupations at differing levels of granularity. In particular, we find that there are some instances where an ESCO Occupation comprises more than one ICATUS group level. For instance, the ICATUS group level activities, “Cleaning up after food preparation/meals/snacks'' and “Preparing meals/snacks” are each matched to the ESCO occupation, “kitchen assistant” (defined as “Kitchen assistants assist in the preparation of food and cleaning of the kitchen area.”). Clearly, the occupation “kitchen assistant” is made up of these two ICATUS group level activities. Theoretically, one way to circumvent this would be to match ICATUS activities at the division level, rather than at the group level. However, this method is ultimately deemed too information costly since at the division level, the chance of omitting relatively rare but relevant ESCO occupations (and in turn, skills) from the ICATUS to ESCO match is very high. This does harm to the end user because it limits the eventual list of skills available to represent the work that they do. After discussion between the research team, and the Harambee team, we mutually agreed that the best way to do no harm in this case is to match ICATUS activities to ESCO occupations at the group level.

## ESCO occupations as a substep to skills (NLP, Word2Vec etc.)

The reason that ICATUS activities are matched to ESCO occupations, and then to skills as opposed to a match from ICATUS activities immediately to skills requires a summary of the conceptual roadmap taken to ultimately come to this decision. Initially, since the goal is to assign skills to activities, the most intuitive course of action seemed to be to directly match ICATUS activities to ESCO skills. In order to do this, Natural Language Processing (NLP) techniques were adopted. In particular, to compare ICATUS activities to ESCO skills, a technique called Word2Vec was adopted. Word2Vec is an algorithm used in NLP that uses word embeddings to assign numerical values to a given word in relation to the surrounding context of this word which is informed by the relationship that this given word has with other words in a dictionary used to train the algorithm (Mikolov et al., 2013). After several attempts to match ESCO skills directly to ICATUS activities, NLP techniques failed due the incompatibility in nature between ICATUS/ESCO as inputs and the required input for the algorithm to function optimally. Since ICATUS comprised short phrases pertaining to activities rather than single words as the ESCO taxonomy does for skills, Word2Vec could not optimally reconcile these taxonomies to produce a meaningful skills match. From this arose a precision-reproducibility tradeoff. On the one hand, NLP methods allow for near perfect reproducibility but score low on the precision scale in this context. A decision was taken to prioritize precision throughout the conceptualizing of the Tabiya Framework. Thus, the prevailing methodology that uses ESCO occupations as a crosswalk to skills proved to strike the precision-reproducibility scale optimally for our purposes. That is, the manual assignment of ESCO occupations to ICATUS activities to derive skills associated with unseen economy proved to score high on the precision scale and high enough on reproducibility scale, since this work was independently checked. Hence, the manual matching procedure prevailed for the Tabiya Framework’s creation.&#x20;

\
\
\
