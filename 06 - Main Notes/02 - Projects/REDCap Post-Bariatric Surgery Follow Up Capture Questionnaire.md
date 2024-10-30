---
project_type:
  - Work Project
start_date: "[[2023.01.20]]"
due_date: N/A
status:
  - In Progress
priority:
  - High
team:
  - Bariatric Team
  - Dino Spaniolas
  - Cathy Tuppo
tags:
  - "#work"
  - "#project"
  - redcap
tech_stack:
  - REDCap
code_repo: "{{Link to repository}}"
related_projects:
  - "[[REDCap Bariatric Patient Tracker]]"
---
# Work Project: {{Project Name}}

## Overview
- **Start Date**: 2023.01.20
- **Due Date**: N/A
- **Status**: In Progress
- **Priority**: High

## Objective
- **Goal**: To capture the full 30 days post-operatively from Bariatric Surgery by providing a quick and convenient electronic questionnaire for the required check-in questions/information in order to increase response rate.
- **Client / Team**: Bariatric Team, Cathy Tuppo, Dino Spaniolas

## Code Involvement
- **Tech Stack**: REDCap script
- **Code Repo**: N/A
- **Scripts/Modules**: N/A

## Steps / Tasks
- [x] create questionnaire
- [x] get QI/QA approval
- [x] send out to patients

## Requirements
- **Software/Tools**: REDCap
- **Hardware**: {N/A
- **Access**: Only: Caroline Sanicola & Dino Spaniolas
- **Documentation**: {{Links to documentation, guidelines, or design documents}}

## Related Projects
- **Past Work**: [Bariatric Patient Tracker](https://redcap.stonybrookmedicine.edu/redcap_v14.0.43/ProjectSetup/index.php?pid=2817)
- **Dependencies**: [Bariatric Patient Tracker](https://redcap.stonybrookmedicine.edu/redcap_v14.0.43/ProjectSetup/index.php?pid=2817)
- **Future Extensions**: {{Possible follow-up projects or improvements}}

## Challenges / Roadblocks
- Response rate is still not as high as we wish
	- make sure surgeons and nps/pas are advising patients this will need to be completed

## Resources & References
- **Links**: [Post-Bariatric Surgery Follow Up Capture Questionnaire](https://redcap.stonybrookmedicine.edu/redcap_v14.0.43/index.php?pid=2798)
- **Team Contacts**: N/A
- **Notes**: {{Any additional context or notes}}

___
# Questionnaire Layout 
1. REDCap Record ID [record_id] - text
2. First Name [first_name] - text
3. Last Name [last_name] - text
4. Surgery Date [sx_date] - text
5. Are you able to tolerate the soft food diet? [soft_food] - Yes/No
    1. {No selected} If not, why? [diet_not] - paragraph
6. Are you engaging in physical activity as tolerated? [phys_act] - Yes/No
    1. {No selected} If not, why? [phys_not] - paragraph
7. Are you taking your Bariatric Vitamins? [vitamins] - Yes/No
    1. {No selected} If not, why? [vit_not] - paragraph
8. Are you experiencing a normal stooling pattern? [stool] - Yes/No
    1. {No selected} If not, why? [stool_not] - paragraph
9. Are you taking your PPI (ex: pantoprazole, omeprazole) medication? [ppi] - Yes/No
    1. {No selected} If not, why? [ppi_not] - paragraph
10. Have you been to the ER since surgery? [er] - Yes/No
    1. {Yes selected} Did you go to Stony Brook ER or another hospital/health facility? [er_fu] - 1: Stony Brook ; 2: Another Hospital
        1. {Another Hospital selected} What is the name of the other hospital/health facility? [other_hosp] - text
    2. {Yes selected} What is the name of the other hospital/health facility? [ed_date] - date
    3. {Yes selected} What did you go to the ER for? [er_reason] - paragraph
11. Have you been admitted to the hospital since being discharged from your bariatric surgery? [readm] - Yes/No
    1. {Yes selected} Did you go to Stony Brook Hospital or another hospital/health facility? [readm_hosp] - 1: Stony Brook ; 2: Another Hospital
        1. {Another Hospital selected} What is the name of the other hospital/health facility? [readm_hosp] - text
    2. {Yes selected} What date were you admitted? [readm_adm] - date
    3. {Yes selected} What date were you discharged? [readm_disch] - date
    4. {Yes selected} What were you admitted to the hospital for? [readm_reason] - paragraph
12. Have you undergone any procedure since your bariatric surgery? [proc] - Yes/No
    1. {Yes selected} What date did you undergo this procedure? [proc_date] - date
    2. {Yes selected} Did you undergo this procedure at Stony Brook Hospital or another hospital/health facility? [proc_hosp] - 1: Stony Brook ; 2: Another Hospital
        1. {Another Hospital selected} What is the name of the other hospital/health facility? [proc_other] - text
    3. {Yes selected} Was this procedure pre-planned? [proc_pre] - Yes/No
    4. {Yes selected} What was the procedure? [proc_desc] - paragraph
    5. Have you had any discomfort or pain since your surgery? [pain] - Yes/No
        1. {Yes selected} What would you say your average level of pain/discomfort has been? [pain_level] - scale from “No Pain (0)” to “Mild Pain (5)” to “Severe Pain (10)”
    6. Is there anything else you wish to advise your bariatric surgeon/team? [etc] - paragraph

