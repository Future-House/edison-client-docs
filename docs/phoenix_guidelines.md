# Best Practices for Interacting with Phoenix

Phoenix is a chemistry-focused scientific agent. To get the most out of each Phoenix run, follow these guidelines for formulating effective queries:

## 1. Be specific about molecular inputs.
When asking about molecules, provide SMILES strings, CAS numbers, IUPAC names, or molecular formulas explicitly. Phoenix can work with multiple representation types, but being explicit helps ensure accurate results. A chemist familiar with your field should be able to unambiguously identify the molecule(s) you're asking about.

## 2. Specify desired outputs clearly.
Clearly state what you need from Phoenix. It can be a synthesis route, molecular property prediction, safety assessment, literature-backed answer, or a combination of these. The more specific you are about the outputs you need, the better Phoenix can select appropriate tools and provide actionable results.

## 3. Use proper chemical terminology and notation.
Employ standard chemical nomenclature and notation. For example, use SMILES representation for reactions: `reactants>reagents>products`. Use standard property names (e.g., ADMET properties) when requesting specific molecular properties. This helps Phoenix understand your intent and select the most appropriate computational tools.

## 4. Break down complex queries.
Structure multi-part questions logically so Phoenix can create an effective execution plan. While Phoenix can handle multi-step queries and longer workflows, clearly organizing your query helps ensure all components are addressed systematically.

## 5. Provide context when relevant.
Include background information about your use case (e.g., "for drug development" or "for a research synthesis") to help Phoenix select appropriate tools and safety considerations. Context about your constraints, goals, or specific requirements enables Phoenix to provide more targeted and useful responses.

## 6. Request specific properties or analyses.
Instead of asking vaguely about a molecule, specify what you need. For example, request specific ADMET properties, synthetic accessibility scores, solubility predictions, or toxicity data. This allows Phoenix to use the most appropriate computational tools and provide quantitative, actionable results.

## 7. Ask actionable questions that leverage Phoenix's toolset.
Frame queries that can be answered using Phoenix's computational capabilities rather than pure theoretical discussions without computational support. Phoenix excels at property prediction, synthesis planning, reaction analysis, database searches, and literature-enhanced discovery.

Here are some examples of ways to improve Phoenix queries:

| Insufficient queries | More detailed queries |
|---------------------|--------------|
| Tell me about aspirin. | What are the ADMET properties (HIA_Hou, BBB_Martins, and AMES) for aspirin? Also, what are its GHS classification and LD50 value? |
| Modify quercetin to make it more soluble in water. | Suggest three different substitution modifications to quercetin to make its aqueous solubility (logS) higher. Show me the suggested molecules in your final answer and base your answer in evidence from the literature. |
| How do I make aspirin? | Design a retrosynthesis route for the target molecule with SMILES `CC(=O)OC1=CC=CC=C1C(=O)O`. Please identify starting materials and propose reaction steps. |
| Can you synthesize caffeine? | Propose a synthesis route for caffeine, including retrosynthetic analysis, reactants pricing, and reaction conditions where possible. |
| What happens if I mix ethanol and acetic acid? | Predict the product of the reaction of ethanol and acetic acid with SMILES: `CCO.CC(=O)O>>`. Calculate the reaction enthalpy. |
| What drugs treat diabetes? | Propose small molecule binders for the insulin receptor (INSR gene symbol). Propose up to 10 candidates and analyze their drug-likeness using QED scores. |
| Is CC(=O)OC1=CC=CC=C1C(=O)O safe? | Perform a safety assessment for the molecule with SMILES `CC(=O)OC1=CC=CC=C1C(=O)O`, including GHS classification, LD50 value, chemical weapons screening, and toxicity predictions (AMES, ClinTox). |
| Find similar molecules to `CC(=O)OC1=CC=CC=C1C(=O)O`. | Search the ChEMBL database for molecules similar to aspirin (SMILES: `CC(=O)OC1=CC=CC=C1C(=O)O`) for drug repurposing. Return the top 10 candidates with their development phases and bioactivity data. |
| What's the latest on green chemistry? | Using literature search, find recent advances in green chemistry methods for esterification reactions. Focus on catalysts and reaction conditions that minimize environmental impact. |

## 8. Iterate.
Take some time to write your first Phoenix query so you can avoid the common pitfalls listed above. However, trial and error will be your best guide to develop a deep intuition on how to best use the system. Start with familiar molecules or reactions. While Phoenix can handle complex multi-step workflows, begin with simpler queries for faster results. Quicker iteration will help you learn how to use Phoenix more effectively and get the most out of the system.
