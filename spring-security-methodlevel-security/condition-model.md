# Criteria Model
Inclusion or Exclusion Criteria can be defined as 

 ` Subject Meets Condition(s) and Meets Time Constraint(s)`

## Subject
Subject is the person we are trying to search who meets the criteria.He would be send the questionnaire during patient out-reach

## Meets (Satisfies one of the operators)
- Equal
- Less Than
- Greater Than
- In Range
- Or
- And
- Other Extensions 

## Condition
Conditions can be categorized in to the Following Groups and Semantic Classes.

- Health Status 
	- Disease, Symptom and Sign
	- Pregnancy-related activity
	- Neoplasm status
	- Disease stage
	- Allergy
	- Organ or tissue status
	- Life expectancy

- Treatment or Health Care

	- Pharmaceutical substance or drug
    - Therapy or surgery 
	- Device

- Diagnostic or lab test 
	- Diagnostic or lab results
	- Receptor status

- Demographics
	- Age
	- Special patient characteristic
	- Literacy
	- Gender
	- Address
	- Ethnicity

- Ethical Consideration
	- Consent
	- Enrollment in other studies
	- Capacity
	- Patient preference
	- Compliance with protocol
	
- Lifestyle Choice 
	- Addictive behavior
	- Bedtime
	- Exercise
	- Diet
	
#### Groups And Semantic Classes
These information would used for the data analysis for selecting subjects from the data lake.
For example when selecting a criteria of any ` Pregnancy Related Activities ` from the criteria list would direct the ` Data Analysis` Algorithm to search for patients who might have gone HCG tests recently or have visited 'Obstetrician' recently. 
- Todo -  How to use this information in UI and questionnaire ??

## Time Constraint
A condition also has to meet a time constraint.Time constraint is optional. Examples of time constraints are
 
- Histologic evidence of NASH upon central read of a liver biopsy obtained ` no more than 6 months ` before Day 1  
- For subjects with a historical biopsy, is either not taking or is on stable doses of TZDs/glitazones or vitamin E for ` 6 months before Day 1`.


## Examples of Criteria and mapping to Criteria Model
- HbA1c >9.5% within 60 days before Day 1.

 	- Condition with 'Semantic Class' of 'Diagnostic or lab results' with Key Value of {HbA1C, 9.5%} and operator of 'Greater Than' and meeting the Time Constraint of have happened in 'Less Than 6 months'

	`
	{
		  "criteria": [
		    {
		      "group": "DiagnosticOrLabTest",
		      "class": "lab_result",
		      "key": "HbA1c",
		      "value": "9.5",
		      "operator": "greater_than",
		      "time_constraint": {
		        "operator": "less_than",
		        "value": "6 months"
		      }
		    }
		  ]
		}
`