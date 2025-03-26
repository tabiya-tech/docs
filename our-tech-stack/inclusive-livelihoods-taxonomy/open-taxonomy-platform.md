---
description: >-
  Labor markets are diverse and fast changing, so a useful taxonomy must be
  localizable and adaptable in a transparent way. Our open taxonomy platform
  empower partners to do this.
---

# Open Taxonomy Platform

We are currently developing the **Open Taxonomy Platform,** which lets partners flexibly adapt our reference taxonomy in a transparent way. The platform is currently under active open-source development. You can [follow along and contribute on Github](https://github.com/tabiya-tech/taxonomy-model-application). If you would like to learn more, please [get in touch](mailto:hi@tabiya.tech).

## Key Features

1. **Reference Taxonomy**\
   We maintain a canonical set of occupations and skills for general use. This includes both traditional roles (e.g., _Accountant_) and informal or unpaid roles (e.g., _Family Caregiver_).
2. **Localization**\
   Partners create “forks” or branches of the base taxonomy to adapt local job titles, language requirements, or cultural specifics—without losing the broader structure. This means a localized taxonomy can still talk “under the hood” to other regions.
3. **API Access**\
   A simple REST API (with plans for GraphQL in the future) allows you to search, retrieve, and update taxonomy entries. Whether you’re building a job-matching platform or a chatbot, you can programmatically look up occupations, skills, tasks, or synonyms.
4. **Version Control & Transparency**\
   Every revision is tracked, and older versions remain accessible. Anyone can see what changed, when, and why—a key requirement when multiple organizations or contributors collaborate over time.
5. **Community Contributions**\
   We welcome pull requests and issue reports on GitHub. Contributors can:
   * Propose new occupations or skills that capture informal work or emerging digital livelihoods.
   * Offer local language translations.
   * Flag redundancies or gaps in the taxonomy structure.

### Use Cases

This taxonomy is best used for:&#x20;

* **Public Employment Services (PES)**\
  A government job portal may need to index both formal occupations (like _Nurse_ or _Electrician_) and informal tasks (like _Childcare at Home_). The Open Taxonomy Platform lets PES administrators adapt the reference taxonomy to local categories while remaining compatible with international frameworks.
* **Youth Employment NGOs**\
  A non-profit that focuses on upskilling young people can integrate the platform’s API into its app. When a user describes an unpaid or informal experience—such as cooking at home for large extended families—the NGO’s app can quickly map that to recognized culinary or budget-management skills.
* **Research and Analytics**\
  Think tanks or academic teams might want to track how the labor market shifts over time, especially in informal sectors. By using version-controlled, transparent data on occupations and skills, they can compare how certain roles or skill sets grow or shrink across multiple regions.

### Getting Started

1. **Explore the Reference Taxonomy**\
   Head to our [GitHub repository](https://github.com/tabiya-tech/taxonomy-model-app) for an overview. You’ll find JSON definitions of occupations, tasks, and skill mappings, along with instructions on how to propose changes.
2. **Set Up the Platform Locally**\
   If you want to adapt or extend the taxonomy for your own region, clone the repo and follow the quick-start guide to run a local instance of our platform.
3. **Use the API**\
   Documentation on authentication, queries, and updates is available in our `/docs` folder on GitHub. You can also find sample scripts and postman collections that show how to retrieve occupations, look up skill definitions, and commit changes.
4. **Contribute**
   * **Issues and Pull Requests**: Found an occupation that needs local adaptation or noticed a skill that’s missing? Open an issue or submit a pull request on GitHub.
   * **Discussion & Feedback**: Join our community forum (link coming soon!) where practitioners and developers share best practices, tips, and localized expansions.

### Roadmap

While the Open Taxonomy Platform is already in active development, some exciting features are in progress:

* **Multilingual Support**: We aim to standardize how we store localized names and synonyms for occupations and skills, making it easy to deploy in multiple languages.
* **Advanced API Queries**: Searching by skill clusters or skill synonyms to quickly find relevant occupations.
* **Integrations with Compass and Classifier**: Our [Compass conversational tool](https://docs.tabiya.org/compass) and Inclusive Livelihoods Classifier both rely on the taxonomy. We plan to release more examples of how to combine them seamlessly.

### License and Community Guidelines

The Open Taxonomy Platform is licensed under MIT, reflecting our commitment to openness and widespread adoption. We encourage everyone—government agencies, NGOs, private job-matching platforms, researchers, and individuals—to explore, test, and refine the taxonomy so that, together, we build a more inclusive, dynamic picture of labor markets.
