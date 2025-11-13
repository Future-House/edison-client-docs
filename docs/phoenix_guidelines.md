# Best Practices for Interacting with Phoenix

Phoenix is a chemistry-focused scientific agent. To get the most out of each Phoenix run, follow these guidelines for formulating effective queries:

## 1. Be specific about molecular inputs.
When asking about molecules, provide explicit identifiers such as:
- SMILES strings
- CAS numbers
- IUPAC names

Phoenix can handle multiple representations, but being explicit reduces ambiguity. A chemist familiar with your field should be able to unambiguously identify the molecule(s) from your query.

| Insufficient queries | More detailed queries |
|---------------------|----------------------|
| Tell me about anti-inflammatory drugs. | What are the ADMET properties for aspirin (SMILES: `CC(=O)OC1=CC=CC=C1C(=O)O` or CAS: 50-78-2)? |
| What are the functional groups of vitamin C? | List the functional groups available in ascorbic acid (SMILES: `C([C@@H]([C@@H]1C(=C(C(=O)O1)O)O)O)O`). |
| Find compounds to be used as painkillers. | Search for molecules similar to acetaminophen (SMILES: `CC(=O)NC1=CC=C(C=C1)O`) in the ChEMBL database. |

## 2. Specify desired outputs clearly.
Clearly state what you need from Phoenix. It can be a synthesis route, molecular property prediction, safety assessment, literature-backed answer, or a combination of these. The more specific you are about the outputs you need, the better Phoenix can select appropriate tools and provide actionable results.

| Insufficient queries | More detailed queries |
|---------------------|----------------------|
| Tell me about `CN1C=NC2=C1C(=O)N(C(=O)N2C)C`. | What are the ADMET properties for `CN1C=NC2=C1C(=O)N(C(=O)N2C)C`? Also, what are its GHS classification and LD50 value? |
| Is CC(=O)OC1=CC=CC=C1C(=O)O safe? | Perform a safety assessment for the molecule with SMILES `CC(=O)OC1=CC=CC=C1C(=O)O`, including GHS classification, LD50 value, chemical weapons screening, and toxicity predictions. |
| Can you help me make aspirin? | I need a synthesis route, ADMET property predictions, and a safety assessment for the target molecule with SMILES `CC(=O)OC1=CC=CC=C1C(=O)O`. |

## 3. Use proper chemical terminology and notation.
Employ standard chemical nomenclature and notation. For example, use SMILES representation for reactions: `reactants>reagents>products`. Use standard property names (e.g., ADMET properties) when requesting specific molecular properties. This helps Phoenix understand your intent and select the most appropriate computational tools.

| Insufficient queries | More detailed queries |
|---------------------|----------------------|
| What happens if I mix ethanol and acetic acid? | Predict the product of the reaction with reaction SMILES: `CCO.CC(=O)O>>CC(=O)OC`. Calculate the reaction enthalpy. |
| How do I make an ester from alcohol and acid? | Design a synthesis route for ethyl acetate using reaction SMILES: `CCO.CC(=O)O>>CC(=O)OC` with appropriate catalysts and conditions. |
| Check the drug properties of quercetin. | Calculate ADMET properties (specifically human intestinal absorption, blood-brain barrier permeability, and cytochrome P450 inhibition) for the molecule with SMILES `C1=CC(=C(C=C1C2=C(C(=O)C3=C(C=C(C=C3O2)O)O)O)O)O`. |

## 4. Break down complex queries.
Structure multi-part questions logically so Phoenix can create an effective execution plan. While Phoenix can handle multi-step queries and longer workflows, clearly organizing your query helps ensure all components are addressed systematically.

| Insufficient queries | More detailed queries |
|---------------------|----------------------|
| Find similar drugs to aspirin. | (1) Analyze aspirin (SMILES: `CC(=O)OC1=CC=CC=C1C(=O)O`) for ADMET properties. (2) Search ChEMBL for similar anti-inflammatory compounds. (3) Perform safety assessments on the top 5 candidates. (4) Propose modifications to improve solubility while maintaining efficacy. |
| I need everything about caffeine and how to make it and what it does. | I need you to give me information about caffeine. Follow these steps: (1) Calculate molecular properties (logP, logS, QED) for SMILES `CN1C=NC2=C1C(=O)N(C(=O)N2C)C`. (2) Design a retrosynthesis route. (3) Predict biological activity targets. |
| Find drugs for diabetes, check if they work, and make new ones. | (1) Search ChEMBL for approved diabetes drugs targeting INSR. (2) Analyze their binding affinities and ADMET properties. (3) Propose 5 novel small molecule candidates with improved properties. |

## 5. Provide context when relevant.
Include background information about your use case (e.g., "for drug development" or "for a research synthesis") to help Phoenix select appropriate tools and safety considerations. Context about your constraints, goals, or specific requirements enables Phoenix to provide more targeted and useful responses.

| Insufficient queries | More detailed queries |
|---------------------|----------------------|
| Find similar molecules to `CC(=O)OC1=CC=CC=C1C(=O)O`. | Search the ChEMBL database for molecules similar to aspirin (SMILES: `CC(=O)OC1=CC=CC=C1C(=O)O`) for drug repurposing. Return the top 10 candidates with their development phases and bioactivity data. |

## 6. Request specific properties or analyses.
Instead of asking vaguely about a molecule, specify what you need. For example, request specific ADMET properties, synthetic accessibility scores, solubility predictions, or toxicity data. This allows Phoenix to use the most appropriate computational tools and provide quantitative, actionable results.

| Insufficient queries | More detailed queries |
|---------------------|----------------------|
| Modify quercetin to make it more soluble. | Suggest three different substitution modifications to quercetin to make its aqueous solubility (logS) higher. Show me the suggested molecules in your final answer and base your answer in predicted solubility data. |
| Is aspirin drug-like? | Calculate the drug-likeness score (QED), synthetic accessibility score (SAscore), and Lipinski's Rule of Five violations for `CC(=O)OC1=CC=CC=C1C(=O)O`. |
| What are the properties of caffeine? | Calculate the following properties for caffeine (SMILES: `CN1C=NC2=C1C(=O)N(C(=O)N2C)C`): (1) aqueous solubility (logS), (2) partition coefficient (logP), (3) polar surface area (PSA), and (4) number of rotatable bonds. |

## 7. Ask actionable questions that leverage Phoenix's toolset.
Frame queries that can be answered using Phoenix's computational capabilities rather than pure theoretical discussions without computational support. Phoenix excels at property prediction, synthesis planning, reaction analysis, database searches, and literature-enhanced discovery.

| Insufficient queries | More detailed queries |
|---------------------|----------------------|
| How do I make aspirin? | Design a retrosynthesis route for the target molecule with SMILES `CC(=O)OC1=CC=CC=C1C(=O)O`. Please identify starting materials and propose reaction steps. |
| Can you synthesize caffeine? | Propose a synthesis route for caffeine (SMILES: `CN1C=NC2=C1C(=O)N(C(=O)N2C)C`), including retrosynthetic analysis, reactants pricing, and reaction conditions where possible. |
| What drugs treat diabetes? | Propose small molecule binders for the insulin receptor (INSR gene symbol). Propose up to 10 candidates and analyze their drug-likeness using QED scores. |
| Explain how this ethanol reacts with acetic acid. | Predict the product of the reaction with SMILES `CCO.CC(=O)O>>`, calculate the reaction enthalpy, identify the mechanism, and suggest optimal catalysts and conditions. |


## 8. Iterate.
Take some time to write your first Phoenix query so you can avoid the common pitfalls listed above. Starting with simpler queries will give you faster results and allow quicker iteration, helping you learn how to use Phoenix more effectively and get the most out of the system.
Your first query does not have to be perfect. Use Phoenix interactively to refine your query:

1. Start simple
   - Begin with a well-known molecule or reaction and a small set of properties or a basic retrosynthesis.

2. Inspect the outputs
   - Check if the properties, synthesis steps, or hits match your expectations.

3. Refine your query
   - If you need more detail, add explicit properties, constraints, or additional steps.
   - Example: "Now also calculate logS and propose modifications to improve solubility."

4. Repeat
   - Use the results of one Phoenix run as input for the next (e.g., take top hits and ask for safety assessments or optimization ideas).
   - Phoenix also accepts follow-up questions to the previous run.
