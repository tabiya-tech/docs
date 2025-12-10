# FAQs

#### **General Usage**

**1. What is the Tabiya Livelihoods Classifier?**\
The Tabiya Livelihoods Classifier is a tool that leverages advanced transformer-based neural networks to extract and categorize key entities from job descriptions. It supports tasks like occupation and skill classification using frameworks like ESCO.

**2. Who can benefit from using this tool?**\
It is designed for HR professionals, recruiters, career advisors, labor market researchers, and developers working on job-matching technologies or workforce analytics.

**3. What types of entities can the tool extract?**\
The classifier identifies and categorizes five entity types: Occupation, Skill, Qualification, Experience, and Domain.

**4. Is this tool compatible with any specific standards or frameworks?**\
Yes, it retrieves ESCO-related entries for Occupations and Skills, aligning with widely used European job classification systems. With minimal work, other taxonomies like O\*Net, could be integrated.

***

#### **Technical Functionality**

**5. How does the Tabiya Livelihoods Classifier work?**\
The process involves two main steps:

1. **Entity Extraction**: Identifies relevant entities in job descriptions.
2. **Similarity Vector Search**: Matches extracted entities to entries in pre-defined frameworks or datasets.

**6. Does the tool use machine learning models?**\
Yes, it utilizes transformer-based models, which represent the state-of-the-art in natural language processing.

**7. Can I customize the classifier for specific industries or datasets?**\
The tool supports customization, allowing users to adapt the similarity search or integrate custom datasets to suit specific domains and use cases.

**8. What is the difference between entity extraction and similarity vector search?**\
Entity extraction identifies relevant entities from text, such as a job title or skill. Similarity vector search then matches these entities to related entries in a knowledge base, like ESCO, for standardization.

**9. Where can I find more technical details about the methods used?**\
For a deeper explanation of the underlying techniques, model design, and evaluation methodology, see the [research paper](https://arxiv.org/abs/2512.03195) _Enhancing Job Matching: Occupation, Skill and Qualification Linking with the ESCO and EQF taxonomies_ (Saroglou _et al_., 2025).

***

#### **Integration and Setup**

**10. How do I install and use the classifier?**\
Detailed installation and setup instructions are available in the [user guide](getting-started.md#quickstart-guide).

**11. Can the classifier be integrated into existing HR systems?**\
Yes, it is designed to be easily integrated into workflows or systems through APIs or library functions.

**12. Are there any prerequisites for using this tool?**\
A working knowledge of Python is recommended for setup and integration. Familiarity with natural language processing concepts is beneficial but not mandatory.

***

#### **Performance and Limitations**

**13. How accurate is the entity classification?**\
The classifier achieves state-of-the-art entity recognition results based on the dataset released by [Green et al](https://aclanthology.org/2022.lrec-1.128/). Albeit, as with any machine learning model, the Entity Linker is not perfect. If you encounter bugs or inappropriate use-cases, please open an issue on [GitHub](https://github.com/tabiya-tech/tabiya-livelihoods-classifier/issues)!

**14. Does the tool handle multilingual job descriptions?**\
We are currently working on developing a method of expanding the tool's capabilities for multiple languages. As of right now, the tool supports only the English and French languages.

**15. Are there limitations on the size of input text?**\
The model uses the [NLTK sentence tokenizer](https://www.nltk.org/api/nltk.tokenize.sent_tokenize.html) function to handle large texts, so theoretically, there is no limit to the input text size. In the current version, the BERT-based models used for entity extraction have a limit of 128 tokens (roughly 100 words). You can use the[ training script](training.md#train-an-entity-extraction-model) to retrain the model to fit your needs.

***

#### **Support and Customization**

**16. Can I contribute to or extend the tool?**\
Yes, developers are welcome to customize and extend the tool. Refer to the contributing guide in the documentation for guidelines.

**17. Where can I find support or report issues?**\
Support is available through the official repository or customer service channels. Issues can be reported on the [GitHub issues page](https://github.com/tabiya-tech/tabiya-livelihoods-classifier/issues) or via email.

**18. Are updates and new features planned?**\
Yes, the tool is actively maintained, with plans for additional features and improved integrations based on user feedback.
