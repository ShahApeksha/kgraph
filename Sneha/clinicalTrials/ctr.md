# Using Semantic Web technologies for Clinical Trial Recruitment

1.	Introduction:
-Clinical trials are important for evaluating new treatments and diagnostic approaches.
-Recruitment of patients for clinical trials is challenging and often results in a lack of participants.
-This paper proposes a method using semantic web technologies to automate patient recruitment for clinical trials.
2.	Clinical Trials:
-Clinical trials are research studies that test the safety and effectiveness of interventions.
-They address various medical issues and require adequate sample sizes for reliable results.
-Meeting recruitment targets in a timely and cost-effective manner is a common challenge.
3.	Problem Description: 
 - 3.1 Patient Data:
    - •	Patient data, including medical history and current health status, can be stored in Electronic Health Records (EHR).
    - •	Formal representation of patient data is essential for querying and interoperability.
    - •	An example of patient record is provided.
Figure 1: Example of a patient record available at a multidisciplinary meeting.
 - 3.2 Eligibility Criteria:
    - •	Eligibility criteria define the characteristics required for patients to participate in a clinical trial.
    - •	Criteria can include medical parameters, personal attributes, disease staging, and time constraints.
    - •	An example of eligibility criteria for a prostate cancer trial is given.
4.	State of the Art:
- Different formalisms have been used to represent eligibility criteria.
- Ad hoc languages, such as HL7 RIM, provide basic comparison and logical operators.
- Arden Syntax offers a hybrid approach with rich time functions and explicit links to clinical data.
- Logic-based languages, including SQL and Description Logic, vary in expressivity.
- The paper describes a case study using ontologies and reasoning for matching eligibility criteria to patients' conditions.
- The Epoch project develops an ontology-based framework for managing clinical trials.
Figure 2: Eligibility criteria for a clinical trial for adjuvant therapy for prostate cancer.
5. Method
 - Reasoning over ontologies is necessary for formalizing and reasoning over eligibility criteria, especially when criteria are expressed as generic conditions or when only some attributes of diseases are specified. It also requires the ability to represent and reason over data types and time. Traceability of results is important for identifying supporting observations for patient selection or rejection in clinical trials.
 - The hypothesis is made that mapping terms from patients' records and eligibility criteria to a formal ontology minimizes ambiguity and enables automatic reasoning. The ontology serves as a reference terminology and background knowledge.
 - The system loads all active trials and patients into the system before a multidisciplinary meeting. Eligibility criteria are matched to patient observations, aggregated, and used to extract a list of clinical trials that satisfy inclusion criteria and do not satisfy exclusion criteria.
 - The system exclusively uses OWL and SWRL to represent patient data and eligibility criteria, with everything loaded into an ontology and all operations performed within the ontology.
- 5.1 Choosing the Medical Ontology
    - The selection of a suitable medical ontology involves considering coverage, availability, and format. The NCI Thesaurus (NCI-T) and SNOMED CT are evaluated based on these criteria.
•	An expert selects 200 criteria from clinicaltrials.gov, and MetaMap is used to map the criteria to concepts in the UMLS metathesaurus. The evaluation reveals that NCI-T provides the best coverage (75%), followed by SNOMED CT (65%).
•	NCI-T is open source and directly available in OWL1.1, while SNOMED CT has an expensive license and requires conversion from database tables. NCI-T's properties (may_have and excludes_) have specific meanings for human use but do not impact consistency verification from a Description Logics perspective.
•	NCI-Thesaurus is chosen as the background knowledge due to its coverage and availability. The system aims for minimal coupling with the ontology to allow portability in other domains.
Figure 3: Shows the general architecture of the system, with the TBox containing the glue ontology, NCI-T, and SWRL ontologies, and the ABox containing instances of NCI-T classes and criteria observations.
5.2 Representing Patient Data
•	Medical ontologies like SNOMED CT and NCI Thesaurus were not originally designed for directly representing patient data. Observations are used to capture information about patients by linking observable entities, observable properties, and observed values.
•	An observation is a reified relation represented as an instance of the Observation class in OWL. Entities and values, except for datatypes, need to be instances in OWL-DL. Existential restrictions are used for reasoning purposes.
•	An example demonstrates the translation of observations into OWL, showing the representation of patient data such as date of birth, diagnosis, clinical procedures, and test results.
5.3 Representing Clinical Trials
•	Criteria are represented as queries over patient observations. SWRL is used to define rules that match observations and determine if a criterion is supported or not. Inclusion criteria lead to patient enrollment, while exclusion criteria prevent enrollment.
•	SWRL provides a high-level syntax for rules, maintaining the expressivity of OWL-DL and offering built-in functions for data types. SWRL rules are computed using Jess, a library based on the RETE algorithm.
•	Inclusion and exclusion criteria are defined as instances of InclusionCriteria and ExclusionCriteria classes. Rules match observations and add them to the support list of a criterion.
•	Aggregation rules are used to determine which criteria support a clinical trial or act as arguments against it.
•	Criteria can be annotated with human-readable descriptions, aiding the final report generation.
5.4 Aggregating the Results
•	A clinical trial has a list of arguments in favor and against patient enrollment. Inclusion criteria contribute to the list in favor, while exclusion criteria contribute to the list against.
•	After running the criteria rules, supported inclusion criteria are added as supporting arguments to a clinical trial, while supported exclusion criteria are added as arguments against it.
•	Clinical trial-specific rules aggregate the results by considering all inclusion criteria and the presence of arguments against the clinical trial.
•	The extraction of supported clinical trials without arguments against them requires reasoning with the closed world assumption, performed outside the ontology.
6 Evaluation and Discussion
•	The evaluation assesses the representation of eligibility criteria using SWRL and NCI Thesaurus. The criteria selected from clinicaltrials.gov are successfully represented, with difficulties arising when corresponding entities are missing in NCI-T.
•	Real clinical trials and patient data from the University Hospital of Rennes are used for evaluation. The majority of criteria are successfully represented, with some exceptions related to terms from different domains.
•	The system's performance is analyzed, indicating loading time for NCI-T, conversion time for ontology and rules, and the runtime of the reasoning engine. The system shows promising results compared to related work.
7 Future Work
•	Future work aims to address the representation challenges caused by missing entities in NCI-T. Importing fragments of other medical ontologies may be considered to cover the gaps.
•	The system plans to adapt to the new version of NCI-T released in OWL2.0, utilizing the new features on datatypes.
•	Expanding the system's applicability to different domains and types of cancers is considered, either by identifying domain-specific ontologies or utilizing SNOMED CT.
8 Conclusion
•	The paper presents an approach based on OWL and SWRL for representing and reasoning over eligibility criteria in clinical trials.
•	Patient data is represented through observations, and eligibility criteria are represented as SWRL rules. The system demonstrates the successful representation of criteria and patient data.
•	The evaluation shows the feasibility of the approach and highlights areas for improvement. The system performs well in terms of loading time, conversion time, and runtime.
•	The system's focus on patient data representation and eligibility criteria using a domain-specific ontology provides a workable formalism within the boundaries of DL.
