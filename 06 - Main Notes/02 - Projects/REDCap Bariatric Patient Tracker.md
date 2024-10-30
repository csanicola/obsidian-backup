---
project_type:
  - Work Project
start_date: "[[2023.01.31]]"
due_date: N/A
status:
  - In Progress
priority:
  - High
team:
  - Bariatric Team
tags:
  - "#work"
  - "#project"
  - redcap
tech_stack:
  - REDCap
code_repo: "{{Link to repository}}"
related_projects:
  - "[[REDCap Post-Bariatric Surgery Follow Up Capture Questionnaire]]"
---

# Work Project: REDCap Bariatric Patient Tracker

## Overview
- **Start Date**: 2023.01.31
- **Due Date**: N/A
- **Status**: {{Not Started / In Progress / Completed}}
- **Priority**: {{High / Medium / Low}}

## Objective
- **Goal**: {{Brief description of what this project aims to achieve}}
- **Client / Team**: {{Stakeholders, collaborators, or departments involved}}

## Code Involvement
- **Tech Stack**: {{List of programming languages, frameworks, or tools used}}
- **Code Repo**: {{Link to repository or internal Git link}}
- **Scripts/Modules**: {{List of specific scripts or modules written}}

## Steps / Tasks
- [ ] {{Task 1 description and any sub-tasks or details needed}}
- [ ] {{Task 2 description and any sub-tasks or details needed}}
- [ ] {{Task 3 description and any sub-tasks or details needed}}

## Requirements
- **Software/Tools**: {{Any required software, plugins, or accounts needed}}
- **Hardware**: {{If any specific hardware requirements are needed}}
- **Access**: {{Permissions, server access, or account credentials required}}
- **Documentation**: {{Links to documentation, guidelines, or design documents}}

## Related Projects
- **Past Work**: {{List or link any relevant past projects or codebases}}
- **Dependencies**: {{List any projects or modules that this project depends on}}
- **Future Extensions**: {{Possible follow-up projects or improvements}}

## Challenges / Roadblocks
- {{List known or potential issues, bugs, or dependencies that could affect progress}}

## Resources & References
- **Links**: {{Links to any related docs, articles, or tutorials}}
- **Team Contacts**: {{List key people you might need to consult for questions}}
- **Notes**: {{Any additional context or notes}}

___
## REDCap Tracker Layout
### Demographics

|#|Variable / Field Name|Field Label|Field Attributes (Field Type, Validation, Choices, Calculations, etc.)|_**Notes**_|
|---|---|---|---|---|
|1|[record_id]|REDCap Record ID|text (integer, Min: 0)|_this will generate automatically_|
|2|[mrn]|MRN|text (mrn_08d), Identifier||
|Field Annotation: @CHARLIMIT=8|_if the MRN is shorter than 8 digits, put in leading 0s_||||
|3|[contact_date]|Contact Date|text (date_ymd), Required, Identifier|_this will always be the first date that the patient contacts the practice no matter how many times they restart or go for multiple procedures/interests_|
|4|[first_name]|First Name|text, Required, Identifier||
|5|[last_name]|Last Name|text, Required, Identifier||
|6|[dob]|Date of Birth|text (date_ymd), Identifier||
|7|[age_contact]|Age at Contact Date|calc||
|Calculation: rounddown(datediff([dob],[contact_date],"y","ymd"),1)|||||
|8|[current_age]|Current Age|calc||
|Calculation: rounddown(datediff([dob],"today","y","ymd"),1)|||||
|9|[gender]|Gender|radio||
|0, Male|||||
|1, Female|||||
|2, Other|||||
|3, Not stated|_gender should be what is listed in IDX for “Adm. Sex”_||||
|10|[race]|Race|checkbox||
|1, race___1, African-American|||||
|2, race___2, Asian|||||
|3, race___3, Caucasian|||||
|4, race___4, Hispanic|||||
|5, race___5, Pacific Islander/Hawaiian|||||
|6, race___6, Native American|||||
|99, race___99, Other|_if unknown and patient is in Powerchart, you can click on their name to the right of their display photo and it is shown under the GENERAL INFORMATION_||||
|11|[language]|Primary Language|radio||
|1, English|||||
|2, Spanish|||||
|3, Other|||||
|12|[lang_other]|OTHER Language|text||
|13|[insurance]|Insurance|dropdown||
|1, Aetna|||||
|2, Affinity|||||
|20, Agewell|||||
|21, Americhoice|||||
|22, Asmed|||||
|3, Cigna|||||
|23, Commercial|||||
|24, Emergent Medicaid|||||
|4, Empire Blue Cross / Blue Shield|||||
|5, Fidelis|||||
|25, First Choice Medical|||||
|6, GHI|||||
|7, GHI NYC|||||
|26, Health Republic Platinum|||||
|8, Healthcare Partners|||||
|9, Healthfirst|||||
|10, HIP|||||
|27, Humana/Tricare|||||
|11, IGA|||||
|28, Kidney Fund L50|||||
|12, Magnacare|||||
|13, Medcaid|||||
|14, Medicare|||||
|19, Member 1199|||||
|29, Multiplan|||||
|30, National Health Plan|||||
|31, Neighborhood|||||
|15, Oxford|||||
|32, Railroad Medicare|||||
|33, Shinnecock|||||
|34, State Agency|||||
|35, Triwest|||||
|36, United Compass|||||
|16, United Healthcare|||||
|18, United Healthcare Community Plan|||||
|17, United Healthcare Empire Plan (NYSHIP)|||||
|37, United Healthcare Medicare|||||
|38, VA|||||
|39, Vytra|||||
|0, None|||||
|999, Other Insurance|_this does include insurances that no longer exist but that is for backlogging purposes_||||
|14|[insurance_other]|OTHER Insurance|text||
|15|[ph]|Phone Number|text (phone), Identifier||
|16|[ph_2]|Alt Phone Number|text (phone), Identifier||
|17|[email]|Email Address|text (email), Identifier||
|18|[zipcode]|Zip Code|text (zipcode), Identifier|_this should NOT include the 4 digit postal codes that are sometimes after the 5 digit zipcode_|
|19|[referral]|Referral Source|dropdown||
|15, Brochure|||||
|16, Case Manager|||||
|10, Continuing From Outside Facility|||||
|17, Coworker|||||
|1, Doctor / Medical Practitioner|||||
|11, ED|||||
|8, Family|||||
|5, Friend|||||
|14, General Surgery Patient|||||
|9, Insurance|||||
|12, Mary Zotos/Brookhaven|||||
|6, Media / Social Media Ad|||||
|18, Our Website Form|||||
|13, Previous Patient (Friend/Family/Coworker)|||||
|7, Self|||||
|3, Seminar|||||
|19, Stony Brook Employee|||||
|20, Stony Brook Patient|||||
|4, Web Search|||||
|2, Webinar|||||
|999, Other Referral Source|||||
|0, Not Stated|_Physician Referrals always take priority with being the primary source of a referral; Default referral will be what the patient lists on the New Bariatric Patient Packe_t||||
|20|[referral_media]||||
|Show the field ONLY if:|||||
|[referral]='6'|(If Media) Media Type|dropdown|||
|1, Print|||||
|2, Radio|||||
|3, Internet|||||
|4, TV|||||
|5, Brochure|||||
|21|[referral_md]||||
|Show the field ONLY if:[referral]='1'|(If Practitioner) Name & Practice|dropdown|||
|[_over 1000 unique names_]|||||
|22|[referral_md_other]||||
|Show the field ONLY if:|||||
|[referral_md]='99999'|(If Practitioner) Name & Practice - OTHER|text|||
|23|[referral_other]||||
|Show the field ONLY if:|||||
|[referral]='999'|(If Other) Specify Other Referral Source|text|||
|24|[pcp]|Primary Care Physician (PCP)|dropdown||
|[_over 1000 unique names_]|||||
|25|[pcp_other]||||
|Show the field ONLY if:|||||
|[pcp]='99999'|Primary Care Physician - OTHER|text|||
|26|[pcp_refmd_match]|Is the Referral MD the Patient's PCP?|calc||
|Calculation: if([referral_md]<>'',if([referral_md]=[pcp],1,0),0)|||||
|27|[patient_status]|PATIENT STATUS|radio||
|1, ACTIVE|||||
|6, WTLS/MEDICATION ONLY|||||
|2, DROPPED OUT|||||
|3, POST-OP LTF|||||
|4, POST-OP + REV/CON|||||
|7, NEVER SEEN|||||
|5, DECEASED|||||
|0, UNKNOWN|||||
|999, OTHER|||||
|28|[patient_status_other]||||
|Show the field ONLY if:|||||
|[patient_status]=999|PATIENT STATUS OTHER:|text|||
|29|[contact_year_24]|Contact Year (2024)|calc||
|Calculation: if(contains([contact_date],"2024"),1,0)|||||
|30|[contact_year_23]|Contact Year (2023)|calc||
|Calculation: if(contains([contact_date],"2023"),1,0)|||||
|31|[contact_year_22]|Contact Year (2022)|calc||
|Calculation: if(contains([contact_date],"2022"),1,0)|||||
|32|[contact_year_21]|Contact Year (2021)|calc||
|Calculation: if(contains([contact_date],"2021"),1,0)|||||
|33|[contact_year_20]|Contact Year (2020)|calc||
|Calculation: if(contains([contact_date],"2020"),1,0)|||||
|34|[contact_year_19]|Contact Year (2019)|calc||
|Calculation: if(contains([contact_date],"2019"),1,0)|||||
|35|[contact_year_18]|Contact Year (2018)|calc||
|Calculation: if(contains([contact_date],"2018"),1,0)|||||
|36|[contact_year_17]|Contact Year (2017)|calc||
|Calculation: if(contains([contact_date],"2017"),1,0)|||||
|37|[contact_year_16]|Contact Year (2016)|calc||
|Calculation: if(contains([contact_date],"2016"),1,0)|||||
|38|[contact_year_15]|Contact Year (2015)|calc||
|Calculation: if(contains([contact_date],"2015"),1,0)|||||
|39|[contact_year_14]|Contact Year (2014)|calc||
|Calculation: if(contains([contact_date],"2014"),1,0)|||||
|40|[contact_year_13]|Contact Year (2013)|calc||
|Calculation: if(contains([contact_date],"2013"),1,0)|||||
|41|[contact_year_12]|Contact Year (2012)|calc||
|Calculation: if(contains([contact_date],"2012"),1,0)|||||
|42|[contact_year_11]|Contact Year (2011)|calc||
|Calculation: if(contains([contact_date],"2011"),1,0)|||||
|43|[contact_month_jan]|Contact Month (January)|calc||
|Calculation: if(contains([contact_date],"-01-"),1,0)|||||
|44|[contact_month_feb]|Contact Month (February)|calc||
|Calculation: if(contains([contact_date],"-02-"),1,0|||||
|45|[contact_month_mar]|Contact Month (March)|calc||
|Calculation: if(contains([contact_date],"-03-"),1,0|||||
|46|[contact_month_apr]|Contact Month (April)|calc||
|Calculation: if(contains([contact_date],"-04-"),1,0|||||
|47|[contact_month_may]|Contact Month (May)|calc||
|Calculation: if(contains([contact_date],"-05-"),1,0|||||
|48|[contact_month_jun]|Contact Month (June)|calc||
|Calculation: if(contains([contact_date],"-06-"),1,0|||||
|49|[contact_month_jul]|Contact Month (July)|calc||
|Calculation: if(contains([contact_date],"-07-"),1,0|||||
|50|[contact_month_aug]|Contact Month (August)|calc||
|Calculation: if(contains([contact_date],"-08-"),1,0|||||
|51|[contact_month_sep]|Contact Month (September)|calc||
|Calculation: if(contains([contact_date],"-09-"),1,0|||||
|52|[contact_month_oct]|Contact Month (October)|calc||
|Calculation: if(contains([contact_date],"-10-"),1,0|||||
|53|[contact_month_nov]|Contact Month (November)|calc||
|Calculation: if(contains([contact_date],"-11-"),1,0|||||
|54|[contact_month_dec]|Contact Month (December)|calc||
|Calculation: if(contains([contact_date],"-12-"),1,0|||||
|55|[demographics_complete]|Complete?|dropdown||
|0, Incomplete|||||
|1, Unverified|||||
|2, Complete|||||

> [!warning] Important Information
> The redcap_id can be use individually with all of the other repeating instruments and not create multiple rows but that is the only variable that will follow that rule

### Appointment

|#|Variable / Field Name|Field Label|Field Attributes (Field Type, Validation, Choices, Calculations, etc.)|_**Notes**_|
|---|---|---|---|---|
|56|[appt_made]|REDCap Record ID|text (integer, Min: 0)||
||[appt_not_reason]||||
|Show the field ONLY if:|||||
|[appt_made]='0'|Reason Appt Not Set|dropdown|||
|1, Insurance|||||
|2, Time|||||
|3, $$$$|||||
|4, BMI|||||
|5, Unable to Contact|||||
|6, Pt will c/b|||||
|7, Not Interested|||||
|8, Medical|||||
|9, Unknown|||||
|10, Pt seen/Operated on Directly Through ED [Appt not necessary]|||||
|999, Other|||||
|58|[appt_not_reason_other]||||
|Show the field ONLY if:|||||
|[appt_not_reason]='999'|Appt Not Set Other Reason|text|||
|59|[initial_interest]|Initial Interest|dropdown||
|1, Initial Surgery|||||
|2, Revision/Conversion|||||
|3, Post-Op Maintenance|||||
|4, Balloon|||||
|5, Weight Loss Only|||||
|6, Unknown|||||
|7, General Surgery|*a. Revision/Conversion = Patient had any type of Bariatric Surgery already and “want to discuss what their surgical options are”||||
|b. Post-Op Maintenance = Previous Bariatric Surgery and just need to maintain their current status (ex: Band and will be seen for monthly adjustments only)|||||
|c. (Ex: If they were coming in for a hernia procedure but were enrolled in the bariatric program, select GENERAL SURGER*Y)|||||
|60|[consulting_md]|Consulting Doctor|dropdown||
|1, Aurora Pryor|||||
|2, Dino Spaniolas|||||
|3, Sal Docimo|||||
|4, Kinga Powers|||||
|5, Amy Rosenbluth|||||
|6, Andrew Bates|||||
|7, Dana Telem|||||
|8, Edmund Lee|||||
|9, Artem Shmelev|||||
|999, N/A|||||
|61|[consulting_rd]|Consulting Dietitian|dropdown||
|1, Kate Cottell|||||
|2, Megan Bennett|||||
|3, Marianna Dayre|||||
|4, Kelly Tahlor|||||
|999, N/A|||||
|62|[consulting_np]|Consulting NP|dropdown||
|1, Darragh Herlihy|||||
|2, Fran Decade|||||
|3, Sonia Varughese|||||
|4, Deena Zacharia|||||
|5, Roberto Rodriguez|||||
|6, Justine Tuttle|||||
|999, N/A|||||
|63|[appt_date]|Consult Appt|||
|time in military time|text (datetime_ymd), Identifier||||
|64|[appt_arriv]|Appt. Status|dropdown||
|1, arrived|||||
|2, canceled|||||
|3, nos|||||
|4, bumped|||||
|5, pending|||||
|65|[appt_cancel_reason]||||
|Show the field ONLY if:[appt_arriv]='2'|Appt Cancel Reason|dropdown|||
|35, Another Provider/Practice Instead|||||
|16, Change Provider|||||
|17, Change Provider Schedule|||||
|10, Conflicting Appt|||||
|9, Death|||||
|18, Employee|||||
|15, Family|||||
|22, Financial Situation|||||
|14, Home (Issue/Repair)|||||
|1, Insurance|||||
|7, Job|||||
|6, LM|||||
|5, Medical|||||
|12, No Child Care|||||
|26, No Longer Interested|||||
|19, Patient Request|||||
|28, Poor Prep|||||
|27, Pregnant|||||
|34, Provider Request|||||
|21, Referral Issues|||||
|33, Requesting Different Office Location|||||
|29, Requesting Earlier Appointment|||||
|30, Requesting Later Appointment|||||
|31, Scheduling Error|||||
|4, School|||||
|23, Seminar First|||||
|8, Sick|||||
|3, Time Off|||||
|11, Transportation|||||
|32, Vacation|||||
|20, Via Phone Service|||||
|24, Wants to Wait|||||
|13, Weather|||||
|25, Weight Loss On Own|||||
|2, Will C/B|||||
|100, Unknown|||||
|999, Other|||||
|66|[appt_cancel_other]||||
|Show the field ONLY if:|||||
|[appt_cancel_reason]='999'|Appt Cancel Reason Other|text|||
|67|[appt_resch]||||
|Show the field ONLY if:|||||
|[appt_arriv]='2' or [appt_arriv]='3' or [appt_arriv]='4'|Appt Rescheduled?|yesno|||
|1, Yes|||||
|0, No|||||
|68|[appt_date_2]||||
|Show the field ONLY if:|||||
|[appt_resch]='1'|Rescheduled Appt||||
|time in military time|text (datetime_ymd), Identifier||||
|69|[appt_arriv_2]||||
|Show the field ONLY if:[appt_resch]='1'|Appt. Status|dropdown|||
|[_same as appt_arriv_]|||||
|70|[appt_cancel_reason_2]||||
|Show the field ONLY if:[appt_arriv_2]='2'|Appt Cancel Reason|dropdown|||
|[_same as appt_cancel_reason_]|||||
|71|[appt_cancel_other_2]||||
|Show the field ONLY if:|||||
|[appt_cancel_reason_2]='999'|Appt Cancel Reason Other|text|||
|72|[appt_resch_2]||||
|Show the field ONLY if:|||||
|[appt_arriv_2]='2' or [appt_arriv_2]='3' or [appt_arriv_2]='4'|Appt Rescheduled?|yesno|||
|1, Yes|||||
|0, No|||||
|73|[appt_date_3]||||
|Show the field ONLY if:|||||
|[appt_resch_2]='1'|Rescheduled Appt||||
|time in military time|text (datetime_ymd), Identifier||||
|74|[appt_arriv_3]||||
|Show the field ONLY if:|||||
|[appt_resch_2]='1'|Appt. Status|dropdown|||
|[_same as appt_arriv_]|||||
|75|[appt_cancel_reason_3]||||
|Show the field ONLY if:|||||
|[appt_arriv_3]='2'|Appt Cancel Reason|dropdown|||
|[_same as appt_cancel_reason_]|||||
|76|[appt_cancel_other_3]||||
|Show the field ONLY if:|||||
|[appt_cancel_reason_3]='999'|Appt Cancel Reason Other|text|||
|77|[appt_resch_3]||||
|Show the field ONLY if:|||||
|[appt_arriv_3]='2' or [appt_arriv_3]='3' or [appt_arriv_3]='4'|Appt Rescheduled?|yesno|||
|1, Yes|||||
|0, No|||||
|78|[appt_date_4]||||
|Show the field ONLY if:[appt_resch_3]='1'|Rescheduled Appt||||
|time in military time|text (datetime_ymd), Identifier||||
|79|[appt_arriv_4]||||
|Show the field ONLY if:|||||
|[appt_resch_3]='1'|Appt. Status|dropdown|||
|[_same as appt_arriv_]|||||
|80|[appt_cancel_reason_4]||||
|Show the field ONLY if:|||||
|[appt_arriv_4]='2'|Appt Cancel Reason|dropdown|||
|[_same as appt_cancel_reason_]|||||
|81|[appt_cancel_other_4]||||
|Show the field ONLY if:|||||
|[appt_cancel_reason_4]='999'|Appt Cancel Reason Other|text|||
|82|[appt_resch_4]||||
|Show the field ONLY if:|||||
|[appt_arriv_4]='2' or [appt_arriv_4]='3' or [appt_arriv_4]='4'|Appt Rescheduled?|yesno|||
|1, Yes|||||
|0, No|||||
|83|[appt_date_5]||||
|Show the field ONLY if:[appt_resch_4]='1'|Rescheduled Appt||||
|time in military time|text (datetime_ymd), Identifier||||
|84|[appt_arriv_5]||||
|Show the field ONLY if:[appt_resch_4]='1'|Appt. Status|dropdown|||
|[_same as appt_arriv_]|||||
|85|[appt_cancel_reason_5]||||
|Show the field ONLY if:|||||
|[appt_arriv_5]='2'|Appt Cancel Reason|dropdown|||
|[_same as appt_cancel_reason_]|||||
|86|[appt_cancel_other_5]||||
|Show the field ONLY if:[appt_cancel_reason_5]='999'|Appt Cancel Reason Other|text|||
|87|[appt_resch_5]||||
|Show the field ONLY if:|||||
|[appt_arriv_5]='2' or [appt_arriv_5]='3' or [appt_arriv_5]='4'|Appt Rescheduled?|yesno|||
|1, Yes|||||
|0, No|||||
|88|[appt_date_6]||||
|Show the field ONLY if:|||||
|[appt_resch_5]='1'|Rescheduled Appt||||
|time in military time|text (datetime_ymd), Identifier||||
|89|[appt_arriv_6]||||
|Show the field ONLY if:|||||
|[appt_resch_5]='1'|Appt. Status|dropdown|||
|[_same as appt_arriv_]|||||
|90|[appt_cancel_reason_6]||||
|Show the field ONLY if:|||||
|[appt_arriv_6]='2'|Appt Cancel Reason|dropdown|||
|[_same as appt_cancel_reason_]|||||
|91|[appt_cancel_other_6]||||
|Show the field ONLY if:|||||
|[appt_cancel_reason_6]='999'|Appt Cancel Reason Other|text|||
|92|[most_recent_date]|Most Recent Appointment Date|text, Identifier||
|Field Annotation: @CALCTEXT(if([appt_date_6] <> "", [appt_date_6], if([appt_date_5] <> "", [appt_date_5], if([appt_date_4] <> "", [appt_date_4], if([appt_date_3] <> "", [appt_date_3], if([appt_date_2] <> "", [appt_date_2], if([appt_date] <> "",[appt_date], "")))))))|||||
|93|[most_recent_status]|Most Recent Appointment Status|text||
|Field Annotation: @CALCTEXT(if([appt_arriv_6]='1','arrived',if([appt_arriv_6]='2','canceled',if([appt_arriv_6]='3','nos',if([appt_arriv_6]='4','bumped',if([appt_arriv_6]='5','pending',if([appt_arriv_5]='1','arrived',if([appt_arriv_5]='2','canceled',if([appt_arriv_5]='3','nos',if([appt_arriv_5]='4','bumped',if([appt_arriv_5]='5','pending',if([appt_arriv_4]='1','arrived',if([appt_arriv_4]='2','canceled',if([appt_arriv_4]='3','nos',if([appt_arriv_4]='4','bumped',if([appt_arriv_4]='5','pending',if([appt_arriv_3]='1','arrived',if([appt_arriv_3]='2','canceled',if([appt_arriv_3]='3','nos',if([appt_arriv_3]='4','bumped',if([appt_arriv_3]='5','pending',if([appt_arriv_2]='1','arrived',if([appt_arriv_2]='2','canceled',if([appt_arriv_2]='3','nos',if([appt_arriv_2]='4','bumped',if([appt_arriv_2]='5','pending',if([appt_arriv]='1','arrived',if([appt_arriv]='2','canceled',if([appt_arriv]='3','nos',if([appt_arriv]='4','bumped',if([appt_arriv]='5','pending',"")))))))))))))))))))))))))))))))|||||
|94|[contact_to_arrive]|Contact to Arrival|||
|days|calc||||
|Calculation: if([most_recent_status]="arrived",round(datediff([contact_date], [most_recent_date], 'd', true),2),"")|||||
|95|[appt_loc]|Office|dropdown||
|1, Centereach|||||
|2, Smithtown|||||
|3, Patchogue|||||
|4, Commack|||||
|5, Southampton|||||
|6, West Hampton|||||
|7, Research Way|||||
|8, Stony Brook Road|||||
|9, Holbrook|||||
|10, Riverhead|||||
|11, Hampton Bays|||||
|999, Telehealth|_If there is a TELEHEALTH appointment scheduled, select TELEHEALTH, NOT the location of the TELEHEALTH Appointment_||||
|96|[procedural_track]||||
|Show the field ONLY if:|||||
|[appt_arriv]='1' or [appt_arriv_2]='1' or [appt_arriv_3]='1' or [appt_arriv_4]='1' or [appt_arriv_5]='1' or [appt_arriv_6]='1'|Post-Consult Track|dropdown|||
|1, Initial Surgery|||||
|2, Revision/Conversion|||||
|3, Post-Op Maintenance|||||
|4, Balloon|||||
|5, Weight Loss Only|||||
|6, Unknown|||||
|7, General Surgery|||||
|97|[medication]||||
|Show the field ONLY if:|||||
|[appt_arriv]='1' or [appt_arriv_2]='1' or [appt_arriv_3]='1' or [appt_arriv_4]='1' or [appt_arriv_5]='1' or [appt_arriv_6]='1'|Medication?|yesno|||
|1, Yes|||||
|0, No|||||
|98|[ibw_ml]|Ideal Body Weight (IBW) - Metlife|||
|lbs|calc||||
|Calculation: if([gender]='0',round(106+6*([height]-60)),if([gender]='1',round(100+5*([height]-60)),""))|||||
|99|[ibw_25]|Ideal Body Weight (IBW) - 25|||
|lbs|calc||||
|Calculation: round(25*([height]*0.0254)^(2)/0.453592)|||||
|100|[initial_weight]|Weight|||
|lbs|text (number, Min: 0, Max: 2000)||||
|101|[height]|Height|||
|inch|text (number, Min: 0, Max: 99)||||
|102|[initial_ebw_ml]|Initial Excess Body Weight (EBW) based on IBW-Metlife|calc||
|Calculation: round([initial_weight]-[ibw_ml],2)|||||
|103|[initial_ebw_25]|Initial Excess Body Weight (EBW) based on IBW-25|calc||
|Calculation: round([initial_weight]-[ibw_25],2)|||||
|104|[initial_bmi]|Initial Body Mass Index (BMI)|calc||
|Calculation: round(([initial_weight]*703)/(([height])^(2)),2)|||||
|105|[most_recent_date_year_24]|Most Recent Appointment Year (2024)|calc||
|Calculation: if(contains([most_recent_date],"2024"),1,0)|||||
|106|[most_recent_date_year_23]|Most Recent Appointment Year (2023)|calc||
|Calculation: if(contains([most_recent_date],"2023"),1,0)|||||
|107|[most_recent_date_year_22]|Most Recent Appointment Year (2022)|calc||
|Calculation: if(contains([most_recent_date],"2022"),1,0)|||||
|108|[most_recent_date_year_21]|Most Recent Appointment Year (2021)|calc||
|Calculation: if(contains([most_recent_date],"2021"),1,0)|||||
|109|[most_recent_date_year_20]|Most Recent Appointment Year (2020)|calc||
|Calculation: if(contains([most_recent_date],"2020"),1,0)|||||
|110|[most_recent_date_year_19]|Most Recent Appointment Year (2019)|calc||
|Calculation: if(contains([most_recent_date],"2019"),1,0)|||||
|111|[most_recent_date_year_18]|Most Recent Appointment Year (2018)|calc||
|Calculation: if(contains([most_recent_date],"2018"),1,0)|||||
|112|[most_recent_date_year_17]|Most Recent Appointment Year (2017)|calc||
|Calculation: if(contains([most_recent_date],"2017"),1,0)|||||
|113|[most_recent_date_year_16]|Most Recent Appointment Year (2016)|calc||
|Calculation: if(contains([most_recent_date],"2016"),1,0)|||||
|114|[most_recent_date_year_15]|Most Recent Appointment Year (2015)|calc||
|Calculation: if(contains([most_recent_date],"2015"),1,0)|||||
|115|[most_recent_date_year_14]|Most Recent Appointment Year (2014)|calc||
|Calculation: if(contains([most_recent_date],"2014"),1,0)|||||
|116|[most_recent_date_year_13]|Most Recent Appointment Year (2013)|calc||
|Calculation: if(contains([most_recent_date],"2013"),1,0)|||||
|117|[most_recent_date_year_12]|Most Recent Appointment Year (2012)|calc||
|Calculation: if(contains([most_recent_date],"2012"),1,0)|||||
|118|[most_recent_date_year_11]|Most Recent Appointment Year (2011)|calc||
|Calculation: if(contains([most_recent_date],"2011"),1,0)|||||
|119|[most_recent_date_month_jan]|Most Recent Appointment Month (January)|calc||
|Calculation: if(contains([most_recent_date],"-01-"),1,0)|||||
|120|[most_recent_date_month_feb]|Most Recent Appointment Month (February)|calc||
|Calculation: if(contains([most_recent_date],"-02-"),1,0)|||||
|121|[most_recent_date_month_mar]|Most Recent Appointment Month (March)|calc||
|Calculation: if(contains([most_recent_date],"-03-"),1,0)|||||
|122|[most_recent_date_month_apr]|Most Recent Appointment Month (April)|calc||
|Calculation: if(contains([most_recent_date],"-04-"),1,0)|||||
|123|[most_recent_date_month_may]|Most Recent Appointment Month (May)|calc||
|Calculation: if(contains([most_recent_date],"-05-"),1,0)|||||
|124|[most_recent_date_month_jun]|Most Recent Appointment Month (June)|calc||
|Calculation: if(contains([most_recent_date],"-06-"),1,0)|||||
|125|[most_recent_date_month_jul]|Most Recent Appointment Month (July)|calc||
|Calculation: if(contains([most_recent_date],"-07-"),1,0)|||||
|126|[most_recent_date_month_aug]|Most Recent Appointment Month (August)|calc||
|Calculation: if(contains([most_recent_date],"-08-"),1,0)|||||
|127|[most_recent_date_month_sep]|Most Recent Appointment Month (September)|calc||
|Calculation: if(contains([most_recent_date],"-09-"),1,0)|||||
|128|[most_recent_date_month_oct]|Most Recent Appointment Month (October)|calc||
|Calculation: if(contains([most_recent_date],"-10-"),1,0)|||||
|129|[most_recent_date_month_nov]|Most Recent Appointment Month (November)|calc||
|Calculation: if(contains([most_recent_date],"-11-"),1,0)|||||
|130|[most_recent_date_month_dec]|Most Recent Appointment Month (December)|calc||
|Calculation: if(contains([most_recent_date],"-12-"),1,0)|||||
|131|[appointment_complete]|Complete?|dropdown||
|0, Incomplete|||||
|1, Unverified|||||
|2, Complete|||||

### Comorbidities

|#|Variable / Field Name|Field Label|Field Attributes (Field Type, Validation, Choices, Calculations, etc.)|_**Notes**_|
|---|---|---|---|---|
|132|[smoking]|Smoking|dropdown||
|1, Current Smoker|||||
|2, History of Smoking|||||
|3, Never|_this differs from MBSAQIP because they only have current smoker or never; for internal purposes added history of smoking_||||
|133|[diabetes]|Diabetes|dropdown||
|1, Yes, non-insulin|||||
|2, Yes, insulin|||||
|3, No|||||
|134|[immuno]|Steroid/Immunosuppressant for Chronic Condition|yesno||
|1, Yes|||||
|0, No|||||
|135|[copd]|History of Severe COPD|yesno||
|1, Yes|||||
|0, No|||||
|136|[pulm_emb]|History of Pulmonary Embolism|yesno||
|1, Yes|||||
|0, No|||||
|137|[osa]|Sleep Apnea|yesno||
|1, Yes|||||
|0, No|||||
|138|[gerd]|GERD|yesno||
|1, Yes|||||
|0, No|||||
|139|[prev_foregut]|Previous Foregut Surgery|yesno||
|1, Yes|||||
|0, No|||||
|140|[liver]|Liver Disease|yesno||
|1, Yes|||||
|0, No|||||
|141|[mi]|History of Myocardial Infarction|yesno||
|1, Yes|||||
|0, No|||||
|142|[pci_ptca]|Previous PCI/PTCA|yesno||
|1, Yes|||||
|0, No|||||
|143|[cardiac]|Previous Cardiac Surgery|yesno||
|1, Yes|||||
|0, No|||||
|144|[vent_device]|Ventricular Assist Device|yesno||
|1, Yes|||||
|0, No|||||
|145|[heart_fail]|Heart Failure|yesno||
|1, Yes|||||
|0, No|||||
|146|[hld]|Hyperlipidemia|yesno||
|1, Yes|||||
|0, No|||||
|147|[htn]|Hypertension|yesno||
|1, Yes|||||
|0, No|||||
|148|[htn_meds]||||
|Show the field ONLY if:[htn]='1'|Number of Anti-Hypertensive Medications|radio|||
|1, 1|||||
|2, 2|||||
|3, 3 or more|||||
|149|[vthrom]|Vein Thrombosis Requiring Therapy|yesno||
|1, Yes|||||
|0, No|||||
|150|[anticoag]|Therapeutic Anticoagulation|yesno||
|1, Yes|||||
|0, No|||||
|151|[venous]|Venous Stasis|yesno||
|1, Yes|||||
|0, No|||||
|152|[ivc]|IVC Filter|yesno||
|1, Yes|||||
|0, No|||||
|153|[ivc_timing]||||
|Show the field ONLY if:|||||
|[ivc]='1'|IVC Filter Timing|radio|||
|1, IVC filter placed in anticipation of the metabolic or bariatric procedure|||||
|2, IVC filter was pre-existing|||||
|3, Unknown|||||
|154|[dialy]|Currently Requiring/On Dialysis|yesno||
|1, Yes|||||
|0, No|||||
|155|[renal]|Renal Insufficiency|yesno||
|1, Yes|||||
|0, No|||||
|156|[other_comorb]|Other Comorbidities|notes||
|157|[comorbidities_complete]|Complete?|dropdown||
|0, Incomplete|||||
|1, Unverified|||||
|2, Complete|||||

### Group Sessions

|#|Variable / Field Name|Field Label|Field Attributes (Field Type, Validation, Choices, Calculations, etc.)|_**Notes**_|
|---|---|---|---|---|
|158|[groups_redq_insr]|Number of Group Sessions REQUIRED by Insurance/Program|dropdown||
|0, 0|||||
|1, 1|||||
|2, 2|||||
|3, 3|||||
|4, 4|||||
|5, 5|||||
|6, 6|||||
|7, 7|||||
|8, 8|||||
|9, 9|||||
|10, 10|||||
|11, 11|||||
|12, 12|||||
|999, Other|||||
|159|[groups_reqd_other]||||
|Show the field ONLY if:|||||
|[groups_redq_insr]='999'|(If "Other") Number of Group Sessions Needed|text|||
|160|[groups_comp]|Groups Completed|calc||
|Calculation: sum([group_1],[group_2],[group_3],[group_4],[group_5],[group_6],[group_7],[group_8],[group_9],[group_10],[group_11],[group_12],[group_13],[group_14],[group_15])|||||
|161|[groups_left]|Groups Left|calc||
|Calculation: if([groups_redq_insr]='0',0,if([groups_redq_insr]<>'999',[groups_redq_insr]-[groups_comp],''))|||||
|162|[group_date_1]|Group Scheduled Date|text (date_mdy)||
|163|[group_1]||||
|Show the field ONLY if:[group_date_1]<>''|Group Status|radio|||
|1, Arrived|||||
|0, NOS/Canceled|||||
|164|[group_date_2]||||
|Show the field ONLY if:|||||
|[group_date_1]<>''|Group Scheduled Date|text (date_mdy)|||
|165|[group_2]||||
|Show the field ONLY if:|||||
|[group_date_2]<>''|Group Status|radio|||
|1, Arrived|||||
|0, NOS/Canceled|||||
|166|[group_date_3]||||
|Show the field ONLY if:[group_date_2]<>''|Group Scheduled Date|text (date_mdy)|||
|167|[group_3]||||
|Show the field ONLY if:|||||
|[group_date_3]<>''|Group Status|radio|||
|1, Arrived|||||
|0, NOS/Canceled|||||
|168|[group_date_4]||||
|Show the field ONLY if:|||||
|[group_date_3]<>''|Group Scheduled Date|text (date_mdy)|||
|169|[group_4]||||
|Show the field ONLY if:|||||
|[group_date_4]<>''|Group Status|radio|||
|1, Arrived|||||
|0, NOS/Canceled|||||
|170|[group_date_5]||||
|Show the field ONLY if:|||||
|[group_date_4]<>''|Group Scheduled Date|text (date_mdy)|||
|171|[group_5]||||
|Show the field ONLY if:|||||
|[group_date_5]<>''|Group Status|radio|||
|1, Arrived|||||
|0, NOS/Canceled|||||
|172|[group_date_6]||||
|Show the field ONLY if:[group_date_5]<>''|Group Scheduled Date|text (date_mdy)|||
|173|[group_6]||||
|Show the field ONLY if:|||||
|[group_date_6]<>''|Group Status|radio|||
|1, Arrived|||||
|0, NOS/Canceled|||||
|174|[group_date_7]||||
|Show the field ONLY if:|||||
|[group_date_6]<>''|Group Scheduled Date|text (date_mdy)|||
|175|[group_7]||||
|Show the field ONLY if:|||||
|[group_date_7]<>''|Group Status|radio|||
|1, Arrived|||||
|0, NOS/Canceled|||||
|176|[group_date_8]||||
|Show the field ONLY if:[group_date_7]<>''|Group Scheduled Date|text (date_mdy)|||
|177|[group_8]||||
|Show the field ONLY if:|||||
|[group_date_8]<>''|Group Status|radio|||
|1, Arrived|||||
|0, NOS/Canceled|||||
|178|[group_date_9]||||
|Show the field ONLY if:|||||
|[group_date_8]<>''|Group Scheduled Date|text (date_mdy)|||
|179|[group_9]||||
|Show the field ONLY if:[group_date_9]<>''|Group Status|radio|||
|1, Arrived|||||
|0, NOS/Canceled|||||
|180|[group_date_10]||||
|Show the field ONLY if:[group_date_9]<>''|Group Scheduled Date|text (date_mdy)|||
|181|[group_10]||||
|Show the field ONLY if:|||||
|[group_date_10]<>''|Group Status|radio|||
|1, Arrived|||||
|0, NOS/Canceled|||||
|182|[group_date_11]||||
|Show the field ONLY if:|||||
|[group_date_10]<>''|Group Scheduled Date|text (date_mdy)|||
|183|[group_11]||||
|Show the field ONLY if:[group_date_11]<>''|Group Status|radio|||
|1, Arrived|||||
|0, NOS/Canceled|||||
|184|[group_date_12]||||
|Show the field ONLY if:|||||
|[group_date_11]<>''|Group Scheduled Date|text (date_mdy)|||
|185|[group_12]||||
|Show the field ONLY if:|||||
|[group_date_12]<>''|Group Status|radio|||
|1, Arrived|||||
|0, NOS/Canceled|||||
|186|[group_date_13]||||
|Show the field ONLY if:|||||
|[group_date_12]<>''|Group Scheduled Date|text (date_mdy)|||
|187|[group_13]||||
|Show the field ONLY if:|||||
|[group_date_13]<>''|Group Status|radio|||
|1, Arrived|||||
|0, NOS/Canceled|||||
|188|[group_date_14]||||
|Show the field ONLY if:|||||
|[group_date_13]<>''|Group Scheduled Date|text (date_mdy)|||
|189|[group_14]||||
|Show the field ONLY if:[group_date_14]<>''|Group Status|radio|||
|1, Arrived|||||
|0, NOS/Canceled|||||
|190|[group_date_15]||||
|Show the field ONLY if:|||||
|[group_date_14]<>''|Group Scheduled Date|text (date_mdy)|||
|191|[group_15]||||
|Show the field ONLY if:|||||
|[group_date_15]<>''|Group Status|radio|||
|1, Arrived|||||
|0, NOS/Canceled|||||
|192|[groups_last]|Last Scheduled Group Date|text||
|Field Annotation: @CALCTEXT(if([group_date_15] <> "", [group_date_15], if([group_date_14] <> "", [group_date_14], if([group_date_13] <> "", [group_date_13], if([group_date_12] <> "", [group_date_12], if([group_date_11] <> "", [group_date_11], if([group_date_10] <> "", [group_date_10], if([group_date_9] <> "", [group_date_9], if([group_date_8] <> "", [group_date_8], if([group_date_7] <> "", [group_date_7], if([group_date_6] <> "", [group_date_6], if([group_date_5] <> "", [group_date_5], if([group_date_4] <> "", [group_date_4], if([group_date_3] <> "", [group_date_3], if([group_date_2] <> "", [group_date_2], if([group_date_1] <> "", [group_date_1],""))))))))))))))))|||||
|193|[group_notes]|Group Session Notes|notes||
|194|[group_sessions_complete]|Complete?|dropdown||
|0, Incomplete|||||
|1, Unverified|||||
|2, Complete|||||

### Pre-Testing/Clearances

|#|Variable / Field Name|Field Label|Field Attributes (Field Type, Validation, Choices, Calculations, etc.)|_**Notes**_|
|---|---|---|---|---|
|195|[pst_labs]|Labs|radio||
|1, COMPLETED|||||
|2, PARTIAL|||||
|3, NOT COMPLETED|||||
|4, NOT ORDERED|||||
|196|[pst_labs_date]||||
|Show the field ONLY if:|||||
|[pst_labs]='1' OR [pst_labs]='2'|Lab Date|text (date_mdy)|||
|197|[pst_labs_results]||||
|Show the field ONLY if:|||||
|[pst_labs]='1' OR [pst_labs]='2'|Lab Results|radio|||
|1, NORMAL|||||
|2, ABNORMAL|||||
|3, NEEDS REPEAT|||||
|198|[pst_lab_notes]||||
|Show the field ONLY if:|||||
|[pst_labs]='1' OR [pst_labs]='2'|Lab Notes|notes|||
|199|[pst_ekg]|EKG|radio||
|1, COMPLETED|||||
|2, PARTIAL|||||
|3, NOT COMPLETED|||||
|4, NOT ORDERED|||||
|200|[pst_ekg_date]||||
|Show the field ONLY if:[pst_ekg]='1' OR [pst_ekg]='2'|EKG Date|text (date_mdy)|||
|201|[pst_ekg_results]||||
|Show the field ONLY if:|||||
|[pst_ekg]='1' OR [pst_ekg]='2'|EKG Results|radio|||
|1, NORMAL|||||
|2, ABNORMAL|||||
|4, BORDERLINE|||||
|3, NEEDS REPEAT|||||
|202|[pst_ekg_notes]||||
|Show the field ONLY if:|||||
|[pst_ekg]='1' OR [pst_ekg]='2'|EKG Notes|notes|||
|203|[pst_cxr]|Chest X-Ray|radio||
|1, COMPLETED|||||
|2, PARTIAL|||||
|3, NOT COMPLETED|||||
|4, NOT ORDERED|||||
|204|[pst_cxr_date]||||
|Show the field ONLY if:[pst_cxr]='1' OR [pst_cxr]='2'|Chest X-Ray Date|text (date_mdy)|||
|205|[pst_cxr_results]||||
|Show the field ONLY if:[pst_cxr]='1' OR [pst_cxr]='2'|Chest X-Ray Results|radio|||
|1, NORMAL|||||
|2, ABNORMAL|||||
|3, NEEDS REPEAT|||||
|206|[pst_cxr_notes]||||
|Show the field ONLY if:|||||
|[pst_cxr]='1' OR [pst_cxr]='2'|Chest X-Ray Notes|notes|||
|207|[pst_egd]|EGD|radio||
|1, COMPLETED|||||
|2, PARTIAL|||||
|3, NOT COMPLETED|||||
|6, SCHEDULED|||||
|5, TEST CONVERTED TO ANOTHER|||||
|4, NOT ORDERED|_when scheduled is selected first, the scheduled specific date and bravo options will show up but when the egd is finally complete or partial (or any other option selected) the scheduled date and bravo will reset and a notification will pop up to confirm this_||||
|208|[pst_egd_sch_bravo]||||
|Show the field ONLY if:[pst_egd]='6'|With Bravo?|radio|||
|0, No|||||
|1, Yes|||||
|209|[pst_egd_sch]||||
|Show the field ONLY if:|||||
|[pst_egd] = '6'|Scheduled Date|text (date_mdy)|||
|210|[pst_egd_bravo]||||
|Show the field ONLY if:[pst_egd]='1' OR [pst_egd]='2'|With Bravo?|radio|||
|0, No|||||
|1, Yes|||||
|211|[pst_egd_date]||||
|Show the field ONLY if:|||||
|[pst_egd]='1' OR [pst_egd]='2'|EGD Completion Date|text (date_mdy)|||
|212|[pst_egd_results]||||
|Show the field ONLY if:|||||
|[pst_egd]='1' OR [pst_egd]='2'|EGD Results|radio|||
|1, NORMAL|||||
|2, ABNORMAL|||||
|3, NEEDS REPEAT|||||
|213|[pst_egd_abn]||||
|Show the field ONLY if:|||||
|[pst_egd_results]='2'|EGD Abnormal Findings|checkbox|||
|1, pst_egd_abn___1, Hiatal Hernia|||||
|2, pst_egd_abn___2, Esophagitis|||||
|3, pst_egd_abn___3, Gastritis|||||
|4, pst_egd_abn___4, Barrett’s Esophagus|||||
|5, pst_egd_abn___5, Gastric Ulcer|||||
|999, pst_egd_abn___999, Other|||||
|214|[pst_egd_abn_other]||||
|Show the field ONLY if:[pst_egd_abn(999)] = '1'|EGD Abnormal Findings Other|text|||
|215|[pst_egd_notes]||||
|Show the field ONLY if:|||||
|[pst_egd]='1' OR [pst_egd]='2'|EGD Notes|notes|||
|216|[pst_barium]|Barium Swallow|radio||
|1, COMPLETED|||||
|2, PARTIAL|||||
|3, NOT COMPLETED|||||
|4, NOT ORDERED|||||
|217|[pst_barium_date]||||
|Show the field ONLY if:|||||
|[pst_barium]='1' OR [pst_barium]='2'|Barium Swallow Date|text (date_mdy)|||
|218|[pst_barium_results]||||
|Show the field ONLY if:|||||
|[pst_barium]='1' OR [pst_barium]='2'|Barium Swallow Results|radio|||
|1, NORMAL|||||
|2, ABNORMAL|||||
|3, NEEDS REPEAT|||||
|219|[pst_barium_abn]||||
|Show the field ONLY if:|||||
|[pst_barium_results]='2'|Barium Swallow Abnormal Findings|checkbox|||
|1, pst_barium_abn___1, Reflux/GERD|||||
|2, pst_barium_abn___2, Hiatal Hernia|||||
|3, pst_barium_abn___3, Stricture|||||
|4, pst_barium_abn___4, Tertiary Contractions|||||
|8, pst_barium_abn___8, Gastric Ulcer|||||
|999, pst_barium_abn___999, Other|||||
|220|[pst_barium_results_other]||||
|Show the field ONLY if:|||||
|[pst_barium_abn(999)] = '1'|Barium Swallow Results Other|text|||
|221|[pst_barium_notes]||||
|Show the field ONLY if:|||||
|[pst_barium]='1' OR [pst_barium]='2'|Barium Swallow Notes|notes|||
|222|[pst_pft]|PFT|radio||
|1, COMPLETED|||||
|2, PARTIAL|||||
|3, NOT COMPLETED|||||
|4, NOT ORDERED|||||
|223|[pst_pft_date]||||
|Show the field ONLY if:|||||
|[pst_pft]='1' OR [pst_pft]='2'|PFT Date|text (date_mdy)|||
|224|[pst_pft_results]||||
|Show the field ONLY if:[pst_pft]='1' OR [pst_pft]='2'|PFT Results|radio|||
|1, NORMAL|||||
|2, ABNORMAL|||||
|3, NEEDS REPEAT|||||
|225|[pst_pft_notes]||||
|Show the field ONLY if:|||||
|[pst_pft]='1' OR [pst_pft]='2'|PFT Notes|notes|||
|226|[pst_phm]|pH / Manometry|radio||
|1, COMPLETED|||||
|2, PARTIAL|||||
|3, NOT COMPLETED|||||
|4, NOT ORDERED|||||
|227|[pst_phm_date]||||
|Show the field ONLY if:|||||
|[pst_phm]='1' OR [pst_phm]='2'|pH / Manometry Date|text (date_mdy)|||
|228|[pst_phm_results]||||
|Show the field ONLY if:|||||
|[pst_phm]='1' OR [pst_phm]='2'|pH / Manometry Results|radio|||
|1, NORMAL|||||
|2, ABNORMAL|||||
|3, NEEDS REPEAT|||||
|229|[pst_phm_notes]||||
|Show the field ONLY if:[pst_phm]='1' OR [pst_phm]='2'|pH / Manometry Notes|notes|||
|230|[pst_urinenic]|Urine Nicotine|radio||
|1, COMPLETED|||||
|2, PARTIAL|||||
|3, NOT COMPLETED|||||
|4, NOT ORDERED|||||
|231|[pst_urinenic_date]||||
|Show the field ONLY if:|||||
|[pst_urinenic]='1' OR [pst_urinenic]='2'|Urine Nicotine Date|text (date_mdy)|||
|232|[pst_urinenic_results]||||
|Show the field ONLY if:[pst_urinenic]='1' OR [pst_urinenic]='2'|Urine Nicotine Results|radio|||
|1, POSITIVE|||||
|2, NEGATIVE|||||
|3, INCONCLUSIVE|||||
|233|[pst_urinenic_notes]||||
|Show the field ONLY if:|||||
|[pst_urinenic]='1' OR [pst_urinenic]='2'|Urine Nicotine Notes|notes|||
|234|[pst_sleep]|Sleep Study|radio||
|1, NOT ORDERED|||||
|2, NO SLEEP APNEA|||||
|3, CPAP ORDERED/HAS|||||
|4, NOT COMPLETED|||||
|999, OTHER|||||
|235|[pst_sleep_other]||||
|Show the field ONLY if:|||||
|[pst_sleep]='999'|Sleep Study Other|text|||
|236|[pst_sleep_date]||||
|Show the field ONLY if:|||||
|[pst_sleep]='2' OR [pst_sleep]='3' OR [pst_sleep]='4' OR [pst_sleep]='999'|Sleep Study Date|text (date_mdy)|||
|237|[pst_sleep_notes]||||
|Show the field ONLY if:|||||
|[pst_sleep]='2' OR [pst_sleep]='3' OR [pst_sleep]='4' OR [pst_sleep]='999'|Sleep Study Notes|notes|||
|238|[pst_othertest_1]|Other Test #1|text||
|239|[pst_othertest_date_1]||||
|Show the field ONLY if:[pst_othertest_1]<>''|Other Test #1 Date|text (date_mdy)|||
|240|[pst_othertest_results_1]Show the field ONLY if:[pst_othertest_1]<>''|Other Test #1 Results|radio||
|1, NORMAL|||||
|2, ABNORMAL|||||
|3, NEEDS REPEAT|||||
|241|[pst_othertest_notes_1]||||
|Show the field ONLY if:|||||
|[pst_othertest_1]<>''|Other Test #1 Notes|notes|||
|242|[pst_othertest_2]|Other Test #2|text||
|243|[pst_othertest_date_2]||||
|Show the field ONLY if:[pst_othertest_2]<>''|Other Test #2 Date|text (date_mdy)|||
|244|[pst_othertest_results_2]||||
|Show the field ONLY if:[pst_othertest_2]<>''|Other Test #2 Results|radio|||
|1, NORMAL|||||
|2, ABNORMAL|||||
|3, NEEDS REPEAT|||||
|245|[pst_othertest_notes_2]||||
|Show the field ONLY if:|||||
|[pst_othertest_2]<>''|Other Test #2 Notes|notes|||
|246|[pst_othertest_3]|Other Test #3|text||
|247|[pst_othertest_date_3]||||
|Show the field ONLY if:|||||
|[pst_othertest_3]<>''|Other Test #3 Date|text (date_mdy)|||
|248|[pst_othertest_results_3]||||
|Show the field ONLY if:|||||
|[pst_othertest_3]<>''|Other Test #3 Results|radio|||
|1, NORMAL|||||
|2, ABNORMAL|||||
|3, NEEDS REPEAT|||||
|249|[pst_othertest_notes_3]||||
|Show the field ONLY if:[pst_othertest_3]<>''|Other Test #3 Notes|notes|||
|250|[pst_othertest_4]|Other Test #4|text||
|251|[pst_othertest_date_4]||||
|Show the field ONLY if:[pst_othertest_4]<>''|Other Test #4 Date|text (date_mdy)|||
|252|[pst_othertest_results_4]||||
|Show the field ONLY if:|||||
|[pst_othertest_4]<>''|Other Test #4 Results|radio|||
|1, NORMAL|||||
|2, ABNORMAL|||||
|3, NEEDS REPEAT|||||
|253|[pst_othertest_notes_4]||||
|Show the field ONLY if:[pst_othertest_4]<>''|Other Test #4 Notes|notes|||
|254|[pst_total_tests]|Total Tests Ordered|calc||
|Calculation: sum(if([pst_labs]='1',1,0)+ if([pst_labs]='2',1,0)+ if([pst_labs]='3',1,0)+ if([pst_ekg]='1',1,0)+ if([pst_ekg]='2',1,0)+ if([pst_ekg]='3',1,0)+ if([pst_cxr]='1',1,0)+ if([pst_cxr]='2',1,0)+ if([pst_cxr]='3',1,0)+ if([pst_egd]='1',1,0)+ if([pst_egd]='2',1,0)+ if([pst_egd]='3',1,0)+ if([pst_egd]='5',1,0)+ if([pst_barium]='1',1,0)+ if([pst_barium]='2',1,0)+ if([pst_barium]='3',1,0)+ if([pst_pft]='1',1,0)+ if([pst_pft]='2',1,0)+ if([pst_pft]='3',1,0)+ if([pst_phm]='1',1,0)+ if([pst_phm]='2',1,0)+ if([pst_phm]='3',1,0)+ if([pst_urinenic]='1',1,0)+ if([pst_urinenic]='2',1,0)+ if([pst_urinenic]='3',1,0)+ if([pst_sleep]='2',1,0)+ if([pst_sleep]='3',1,0)+ if([pst_sleep]='4',1,0)+ if([pst_othertest_1]<>'',1,0)+ if([pst_othertest_2]<>'',1,0)+ if([pst_othertest_3]<>'',1,0)+ if([pst_othertest_4]<>'',1,0))|||||
|255|[pst_total_tests_comp]|Total Tests COMPLETED|calc||
|Calculation: sum(if([pst_labs]='1',1,0)+ if([pst_ekg]='1',1,0)+ if([pst_cxr]='1',1,0)+ if([pst_egd]='1',1,0)+ if([pst_egd]='5',1,0)+ if([pst_barium]='1',1,0)+ if([pst_pft]='1',1,0)+ if([pst_phm]='1',1,0)+ if([pst_urinenic]='1',1,0)+ if([pst_sleep]='2',1,0)+ if([pst_sleep]='3',1,0)+ if([pst_othertest_results_1]='1',1,0)+ if([pst_othertest_results_1]='2',1,0)+ if([pst_othertest_results_2]='1',1,0)+ if([pst_othertest_results_2]='2',1,0)+ if([pst_othertest_results_3]='1',1,0)+ if([pst_othertest_results_3]='2',1,0)+ if([pst_othertest_results_4]='1',1,0)+ if([pst_othertest_results_4]='2',1,0))|||||
|256|[pst_total_tests_left]|Total Tests LEFT|calcCalculation: if(([pst_total_tests_comp] OR [pst_total_tests] > 0),[pst_total_tests]-[pst_total_tests_comp],"")||
|257|[pst_psych]|Psych Clearance|radio||
|7, NOT ORDERED|||||
|8, ORDERED|||||
|1, CLEARED|||||
|2, NOT CLEARED|||||
|3, FOLLOW UP NEEDED|||||
|4, PAPERWORK NEEDED|||||
|5, FOLLOW UP & PAPERWORK NEEDED|||||
|6, CX/NOS TO APPT|||||
|258|[pst_psych_date]||||
|Show the field ONLY if:|||||
|[pst_psych]='1' OR [pst_psych]='2' OR [pst_psych]='3' OR [pst_psych]='4' OR [pst_psych]='5' OR [pst_psych]='6' OR [pst_psych]='8'|Psych Date|text (date_mdy)|||
|259|[pst_psych_notes]||||
|Show the field ONLY if:|||||
|[pst_psych]='1' OR [pst_psych]='2' OR [pst_psych]='3' OR [pst_psych]='4' OR [pst_psych]='5' OR [pst_psych]='6' OR [pst_psych]='8'|Psych Notes|notes|||
|260|[pst_nutr]|Nutrition Clearance|radio||
|5, NOT ORDERED|||||
|6, ORDERED|||||
|1, CLEARED|||||
|2, NOT CLEARED|||||
|3, FOLLOW UP NEEDED|||||
|4, CX/NOS TO APPT|||||
|261|[pst_nutr_date]||||
|Show the field ONLY if:[pst_nutr]='1' OR [pst_nutr]='2' OR [pst_nutr]='3' OR [pst_nutr]='4' OR [pst_nutr]='6'|Nutrition Date|text (date_mdy)|||
|262|[pst_nutr_notes]||||
|Show the field ONLY if:|||||
|[pst_nutr]='1' OR [pst_nutr]='2' OR [pst_nutr]='3' OR [pst_nutr]='4' OR [pst_nutr]='6'|Nutrition Notes|notes|||
|263|[pst_cardio]|Cardiology Clearance|radio||
|6, NOT ORDERED|||||
|7, ORDERED|||||
|1, CLEARED|||||
|2, NOT CLEARED|||||
|3, FOLLOW UP NEEDED|||||
|4, TESTING NEEDED|||||
|5, CX/NOS TO APPT|||||
|264|[pst_cardio_date]||||
|Show the field ONLY if:|||||
|[pst_cardio]='1' OR [pst_cardio]='2' OR [pst_cardio]='3' OR [pst_cardio]='4' OR [pst_cardio]='5' OR [pst_cardio]='7'|Cardiology Date|text (date_mdy)|||
|265|[pst_cardio_notes]||||
|Show the field ONLY if:|||||
|[pst_cardio]='1' OR [pst_cardio]='2' OR [pst_cardio]='3' OR [pst_cardio]='4' OR [pst_cardio]='5' OR [pst_cardio]='7'|Cardiology Notes|notes|||
|266|[pst_endo]|Endocrinology Clearance|radio||
|6, NOT ORDERED|||||
|7, ORDERED|||||
|1, CLEARED|||||
|2, NOT CLEARED|||||
|3, FOLLOW UP NEEDED|||||
|4, TESTING NEEDED|||||
|5, CX/NOS TO APPT|||||
|267|[pst_endo_date]||||
|Show the field ONLY if:|||||
|[pst_endo]='1' OR [pst_endo]='2' OR [pst_endo]='3' OR [pst_endo]='4' OR [pst_endo]='5' OR [pst_endo]='7'|Endocrinology Date|text (date_mdy)|||
|268|[pst_endo_notes]||||
|Show the field ONLY if:|||||
|[pst_endo]='1' OR [pst_endo]='2' OR [pst_endo]='3' OR [pst_endo]='4' OR [pst_endo]='5' OR [pst_endo]='7'|Endocrinology Notes|notes|||
|269|[pst_hema]|Hematology Clearance|radio||
|6, NOT ORDERED|||||
|7, ORDERED|||||
|1, CLEARED|||||
|2, NOT CLEARED|||||
|3, FOLLOW UP NEEDED|||||
|4, TESTING NEEDED|||||
|5, CX/NOS TO APPT|||||
|270|[pst_hema_date]||||
|Show the field ONLY if:[pst_hema]='1' OR [pst_hema]='2' OR [pst_hema]='3' OR [pst_hema]='4' OR [pst_hema]='5' OR [pst_hema]='7'|Hematology Date|text (date_mdy)|||
|271|[pst_hema_notes]||||
|Show the field ONLY if:|||||
|[pst_hema]='1' OR [pst_hema]='2' OR [pst_hema]='3' OR [pst_hema]='4' OR [pst_hema]='5' OR [pst_hema]='7'|Hematology Notes|notes|||
|272|[pst_pulm]|Pulmonology Clearance|radio||
|6, NOT ORDERED|||||
|7, ORDERED|||||
|1, CLEARED|||||
|2, NOT CLEARED|||||
|3, FOLLOW UP NEEDED|||||
|4, TESTING NEEDED|||||
|5, CX/NOS TO APPT|||||
|273|[pst_pulm_date]||||
|Show the field ONLY if:|||||
|[pst_pulm]='1' OR [pst_pulm]='2' OR [pst_pulm]='3' OR [pst_pulm]='4' OR [pst_pulm]='5' OR [pst_pulm]='7'|Pulmonology Date|text (date_mdy)|||
|274|[pst_pulm_notes]||||
|Show the field ONLY if:|||||
|[pst_pulm]='1' OR [pst_pulm]='2' OR [pst_pulm]='3' OR [pst_pulm]='4' OR [pst_pulm]='5' OR [pst_pulm]='7'|Pulmonology Notes|notes|||
|275|[pst_neuro]|Neurology Clearance|radio||
|6, NOT ORDERED|||||
|7, ORDERED|||||
|1, CLEARED|||||
|2, NOT CLEARED|||||
|3, FOLLOW UP NEEDED|||||
|4, TESTING NEEDED|||||
|5, CX/NOS TO APPT|||||
|276|[pst_neuro_date]||||
|Show the field ONLY if:|||||
|[pst_neuro]='1' OR [pst_neuro]='2' OR [pst_neuro]='3' OR [pst_neuro]='4' OR [pst_neuro]='5' OR [pst_neuro]='7'|Neurology Date|text (date_mdy)|||
|277|[pst_neuro_notes]||||
|Show the field ONLY if:|||||
|[pst_neuro]='1' OR [pst_neuro]='2' OR [pst_neuro]='3' OR [pst_neuro]='4' OR [pst_neuro]='5' OR [pst_neuro]='7'|Neurology Notes|notes|||
|278|[pst_vasc]|Vascular Clearance|radio||
|6, NOT ORDERED|||||
|7, ORDERED|||||
|1, CLEARED|||||
|2, NOT CLEARED|||||
|3, FOLLOW UP NEEDED|||||
|4, TESTING NEEDED|||||
|5, CX/NOS TO APPT|||||
|279|[pst_vasc_date]||||
|Show the field ONLY if:|||||
|[pst_vasc]='1' OR [pst_vasc]='2' OR [pst_vasc]='3' OR [pst_vasc]='4' OR [pst_vasc]='5' OR [pst_vasc]='7'|Vascular Date|text (date_mdy)|||
|280|[pst_vasc_notes]||||
|Show the field ONLY if:|||||
|[pst_vasc]='1' OR [pst_vasc]='2' OR [pst_vasc]='3' OR [pst_vasc]='4' OR [pst_vasc]='5' OR [pst_vasc]='7'|Vascular Notes|notes|||
|281|[pst_peds]|Pediatric Clearance|radio||
|6, NOT ORDERED|||||
|7, ORDERED|||||
|1, CLEARED|||||
|2, NOT CLEARED|||||
|3, FOLLOW UP NEEDED|||||
|4, TESTING NEEDED|||||
|5, CX/NOS TO APPT|||||
|282|[pst_peds_date]||||
|Show the field ONLY if:|||||
|[pst_peds]='1' OR [pst_peds]='2' OR [pst_peds]='3' OR [pst_peds]='4' OR [pst_peds]='5' OR [pst_peds]='7'|Pediatric Date|text (date_mdy)|||
|283|[pst_peds_notes]||||
|Show the field ONLY if:|||||
|[pst_peds]='1' OR [pst_peds]='2' OR [pst_peds]='3' OR [pst_peds]='4' OR [pst_peds]='5' OR [pst_peds]='7'|Pediatric Notes|notes|||
|284|[pst_pcp]|PCP|radio||
|7, NOT REQUIRED|||||
|6, REQUIRED|||||
|1, COMPLETED|||||
|3, FOLLOW UP NEEDED|||||
|4, CX/NOS TO APPT|||||
|285|[pst_pcp_date]||||
|Show the field ONLY if:|||||
|[pst_pcp]='1' OR [pst_pcp]='2' OR [pst_pcp]='3' OR [pst_pcp]='4' OR [pst_pcp]='5' OR [pst_pcp]='6'|PCP Date|text (date_mdy)|||
|286|[pst_pcp_notes]Show the field ONLY if:[pst_pcp]='1' OR [pst_pcp]='2' OR [pst_pcp]='3' OR [pst_pcp]='4' OR [pst_pcp]='5' OR [pst_pcp]='6'|PCP Notes|notes||
|287|[pst_otherclear_1]|Other Clearance #1|text||
|288|[pst_otherclear_status_1]||||
|Show the field ONLY if:|||||
|[pst_otherclear_1]<>''|Other Clearance #1 Status|radio|||
|6, REQUIRED|||||
|7, NOT REQUIRED|||||
|1, COMPLETED|||||
|3, FOLLOW UP NEEDED|||||
|4, CX/NOS TO APPT|||||
|289|[pst_otherclear_date_1]||||
|Show the field ONLY if:|||||
|[pst_otherclear_status_1]='1' OR [pst_otherclear_status_1]='2' OR [pst_otherclear_status_1]='3' OR [pst_otherclear_status_1]='4' OR [pst_otherclear_status_1]='5' OR [pst_otherclear_status_1]='6'|Other Clearance #1 Date|text (date_mdy)|||
|290|[pst_otherclear_notes]Show the field ONLY if:[pst_otherclear_status_1]='1' OR [pst_otherclear_status_1]='2' OR [pst_otherclear_status_1]='3' OR [pst_otherclear_status_1]='4' OR [pst_otherclear_status_1]='5' OR [pst_otherclear_status_1]='6'|Other Clearance #1 Notes|notes||
|291|[pst_otherclear_2]|Other Clearance #2|text||
|292|[pst_otherclear_status_2]||||
|Show the field ONLY if:|||||
|[pst_otherclear_2]<>''|Other Clearance #2 Status|radio|||
|6, REQUIRED|||||
|7, NOT REQUIRED|||||
|1, COMPLETED|||||
|3, FOLLOW UP NEEDED|||||
|4, CX/NOS TO APPT|||||
|293|[pst_otherclear_date_2]||||
|Show the field ONLY if:|||||
|[pst_otherclear_status_2]='1' OR [pst_otherclear_status_2]='2' OR [pst_otherclear_status_2]='3' OR [pst_otherclear_status_2]='4' OR [pst_otherclear_status_2]='5' OR [pst_otherclear_status_2]='6'|Other Clearance #2 Date|text (date_mdy)|||
|294|[pst_otherclear_notes_2]||||
|Show the field ONLY if:|||||
|[pst_otherclear_status_2]='1' OR [pst_otherclear_status_2]='2' OR [pst_otherclear_status_2]='3' OR [pst_otherclear_status_2]='4' OR [pst_otherclear_status_2]='5' OR [pst_otherclear_status_2]='6'|Other Clearance #2 Notes|notes|||
|295|[pst_otherclear_3]|Other Clearance #3|text||
|296|[pst_otherclear_status_3]||||
|Show the field ONLY if:[pst_otherclear_3]<>''|Other Clearance #3 Status|radio|||
|6, REQUIRED|||||
|7, NOT REQUIRED|||||
|1, COMPLETED|||||
|3, FOLLOW UP NEEDED|||||
|4, CX/NOS TO APPT|||||
|297|[pst_otherclear_date_3]||||
|Show the field ONLY if:|||||
|[pst_otherclear_status_3]='1' OR [pst_otherclear_status_3]='2' OR [pst_otherclear_status_3]='3' OR [pst_otherclear_status_3]='4' OR [pst_otherclear_status_3]='5' OR [pst_otherclear_status_3]='6'|Other Clearance #3 Date|text (date_mdy)|||
|298|[pst_otherclear_notes_3]||||
|Show the field ONLY if:|||||
|[pst_otherclear_status_3]='1' OR [pst_otherclear_status_3]='2' OR [pst_otherclear_status_3]='3' OR [pst_otherclear_status_3]='4' OR [pst_otherclear_status_3]='5' OR [pst_otherclear_status_3]='6'|Other Clearance #3 Notes|notes|||
|299|[pst_otherclear_4]|Other Clearance #4|text||
|300|[pst_otherclear_status_4]||||
|Show the field ONLY if:|||||
|[pst_otherclear_4]<>''|Other Clearance #4 Status|radio|||
|6, REQUIRED|||||
|7, NOT REQUIRED|||||
|1, COMPLETED|||||
|3, FOLLOW UP NEEDED|||||
|4, CX/NOS TO APPT|||||
|301|[pst_otherclear_date_4]||||
|Show the field ONLY if:|||||
|[pst_otherclear_status_4]='1' OR [pst_otherclear_status_4]='2' OR [pst_otherclear_status_4]='3' OR [pst_otherclear_status_4]='4' OR [pst_otherclear_status_4]='5' OR [pst_otherclear_status_4]='6'|Other Clearance #4 Date|text (date_mdy)|||
|302|[pst_otherclear_notes_4]Show the field ONLY if:[pst_otherclear_status_4]='1' OR [pst_otherclear_status_4]='2' OR [pst_otherclear_status_4]='3' OR [pst_otherclear_status_4]='4' OR [pst_otherclear_status_4]='5' OR [pst_otherclear_status_4]='6'|Other Clearance #4 Notes|notes||
|303|[pst_total_clear]|Total Clearances Ordered|calcCalculation: sum(if([pst_psych]='1',1,0)+ if([pst_psych]='2',1,0)+ if([pst_psych]='3',1,0)+ if([pst_psych]='4',1,0)+ if([pst_psych]='5',1,0)+ if([pst_psych]='6',1,0)+ if([pst_psych]='8',1,0)+ if([pst_nutr]='1',1,0)+ if([pst_nutr]='2',1,0)+ if([pst_nutr]='3',1,0)+ if([pst_nutr]='4',1,0)+ if([pst_nutr]='6',1,0)+ if([pst_cardio]='1',1,0)+ if([pst_cardio]='2',1,0)+ if([pst_cardio]='3',1,0)+ if([pst_cardio]='4',1,0)+ if([pst_cardio]='5',1,0)+ if([pst_cardio]='7',1,0)+ if([pst_endo]='1',1,0)+ if([pst_endo]='2',1,0)+ if([pst_endo]='3',1,0)+ if([pst_endo]='4',1,0)+ if([pst_endo]='5',1,0)+ if([pst_endo]='7',1,0)+ if([pst_hema]='1',1,0)+ if([pst_hema]='2',1,0)+ if([pst_hema]='3',1,0)+ if([pst_hema]='4',1,0)+ if([pst_hema]='5',1,0)+ if([pst_hema]='7',1,0)+ if([pst_pulm]='1',1,0)+ if([pst_pulm]='2',1,0)+ if([pst_pulm]='3',1,0)+ if([pst_pulm]='4',1,0)+ if([pst_pulm]='5',1,0)+ if([pst_pulm]='7',1,0)+ if([pst_neuro]='1',1,0)+ if([pst_neuro]='2',1,0)+ if([pst_neuro]='3',1,0)+ if([pst_neuro]='4',1,0)+ if([pst_neuro]='5',1,0)+ if([pst_neuro]='7',1,0)+ if([pst_vasc]='1',1,0)+ if([pst_vasc]='2',1,0)+ if([pst_vasc]='3',1,0)+ if([pst_vasc]='4',1,0)+ if([pst_vasc]='5',1,0)+ if([pst_vasc]='7',1,0)+ if([pst_peds]='1',1,0)+ if([pst_peds]='2',1,0)+ if([pst_peds]='3',1,0)+ if([pst_peds]='4',1,0)+ if([pst_peds]='5',1,0)+ if([pst_peds]='7',1,0)+ if([pst_pcp]='1',1,0)+ if([pst_pcp]='2',1,0)+ if([pst_pcp]='3',1,0)+ if([pst_pcp]='4',1,0)+ if([pst_pcp]='5',1,0)+ if([pst_pcp]='6',1,0)+ if([pst_otherclear_status_1]='1',1,0)+ if([pst_otherclear_status_1]='2',1,0)+ if([pst_otherclear_status_1]='3',1,0)+ if([pst_otherclear_status_1]='4',1,0)+ if([pst_otherclear_status_1]='5',1,0)+ if([pst_otherclear_status_1]='6',1,0)+ if([pst_otherclear_status_2]='1',1,0)+ if([pst_otherclear_status_2]='2',1,0)+ if([pst_otherclear_status_2]='3',1,0)+ if([pst_otherclear_status_2]='4',1,0)+ if([pst_otherclear_status_2]='5',1,0)+ if([pst_otherclear_status_2]='6',1,0)+ if([pst_otherclear_status_3]='1',1,0)+ if([pst_otherclear_status_3]='2',1,0)+ if([pst_otherclear_status_3]='3',1,0)+ if([pst_otherclear_status_3]='4',1,0)+ if([pst_otherclear_status_3]='5',1,0)+ if([pst_otherclear_status_3]='6',1,0)+ if([pst_otherclear_status_4]='1',1,0)+ if([pst_otherclear_status_4]='2',1,0)+ if([pst_otherclear_status_4]='3',1,0)+ if([pst_otherclear_status_4]='4',1,0)+ if([pst_otherclear_status_4]='5',1,0)+ if([pst_otherclear_status_4]='6',1,0))||
|304|[pst_total_clear_comp]|Total Clearances COMPLETED|calc||
|Calculation: sum(if([pst_psych]='1',1,0)+ if([pst_nutr]='1',1,0)+ if([pst_cardio]='1',1,0)+ if([pst_endo]='1',1,0)+ if([pst_hema]='1',1,0)+ if([pst_pulm]='1',1,0)+ if([pst_neuro]='1',1,0)+ if([pst_vasc]='1',1,0)+ if([pst_peds]='1',1,0)+ if([pst_pcp]='1',1,0)+ if([pst_otherclear_status_1]='1',1,0)+ if([pst_otherclear_status_2]='1',1,0)+ if([pst_otherclear_status_3]='1',1,0)+ if([pst_otherclear_status_4]='1',1,0))|||||
|305|[pst_total_clear_left]|Total Clearances LEFT|calc||
|Calculation: if(([pst_total_clear_comp] OR [pst_total_clear] > 0),[pst_total_clear]-[pst_total_clear_comp],"")|||||
|306|[pst_appt_review]|Review Tests/Clearances Appointment Status|radio, Required||
|1, COMPLETE/NOT NEEDED|||||
|2, PENDING|||||
|3, CX/NOS TO APPT|||||
|4, FOLLOW UP NEEDED|||||
|5, NOT SCHEDULED|||||
|307|[pst_appt_review_date]|Appointment Date|text (date_mdy)||
|308|[pretestingclearances_complete]|Complete?|dropdown||
|0, Incomplete|||||
|1, Unverified|||||
|2, Complete|||||

### Pre-Surgery Labs

|#|Variable / Field Name|Field Label|Field Attributes (Field Type, Validation, Choices, Calculations, etc.)|_**Notes**_|
|---|---|---|---|---|
|309|[psl_lab_date]|Lab Date|text (date_mdy)|_The Lab Date should be entered as the date the labs were drawn_|
|310|[psl_hemo]|Hemoglobin|text||
|311|[psl_hema]|Hematocrit|text||
|312|[psl_plate]|Platelet Count|text||
|313|[psl_wbc]|White blood cell (WBC) Count|text||
|314|[psl_album]|Albumin|text||
|315|[psl_alk]|Alkaline phosphatase|text||
|316|[psl_alt]|ALT (alanine aminotransferase)|text||
|317|[psl_ast]|AST (aspartate aminotransferase)|text||
|318|[psl_bun]|BUN (blood urea nitrogen)|text||
|319|[psl_calc]|Calcium|text||
|320|[psl_chlor]|Chloride|text||
|321|[psl_co2]|CO2 (carbon dioxide)|text||
|322|[psl_creat]|Creatinine|text||
|323|[psl_gluc]|Glucose|text||
|324|[psl_pota]|Potassium|text||
|325|[psl_sod]|Sodium|text||
|326|[psl_bili]|Total bilirubin|text||
|327|[psl_prot]|Total protein|text||
|328|[psl_vita]|Vitamin A|text||
|329|[psl_vitb1]|Vitamin B1 (Thiamine)|text||
|330|[psl_vitb12]|Vitamin B12|text||
|331|[psl_vitd]|Vitamin D, 25-Hydroxy|text||
|332|[psl_vite]|Vitamin E|text||
|333|[psl_vitk1]|Vitamin K1|text||
|334|[psl_tot_chl]|Total Cholesterol|text||
|335|[psl_ldl]|LDL Cholesterol|text||
|336|[psl_hdl]|HDL Cholesterol|text||
|337|[psl_fola]|Folate|text||
|338|[psl_ferr]|Ferritin|text||
|339|[psl_tsh]|TSH|text||
|340|[psl_iron]|Iron|text||
|341|[psl_hgb]|HgbA1C|text||
|342|[lab_notes]|Lab Notes|notes||
|343|[presurgery_labs_complete]|Complete?|dropdown||
|0, Incomplete|||||
|1, Unverified|||||
|2, Complete|||||

### Patient Notes/Communication

|#|Variable / Field Name|Field Label|Field Attributes (Field Type, Validation, Choices, Calculations, etc.)|_**Notes**_|
|---|---|---|---|---|
|344|[commun_date]|Date|text (datetime_mdy)||
|Field Annotation: @DEFAULT=@NOW-UTC|||||
|345|[commun]||notes, Identifier||
|346|[commun_user]|Communication Entered By:|text||
|Field Annotation: @USERNAME|||||
|347|[patient_notescommunication_complete]|Complete?|dropdown||
|0, Incomplete|||||
|1, Unverified|||||
|2, Complete|||||

### PT STATUS

|#|Variable / Field Name|Field Label|Field Attributes (Field Type, Validation, Choices, Calculations, etc.)|_**Notes**_|
|---|---|---|---|---|
|348|[status_patient]|MRN Name Current Age Insurance [mrn] [first_name] [last_name] [current_age] [insurance] Consultation [most_recent_date] [consulting_md] [procedural_track]|descriptive||
|349|[status_overview]|Groups Completed [groups_comp][last-instance] (out of [groups_redq_insr][last-instance]) Tests Completed [pst_total_tests_comp][last-instance] (out of [pst_total_tests][last-instance]) Clearances Completed [pst_total_clear_comp][last-instance] (out of [pst_total_clear][last-instance])|descriptive||
|350|[status_tests]|Test Date Status Results Abnormal Results / Notes Labs [pst_labs_date][last-instance] [pst_labs][last-instance] [pst_labs_results][last-instance] [pst_lab_notes][last-instance] EKG [pst_ekg_date][last-instance] [pst_ekg][last-instance] [pst_ekg_results][last-instance] [pst_ekg_notes][last-instance] Chest X-Ray [pst_cxr_date][last-instance] [pst_cxr][last-instance] [pst_cxr_results][last-instance] [pst_cxr_notes][last-instance] EGD [pst_egd_date][last-instance] [pst_egd][last-instance] [pst_egd_bravo][last-instance] with Bravo [pst_egd_results][last-instance] [pst_egd_abn][last-instance] [pst_egd_notes][last-instance] Barium [pst_barium_date][last-instance] [pst_barium][last-instance] [pst_barium_results][last-instance] [pst_barium_abn][last-instance] [pst_barium_notes][last-instance] PFT [pst_pft_date][last-instance] [pst_pft][last-instance] [pst_pft_results][last-instance] [pst_pft_notes][last-instance] pH / Manometry [pst_phm_date][last-instance] [pst_phm][last-instance] [pst_phm_results][last-instance] [pst_phm_notes][last-instance] Urine Nicotine [pst_urinenic_date][last-instance] [pst_urinenic][last-instance] [pst_urinenic_results][last-instance] [pst_urinenic_notes][last-instance] Sleep Study [pst_sleep_date][last-instance] [pst_sleep][last-instance] --- [pst_sleep_notes][last-instance] [pst_othertest_1] [pst_othertest_date_1][last-instance] --- [pst_othertest_results_1][last-instance] [pst_othertest_notes_1][last-instance] [pst_othertest_2] [pst_othertest_date_2][last-instance] --- [pst_othertest_results_2][last-instance] [pst_othertest_notes_2][last-instance] [pst_othertest_3] [pst_othertest_date_3][last-instance] --- [pst_othertest_results_3][last-instance] [pst_othertest_notes_3][last-instance] [pst_othertest_4] [pst_othertest_date_4][last-instance] --- [pst_othertest_results_4][last-instance] [pst_othertest_notes_4][last-instance]|descriptive||
|351|[status_clearances]|Clearance Date Status Notes Psych [pst_psych_date][last-instance] [pst_psych][last-instance] [pst_psych_notes][last-instance] Nutrition [pst_nutr_date][last-instance] [pst_nutr][last-instance] [pst_nutr_notes][last-instance] Cardiology [pst_cardio_date][last-instance] [pst_cardio][last-instance] [pst_cardio_notes][last-instance] Endocrinology [pst_endo_date][last-instance] [pst_endo][last-instance] [pst_endo_notes][last-instance] Hematology [pst_hema_date][last-instance] [pst_hema][last-instance] [pst_hema_notes][last-instance] Pulmonology [pst_pulm_date][last-instance] [pst_pulm][last-instance] [pst_pulm_notes][last-instance] Neurology [pst_neuro_date][last-instance] [pst_neuro][last-instance] [pst_neuro_notes][last-instance] Vascular [pst_vasc_date][last-instance] [pst_vasc][last-instance] [pst_vasc_notes][last-instance] Pediatric [pst_peds_date][last-instance] [pst_peds][last-instance] [pst_peds_notes][last-instance] [pst_otherclear_1] [pst_otherclear_date_1][last-instance] [pst_otherclear_status_1][last-instance] [pst_otherclear_notes][last-instance] [pst_otherclear_2] [pst_otherclear_date_2][last-instance] [pst_otherclear_status_2][last-instance] [pst_otherclear_notes_2][last-instance] [pst_otherclear_3] [pst_otherclear_date_3][last-instance] [pst_otherclear_status_3][last-instance] [pst_otherclear_notes_3][last-instance] [pst_otherclear_4] [pst_otherclear_date_4][last-instance] [pst_otherclear_status_4][last-instance] [pst_otherclear_notes_4][last-instance] PCP [pst_pcp_date][last-instance] [pst_pcp][last-instance] [pst_pcp_notes][last-instance]|descriptive||
|352|[status_groups]|Groups Completed?|text||
|Field Annotation: @CALCTEXT(if([groups_left][last-instance]<=0,"YES","NO"))|||||
|353|[status_testing]|Testing Completed?|text||
|Field Annotation: @CALCTEXT(if([pst_total_tests_left][last-instance]=0,"YES","NO"))|||||
|354|[status_clear]|Clearances Completed?|text||
|Field Annotation: @CALCTEXT(if([pst_total_clear_left][last-instance]=0,"YES","NO"))|||||
|355|[status_review]|Patient Seen to Review Tests/Clearances?|textField Annotation: @CALCTEXT(if([pst_appt_review][last-instance]=1,"YES","NO"))||
|356|[status]|Is Patient Ready?|text||
|Field Annotation: @CALCTEXT(if([status_groups]="YES" AND [status_testing]="YES" AND [status_clear]="YES" AND [status_review]="YES" ,"YES", "NO"))|||||
|357|[status_sx_date]|Scheduled Surgery Date|text (date_mdy)||
|358|[status_md]|Scheduled Surgeon|dropdown||
|1, Aurora Pryor|||||
|2, Dino Spaniolas|||||
|3, Sal Docimo|||||
|4, Kinga Powers|||||
|5, Amy Rosenbluth|||||
|6, Andrew Bates|||||
|7, Dana Telem|||||
|8, Edmund Lee|||||
|999, Other|||||
|359|[status_md_other]||||
|Show the field ONLY if:[status_md]='999'|Other Surgeon|text|||
|360|[status_sx]|Scheduled Procedure|radio||
|2, Balloon|||||
|3, Band|||||
|4, Bypass|||||
|5, Conversion|||||
|7, Reoperation|||||
|8, Revision|||||
|9, Sleeve|||||
|10, Switch|||||
|361|[status_sx_details]Show the field ONLY if:[status_sx] = '5' or [status_sx] = '7' or [status_sx] = '8'|Type of Revision/Conversion/Reoperation|dropdown||
|1, Band Removal|||||
|2, Band to Bypass|||||
|3, Band to Sleeve|||||
|4, Bypass Reversal|||||
|5, Bypass to Sleeve|||||
|6, Dor Fundoplication to Bypass|||||
|7, Obalon Removal|||||
|8, Open Sleeve|||||
|9, Open Sleeve to Bypass|||||
|10, Orbera|||||
|11, Orbera Placement|||||
|12, Orbera Removal|||||
|13, Port Placement|||||
|14, Port Removal|||||
|15, Port Replacement|||||
|16, Port Revision|||||
|17, Prev Band to Bypass|||||
|18, Prev Band to Sleeve|||||
|19, Prev VBG to Bypass|||||
|21, Single Anastomosis|||||
|22, Sleeve to Bypass|||||
|23, Sleeve to Switch|||||
|24, Stoma Reduction|||||
|25, TORe|||||
|26, Tubing Revision|||||
|27, VBLOC Removal|||||
|28, VBG to Bypass|||||
|999, OTHER|||||
|362|[status_sx_loc]|Surgery Location|radio||
|1, Stony Brook Hospital|||||
|2, Long Island Community Hospital|||||
|3, Southampton Hospital|||||
|4, St. Charles Hospital|||||
|5, Other|||||
|363|[status_sx_loc_other]||||
|Show the field ONLY if:|||||
|[status_sx_loc] = '5'|Surgery Location OTHER|text|||
|364|[sx_endo]|Needs Endo Inpatient|radio||
|0, No|||||
|1, Yes|||||
|365|[status_notes_v2]|Status Notes|notes||
|366|[pt_status_complete]|Complete?|dropdown||
|0, Incomplete|||||
|1, Unverified|||||
|2, Complete|||||

### Surgery

|#|Variable / Field Name|Field Label|Field Attributes (Field Type, Validation, Choices, Calculations, etc.)|_**Notes**_|
|---|---|---|---|---|
|367|[demo_surg]|PT INFO|notes||
|Field Annotation: @SETVALUE='[static_arm_1][mrn] [static_arm_1][last_name], [static_arm_1][first_name] DOB: [static_arm_1][dob] Contact Date: [static_arm_1][contact_date]'|||||
|368|[sx_status]|ACTIVE?:|radio||
|1, YES|||||
|2, NO|||||
|3, N/A|||||
|4, NEW SX|||||
|5, DECEASED|||||
|369|[surgery_date]|Surgery Date|text (date_ymd), Required, Identifier||
|370|[con_to_sx]|Days from Consult to Surgery|calc||
|Calculation: round(datediff([static_arm_1][most_recent_date],[surgery_date],'d','ymd'),2)|||||
|371|[flr]|Floor|text||
|372|[age_tos]|Age at Surgery|calc||
|Calculation: round(datediff([static_arm_1][dob],[surgery_date],"y","ymd"),1)|||||
|373|[surgery_md]|Surgeon|dropdown||
|1, Aurora Pryor|||||
|2, Dino Spaniolas|||||
|3, Sal Docimo|||||
|4, Kinga Powers|||||
|5, Amy Rosenbluth|||||
|6, Andrew Bates|||||
|7, Dana Telem|||||
|8, Edmund Lee|||||
|999, Other|||||
|374|[surgery_md_other]||||
|Show the field ONLY if:[surgery_md]='999'|OTHER Surgeon|text|||
|375|[surgery_type]|Surgery Type|dropdown||
|1, Aborted|||||
|2, Balloon|||||
|3, Band|||||
|4, Bypass|||||
|5, Conversion|||||
|6, Intervention|||||
|7, Reoperation|||||
|8, Revision|||||
|9, Sleeve|||||
|10, Switch|||||
|11, SADI|||||
|376|[primary_sx]|Primary Surgery?|calc||
|Calculation: if([surgery_type]=3,1,if([surgery_type]=4,1,if([surgery_type]=9,1,if([surgery_type]=10,1,if([surgery_type]=11,1,0)))))|||||
|377|[mbsaqip_case]|MBSAQIP Case Description|dropdown||
|1, Biliopancreatic diversion with duodenal switch|||||
|2, Gastric Band Placement|||||
|3, Roux-en-Y gastric bypass|||||
|4, Single anastomosis gastric bypass|||||
|5, Sleeve gastrectomy|||||
|B001, Diagnostic endoscopy|||||
|B002, Intragastric balloon placement|||||
|B003, Intragastric balloon adjustment|||||
|B004, Intragastric balloon removal|||||
|B005, Therapeutic endoscopy with dilation and/or stent placement|||||
|B006, Therapeutic endoscopy with stoma resizing|||||
|B007, Therapeutic endoscopy with gastric plication or oversew (pouch resizing)|||||
|B008, Therapeutic endoscopy with fistula closure|||||
|B009, Therapeutic endoscopy with band removal|||||
|B010, Therapeutic endoscopy with endoscopic gastroplasty|||||
|B011, Endoscopy with percutaneous tube placement (G-tube, J-tube)|||||
|B012, Other intervention (not listed)|||||
|A001, Adjustable gastric band, port, and/or tubing revision|||||
|A002, Adjustable gastric banding over Roux-en-Y bypass|||||
|A003, Biliopancreatic diversion with or without duodenal switch revision|||||
|A004, Biliopancreatic diversion common channel lengthening|||||
|A005, Feeding tube placement (G-tube or J-tube) (laparoscopic or open)|||||
|A006, Gastrectomy|||||
|A007, Gastric pouch or stoma plication or revision|||||
|A008, Gastrointestinal tract repair (involving metabolic or bariatric surgery anatomy)|||||
|A009, Hernia repair (involving metabolic or bariatric surgery anatomy)|||||
|A010, Roux-en-Y gastric bypass revision|||||
|A011, Roux-en-Y limb lengthening|||||
|A012, Single anastomosis duodeno-ileal bypass / Loop duodenal switch|||||
|A013, Sleeve gastrectomy revision (Re-sleeve)|||||
|A014, Takedown or reversal of metabolic or bariatric procedure|||||
|A015, Other abdominal procedure involving metabolic or bariatric anatomy (not listed)|||||
|A016, Other investigational (not listed)|||||
|A017, Other abdominal NOT involving metabolic or bariatric anatomy (not listed)|||||
|A018, Other reoperation (not listed)|||||
|378|[sx_details]|Details|dropdown||
|1, Band Removal|||||
|2, Band to Bypass|||||
|3, Band to Sleeve|||||
|4, Bypass Reversal|||||
|5, Bypass to Sleeve|||||
|6, Dor Fundoplication to Bypass|||||
|7, Obalon Removal|||||
|8, Open Sleeve|||||
|9, Open Sleeve to Bypass|||||
|10, Orbera|||||
|11, Orbera Placement|||||
|12, Orbera Removal|||||
|13, Port Placement|||||
|14, Port Removal|||||
|15, Port Replacement|||||
|16, Port Revision|||||
|17, Prev Band to Bypass|||||
|18, Prev Band to Sleeve|||||
|19, Prev VBG to Bypass|||||
|21, Single Anastomosis|||||
|22, Sleeve to Bypass|||||
|23, Sleeve to Switch|||||
|24, Stoma Reduction|||||
|25, TORe|||||
|26, Tubing Revision|||||
|27, VBLOC Removal|||||
|28, VBG to Bypass|||||
|999, OTHER|||||
|379|[sx_details_other]||||
|Show the field ONLY if:|||||
|[sx_details]='999'|Details - OTHER|notes|||
|380|[sx_robotic]|Robotic?|yesno||
|1, Yes|||||
|0, No|||||
|381|[cpt]|CPT|text||
|Field Annotation: @CHARLIMIT=5|||||
|382|[admit_date]|Admit Date|text (datetime_mdy), Identifier||
|383|[disch_date]|Discharge Date|text (datetime_mdy), Identifier||
|384|[los]|Length of Stay|||
|days|calc||||
|Calculation: rounddown(datediff([admit_date],[disch_date],'d','mdy'),2)|||||
|385|[loc]|Location|dropdown||
|1, Stony Brook Hospital|||||
|2, Long Island Community Hospital|||||
|3, Southampton Hospital|||||
|4, St. Charles Hospital|||||
|5, Other|||||
|386|[loc_other]||||
|Show the field ONLY if:|||||
|[loc]='5'|Location Other:|text|||
|387|[mbsaqip]|Entered Into MBSAQIP|radio||
|0, No|||||
|1, Yes|||||
|2, Pending|||||
|3, N/A|||||
|388|[redcap_30]|Redcap 30D Check-in Sent|dropdown||
|1, SENT|||||
|2, SENT|RESPONDED||||
|8, SENT|NO RESPONSE||||
|9, SENT|NO RESPONSE - NP CALLED||||
|3, SENT|BAD EMAIL; CALL||||
|7, SENT|ABLE TO ASSESS FROM EMR INSTEAD||||
|4, NO EMAIL|NP TO CALL||||
|5, NO EMAIL|NP CAPTURED||||
|6, NO EMAIL|LM||||
|999, N/A|||||
|389|[preop_date]|Preop Date|text (date_mdy), Identifier||
|390|[preop_tbw]|Preop: Total Body Weight|||
|lbs|text (number)||||
|391|[preop_ebw_ml]|Preop: EBW - Metlife|||
|lbs|calc||||
|Calculation: round(([preop_tbw]-[static_arm_1][ibw_ml]),2)|||||
|392|[preop_ebw_25]|Preop: EBW - 25|calc||
|Calculation: round(([preop_tbw]-[static_arm_1][ibw_25]),2)|||||
|393|[preop_bmi]|Preop: BMI|calc||
|Calculation: round(([preop_tbw]*703)/(([static_arm_1][height])^(2)),2)|||||
|394|[d30_seen]|30 Day: Seen|dropdown||
|1, CX|||||
|2, DECEASED|||||
|3, LTF|||||
|4, MISSED|||||
|9, MOVED|||||
|5, N/A|||||
|6, NO|||||
|7, NOS|||||
|8, YES|||||
|395|[d30_captured]|30 Day: Captured|dropdown||
|1, CX|||||
|2, DECEASED|||||
|3, LTF|||||
|4, MISSED|||||
|9, MOVED|||||
|5, N/A|||||
|6, NO|||||
|7, NOS|||||
|10, REFUSED F/U|||||
|8, YES|||||
|396|[d30_date]|30 Day: Date|text (date_mdy), Identifier||
|397|[d30_end]|30 Day: End|text (date_mdy)||
|Field Annotation: @CALCDATE([surgery_date], 30, 'd')|||||
|398|[d30_data_end]|30 Day: Data End|text (date_mdy)||
|Field Annotation: @CALCDATE([surgery_date], 90, 'd')|||||
|399|[d30_tbw]|30 Day: Total Body Weight|||
|lbs|text (number)||||
|400|[d30_tbw_loss]||||
|Show the field ONLY if:|||||
|[d30_tbw]<>''|30 Day: Preop TBW - 30D TBW||||
|lbs|calc||||
|Calculation: if([d30_tbw]<>'',round(([preop_tbw]-[d30_tbw]),2),'')|||||
|401|[d30_tbw_loss_per]||||
|Show the field ONLY if:|||||
|[d30_tbw]<>''|30 Day: Preop TBW - 30D TBW %||||
|%|calc||||
|Calculation: if([d30_tbw]<>'',round(((([preop_tbw]-[d30_tbw])/[preop_tbw])*100),2),'')|||||
|402|[d30_ebw_ml]||||
|Show the field ONLY if:|||||
|[d30_tbw]<>''|30 Day: EBW - Metlife|calc|||
|Calculation: if([d30_tbw]<>'',round(([d30_tbw]-[static_arm_1][ibw_ml]),2),'')|||||
|403|[d30_ebw_ml_loss]||||
|Show the field ONLY if:|||||
|[d30_tbw]<>''|30 Day: % EBW - Metlife Loss from Preop||||
|%|calc||||
|Calculation: if([d30_tbw]<>'',round(((([preop_ebw_ml]-[d30_ebw_ml])/[preop_ebw_ml])*100),2),'')|||||
|404|[d30_ebw_25]||||
|Show the field ONLY if:|||||
|[d30_tbw]<>''|30 Day: EBW - 25|calc|||
|Calculation: if([d30_tbw]<>'',round(([d30_tbw]-[static_arm_1][ibw_25]),2),'')|||||
|405|[d30_ebw_25_loss]||||
|Show the field ONLY if:|||||
|[d30_tbw]<>''|30 Day: % EBW - 25 Loss from Preop||||
|%|calc||||
|Calculation: if([d30_tbw]<>'',round(((([preop_ebw_25]-[d30_ebw_25])/[preop_ebw_25])*100),2),'')|||||
|406|[d30_bmi]Show the field ONLY if:[d30_tbw]<>''|30 Day: BMI|calc||
|Calculation: if([d30_tbw]<>'',round(([d30_tbw]*703)/(([static_arm_1][height])^(2)),2),'')|||||
|407|[m6_start]|6 Month: Start|text (date_mdy)||
|Field Annotation: @CALCDATE([surgery_date], 1, 'M')|||||
|408|[m6_captured]|6 Month: Captured|dropdown||
|1, CX|||||
|2, DECEASED|||||
|3, LTF|||||
|4, MISSED|||||
|9, MOVED|||||
|5, N/A|||||
|11, NEW SX|||||
|6, NO|||||
|7, NOS|||||
|10, REFUSING F/U|||||
|12, F/U PCP INSTEAD|||||
|8, YES|||||
|409|[m6_call]|6 Month: Call|yesno||
|1, Yes|||||
|0, No|||||
|410|[m6_ltr]|6 Month: Letter/Email|yesno||
|1, Yes|||||
|0, No|||||
|411|[m6_date]|6 Month: Date|text (date_mdy), Identifier||
|412|[m6_end]|6 Month: End|text (date_mdy)||
|Field Annotation: @CALCDATE([surgery_date], 272.75, 'd')|||||
|413|[m6_data_end]|6 Month: Data End|text (date_mdy)||
|Field Annotation: @CALCDATE([surgery_date], 305.167, 'd')|||||
|414|[m6_tbw]|6 Month: Total Body Weight|||
|lbs|text||||
|415|[m6_tbw_loss]||||
|Show the field ONLY if:|||||
|[m6_tbw]<>''|6 Month: Preop TBW - 6M TBW||||
|lbs|calc||||
|Calculation: if([m6_tbw]<>'',round((([preop_tbw]-[m6_tbw])),2),'')|||||
|416|[m6_tbw_loss_per]||||
|Show the field ONLY if:|||||
|[m6_tbw]<>''|6 Month: Preop TBW - 6M TBW %||||
|%|calc||||
|Calculation: if([m6_tbw]<>'',round(((([preop_tbw]-[m6_tbw])/[preop_tbw])*100),2),'')|||||
|417|[m6_tbw_loss_prev]||||
|Show the field ONLY if:|||||
|[m6_tbw]<>''|6 Month: 30D TBW - 6M TBW||||
|lbs|calc||||
|Calculation: if([m6_tbw]<>'' AND [d30_tbw]<>'',round((([d30_tbw]-[m6_tbw])),2),'')|||||
|418|[m6_ebw_ml]||||
|Show the field ONLY if:|||||
|[m6_tbw]<>''|6 Month: EBW - Metlife|calc|||
|Calculation: if([m6_tbw]<>'',round(([m6_tbw]-[static_arm_1][ibw_ml]),2),'')|||||
|419|[m6_ebw_ml_loss]||||
|Show the field ONLY if:[m6_tbw]<>''|6 Month: % EBW - Metlife Loss from Preop||||
|%|calc||||
|Calculation: if([m6_tbw]<>'',round(((([preop_ebw_ml]-[m6_ebw_ml])/[preop_ebw_ml])*100),2),'')|||||
|420|[m6_ebw_25]||||
|Show the field ONLY if:[m6_tbw]<>''|6 Month: EBW - 25|calc|||
|Calculation: if([m6_tbw]<>'',round(([m6_tbw]-[static_arm_1][ibw_25]),2),'')|||||
|421|[m6_ebw_25_loss]||||
|Show the field ONLY if:|||||
|[m6_tbw]<>''|6 Month: % EBW - 25 Loss from Preop||||
|%|calc||||
|Calculation: if([m6_tbw]<>'',round(((([preop_ebw_25]-[m6_ebw_25])/[preop_ebw_25])*100),2),'')|||||
|422|[m6_bmi]||||
|Show the field ONLY if:|||||
|[m6_tbw]<>''|6 Month: BMI|calc|||
|Calculation: if([m6_tbw]<>'',round(([m6_tbw]*703)/(([static_arm_1][height])^(2)),2),'')|||||
|423|[m6_diabetes]||||
|Show the field ONLY if:|||||
|[m6_date]<>''|6 Month: Diabetes|dropdown|||
|1, Yes, non-insulin|||||
|2, Yes, insulin|||||
|3, No|||||
|424|[m6_gerd]||||
|Show the field ONLY if:|||||
|[m6_date]<>''|6 Month: GERD|yesno|||
|1, Yes|||||
|0, No|||||
|425|[m6_hld]||||
|Show the field ONLY if:|||||
|[m6_date]<>''|6 Month: Hyperlipidemia|yesno|||
|1, Yes|||||
|0, No|||||
|426|[m6_htn]||||
|Show the field ONLY if:|||||
|[m6_date]<>''|6 Month: Hypertension|yesno|||
|1, Yes|||||
|0, No|||||
|427|[m6_htn_meds]||||
|Show the field ONLY if:|||||
|[m6_htn]='1'|6 Month: Number of Anti-Hypertensive Medications|radio|||
|1, 1|||||
|2, 2|||||
|3, 3 or more|||||
|428|[m6_osa]||||
|Show the field ONLY if:|||||
|[m6_date]<>''|6 Month: Sleep Apnea|yesno|||
|1, Yes|||||
|0, No|||||
|429|[y1_start]|1 Year: Start|text (date_mdy)||
|Field Annotation: @CALCDATE([surgery_date], 9, 'M')|||||
|430|[y1_captured]|1 Year: Captured|dropdown||
|1, CX|||||
|2, DECEASED|||||
|3, LTF|||||
|4, MISSED|||||
|9, MOVED|||||
|5, N/A|||||
|11, NEW SX|||||
|6, NO|||||
|7, NOS|||||
|10, REFUSING F/U|||||
|12, F/U PCP INSTEAD|||||
|8, YES|||||
|431|[y1_call]|1 Year: Call|yesno||
|1, Yes|||||
|0, No|||||
|432|[y1_ltr]|1 Year: Letter/Email|yesno||
|1, Yes|||||
|0, No|||||
|433|[y1_date]|1 Year Date|text (date_mdy), Identifier||
|434|[y1_end]|1 Year: End|text (date_mdy)||
|Field Annotation: @CALCDATE([surgery_date], 546.501, 'd')|||||
|435|[y1_data_end]|1 Year: Data End|text (date_mdy)||
|Field Annotation: @CALCDATE([surgery_date], 578.917, 'd')|||||
|436|[y1_tbw]|1 Year: Total Body Weight|||
|lbs|text (number)||||
|437|[y1_tbw_loss]||||
|Show the field ONLY if:[y1_tbw]<>''|1 Year: Preop TBW - 1Y TBW||||
|lbs|calc||||
|Calculation: if([y1_tbw]<>'',round((([preop_tbw]-[y1_tbw])),2),'')|||||
|438|[y1_tbw_loss_per]||||
|Show the field ONLY if:|||||
|[y1_tbw]<>''|1 Year: Preop TBW - 1Y TBW %||||
|%|calc||||
|Calculation: if([y1_tbw]<>'',round(((([preop_tbw]-[y1_tbw])/[preop_tbw])*100),2),'')|||||
|439|[y1_tbw_loss_prev]||||
|Show the field ONLY if:|||||
|[y1_tbw]<>''|1 Year: 6M TBW - 1Y TBW||||
|lbs|calc||||
|Calculation: if([y1_tbw]<>'' AND [m6_tbw]<>'',round((([m6_tbw]-[y1_tbw])),2),'')|||||
|440|[y1_ebw_ml]||||
|Show the field ONLY if:|||||
|[y1_tbw]<>''|1 Year: EBW - Metlife|calc|||
|Calculation: if([y1_tbw]<>'',round(([y1_tbw]-[static_arm_1][ibw_ml]),2),'')|||||
|441|[y1_ebw_ml_loss]||||
|Show the field ONLY if:|||||
|[y1_tbw]<>''|1 Year: % EBW - Metlife Loss from Preop||||
|%|calc||||
|Calculation: if([y1_tbw]<>'',round(((([preop_ebw_ml]-[y1_ebw_ml])/[preop_ebw_ml])*100),2),'')|||||
|442|[y1_ebw_25]||||
|Show the field ONLY if:|||||
|[y1_tbw]<>''|1 Year: EBW - 25|calc|||
|Calculation: if([y1_tbw]<>'',round(([y1_tbw]-[static_arm_1][ibw_25]),2),'')|||||
|443|[y1_ebw_25_loss]||||
|Show the field ONLY if:[y1_tbw]<>''|1 Year: % EBW - 25 Loss from Preop||||
|%|calc||||
|Calculation: if([y1_tbw]<>'',round(((([preop_ebw_25]-[y1_ebw_25])/[preop_ebw_25])*100),2),'')|||||
|444|[y1_bmi]||||
|Show the field ONLY if:|||||
|[y1_tbw]<>''|1 Year: BMI|calc|||
|Calculation: if([y1_tbw]<>'',round(([y1_tbw]*703)/(([static_arm_1][height])^(2)),2),'')|||||
|445|[y1_diabetes]||||
|Show the field ONLY if:|||||
|[y1_date]<>''|1 Year: Diabetes|dropdown|||
|1, Yes, non-insulin|||||
|2, Yes, insulin|||||
|3, No|||||
|446|[y1_gerd]||||
|Show the field ONLY if:|||||
|[y1_date]<>''|1 Year: GERD|yesno|||
|1, Yes|||||
|0, No|||||
|447|[y1_hld]||||
|Show the field ONLY if:|||||
|[y1_date]<>''|1 Year: Hyperlipidemia|yesno|||
|1, Yes|||||
|0, No|||||
|448|[y1_htn]||||
|Show the field ONLY if:|||||
|[y1_date]<>''|1 Year: Hypertension|yesno|||
|1, Yes|||||
|0, No|||||
|449|[y1_htn_meds]||||
|Show the field ONLY if:|||||
|[y1_htn]='1'|1 Year: Number of Anti-Hypertensive Medications|radio|||
|1, 1|||||
|2, 2|||||
|3, 3 or more|||||
|450|[y1_osa]||||
|Show the field ONLY if:|||||
|[y1_date]<>''|1 Year: Sleep Apnea|yesno|||
|1, Yes|||||
|0, No|||||
|451|[y2_start]|2 Year: Start|text (date_mdy)||
|Field Annotation: @CALCDATE([surgery_date], 18, 'M')|||||
|452|[y2_captured]|2 Year: Captured|dropdown||
|1, CX|||||
|2, DECEASED|||||
|3, LTF|||||
|4, MISSED|||||
|9, MOVED|||||
|5, N/A|||||
|11, NEW SX|||||
|6, NO|||||
|7, NOS|||||
|10, REFUSING F/U|||||
|12, F/U PCP INSTEAD|||||
|8, YES|||||
|453|[y2_call]|2 Year: Call|yesno||
|1, Yes|||||
|0, No|||||
|454|[y2_ltr]|2 Year: Letter/Email|yesno||
|1, Yes|||||
|0, No|||||
|455|[y2_date]|2 Year Date|text (date_mdy), Identifier||
|456|[y2_end]|2 Year: End|text (date_mdy)||
|Field Annotation: @CALCDATE([surgery_date], 911.501, 'd')|||||
|457|[y2_data_end]|2 Year: Data End|text (date_mdy)||
|Field Annotation: @CALCDATE([surgery_date], 943.918, 'd')|||||
|458|[y2_tbw]|2 Year: Total Body Weight|||
|lbs|text (number)||||
|459|[y2_tbw_loss]||||
|Show the field ONLY if:|||||
|[y2_tbw]<>''|2 Year: Preop TBW - 2Y TBW||||
|lbs|calc||||
|Calculation: if([y2_tbw]<>'',round((([preop_tbw]-[y2_tbw])),2),'')|||||
|460|[y2_tbw_loss_per]||||
|Show the field ONLY if:|||||
|[y2_tbw]<>''|2 Year: Preop TBW - 2Y TBW %||||
|%|calc||||
|Calculation: if([y2_tbw]<>'',round(((([preop_tbw]-[y2_tbw])/[preop_tbw])*100),2),'')|||||
|461|[y2_tbw_loss_prev]||||
|Show the field ONLY if:|||||
|[y2_tbw]<>''|2 Year: 1Y TBW - 2Y TBW||||
|lbs|calc||||
|Calculation: if([y2_tbw]<>'' AND [y1_tbw]<>'',round((([y1_tbw]-[y2_tbw])),2),'')|||||
|462|[y2_ebw_ml]||||
|Show the field ONLY if:[y2_tbw]<>''|2 Year: EBW - Metlife|calc|||
|Calculation: if([y2_tbw]<>'',round(([y2_tbw]-[static_arm_1][ibw_ml]),2),'')|||||
|463|[y2_ebw_ml_loss]||||
|Show the field ONLY if:[y2_tbw]<>''|2 Year: % EBW - Metlife Loss from Preop||||
|%|calc||||
|Calculation: if([y2_tbw]<>'',round(((([preop_ebw_ml]-[y2_ebw_ml])/[preop_ebw_ml])*100),2),'')|||||
|464|[y2_ebw_25]||||
|Show the field ONLY if:[y2_tbw]<>''|2 Year: EBW - 25|calc|||
|Calculation: if([y2_tbw]<>'',round(([y2_tbw]-[static_arm_1][ibw_25]),2),'')|||||
|465|[y2_ebw_25_loss]||||
|Show the field ONLY if:[y2_tbw]<>''|2 Year: % EBW - 25 Loss from Preop||||
|%|calc||||
|Calculation: if([y2_tbw]<>'',round(((([preop_ebw_25]-[y2_ebw_25])/[preop_ebw_25])*100),2),'')|||||
|466|[y2_bmi]||||
|Show the field ONLY if:[y2_tbw]<>''|2 Year: BMI|calc|||
|Calculation: if([y2_tbw]<>'',round(([y2_tbw]*703)/(([static_arm_1][height])^(2)),2),'')|||||
|467|[y2_diabetes]||||
|Show the field ONLY if:[y2_date]<>''|2 Year: Diabetes|dropdown|||
|1, Yes, non-insulin|||||
|2, Yes, insulin|||||
|3, No|||||
|468|[y2_gerd]||||
|Show the field ONLY if:[y2_date]<>''|2 Year: GERD|yesno|||
|1, Yes|||||
|0, No|||||
|469|[y2_hld]||||
|Show the field ONLY if:[y2_date]<>''|2 Year: Hyperlipidemia|yesno|||
|1, Yes|||||
|0, No|||||
|470|[y2_htn]||||
|Show the field ONLY if:[y2_date]<>''|2 Year: Hypertension|yesno|||
|1, Yes|||||
|0, No|||||
|471|[y2_htn_meds]||||
|Show the field ONLY if:[y2_htn]='1'|2 Year: Number of Anti-Hypertensive Medications|radio|||
|1, 1|||||
|2, 2|||||
|3, 3 or more|||||
|472|[y2_osa]||||
|Show the field ONLY if:[y2_date]<>''|2 Year: Sleep Apnea|yesno|||
|1, Yes|||||
|0, No|||||
|473|[y3_start]|3 Year: Start|text (date_mdy)||
|Field Annotation: @CALCDATE([surgery_date], 30, 'M')|||||
|474|[y3_captured]|3 Year: Captured|dropdown||
|1, CX|||||
|2, DECEASED|||||
|3, LTF|||||
|4, MISSED|||||
|9, MOVED|||||
|5, N/A|||||
|11, NEW SX|||||
|6, NO|||||
|7, NOS|||||
|10, REFUSING F/U|||||
|12, F/U PCP INSTEAD|||||
|8, YES|||||
|475|[y3_call]|3 Year: Call|yesno||
|1, Yes|||||
|0, No|||||
|476|[y3_ltr]|3 Year: Letter/Email|yesno||
|1, Yes|||||
|0, No|||||
|477|[y3_date]|3 Year Date|text (date_mdy), Identifier||
|478|[y3_end]|3 Year: End|text (date_mdy)||
|Field Annotation: @CALCDATE([surgery_date], 1276.5, 'd')|||||
|479|[y3_data_end]|3 Year: Data End|text (date_mdy)||
|Field Annotation: @CALCDATE([surgery_date], 1306.92, 'd')|||||
|480|[y3_tbw]|3 Year: Total Body Weight|||
|lbs|text (number)||||
|481|[y3_tbw_loss]||||
|Show the field ONLY if:[y3_tbw]<>''|3 Year: Preop TBW - 3Y TBW||||
|lbs|calc||||
|Calculation: if([y3_tbw]<>'',round((([preop_tbw]-[y3_tbw])),2),'')|||||
|482|[y3_tbw_loss_per]||||
|Show the field ONLY if:[y3_tbw]<>''|3 Year: Preop TBW - 3Y TBW %||||
|%|calc||||
|Calculation: if([y3_tbw]<>'',round(((([preop_tbw]-[y3_tbw])/[preop_tbw])*100),2),'')|||||
|483|[y3_tbw_loss_prev]||||
|Show the field ONLY if:[y3_tbw]<>''|3 Year: 2Y TBW - 3Y TBW||||
|lbs|calc||||
|Calculation: if([y3_tbw]<>'' AND [y2_tbw]<>'',round((([y2_tbw]-[y3_tbw])),2),'')|||||
|484|[y3_ebw_ml]||||
|Show the field ONLY if:[y3_tbw]<>''|3 Year: EBW - Metlife|calc|||
|Calculation: if([y3_tbw]<>'',round(([y3_tbw]-[static_arm_1][ibw_ml]),2),'')|||||
|485|[y3_ebw_ml_loss]||||
|Show the field ONLY if:[y3_tbw]<>''|3 Year: % EBW - Metlife Loss from Preop||||
|%|calc||||
|Calculation: if([y3_tbw]<>'',round(((([preop_ebw_ml]-[y3_ebw_ml])/[preop_ebw_ml])*100),2),'')|||||
|486|[y3_ebw_25]||||
|Show the field ONLY if:[y3_tbw]<>''|3 Year: EBW - 25|calc|||
|Calculation: if([y3_tbw]<>'',round(([y3_tbw]-[static_arm_1][ibw_25]),2),'')|||||
|487|[y3_ebw_25_loss]||||
|Show the field ONLY if:[y3_tbw]<>''|3 Year: % EBW - 25 Loss from Preop||||
|%|calc||||
|Calculation: if([y3_tbw]<>'',round(((([preop_ebw_25]-[y3_ebw_25])/[preop_ebw_25])*100),2),'')|||||
|488|[y3_bmi]||||
|Show the field ONLY if:[y3_tbw]<>''|3 Year: BMI|calc|||
|Calculation: if([y3_tbw]<>'',round(([y3_tbw]*703)/(([static_arm_1][height])^(2)),2),'')|||||
|489|[y3_diabetes]Show the field ONLY if:[y3_date]<>''|3 Year: Diabetes|dropdown||
|1, Yes, non-insulin|||||
|2, Yes, insulin|||||
|3, No|||||
|490|[y3_gerd]Show the field ONLY if:[y3_date]<>''|3 Year: GERD|yesno||
|1, Yes|||||
|0, No|||||
|491|[y3_hld]Show the field ONLY if:[y3_date]<>''|3 Year: Hyperlipidemia|yesno||
|1, Yes|||||
|0, No|||||
|492|[y3_htn]Show the field ONLY if:[y3_date]<>''|3 Year: Hypertension|yesno||
|1, Yes|||||
|0, No|||||
|493|[y3_htn_meds]Show the field ONLY if:[y3_htn]='1'|3 Year: Number of Anti-Hypertensive Medications|radio||
|1, 1|||||
|2, 2|||||
|3, 3 or more|||||
|494|[y3_osa]Show the field ONLY if:[y3_date]<>''|3 Year: Sleep Apnea|yesno||
|1, Yes|||||
|0, No|||||
|495|[y4_start]|4 Year: Start|text (date_mdy)||
|Field Annotation: @CALCDATE([surgery_date], 42, 'M')|||||
|496|[y4_captured]|4 Year: Captured|dropdown||
|1, CX|||||
|2, DECEASED|||||
|3, LTF|||||
|4, MISSED|||||
|9, MOVED|||||
|5, N/A|||||
|11, NEW SX|||||
|6, NO|||||
|7, NOS|||||
|10, REFUSING F/U|||||
|12, F/U PCP INSTEAD|||||
|8, YES|||||
|497|[y4_call]|4 Year: Call|yesno||
|1, Yes|||||
|0, No|||||
|498|[y4_ltr]|4 Year: Letter/Email|yesno||
|1, Yes|||||
|0, No|||||
|499|[y4_date]|4 Year Date|text (date_mdy), Identifier||
|500|[y4_end]|4 Year: End|text (date_mdy)||
|Field Annotation: @CALCDATE([surgery_date], 1641.5, 'd')|||||
|501|[y4_data_end]|4 Year: Data End|text (date_mdy)||
|Field Annotation: @CALCDATE([surgery_date], 1671.92, 'd')|||||
|502|[y4_tbw]|4 Year: Total Body Weight|||
|lbs|text (number)||||
|503|y4_tbw_loss]||||
|Show the field ONLY if:[y4_tbw]<>''|4 Year: Preop TBW - 4Y TBW||||
|lbs|calc||||
|Calculation: if([y4_tbw]<>'',round((([preop_tbw]-[y4_tbw])),2),'')|||||
|504|[y4_tbw_loss_per]||||
|Show the field ONLY if:[y4_tbw]<>''|4 Year: Preop TBW - 4Y TBW %||||
|%|calc||||
|Calculation: if([y4_tbw]<>'',round(((([preop_tbw]-[y4_tbw])/[preop_tbw])*100),2),'')|||||
|505|[y4_tbw_loss_prev]||||
|Show the field ONLY if:[y4_tbw]<>''|4 Year: 3Y TBW - 4Y TBW||||
|lbs|calc||||
|Calculation: if([y4_tbw]<>'' AND [y3_tbw]<>'',round((([y3_tbw]-[y4_tbw])),2),'')|||||
|506|[y4_ebw_ml]||||
|Show the field ONLY if:[y4_tbw]<>''|4 Year: EBW - Metlife|calc|||
|Calculation: if([y4_tbw]<>'',round(([y4_tbw]-[static_arm_1][ibw_ml]),2),'')|||||
|507|[y4_ebw_ml_loss]||||
|Show the field ONLY if:[y4_tbw]<>''|4 Year: % EBW - Metlife Loss from Preop||||
|%|calc||||
|Calculation: if([y4_tbw]<>'',round(((([preop_ebw_ml]-[y4_ebw_ml])/[preop_ebw_ml])*100),2),'')|||||
|508|[y4_ebw_25]||||
|Show the field ONLY if:[y4_tbw]<>''|4 Year: EBW - 25|calc|||
|Calculation: if([y4_tbw]<>'',round(([y4_tbw]-[static_arm_1][ibw_25]),2),'')|||||
|509|[y4_ebw_25_loss]||||
|Show the field ONLY if:[y4_tbw]<>''|4 Year: % EBW - 25 Loss from Preop||||
|%|calc||||
|Calculation: if([y4_tbw]<>'',round(((([preop_ebw_25]-[y4_ebw_25])/[preop_ebw_25])*100),2),'')|||||
|510|[y4_bmi]||||
|Show the field ONLY if:[y4_tbw]<>''|4 Year: BMI|calc|||
|Calculation: if([y4_tbw]<>'',round(([y4_tbw]*703)/(([static_arm_1][height])^(2)),2),'')|||||
|511|[y4_diabetes]||||
|Show the field ONLY if:[y4_date]<>''|4 Year: Diabetes|dropdown|||
|1, Yes, non-insulin|||||
|2, Yes, insulin|||||
|3, No|||||
|512|[y4_gerd]||||
|Show the field ONLY if:[y4_date]<>''|4 Year: GERD|yesno|||
|1, Yes|||||
|0, No|||||
|513|[y4_hld]||||
|Show the field ONLY if:[y4_date]<>''|4 Year: Hyperlipidemia|yesno|||
|1, Yes|||||
|0, No|||||
|514|[y4_htn]||||
|Show the field ONLY if:[y4_date]<>''|4 Year: Hypertension|yesno|||
|1, Yes|||||
|0, No|||||
|515|[y4_htn_meds]||||
|Show the field ONLY if:[y4_htn]='1'|4 Year: Number of Anti-Hypertensive Medications|radio|||
|1, 1|||||
|2, 2|||||
|3, 3 or more|||||
|516|[y4_osa]||||
|Show the field ONLY if:[y4_date]<>''|4 Year: Sleep Apnea|yesno|||
|1, Yes|||||
|0, No|||||
|517|[y5_start]|5 Year: Start|text (date_mdy)||
|Field Annotation: @CALCDATE([surgery_date], 54, 'M')|||||
|518|[y5_captured]|5 Year: Captured|dropdown||
|1, CX|||||
|2, DECEASED|||||
|3, LTF|||||
|4, MISSED|||||
|9, MOVED|||||
|5, N/A|||||
|11, NEW SX|||||
|6, NO|||||
|7, NOS|||||
|10, REFUSING F/U|||||
|12, F/U PCP INSTEAD|||||
|8, YES|||||
|519|[y5_call]|5 Year: Call|yesno||
|1, Yes|||||
|0, No|||||
|520|[y5_ltr]|5 Year: Letter/Email|yesno||
|1, Yes|||||
|0, No|||||
|521|[y5_date]|5 Year Date|text (date_mdy), Identifier||
|522|[y5_end]|5 Year: End|text (date_mdy)||
|Field Annotation: @CALCDATE([surgery_date], 2006.5, 'd')|||||
|523|[y5_data_end]|5 Year: Data End|text (date_mdy)Field Annotation: @CALCDATE([surgery_date], 2036.92, 'd')||
|524|[y5_tbw]|5 Year: Total Body Weight|||
|lbs|text (number)||||
|525|[y5_tbw_loss]||||
|Show the field ONLY if:[y5_tbw]<>''|5 Year: Preop TBW - 5Y TBW||||
|lbs|calc||||
|Calculation: if([y5_tbw]<>'',round((([preop_tbw]-[y5_tbw])),2),'')|||||
|526|[y5_tbw_loss_per]||||
|Show the field ONLY if:[y5_tbw]<>''|5 Year: Preop TBW - 5Y TBW %||||
|%|calc||||
|Calculation: if([y5_tbw]<>'',round(((([preop_tbw]-[y5_tbw])/[preop_tbw])*100),2),'')|||||
|527|[y5_tbw_loss_prev]||||
|Show the field ONLY if:[y5_tbw]<>''|5 Year: 4Y TBW - 5Y TBW||||
|lbs|calc||||
|Calculation: if([y5_tbw]<>'' AND [y4_tbw]<>'',round((([y4_tbw]-[y5_tbw])),2),'')|||||
|528|[y5_ebw_ml]||||
|Show the field ONLY if:[y5_tbw]<>''|5 Year: EBW - Metlife|calc|||
|Calculation: if([y5_tbw]<>'',round(([y5_tbw]-[static_arm_1][ibw_ml]),2),'')|||||
|529|[y5_ebw_ml_loss]||||
|Show the field ONLY if:[y5_tbw]<>''|5 Year: % EBW - Metlife Loss from Preop||||
|%|calc||||
|Calculation: if([y5_tbw]<>'',round(((([preop_ebw_ml]-[y5_ebw_ml])/[preop_ebw_ml])*100),2),'')|||||
|530|[y5_ebw_25]||||
|Show the field ONLY if:[y5_tbw]<>''|5 Year: EBW - 25|calc|||
|Calculation: if([y5_tbw]<>'',round(([y5_tbw]-[static_arm_1][ibw_25]),2),'')|||||
|531|[y5_ebw_25_loss]||||
|Show the field ONLY if:[y5_tbw]<>''|5 Year: % EBW - 25 Loss from Preop||||
|%|calc||||
|Calculation: if([y5_tbw]<>'',round(((([preop_ebw_25]-[y5_ebw_25])/[preop_ebw_25])*100),2),'')|||||
|532|[y5_bmi]||||
|Show the field ONLY if:[y5_tbw]<>''|5 Year: BMI|calc|||
|Calculation: if([y5_tbw]<>'',round(([y5_tbw]*703)/(([static_arm_1][height])^(2)),2),'')|||||
|533|[y5_diabetes]Show the field ONLY if:[y5_date]<>''|5 Year: Diabetes|dropdown||
|1, Yes, non-insulin|||||
|2, Yes, insulin|||||
|3, No|||||
|534|[y5_gerd]Show the field ONLY if:[y5_date]<>''|5 Year: GERD|yesno||
|1, Yes|||||
|0, No|||||
|535|[y5_hld]Show the field ONLY if:[y5_date]<>''|5 Year: Hyperlipidemia|yesno||
|1, Yes|||||
|0, No|||||
|536|[y5_htn]Show the field ONLY if:[y5_date]<>''|5 Year: Hypertension|yesno||
|1, Yes|||||
|0, No|||||
|537|[y5_htn_meds]Show the field ONLY if:[y5_htn]='1'|5 Year: Number of Anti-Hypertensive Medications|radio||
|1, 1|||||
|2, 2|||||
|3, 3 or more|||||
|538|[y5_osa]Show the field ONLY if:[y5_date]<>''|5 Year: Sleep Apnea|yesno||
|1, Yes|||||
|0, No|||||
|539|[y6_start]|Section Header: Year 66 Year: Start|text (date_mdy)||
|Field Annotation: @CALCDATE([surgery_date], 66, 'M')|||||
|540|[y6_captured]|6 Year: Captured|dropdown||
|1, CX|||||
|2, DECEASED|||||
|3, LTF|||||
|4, MISSED|||||
|9, MOVED|||||
|5, N/A|||||
|11, NEW SX|||||
|6, NO|||||
|7, NOS|||||
|10, REFUSING F/U|||||
|12, F/U PCP INSTEAD|||||
|8, YES|||||
|541|[y6_call]|6 Year: Call|yesno||
|1, Yes|||||
|0, No|||||
|542|[y6_ltr]|6 Year: Letter/Email|yesno||
|1, Yes|||||
|0, No|||||
|543|[y6_date]|6 Year Date|text (date_mdy), Identifier||
|544|[y6_end]|6 Year: End|text (date_mdy)||
|Field Annotation: @CALCDATE([surgery_date], 2371.5, 'd')|||||
|545|[y6_data_end]|6 Year: Data End|text (date_mdy)||
|Field Annotation: @CALCDATE([surgery_date], 2401.92, 'd')|||||
|546|[y6_tbw]|6 Year: Total Body Weight|||
|lbs|text (number)||||
|547|[y6_tbw_loss]||||
|Show the field ONLY if:[y6_tbw]<>''|6 Year: Preop TBW - 6Y TBW||||
|lbs|calc||||
|Calculation: if([y6_tbw]<>'',round((([preop_tbw]-[y6_tbw])),2),'')|||||
|548|[y6_tbw_loss_per]||||
|Show the field ONLY if:[y6_tbw]<>''|6 Year: Preop TBW - 6Y TBW %||||
|%|calc||||
|Calculation: if([y6_tbw]<>'',round(((([preop_tbw]-[y6_tbw])/[preop_tbw])*100),2),'')|||||
|549|[y6_tbw_loss_prev]||||
|Show the field ONLY if:[y6_tbw]<>''|6 Year: 5Y TBW - 6Y TBW||||
|lbs|calc||||
|Calculation: if([y6_tbw]<>'' AND [y5_tbw]<>'',round((([y5_tbw]-[y6_tbw])),2),'')|||||
|550|[y6_ebw_ml]||||
|Show the field ONLY if:[y6_tbw]<>''|6 Year: EBW - Metlife|calc|||
|Calculation: if([y6_tbw]<>'',round(([y6_tbw]-[static_arm_1][ibw_ml]),2),'')|||||
|551|[y6_ebw_ml_loss]||||
|Show the field ONLY if:[y6_tbw]<>''|6 Year: % EBW - Metlife Loss from Preop||||
|%|calc||||
|Calculation: if([y6_tbw]<>'',round(((([preop_ebw_ml]-[y6_ebw_ml])/[preop_ebw_ml])*100),2),'')|||||
|552|[y6_ebw_25]||||
|Show the field ONLY if:[y6_tbw]<>''|6 Year: EBW - 25|calc|||
|Calculation: if([y6_tbw]<>'',round(([y6_tbw]-[static_arm_1][ibw_25]),2),'')|||||
|553|[y6_ebw_25_loss]||||
|Show the field ONLY if:[y6_tbw]<>''|6 Year: % EBW - 25 Loss from Preop||||
|%|calc||||
|Calculation: if([y6_tbw]<>'',round(((([preop_ebw_25]-[y6_ebw_25])/[preop_ebw_25])*100),2),'')|||||
|554|[y6_bmi]||||
|Show the field ONLY if:[y6_tbw]<>''|6 Year: BMI|calc|||
|Calculation: if([y6_tbw]<>'',round(([y6_tbw]*703)/(([static_arm_1][height])^(2)),2),'')|||||
|555|[y6_diabetes]||||
|Show the field ONLY if:[y6_date]<>''|6 Year: Diabetes|dropdown|||
|1, Yes, non-insulin|||||
|2, Yes, insulin|||||
|3, No|||||
|556|[y6_gerd]||||
|Show the field ONLY if:[y6_date]<>''|6 Year: GERD|yesno|||
|1, Yes|||||
|0, No|||||
|557|[y6_hld]||||
|Show the field ONLY if:[y6_date]<>''|6 Year: Hyperlipidemia|yesno|||
|1, Yes|||||
|0, No|||||
|558|[y6_htn]||||
|Show the field ONLY if:[y6_date]<>''|6 Year: Hypertension|yesno|||
|1, Yes|||||
|0, No|||||
|559|[y6_htn_meds]||||
|Show the field ONLY if:[y6_htn]='1'|6 Year: Number of Anti-Hypertensive Medications|radio|||
|1, 1|||||
|2, 2|||||
|3, 3 or more|||||
|560|[y6_osa]||||
|Show the field ONLY if:[y6_date]<>''|6 Year: Sleep Apnea|yesno|||
|1, Yes|||||
|0, No|||||
|561|[y7_start]|7 Year: Start|text (date_mdy)||
|Field Annotation: @CALCDATE([surgery_date], 78, 'M')|||||
|562|[y7_captured]|7 Year: Captured|dropdown||
|1, CX|||||
|2, DECEASED|||||
|3, LTF|||||
|4, MISSED|||||
|9, MOVED|||||
|5, N/A|||||
|11, NEW SX|||||
|6, NO|||||
|7, NOS|||||
|10, REFUSING F/U|||||
|12, F/U PCP INSTEAD|||||
|8, YES|||||
|563|[y7_call]|7 Year: Call|yesno||
|1, Yes|||||
|0, No|||||
|564|[y7_ltr]|7 Year: Letter/Email|yesno||
|1, Yes|||||
|0, No|||||
|565|[y7_date]|7 Year Date|text (date_mdy), Identifier||
|566|[y7_end]|7 Year: End|text (date_mdy)||
|Field Annotation: @CALCDATE([surgery_date], 2736.5, 'd')|||||
|567|[y7_data_end]|7 Year: Data End|text (date_mdy)||
|Field Annotation: @CALCDATE([surgery_date], 2766.92, 'd')|||||
|568|[y7_tbw]|7 Year: Total Body Weight|||
|lbs|text (number)||||
|569|[y7_tbw_loss]||||
|Show the field ONLY if:[y7_tbw]<>''|7 Year: Preop TBW - 7Y TBW||||
|lbs|calc||||
|Calculation: if([y7_tbw]<>'',round((([preop_tbw]-[y7_tbw])),2),'')|||||
|570|[y7_tbw_loss_per]||||
|Show the field ONLY if:[y7_tbw]<>''|7 Year: Preop TBW - 7Y TBW %||||
|%|calc||||
|Calculation: if([y7_tbw]<>'',round(((([preop_tbw]-[y7_tbw])/[preop_tbw])*100),2),'')|||||
|571|[y7_tbw_loss_prev]||||
|Show the field ONLY if:[y7_tbw]<>''|7 Year: 6Y TBW - 7Y TBW||||
|lbs|calc||||
|Calculation: if([y7_tbw]<>'' AND [y6_tbw]<>'',round((([y6_tbw]-[y7_tbw])),2),'')|||||
|572|[y7_ebw_ml]||||
|Show the field ONLY if:[y7_tbw]<>''|7 Year: EBW - Metlife|calc|||
|Calculation: if([y7_tbw]<>'',round(([y7_tbw]-[static_arm_1][ibw_ml]),2),'')|||||
|573|[y7_ebw_ml_loss]||||
|Show the field ONLY if:[y7_tbw]<>''|7 Year: % EBW - Metlife Loss from Preop||||
|%|calc||||
|Calculation: if([y7_tbw]<>'',round(((([preop_ebw_ml]-[y7_ebw_ml])/[preop_ebw_ml])*100),2),'')|||||
|574|[y7_ebw_25]||||
|Show the field ONLY if:[y7_tbw]<>''|7 Year: EBW - 25|calc|||
|Calculation: if([y7_tbw]<>'',round(([y7_tbw]-[static_arm_1][ibw_25]),2),'')|||||
|575|[y7_ebw_25_loss]||||
|Show the field ONLY if:[y7_tbw]<>''|7 Year: % EBW - 25 Loss from Preop||||
|%|calc||||
|Calculation: if([y7_tbw]<>'',round(((([preop_ebw_25]-[y7_ebw_25])/[preop_ebw_25])*100),2),'')|||||
|576|[y7_bmi]||||
|Show the field ONLY if:[y7_tbw]<>''|7 Year: BMI|calc|||
|Calculation: if([y7_tbw]<>'',round(([y7_tbw]*703)/(([static_arm_1][height])^(2)),2),'')|||||
|577|[y7_diabetes]||||
|Show the field ONLY if:[y7_date]<>''|7 Year: Diabetes|dropdown|||
|1, Yes, non-insulin|||||
|2, Yes, insulin|||||
|3, No|||||
|578|[y7_gerd]||||
|Show the field ONLY if:[y7_date]<>''|7 Year: GERD|yesno|||
|1, Yes|||||
|0, No|||||
|579|[y7_hld]||||
|Show the field ONLY if:[y7_date]<>''|7 Year: Hyperlipidemia|yesno|||
|1, Yes|||||
|0, No|||||
|580|[y7_htn]||||
|Show the field ONLY if:[y7_date]<>''|7 Year: Hypertension|yesno|||
|1, Yes|||||
|0, No|||||
|581|[y7_htn_meds]||||
|Show the field ONLY if:[y7_htn]='1'|7 Year: Number of Anti-Hypertensive Medications|radio|||
|1, 1|||||
|2, 2|||||
|3, 3 or more|||||
|582|[y7_osa]||||
|Show the field ONLY if:[y7_date]<>''|7 Year: Sleep Apnea|yesno|||
|1, Yes|||||
|0, No|||||
|583|[y8_start]|8 Year: Start|text (date_mdy)||
|Field Annotation: @CALCDATE([surgery_date], 90, 'M')|||||
|584|[y8_captured]|8 Year: Captured|dropdown||
|1, CX|||||
|2, DECEASED|||||
|3, LTF|||||
|4, MISSED|||||
|9, MOVED|||||
|5, N/A|||||
|11, NEW SX|||||
|6, NO|||||
|7, NOS|||||
|10, REFUSING F/U|||||
|12, F/U PCP INSTEAD|||||
|8, YES|||||
|585|[y8_call]|8 Year: Call|yesno||
|1, Yes|||||
|0, No|||||
|586|[y8_ltr]|8 Year: Letter/Email|yesno||
|1, Yes|||||
|0, No|||||
|587|[y8_date]|8 Year Date|text (date_mdy), Identifier||
|588|[y8_end]|8 Year: End|text (date_mdy)||
|Field Annotation: @CALCDATE([surgery_date], 3101.5, 'd')|||||
|589|[y8_data_end]|8 Year: Data End|text (date_mdy)||
|Field Annotation: @CALCDATE([surgery_date], 3132.92, 'd')|||||
|590|[y8_tbw]|8 Year: Total Body Weight|||
|lbs|text (number)||||
|591|[y8_tbw_loss]||||
|Show the field ONLY if:[y8_tbw]<>''|8 Year: Preop TBW - 8Y TBW||||
|lbs|calc||||
|Calculation: if([y8_tbw]<>'',round((([preop_tbw]-[y8_tbw])),2),'')|||||
|592|[y8_tbw_loss_per]||||
|Show the field ONLY if:[y8_tbw]<>''|8 Year: Preop TBW - 8Y TBW %||||
|%|calc||||
|Calculation: if([y8_tbw]<>'',round(((([preop_tbw]-[y8_tbw])/[preop_tbw])*100),2),'')|||||
|593|[y8_tbw_loss_prev]||||
|Show the field ONLY if:[y8_tbw]<>''|8 Year: 7Y TBW - 8Y TBW||||
|lbs|calc||||
|Calculation: if([y8_tbw]<>'' AND [y7_tbw]<>'',round((([y7_tbw]-[y8_tbw])),2),'')|||||
|594|[y8_ebw_ml]||||
|Show the field ONLY if:[y8_tbw]<>''|8 Year: EBW - Metlife|calc|||
|Calculation: if([y8_tbw]<>'',round(([y8_tbw]-[static_arm_1][ibw_ml]),2),'')|||||
|595|[y8_ebw_ml_loss]||||
|Show the field ONLY if:[y8_tbw]<>''|8 Year: % EBW - Metlife Loss from Preop||||
|%|calc||||
|Calculation: if([y8_tbw]<>'',round(((([preop_ebw_ml]-[y8_ebw_ml])/[preop_ebw_ml])*100),2),'')|||||
|596|[y8_ebw_25]||||
|Show the field ONLY if:[y8_tbw]<>''|8 Year: EBW - 25|calc|||
|Calculation: if([y8_tbw]<>'',round(([y8_tbw]-[static_arm_1][ibw_25]),2),'')|||||
|597|[y8_ebw_25_loss]||||
|Show the field ONLY if:[y8_tbw]<>''|8 Year: % EBW - 25 Loss from Preop||||
|%|calc||||
|Calculation: if([y8_tbw]<>'',round(((([preop_ebw_25]-[y8_ebw_25])/[preop_ebw_25])*100),2),'')|||||
|598|[y8_bmi]||||
|Show the field ONLY if:[y8_tbw]<>''|8 Year: BMI|calc|||
|Calculation: if([y8_tbw]<>'',round(([y8_tbw]*703)/(([static_arm_1][height])^(2)),2),'')|||||
|599|[y8_diabetes]||||
|Show the field ONLY if:[y8_date]<>''|8 Year: Diabetes|dropdown|||
|1, Yes, non-insulin|||||
|2, Yes, insulin|||||
|3, No|||||
|600|[y8_gerd]||||
|Show the field ONLY if:[y8_date]<>''|8 Year: GERD|yesno|||
|1, Yes|||||
|0, No|||||
|601|[y8_hld]||||
|Show the field ONLY if:[y8_date]<>''|8 Year: Hyperlipidemia|yesno|||
|1, Yes|||||
|0, No|||||
|602|[y8_htn]||||
|Show the field ONLY if:[y8_date]<>''|8 Year: Hypertension|yesno|||
|1, Yes|||||
|0, No|||||
|603|[y8_htn_meds]||||
|Show the field ONLY if:[y8_htn]='1'|8 Year: Number of Anti-Hypertensive Medications|radio|||
|1, 1|||||
|2, 2|||||
|3, 3 or more|||||
|604|[y8_osa]||||
|Show the field ONLY if:[y8_date]<>''|8 Year: Sleep Apnea|yesno|||
|1, Yes|||||
|0, No|||||
|605|[y9_start]|9 Year: Start|text (date_mdy)||
|Field Annotation: @CALCDATE([surgery_date], 102, 'M')|||||
|606|[y9_captured]|9 Year: Captured|dropdown||
|1, CX|||||
|2, DECEASED|||||
|3, LTF|||||
|4, MISSED|||||
|9, MOVED|||||
|5, N/A|||||
|11, NEW SX|||||
|6, NO|||||
|7, NOS|||||
|10, REFUSING F/U|||||
|12, F/U PCP INSTEAD|||||
|8, YES|||||
|607|[y9_call]|9 Year: Call|yesno||
|1, Yes|||||
|0, No|||||
|608|[y9_ltr]|9 Year: Letter/Email|yesno||
|1, Yes|||||
|0, No|||||
|609|[y9_date]|9 Year Date|text (date_mdy), Identifier||
|610|[y9_end]|9 Year: End|text (date_mdy)||
|Field Annotation: @CALCDATE([surgery_date], 3466.5, 'd')|||||
|611|[y9_data_end]|9 Year: Data End|text (date_mdy)||
|Field Annotation: @CALCDATE([surgery_date], 3496.92, 'd')|||||
|612|[y9_tbw]|9 Year: Total Body Weight|||
|lbs|text (number)||||
|613|[y9_tbw_loss]||||
|Show the field ONLY if:[y9_tbw]<>''|9 Year: Preop TBW - 9Y TBW||||
|lbs|calc||||
|Calculation: if([y9_tbw]<>'',round((([preop_tbw]-[y9_tbw])),2),'')|||||
|614|[y9_tbw_loss_per]||||
|Show the field ONLY if:[y9_tbw]<>''|9 Year: Preop TBW - 9Y TBW %||||
|%|calc||||
|Calculation: if([y9_tbw]<>'',round(((([preop_tbw]-[y9_tbw])/[preop_tbw])*100),2),'')|||||
|615|[y9_tbw_loss_prev]||||
|Show the field ONLY if:[y9_tbw]<>''|9 Year: 8Y TBW - 9Y TBW||||
|lbs|calc||||
|Calculation: if([y9_tbw]<>'' AND [y8_tbw]<>'',round((([y8_tbw]-[y9_tbw])),2),'')|||||
|616|[y9_ebw_ml]||||
|Show the field ONLY if:[y9_tbw]<>''|9 Year: EBW - Metlife|calc|||
|Calculation: if([y9_tbw]<>'',round(([y9_tbw]-[static_arm_1][ibw_ml]),2),'')|||||
|617|[y9_ebw_ml_loss]||||
|Show the field ONLY if:[y9_tbw]<>''|9 Year: % EBW - Metlife Loss from Preop||||
|%|calc||||
|Calculation: if([y9_tbw]<>'',round(((([preop_ebw_ml]-[y9_ebw_ml])/[preop_ebw_ml])*100),2),'')|||||
|618|[y9_ebw_25]||||
|Show the field ONLY if:[y9_tbw]<>''|9 Year: EBW - 25|calc|||
|Calculation: if([y9_tbw]<>'',round(([y9_tbw]-[static_arm_1][ibw_25]),2),'')|||||
|619|[y9_ebw_25_loss]||||
|Show the field ONLY if:[y9_tbw]<>''|9 Year: % EBW - 25 Loss from Preop||||
|%|calc||||
|Calculation: if([y9_tbw]<>'',round(((([preop_ebw_25]-[y9_ebw_25])/[preop_ebw_25])*100),2),'')|||||
|620|[y9_bmi]||||
|Show the field ONLY if:[y9_tbw]<>''|9 Year: BMI|calc|||
|Calculation: if([y9_tbw]<>'',round(([y9_tbw]*703)/(([static_arm_1][height])^(2)),2),'')|||||
|621|[y9_diabetes]||||
|Show the field ONLY if:[y9_date]<>''|9 Year: Diabetes|dropdown|||
|1, Yes, non-insulin|||||
|2, Yes, insulin|||||
|3, No|||||
|622|[y9_gerd]||||
|Show the field ONLY if:[y9_date]<>''|9 Year: GERD|yesno|||
|1, Yes|||||
|0, No|||||
|623|[y9_hld]||||
|Show the field ONLY if:[y9_date]<>''|9 Year: Hyperlipidemia|yesno|||
|1, Yes|||||
|0, No|||||
|624|[y9_htn]||||
|Show the field ONLY if:[y9_date]<>''|9 Year: Hypertension|yesno|||
|1, Yes|||||
|0, No|||||
|625|[y9_htn_meds]||||
|Show the field ONLY if:[y9_htn]='1'|9 Year: Number of Anti-Hypertensive Medications|radio|||
|1, 1|||||
|2, 2|||||
|3, 3 or more|||||
|626|[y9_osa]||||
|Show the field ONLY if:[y9_date]<>''|9 Year: Sleep Apnea|yesno|||
|1, Yes|||||
|0, No|||||
|627|[y10_start]|10 Year: Start|text (date_mdy)||
|Field Annotation: @CALCDATE([surgery_date], 114, 'M')|||||
|628|[y10_captured]|10 Year: Captured|dropdown||
|1, CX|||||
|2, DECEASED|||||
|3, LTF|||||
|4, MISSED|||||
|9, MOVED|||||
|5, N/A|||||
|11, NEW SX|||||
|6, NO|||||
|7, NOS|||||
|10, REFUSING F/U|||||
|12, F/U PCP INSTEAD|||||
|8, YES|||||
|629|[y10_call]|10 Year: Call|yesno||
|1, Yes|||||
|0, No|||||
|630|[y10_ltr]|10 Year: Letter/Email|yesno||
|1, Yes|||||
|0, No|||||
|631|[y10_date]|10 Year Date|text (date_mdy), Identifier||
|632|[y10_end]|10 Year: End|text (date_mdy)||
|Field Annotation: @CALCDATE([surgery_date], 3831.5, 'd')|||||
|633|[y10_data_end]|10 Year: Data End|text (date_mdy)||
|Field Annotation: @CALCDATE([surgery_date], 3861.92, 'd')|||||
|634|[y10_tbw]|10 Year: Total Body Weight|||
|lbs|text (number)||||
|635|[y10_tbw_loss]||||
|Show the field ONLY if:[y10_tbw]<>''|10 Year: Preop TBW - 10Y TBW||||
|lbs|calc||||
|Calculation: if([y10_tbw]<>'',round((([preop_tbw]-[y10_tbw])),2),'')|||||
|636|[y10_tbw_loss_per]||||
|Show the field ONLY if:[y10_tbw]<>''|10 Year: Preop TBW - 10Y TBW %||||
|%|calc||||
|Calculation: if([y10_tbw]<>'',round(((([preop_tbw]-[y10_tbw])/[preop_tbw])*100),2),'')|||||
|637|[y10_tbw_loss_prev]||||
|Show the field ONLY if:[y10_tbw]<>''|10 Year: 9Y TBW - 10Y TBW||||
|lbs|calc||||
|Calculation: if([y10_tbw]<>'' AND [y9_tbw]<>'',round((([y9_tbw]-[y10_tbw])),2),'')|||||
|638|[y10_ebw_ml]||||
|Show the field ONLY if:[y10_tbw]<>''|10 Year: EBW - Metlife|calc|||
|Calculation: if([y10_tbw]<>'',round(([y10_tbw]-[static_arm_1][ibw_ml]),2),'')|||||
|639|[y10_ebw_ml_loss]||||
|Show the field ONLY if:[y10_tbw]<>''|10 Year: % EBW - Metlife Loss from Preop||||
|%|calc||||
|Calculation: if([y10_tbw]<>'',round(((([preop_ebw_ml]-[y10_ebw_ml])/[preop_ebw_ml])*100),2),'')|||||
|640|[y10_ebw_25]||||
|Show the field ONLY if:[y10_tbw]<>''|10 Year: EBW - 25|calc|||
|Calculation: if([y10_tbw]<>'',round(([y10_tbw]-[static_arm_1][ibw_25]),2),'')|||||
|641|[y10_ebw_25_loss]||||
|Show the field ONLY if:[y10_tbw]<>''|10 Year: % EBW - 25 Loss from Preop||||
|%|calc||||
|Calculation: if([y10_tbw]<>'',round(((([preop_ebw_25]-[y10_ebw_25])/[preop_ebw_25])*100),2),'')|||||
|642|[y10_bmi]||||
|Show the field ONLY if:[y10_tbw]<>''|10 Year: BMI|calc|||
|Calculation: if([y10_tbw]<>'',round(([y10_tbw]*703)/(([static_arm_1][height])^(2)),2),'')|||||
|643|[y10_diabetes]||||
|Show the field ONLY if:[y10_date]<>''|10 Year: Diabetes|dropdown|||
|1, Yes, non-insulin|||||
|2, Yes, insulin|||||
|3, No|||||
|644|[y10_gerd]||||
|Show the field ONLY if:[y10_date]<>''|10 Year: GERD|yesno|||
|1, Yes|||||
|0, No|||||
|645|[y10_hld]||||
|Show the field ONLY if:[y10_date]<>''|10 Year: Hyperlipidemia|yesno|||
|1, Yes|||||
|0, No|||||
|646|[y10_htn]||||
|Show the field ONLY if:[y10_date]<>''|10 Year: Hypertension|yesno|||
|1, Yes|||||
|0, No|||||
|647|[y10_htn_meds]||||
|Show the field ONLY if:[y10_htn]='1'|10 Year: Number of Anti-Hypertensive Medications|radio|||
|1, 1|||||
|2, 2|||||
|3, 3 or more|||||
|648|[y10_osa]||||
|Show the field ONLY if:[y10_date]<>''|10 Year: Sleep Apnea|yesno|||
|1, Yes|||||
|0, No|||||
|649|[surgery_year_24]|Surgery Year (2024)|calc||
|Calculation: if(contains([surgery_date],"2024"),1,0)|||||
|650|[surgery_year_23]|Surgery Year (2023)|calc||
|Calculation: if(contains([surgery_date],"2023"),1,0)|||||
|651|[surgery_year_22]|Surgery Year (2022)|calc||
|Calculation: if(contains([surgery_date],"2022"),1,0)|||||
|652|[surgery_year_21]|Surgery Year (2021)|calc||
|Calculation: if(contains([surgery_date],"2021"),1,0)|||||
|653|[surgery_year_20]|Surgery Year (2020)|calc||
|Calculation: if(contains([surgery_date],"2020"),1,0)|||||
|654|[surgery_year_19]|Surgery Year (2019)|calc||
|Calculation: if(contains([surgery_date],"2019"),1,0)|||||
|655|[surgery_year_18]|Surgery Year (2018)|calc||
|Calculation: if(contains([surgery_date],"2018"),1,0)|||||
|656|[surgery_year_17]|Surgery Year (2017)|calc||
|Calculation: if(contains([surgery_date],"2017"),1,0)|||||
|657|[surgery_year_16]|Surgery Year (2016)|calc||
|Calculation: if(contains([surgery_date],"2016"),1,0)|||||
|658|[surgery_year_15]|Surgery Year (2015)|calc||
|Calculation: if(contains([surgery_date],"2015"),1,0)|||||
|659|[surgery_year_14]|Surgery Year (2014)|calc||
|Calculation: if(contains([surgery_date],"2014"),1,0)|||||
|660|[surgery_year_13]|Surgery Year (2013)|calc||
|Calculation: if(contains([surgery_date],"2013"),1,0)|||||
|661|[surgery_year_12]|Surgery Year (2012)|calc||
|Calculation: if(contains([surgery_date],"2012"),1,0)|||||
|662|[surgery_year_11]|Surgery Year (2011)|calc||
|Calculation: if(contains([surgery_date],"2011"),1,0)|||||
|663|[surgery_month_jan]|Surgery Month (January)|calc||
|Calculation: if(contains([surgery_date],"-01-"),1,0)|||||
|664|[surgery_month_feb]|Surgery Month (February)|calc||
|Calculation: if(contains([surgery_date],"-02-"),1,0)|||||
|665|[surgery_month_mar]|Surgery Month (March)|calc||
|Calculation: if(contains([surgery_date],"-03-"),1,0)|||||
|666|[surgery_month_apr]|Surgery Month (April)|calc||
|Calculation: if(contains([surgery_date],"-04-"),1,0)|||||
|667|[surgery_month_may]|Surgery Month (May)|calc||
|Calculation: if(contains([surgery_date],"-05-"),1,0)|||||
|668|[surgery_month_jun]|Surgery Month (June)|calc||
|Calculation: if(contains([surgery_date],"-06-"),1,0)|||||
|669|[surgery_month_jul]|Surgery Month (July)|calc||
|Calculation: if(contains([surgery_date],"-07-"),1,0)|||||
|670|[surgery_month_aug]|Surgery Month (August)|calc||
|Calculation: if(contains([surgery_date],"-08-"),1,0)|||||
|671|[surgery_month_sep]|Surgery Month (September)|calc||
|Calculation: if(contains([surgery_date],"-09-"),1,0)|||||
|672|[surgery_month_oct]|Surgery Month (October)|calc||
|Calculation: if(contains([surgery_date],"-10-"),1,0)|||||
|673|[surgery_month_nov]|Surgery Month (November)|calc||
|Calculation: if(contains([surgery_date],"-11-"),1,0)|||||
|674|[surgery_month_dec]|Surgery Month (December)|calc||
|Calculation: if(contains([surgery_date],"-12-"),1,0)|||||
|675|[sx_sar_morb]|SAR Morbidity associated with this surgery|calc||
|Calculation: if([sar_morbidity][last-instance]=1,1, if([sar_morbidity][first-instance]=1,1, if([sar_morbidity][previous-instance]=1,1, if([sar_morbidity][current-instance]=1,1,0))))|||||
|676|[sx_sar_all_occur]|SAR All Occurrences associated with this surgery|calc||
|Calculation: if([sar_all_occur][last-instance]=1,1, if([sar_all_occur][first-instance]=1,1, if([sar_all_occur][previous-instance]=1,1, if([sar_all_occur][current-instance]=1,1,0))))|||||
|677|[sx_sar_serious]|SAR Serious Event associated with this surgery|calc||
|Calculation: if([sar_serious][last-instance]=1,1, if([sar_serious][first-instance]=1,1, if([sar_serious][previous-instance]=1,1, if([sar_serious][current-instance]=1,1,0))))|||||
|678|[sx_sar_all_reop]|SAR All Cause Reoperation associated with this surgery|calc||
|Calculation: if([sar_all_reop][last-instance]=1,1, if([sar_all_reop][first-instance]=1,1, if([sar_all_reop][previous-instance]=1,1, if([sar_all_reop][current-instance]=1,1,0))))|||||
|679|[sx_sar_rel_reop]|SAR Related Reoperation associated with this surgery|calc||
|Calculation: if([sar_rel_reop][last-instance]=1,1, if([sar_rel_reop][first-instance]=1,1, if([sar_rel_reop][previous-instance]=1,1, if([sar_rel_reop][current-instance]=1,1,0))))|||||
|680|[sx_sar_all_int]|SAR All Cause Intervention associated with this surgery|calc||
|Calculation: if([sar_all_int][last-instance]=1,1, if([sar_all_int][first-instance]=1,1, if([sar_all_int][previous-instance]=1,1, if([sar_all_int][current-instance]=1,1,0))))|||||
|681|[sx_sar_rel_int]|SAR Related Intervention associated with this surgery|calc||
|Calculation: if([sar_rel_int][last-instance]=1,1, if([sar_rel_int][first-instance]=1,1, if([sar_rel_int][previous-instance]=1,1, if([sar_rel_int][current-instance]=1,1,0))))|||||
|682|[sx_sar_all_readm]|SAR All Cause Readmission associated with this surgery|calc||
|Calculation: if([sar_all_readm][last-instance]=1,1, if([sar_all_readm][first-instance]=1,1, if([sar_all_readm][previous-instance]=1,1, if([sar_all_readm][current-instance]=1,1,0))))|||||
|683|[sx_sar_rel_readm]|SAR Related Readmission associated with this surgery|calc||
|Calculation: if([sar_rel_readm][last-instance]=1,1, if([sar_rel_readm][first-instance]=1,1, if([sar_rel_readm][previous-instance]=1,1, if([sar_rel_readm][current-instance]=1,1,0))))|||||
|684|[sx_sar_leak]|SAR Leak associated with this surgery|calc||
|Calculation: if([sar_leak][last-instance]=1,1, if([sar_leak][first-instance]=1,1, if([sar_leak][previous-instance]=1,1, if([sar_leak][current-instance]=1,1,0))))|||||
|685|[sx_sar_bleed]|SAR Bleeding associated with this surgery|calc||
|Calculation: if([sar_bleed][last-instance]=1,1, if([sar_bleed][first-instance]=1,1, if([sar_bleed][previous-instance]=1,1, if([sar_bleed][current-instance]=1,1,0))))|||||
|686|[sx_sar_ssi]|SAR SSI associated with this surgery|calc||
|Calculation: if([sar_ssi][last-instance]=1,1, if([sar_ssi][first-instance]=1,1, if([sar_ssi][previous-instance]=1,1, if([sar_ssi][current-instance]=1,1,0))))|||||
|687|[surgery_complete]|Complete?|dropdown||
|0, Incomplete|||||
|1, Unverified|||||
|2, Complete|||||

### Occurrence

|#|Variable / Field Name|Field Label|Field Attributes (Field Type, Validation, Choices, Calculations, etc.)|_**Notes**_|
|---|---|---|---|---|
|688|[demo_occur]|PT INFO|notes||
|Field Annotation: @SETVALUE='[static_arm_1][mrn] [static_arm_1][last_name], [static_arm_1][first_name] DOB: [static_arm_1][dob]|Age at Sx: [event-name][age_tos]|Contact Date: [static_arm_1][contact_date]'|||
|689|[surgery_info]|Patient Surgery Info|notes, Identifier||
|Field Annotation: @SETVALUE='[event-name][surgery_date] [event-name][surgery_type] ([event-name][sx_details]) at [event-name][loc] [FLR:[event-name][flr]] with [event-name][surgery_md]'|||||
|690|[occur_sx_date]|Surgery Date|text (date_ymd), Identifier||
|691|[occur_date]|Occurrence Date|text (date_ymd), Required, Identifier||
|692|[days_from_sx]|Days from Surgery|calc||
|Calculation: round(datediff([occur_sx_date],[occur_date],'d','ymd'),2)|||||
|693|[occur_loc]|Occurrence Location|radio||
|1, SBH|||||
|2, LICH|||||
|3, SCH|||||
|4, SHH|||||
|4, Centereach Clinic|||||
|6, Anther of our clinics|||||
|999, OTHER|||||
|694|[occur_loc_other]||||
|Show the field ONLY if:[occur_loc]='999'|Occurrence Location OTHER|text|||
|695|[occur_cat]|Category|dropdown||
|1, Intraop|||||
|2, Postop|||||
|3, Intervention|||||
|4, Reoperation|||||
|5, Readmission|||||
|6, Mortality|||||
|7, ED|||||
|8, IV Fluids|||||
|696|[occur_type]|Occurrence Type|dropdown||
|B022, Superficial Incisional SSI|||||
|B001, Deep Incisional SSI|||||
|B002, Organ/Space SSI|||||
|B003, Wound disruption|||||
|B004, Pneumonia|||||
|B005, Unplanned embolism|||||
|B006, Pulmonary embolism|||||
|B007, On ventilator > 48 hours|||||
|B008, Progressive renal insufficiency|||||
|B009, Acute renal failure|||||
|B010, Urinary tract infection|||||
|B011, Stroke/CVA|||||
|B012, Cardiac arrest requiring CPR|||||
|B013, Myocardial infarction|||||
|B014, Blood transfusion|||||
|B015, Vein thrombosis requiring therapy|||||
|B016, C.diff|||||
|B017, Sepsis|||||
|B018, Septic shock|||||
|B019, Unplanned admission to ICU|||||
|B020, Gastrointestinal tract bleed|||||
|B021, Bowel obstruction|||||
|C001, Diagnostic endoscopy|||||
|C002, Intragastric balloon placement|||||
|C003, Intragastric balloon adjustment|||||
|C004, Intragastric balloon removal|||||
|C005, Therapeutic endoscopy with dilation and/or stent placement|||||
|C006, Therapeutic endoscopy with stoma resizing|||||
|C007, Therapeutic endoscopy with gastric plication or oversew (pouch resizing)|||||
|C008, Therapeutic endoscopy with fistula closure|||||
|C009, Therapeutic endoscopy with band removal|||||
|C010, Therapeutic endoscopy with endoscopic gastroplasty|||||
|C011, Endoscopy with percutaneous tube placement (G-tube, J-tube)|||||
|C012, Other intervention (not listed)|||||
|D001, Adjustable gastric band, port, and/or tubing revision|||||
|D002, Adjustable gastric banding over Roux-en-Y bypass|||||
|D003, Biliopancreatic diversion with or without duodenal switch revision|||||
|D004, Biliopancreatic diversion common channel lengthening|||||
|D005, Feeding tube placement (G-tube or J-tube) (laparoscopic or open)|||||
|D006, Gastrectomy|||||
|D007, Gastric pouch or stoma plication or revision|||||
|D008, Gastrointestinal tract repair (involving metabolic or bariatric surgery anatomy)|||||
|D009, Hernia repair (involving metabolic or bariatric surgery anatomy)|||||
|D010, Roux-en-Y gastric bypass revision|||||
|D011, Roux-en-Y limb lengthening|||||
|D012, Single anastomosis duodeno-ileal bypass / Loop duodenal switch|||||
|D013, Sleeve gastrectomy revision (Re-sleeve)|||||
|D014, Takedown or reversal of metabolic or bariatric procedure|||||
|D015, Other abdominal procedure involving metabolic or bariatric anatomy (not listed)|||||
|D016, Other investigational (not listed)|||||
|D017, Other abdominal NOT involving metabolic or bariatric anatomy (not listed)|||||
|D018, Other reoperation (not listed)|||||
|697|[occur_diagn]|Occurrence Diagnosis|dropdown||
|A001, Abdominal pain, not otherwise specified|||||
|A002, Acute Renal Failure Requiring Dialysis|||||
|A003, Adhesions|||||
|A004, Anastomotic or staple line leak|||||
|A005, Anastomotic stricture|||||
|A006, Anastomotic ulcer|||||
|A007, Aspiration|||||
|A008, Balloon rupture|||||
|A009, Band erosion|||||
|A010, Band slippage or prolapse|||||
|A011, Bleeding|||||
|A012, Blood transfusion|||||
|A013, Bowel obstruction|||||
|A014, C.diff|||||
|A015, Cancer|||||
|A016, Cardiac Arrest Requiring CPR|||||
|A017, Cardiac, not otherwise specified (arrhythmias, CHF)|||||
|A018, Chest pain|||||
|A019, Cholecystitis, cholelithiasis|||||
|A020, Constipation|||||
|A021, CVA|||||
|A022, Deep Incisional SSI|||||
|A023, Dumping syndrome|||||
|A024, Dysphagia|||||
|A025, Enterocutaneous fistula|||||
|A026, Esophagitis|||||
|A027, Excessive weight loss|||||
|A028, Findings within normal limits|||||
|A029, Gastric distention|||||
|A030, Gastric ulcer|||||
|A031, Gastritis|||||
|A032, Gastroesophageal reflux disease (GERD)|||||
|A033, Gastrointestinal stromal tumor (GIST)|||||
|A034, Gastrointestinal tract bleeding|||||
|A035, Gastrointestinal tract fistula|||||
|A036, Gastrointestinal tract perforation|||||
|A037, Gastrointestinal tract stricture or obstruction|||||
|A038, Gastrointestinal tract ulcer without perforation|||||
|A039, Gastroparesis|||||
|A040, Hematoma|||||
|A041, Hiatal hernia|||||
|A042, Hypoglycemia|||||
|A043, Inadequate weight loss|||||
|A044, Incisional hernia|||||
|A045, Infection and/or fever (not meeting criteria for more specific reason)|||||
|A046, Internal hernia or mesenteric defect|||||
|A047, Intussusception or volvulus|||||
|A048, Mechanical malfunction|||||
|A049, Medication-related|||||
|A050, Musculoskeletal pain|||||
|A051, Myocardial infarction|||||
|A052, Nausea, vomiting, fluid, electrolyte, and/or nutritional depletion|||||
|A053, Nephrolithiasis|||||
|A054, Obstruction|||||
|A055, On ventilator > 48 hours|||||
|A056, Oral intake intolerance|||||
|A057, Organ/Space SSI|||||
|A058, Other|||||
|A059, Other abdominal sepsis|||||
|A060, Other respiratory|||||
|A061, Paraesophageal hernia|||||
|A062, Patient intolerance|||||
|A063, Patient non-compliance|||||
|A064, Patient request|||||
|A065, Perforation|||||
|A066, Persistent co-morbidities|||||
|A067, Planned removal per protocol|||||
|A068, Planned surgery (not metabolic or bariatric related)|||||
|A069, Pneumonia|||||
|A070, Postop venous thrombosis requiring therapy|||||
|A071, Pouch dilation|||||
|A072, Pouch stricture|||||
|A073, Progressive Renal Insufficiency|||||
|A074, Psychiatric-related|||||
|A075, Pulmonary embolism|||||
|A076, Renal failure|||||
|A077, Renal insufficiency|||||
|A078, Revision of metabolic or bariatric procedure for reason not otherwise listed (e.g. scheduled surgery)|||||
|A079, Sepsis|||||
|A080, Septic Shock|||||
|A081, Shortness of breath|||||
|A082, Stroke/Cerebral Vascular Accident (CVA)|||||
|A083, Superficial Incisional SSI|||||
|A084, Traumatic injury (e.g. Motor vehicle accident, fall)|||||
|A085, Unplanned admission to ICU|||||
|A086, Unplanned Intubation|||||
|A087, Urinary Tract Infection|||||
|A088, Vein thrombosis requiring therapy|||||
|A089, Weight gain|||||
|A090, Wound disruption|||||
|A091, Wound infection|||||
|698|[occur_readm_date]||||
|Show the field ONLY if:[occur_cat]='5'|Readmit Date|text (date_mdy), Identifier|||
|699|[occur_disch_date]||||
|Show the field ONLY if:[occur_cat]='5'|Discharge Date|text (date_mdy), Identifier|||
|700|[occur_los]||||
|Show the field ONLY if:[occur_cat]='5'|Readmit Length of Stay|calc|||
|Calculation: round(datediff([occur_readm_date],[occur_disch_date],'d','mdy'),2)|||||
|701|[occur_desc]|Description|notes||
|702|[sar_morbidity]|SAR: Morbidity|calc||
|Calculation: if([sbu_sx_calc]='1' AND [d30_calc]='1' AND [morb_calc]='1',1,0)|||||
|703|[sar_all_occur]|SAR: All Occurrences Morbidity|calc||
|Calculation: if([sbu_sx_calc]=1 AND [d30_calc]=1 AND [sar_morbidity]=1,1, if([sbu_sx_calc]=1 AND [d30_calc]=1 AND [occur_cat]='3' AND [all_occur_calc]=1,1, if([sbu_sx_calc]=1 AND [d30_calc]=1 AND [occur_cat]='4' AND [all_occur_calc]=1,1, if([sbu_sx_calc]=1 AND [d30_calc]=1 AND [occur_cat]='5' AND [all_occur_calc]=1,1,0))))|||||
|704|[sar_serious]|SAR: Serious Event|calc||
|Calculation: if([sbu_sx_calc]=1 AND [d30_calc]=1 AND [serious_calc]=1,1,0)|||||
|705|[sar_all_reop]|SAR: All Cause Reoperation|calc||
|Calculation: if([sbu_sx_calc]=1 AND [d30_calc]=1 AND [occur_cat]='4',1,0)|||||
|706|[sar_rel_reop]|SAR: Related Reoperation|calc||
|Calculation: if([sbu_sx_calc]=1 AND [d30_calc]=1 AND [all_occur_calc]=1 AND [occur_cat]='4',1,0)|||||
|707|[sar_all_int]|SAR: All Cause Intervention|calc||
|Calculation: if([sbu_sx_calc]=1 AND [d30_calc]=1 AND [occur_cat]='3',1,0)|||||
|708|[sar_rel_int]|SAR: Related Intervention|calc||
|Calculation: if([sbu_sx_calc]=1 AND [d30_calc]=1 AND [all_occur_calc]=1 AND [occur_cat]='3',1,0)|||||
|709|[sar_all_readm]|SAR: All Cause Readmission|calc||
|Calculation: if([sbu_sx_calc]=1 AND [d30_calc]=1 AND [occur_cat]='5',1,0)|||||
|710|[sar_rel_readm]|SAR: Related Readmission|calc||
|Calculation: if([sbu_sx_calc]=1 AND [d30_calc]=1 AND [all_occur_calc]=1 AND [occur_cat]='5',1,0)|||||
|711|[sar_leak]|SAR: Anastomotic/Staple Line Leak|calc||
|Calculation: if([sbu_sx_calc]=1 AND [d30_calc]=1 AND [occur_diagn]='A004',1,0)|||||
|712|[sar_bleed]|SAR: Bleeding|calc||
|Calculation: if([sbu_sx_calc]=1 AND [d30_calc]=1 AND [occur_type]='B014',1, if([sbu_sx_calc]=1 AND [d30_calc]=1 AND [occur_diagn]='A012',1, if([sbu_sx_calc]=1 AND [d30_calc]=1 AND [occur_type]='B020',1, if([sbu_sx_calc]=1 AND [d30_calc]=1 AND [occur_diagn]='A034',1, if([sbu_sx_calc]=1 AND [d30_calc]=1 AND [occur_diagn]='A011',1,0)))))|||||
|713|[sar_ssi]|SAR: Surgical Site Infection (SSI)|calc||
|Calculation: if([sbu_sx_calc]=1 AND [d30_calc]=1 AND [occur_type]='B022',1, if([sbu_sx_calc]=1 AND [d30_calc]=1 AND [occur_type]='B001',1, if([sbu_sx_calc]=1 AND [d30_calc]=1 AND [occur_type]='B002',1, if([sbu_sx_calc]=1 AND [d30_calc]=1 AND [occur_diagn]='A022',1, if([sbu_sx_calc]=1 AND [d30_calc]=1 AND [occur_diagn]='A057',1, if([sbu_sx_calc]=1 AND [d30_calc]=1 AND [occur_diagn]='A083',1,0))))))|||||
|714|[sbu_sx_calc]|SBU Surgery|calc||
|Calculation: if([event-name][loc]='1',1,0)|||||
|715|[d30_calc]|Within 30Days of Surgery Calc|calc||
|Calculation: if([days_from_sx]<=30,1,0)|||||
|716|[morb_calc]|Morbidity CalculationA case is assigned a Morbidity occurrence if one or more of the following complications occurred within 30 days of the index procedure: Superficial Incisional SSI1; Deep Incisional SSI1; Organ/Space SSI1; Wound Disruption; Pneumonia1; Unplanned Intubation; Pulmonary Embolism; On Ventilator > 48 hours1; Progressive Renal Insufficiency2; Acute Renal Failure2; Urinary Tract Infection1; Stroke/Cerebral Vascular Accident; Cardiac Arrest Requiring CPR; Myocardial Infarction; Transfusion (within 72 hours of surgery start time); Postop Venous Thrombosis Requiring Therapy; C. diff; Sepsis1; Septic Shock1; Anastomotic/Staple Line Leak; Gastrointestinal Tract Bleed; Bowel Obstruction.|calc||
|Calculation: if([occur_type]='B022', 1, if([occur_type]='B001', 1, if([occur_type]='B002', 1, if([occur_type]='B003', 1, if([occur_type]='B004', 1, if([occur_type]='B005', 1, if([occur_type]='B006', 1, if([occur_type]='B007', 1, if([occur_type]='B008', 1, if([occur_type]='B009', 1, if([occur_type]='B010', 1, if([occur_type]='B011', 1, if([occur_type]='B012', 1, if([occur_type]='B013', 1, if([occur_type]='B014', 1, if([occur_type]='B015', 1, if([occur_type]='B016', 1, if([occur_type]='B017', 1, if([occur_type]='B018', 1, if([occur_type]='B019', 0, if([occur_type]='B020', 1, if([occur_type]='B021', 1, if([occur_type]='C001', 0, if([occur_type]='C002', 0, if([occur_type]='C003', 0, if([occur_type]='C004', 0, if([occur_type]='C005', 0, if([occur_type]='C006', 0, if([occur_type]='C007', 0, if([occur_type]='C008', 0, if([occur_type]='C009', 0, if([occur_type]='C010', 0, if([occur_type]='C011', 0, if([occur_type]='C012', 0, if([occur_type]='D001', 0, if([occur_type]='D002', 0, if([occur_type]='D003', 0, if([occur_type]='D004', 0, if([occur_type]='D005', 0, if([occur_type]='D006', 0, if([occur_type]='D007', 0, if([occur_type]='D008', 0, if([occur_type]='D009', 0, if([occur_type]='D010', 0, if([occur_type]='D011', 0, if([occur_type]='D012', 0, if([occur_type]='D013', 0, if([occur_type]='D014', 0, if([occur_type]='D015', 0, if([occur_type]='D016', 0, if([occur_type]='D017', 0, if([occur_type]='D018', 0, if([occur_diagn]='A001', 0, if([occur_diagn]='A002', 1, if([occur_diagn]='A003', 0, if([occur_diagn]='A004', 1, if([occur_diagn]='A005', 0, if([occur_diagn]='A006', 0, if([occur_diagn]='A007', 0, if([occur_diagn]='A008', 0, if([occur_diagn]='A009', 0, if([occur_diagn]='A010', 0, if([occur_diagn]='A011', 0, if([occur_diagn]='A012', 0, if([occur_diagn]='A013', 1, if([occur_diagn]='A014', 1, if([occur_diagn]='A015', 0, if([occur_diagn]='A016', 1, if([occur_diagn]='A017', 0, if([occur_diagn]='A018', 0, if([occur_diagn]='A019', 0, if([occur_diagn]='A020', 0, if([occur_diagn]='A021', 1, if([occur_diagn]='A022', 1, if([occur_diagn]='A023', 0, if([occur_diagn]='A024', 0, if([occur_diagn]='A025', 0, if([occur_diagn]='A026', 0, if([occur_diagn]='A027', 0, if([occur_diagn]='A028', 0, if([occur_diagn]='A029', 0, if([occur_diagn]='A030', 0, if([occur_diagn]='A031', 0, if([occur_diagn]='A032', 0, if([occur_diagn]='A033', 0, if([occur_diagn]='A034', 1, if([occur_diagn]='A035', 0, if([occur_diagn]='A036', 0, if([occur_diagn]='A037', 1, if([occur_diagn]='A038', 0, if([occur_diagn]='A039', 0, if([occur_diagn]='A040', 0, if([occur_diagn]='A041', 0, if([occur_diagn]='A042', 0, if([occur_diagn]='A043', 0, if([occur_diagn]='A044', 0, if([occur_diagn]='A045', 0, if([occur_diagn]='A046', 0, if([occur_diagn]='A047', 0, if([occur_diagn]='A048', 0, if([occur_diagn]='A049', 0, if([occur_diagn]='A050', 0, if([occur_diagn]='A051', 1, if([occur_diagn]='A052', 0, if([occur_diagn]='A053', 0, if([occur_diagn]='A054', 1, if([occur_diagn]='A055', 1, if([occur_diagn]='A056', 0, if([occur_diagn]='A057', 1, if([occur_diagn]='A058', 0, if([occur_diagn]='A059', 0, if([occur_diagn]='A060', 0, if([occur_diagn]='A061', 0, if([occur_diagn]='A062', 0, if([occur_diagn]='A063', 0, if([occur_diagn]='A064', 0, if([occur_diagn]='A065', 0, if([occur_diagn]='A066', 0, if([occur_diagn]='A067', 0, if([occur_diagn]='A068', 0, if([occur_diagn]='A069', 1, if([occur_diagn]='A070', 1, if([occur_diagn]='A071', 0, if([occur_diagn]='A072', 0, if([occur_diagn]='A073', 1, if([occur_diagn]='A074', 0, if([occur_diagn]='A075', 1, if([occur_diagn]='A076', 1, if([occur_diagn]='A077', 1, if([occur_diagn]='A078', 0, if([occur_diagn]='A079', 1, if([occur_diagn]='A080', 1, if([occur_diagn]='A081', 0, if([occur_diagn]='A082', 1, if([occur_diagn]='A083', 1, if([occur_diagn]='A084', 0, if([occur_diagn]='A085', 0, if([occur_diagn]='A086', 1, if([occur_diagn]='A087', 1, if([occur_diagn]='A088', 1, if([occur_diagn]='A089', 0, if([occur_diagn]='A090', 1, if([occur_diagn]='A091', 0, 0) ))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))) )|||||
|717|[all_occur_calc]|All Occurrences/Related Morbidity Calculation A case is assigned an All Occurrences Morbidity occurrence if(1) The case was assigned a Morbidity occurrence (as defined above)OR(2) An unplanned admission to the ICU occurred within 30 days of the index procedure.OR(3) At least one reoperation, intervention, or readmission occurred within 30 days of the index procedure and the recorded "Postprocedural Diagnosis" or "Discharge Diagnosis" was any of the following: Abdominal Pain; Adhesions; Anastomotic ulcer; Anastomotic stricture; Anastomotic or staple line leak; Band erosion; Band slippage or prolapse; Dumping syndrome; Dysphagia; Constipation; Enterocutaneous fistula; Esophagitis; Gastric distention; Gastroesophageal reflux disease (GERD); Gastrointestinal tract bleeding; Gastrointestinal tract fistula; Gastrointestinal tract perforation; Gastrointestinal tract stricture or Obstruction; Gastrointestinal tract ulcer without perforation; Gastroparesis; Gastritis; Hematoma; Hiatal hernia; Internal hernia or mesenteric defect; Intussusception or volvulus; Mechanical malfunction; Other abdominal sepsis (diverticulitis, pancreatitis; intra-abdominal abscess); Oral intake intolerance; Paraesophageal hernia; Pouch stricture; Pouch dilation; Revision of metabolic or bariatric procedure for reason not otherwise listed; Cardiac (arrhythmias, CHF); Chest pain; Myocardial infarction; Postop Venous thrombosis requiring therapy; Stroke/CVA; Intragastric Balloon (IGB) Aspiration; IGB Bleeding; IGB Balloon rupture; IGB Gastric ulcer; IGB Obstruction; IGB Perforation; IGB Planned removal per protocol; Excessive weight loss; Hypoglycemia; Inadequate weight loss; Nausea, vomiting, fluid, electrolyte, and/or nutritional depletion; Persistent co-morbidities; Weight gain; Other respiratory; Pneumonia; Pulmonary embolism; Shortness of breath; Renal failure; Renal insufficiency; Wound Disruption; Incisional hernia; Wound infection; Infection and/or fever (not meeting other criteria); Patient intolerance; Patient non-compliance; Patient request.|calc||
|Calculation: if([occur_type]='B022', 1, if([occur_type]='B001', 1, if([occur_type]='B002', 1, if([occur_type]='B003', 1, if([occur_type]='B004', 1, if([occur_type]='B005', 1, if([occur_type]='B006', 1, if([occur_type]='B007', 1, if([occur_type]='B008', 1, if([occur_type]='B009', 1, if([occur_type]='B010', 1, if([occur_type]='B011', 1, if([occur_type]='B012', 1, if([occur_type]='B013', 1, if([occur_type]='B014', 1, if([occur_type]='B015', 1, if([occur_type]='B016', 1, if([occur_type]='B017', 1, if([occur_type]='B018', 1, if([occur_type]='B019', 1, if([occur_type]='B020', 1, if([occur_type]='B021', 1, if([occur_type]='C001', 0, if([occur_type]='C002', 0, if([occur_type]='C003', 0, if([occur_type]='C004', 1, if([occur_type]='C005', 0, if([occur_type]='C006', 0, if([occur_type]='C007', 0, if([occur_type]='C008', 0, if([occur_type]='C009', 0, if([occur_type]='C010', 0, if([occur_type]='C011', 0, if([occur_type]='C012', 0, if([occur_type]='D001', 0, if([occur_type]='D002', 0, if([occur_type]='D003', 0, if([occur_type]='D004', 0, if([occur_type]='D005', 0, if([occur_type]='D006', 0, if([occur_type]='D007', 0, if([occur_type]='D008', 0, if([occur_type]='D009', 0, if([occur_type]='D010', 0, if([occur_type]='D011', 0, if([occur_type]='D012', 0, if([occur_type]='D013', 0, if([occur_type]='D014', 0, if([occur_type]='D015', 0, if([occur_type]='D016', 0, if([occur_type]='D017', 0, if([occur_type]='D018', 0, if([occur_diagn]='A001', 1, if([occur_diagn]='A002', 1, if([occur_diagn]='A003', 1, if([occur_diagn]='A004', 1, if([occur_diagn]='A005', 1, if([occur_diagn]='A006', 1, if([occur_diagn]='A007', 1, if([occur_diagn]='A008', 1, if([occur_diagn]='A009', 1, if([occur_diagn]='A010', 1, if([occur_diagn]='A011', 1, if([occur_diagn]='A012', 1, if([occur_diagn]='A013', 1, if([occur_diagn]='A014', 1, if([occur_diagn]='A015', 0, if([occur_diagn]='A016', 1, if([occur_diagn]='A017', 1, if([occur_diagn]='A018', 1, if([occur_diagn]='A019', 0, if([occur_diagn]='A020', 1, if([occur_diagn]='A021', 1, if([occur_diagn]='A022', 1, if([occur_diagn]='A023', 1, if([occur_diagn]='A024', 1, if([occur_diagn]='A025', 1, if([occur_diagn]='A026', 1, if([occur_diagn]='A027', 1, if([occur_diagn]='A028', 0, if([occur_diagn]='A029', 1, if([occur_diagn]='A030', 1, if([occur_diagn]='A031', 1, if([occur_diagn]='A032', 1, if([occur_diagn]='A033', 0, if([occur_diagn]='A034', 1, if([occur_diagn]='A035', 1, if([occur_diagn]='A036', 1, if([occur_diagn]='A037', 1, if([occur_diagn]='A038', 1, if([occur_diagn]='A039', 1, if([occur_diagn]='A040', 1, if([occur_diagn]='A041', 1, if([occur_diagn]='A042', 1, if([occur_diagn]='A043', 1, if([occur_diagn]='A044', 1, if([occur_diagn]='A045', 1, if([occur_diagn]='A046', 1, if([occur_diagn]='A047', 1, if([occur_diagn]='A048', 1, if([occur_diagn]='A049', 0, if([occur_diagn]='A050', 0, if([occur_diagn]='A051', 1, if([occur_diagn]='A052', 1, if([occur_diagn]='A053', 0, if([occur_diagn]='A054', 1, if([occur_diagn]='A055', 1, if([occur_diagn]='A056', 1, if([occur_diagn]='A057', 1, if([occur_diagn]='A058', 0, if([occur_diagn]='A059', 1, if([occur_diagn]='A060', 1, if([occur_diagn]='A061', 1, if([occur_diagn]='A062', 1, if([occur_diagn]='A063', 1, if([occur_diagn]='A064', 1, if([occur_diagn]='A065', 1, if([occur_diagn]='A066', 1, if([occur_diagn]='A067', 1, if([occur_diagn]='A068', 0, if([occur_diagn]='A069', 1, if([occur_diagn]='A070', 1, if([occur_diagn]='A071', 1, if([occur_diagn]='A072', 1, if([occur_diagn]='A073', 1, if([occur_diagn]='A074', 0, if([occur_diagn]='A075', 1, if([occur_diagn]='A076', 1, if([occur_diagn]='A077', 1, if([occur_diagn]='A078', 1, if([occur_diagn]='A079', 1, if([occur_diagn]='A080', 1, if([occur_diagn]='A081', 1, if([occur_diagn]='A082', 1, if([occur_diagn]='A083', 1, if([occur_diagn]='A084', 0, if([occur_diagn]='A085', 1, if([occur_diagn]='A086', 1, if([occur_diagn]='A087', 1, if([occur_diagn]='A088', 1, if([occur_diagn]='A089', 1, if([occur_diagn]='A090', 1, if([occur_diagn]='A091', 1, 0) ))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))) )|||||
|718|[serious_calc]|Serious Event Calculation A case is assigned a Serious Event occurrence if one or more of the following events occurred within 30 days of the index procedure: Death; Related, Unplanned Reoperation (see 'Related Reoperation'); Unplanned Admission to the ICU; Organ/Space SSI3; Pneumonia3; Unplanned Intubation; Pulmonary Embolism; On Ventilator > 48 hours3; Progressive Renal Insufficiency4; Acute Renal Failure4; Stroke/Cerebral Vascular Accident; Cardiac Arrest Requiring CPR; Myocardial Infarction; Transfusion (within 72 hours of surgery start time); Postop Venous Thrombosis Requiring Therapy; Sepsis3; Septic Shock3; Anastomotic/Staple Line leak; Gastrointestinal Tract Bleed; Bowel Obstruction.|calc||
|Calculation: if([occur_cat]='6', 1, if([occur_type]='B022', 0, if([occur_type]='B001', 0, if([occur_type]='B002', 1, if([occur_type]='B003', 0, if([occur_type]='B004', 1, if([occur_type]='B005', 0, if([occur_type]='B006', 1, if([occur_type]='B007', 1, if([occur_type]='B008', 1, if([occur_type]='B009', 1, if([occur_type]='B010', 0, if([occur_type]='B011', 1, if([occur_type]='B012', 1, if([occur_type]='B013', 1, if([occur_type]='B014', 1, if([occur_type]='B015', 0, if([occur_type]='B016', 0, if([occur_type]='B017', 1, if([occur_type]='B018', 1, if([occur_type]='B019', 1, if([occur_type]='B020', 1, if([occur_type]='B021', 1, if([occur_type]='C001', 0, if([occur_type]='C002', 0, if([occur_type]='C003', 0, if([occur_type]='C004', 0, if([occur_type]='C005', 0, if([occur_type]='C006', 0, if([occur_type]='C007', 0, if([occur_type]='C008', 0, if([occur_type]='C009', 0, if([occur_type]='C010', 0, if([occur_type]='C011', 0, if([occur_type]='C012', 0, if([occur_type]='D001', 0, if([occur_type]='D002', 0, if([occur_type]='D003', 0, if([occur_type]='D004', 0, if([occur_type]='D005', 0, if([occur_type]='D006', 0, if([occur_type]='D007', 0, if([occur_type]='D008', 0, if([occur_type]='D009', 0, if([occur_type]='D010', 0, if([occur_type]='D011', 0, if([occur_type]='D012', 0, if([occur_type]='D013', 0, if([occur_type]='D014', 0, if([occur_type]='D015', 0, if([occur_type]='D016', 0, if([occur_type]='D017', 0, if([occur_type]='D018', 0, if([occur_diagn]='A001', 0, if([occur_diagn]='A002', 1, if([occur_diagn]='A003', 0, if([occur_diagn]='A004', 1, if([occur_diagn]='A005', 0, if([occur_diagn]='A006', 0, if([occur_diagn]='A007', 0, if([occur_diagn]='A008', 0, if([occur_diagn]='A009', 0, if([occur_diagn]='A010', 0, if([occur_diagn]='A011', 0, if([occur_diagn]='A012', 1, if([occur_diagn]='A013', 1, if([occur_diagn]='A014', 0, if([occur_diagn]='A015', 0, if([occur_diagn]='A016', 1, if([occur_diagn]='A017', 0, if([occur_diagn]='A018', 0, if([occur_diagn]='A019', 0, if([occur_diagn]='A020', 0, if([occur_diagn]='A021', 0, if([occur_diagn]='A022', 0, if([occur_diagn]='A023', 0, if([occur_diagn]='A024', 0, if([occur_diagn]='A025', 0, if([occur_diagn]='A026', 0, if([occur_diagn]='A027', 0, if([occur_diagn]='A028', 0, if([occur_diagn]='A029', 0, if([occur_diagn]='A030', 0, if([occur_diagn]='A031', 0, if([occur_diagn]='A032', 0, if([occur_diagn]='A033', 0, if([occur_diagn]='A034', 1, if([occur_diagn]='A035', 0, if([occur_diagn]='A036', 0, if([occur_diagn]='A037', 1, if([occur_diagn]='A038', 0, if([occur_diagn]='A039', 0, if([occur_diagn]='A040', 0, if([occur_diagn]='A041', 0, if([occur_diagn]='A042', 0, if([occur_diagn]='A043', 0, if([occur_diagn]='A044', 0, if([occur_diagn]='A045', 0, if([occur_diagn]='A046', 0, if([occur_diagn]='A047', 0, if([occur_diagn]='A048', 0, if([occur_diagn]='A049', 0, if([occur_diagn]='A050', 0, if([occur_diagn]='A051', 1, if([occur_diagn]='A052', 0, if([occur_diagn]='A053', 0, if([occur_diagn]='A054', 1, if([occur_diagn]='A055', 1, if([occur_diagn]='A056', 0, if([occur_diagn]='A057', 1, if([occur_diagn]='A058', 0, if([occur_diagn]='A059', 0, if([occur_diagn]='A060', 0, if([occur_diagn]='A061', 0, if([occur_diagn]='A062', 0, if([occur_diagn]='A063', 0, if([occur_diagn]='A064', 0, if([occur_diagn]='A065', 0, if([occur_diagn]='A066', 0, if([occur_diagn]='A067', 0, if([occur_diagn]='A068', 0, if([occur_diagn]='A069', 1, if([occur_diagn]='A070', 1, if([occur_diagn]='A071', 0, if([occur_diagn]='A072', 0, if([occur_diagn]='A073', 1, if([occur_diagn]='A074', 0, if([occur_diagn]='A075', 1, if([occur_diagn]='A076', 0, if([occur_diagn]='A077', 0, if([occur_diagn]='A078', 0, if([occur_diagn]='A079', 1, if([occur_diagn]='A080', 1, if([occur_diagn]='A081', 0, if([occur_diagn]='A082', 1, if([occur_diagn]='A083', 0, if([occur_diagn]='A084', 0, if([occur_diagn]='A085', 1, if([occur_diagn]='A086', 1, if([occur_diagn]='A087', 0, if([occur_diagn]='A088', 0, if([occur_diagn]='A089', 0, if([occur_diagn]='A090', 0, if([occur_diagn]='A091', 0, 0) )))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))))) )|||||
|719|[sar_occurrence]|SAR Occurrences?|calc||
|Calculation: if([sar_morbidity]=1,1, if([sar_all_occur]=1,1, if([sar_serious]=1,1, if([sar_all_reop]=1,1, if([sar_rel_reop]=1,1, if([sar_all_int]=1,1, if([sar_rel_int]=1,1, if([sar_all_readm]=1,1, if([sar_rel_readm]=1,1, if([sar_leak]=1,1, if([sar_bleed]=1,1, if([sar_ssi]=1,1,0))))))))))))|||||
|720|[occur_year_24]|Occurrence Year (2024)|calc||
|Calculation: if(contains([occur_date],"2024"),1,0)|||||
|721|[occur_sx_year_24]|Occurrence Surgery Year (2024)|calc||
|Calculation: if(contains([occur_sx_date],"2024"),1,0)|||||
|722|[occur_year_23]|Occurrence Year (2023)|calc||
|Calculation: if(contains([occur_date],"2023"),1,0)|||||
|723|[occur_sx_year_23]|Occurrence Surgery Year (2023)|calc||
|Calculation: if(contains([occur_sx_date],"2023"),1,0)|||||
|724|[occur_year_22]|Occurrence Year (2022)|calc||
|Calculation: if(contains([occur_date],"2022"),1,0)|||||
|725|[occur_sx_year_22]|Occurrence Surgery Year (2022)|calc||
|Calculation: if(contains([occur_sx_date],"2022"),1,0)|||||
|726|[occur_year_21]|Occurrence Year (2021)|calc||
|Calculation: if(contains([occur_date],"2021"),1,0)|||||
|727|[occur_sx_year_21]|Occurrence Surgery Year (2021)|calc||
|Calculation: if(contains([occur_sx_date],"2021"),1,0)|||||
|728|[occur_year_20]|Occurrence Year (2020)|calc||
|Calculation: if(contains([occur_date],"2020"),1,0)|||||
|729|[occur_sx_year_20]|Occurrence Surgery Year (2020)|calc||
|Calculation: if(contains([occur_sx_date],"2020"),1,0)|||||
|730|[occur_year_19]|Occurrence Year (2019)|calc||
|Calculation: if(contains([occur_date],"2019"),1,0)|||||
|731|[occur_sx_year_19]|Occurrence Surgery Year (2019)|calc||
|Calculation: if(contains([occur_sx_date],"2019"),1,0)|||||
|732|[occur_year_18]|Occurrence Year (2018)|calc||
|Calculation: if(contains([occur_date],"2018"),1,0)|||||
|733|[occur_sx_year_18]|Occurrence Surgery Year (2018)|calc||
|Calculation: if(contains([occur_sx_date],"2018"),1,0)|||||
|734|[occur_year_17]|Occurrence Year (2017)|calc||
|Calculation: if(contains([occur_date],"2017"),1,0)|||||
|735|[occur_sx_year_17]|Occurrence Surgery Year (2017)|calc||
|Calculation: if(contains([occur_sx_date],"2017"),1,0)|||||
|736|[occur_year_16]|Occurrence Year (2016)|calc||
|Calculation: if(contains([occur_date],"2016"),1,0)|||||
|737|[occur_sx_year_16]|Occurrence Surgery Year (2016)|calc||
|Calculation: if(contains([occur_sx_date],"2016"),1,0)|||||
|738|[occur_year_15]|Occurrence Year (2015)|calc||
|Calculation: if(contains([occur_date],"2015"),1,0)|||||
|739|[occur_sx_year_15]|Occurrence Surgery Year (2015)|calc||
|Calculation: if(contains([occur_sx_date],"2015"),1,0)|||||
|740|[occur_year_14]|Occurrence Year (2014)|calc||
|Calculation: if(contains([occur_date],"2014"),1,0)|||||
|741|[occur_sx_year_14]|Occurrence Surgery Year (2014)|calc||
|Calculation: if(contains([occur_sx_date],"2014"),1,0)|||||
|742|[occur_year_13]|Occurrence Year (2013)|calc||
|Calculation: if(contains([occur_date],"2013"),1,0)|||||
|743|[occur_sx_year_13]|Occurrence Surgery Year (2013)|calc||
|Calculation: if(contains([occur_sx_date],"2013"),1,0)|||||
|744|[occur_year_12]|Occurrence Year (2012)|calc||
|Calculation: if(contains([occur_date],"2012"),1,0)|||||
|745|[occur_sx_year_12]|Occurrence Surgery Year (2012)|calc||
|Calculation: if(contains([occur_sx_date],"2012"),1,0)|||||
|746|[occur_year_11]|Occurrence Year (2011)|calc||
|Calculation: if(contains([occur_date],"2011"),1,0)|||||
|747|[occur_sx_year_11]|Occurrence Surgery Year (2011)|calc||
|Calculation: if(contains([occur_sx_date],"2011"),1,0)|||||
|748|[occur_month_jan]|Occurrence Month (January)|calc||
|Calculation: if(contains([occur_date],"-01-"),1,0)|||||
|749|[occur_sx_month_jan]|Occurrence Surgery Month (January)|calc||
|Calculation: if(contains([occur_sx_date],"-01-"),1,0)|||||
|750|[occur_month_feb]|Occurrence Month (February)|calc||
|Calculation: if(contains([occur_date],"-02-"),1,0)|||||
|751|[occur_sx_month_feb]|Occurrence Surgery Month (February)|calc||
|Calculation: if(contains([occur_sx_date],"-02-"),1,0)|||||
|752|[occur_month_mar]|Occurrence Month (March)|calc||
|Calculation: if(contains([occur_date],"-03-"),1,0)|||||
|753|[occur_sx_month_mar]|Occurrence Surgery Month (March)|calc||
|Calculation: if(contains([occur_sx_date],"-03-"),1,0)|||||
|754|[occur_month_apr]|Occurrence Month (April)|calc||
|Calculation: if(contains([occur_date],"-04-"),1,0)|||||
|755|[occur_sx_month_apr]|Occurrence Surgery Month (April)|calc||
|Calculation: if(contains([occur_sx_date],"-04-"),1,0)|||||
|756|[occur_month_may]|Occurrence Month (May)|calc||
|Calculation: if(contains([occur_date],"-05-"),1,0)|||||
|757|[occur_sx_month_may]|Occurrence Surgery Month (May)|calc||
|Calculation: if(contains([occur_sx_date],"-05-"),1,0)|||||
|758|[occur_month_jun]|Occurrence Month (June)|calc||
|Calculation: if(contains([occur_date],"-06-"),1,0)|||||
|759|[occur_sx_month_jun]|Occurrence Surgery Month (June)|calc||
|Calculation: if(contains([occur_sx_date],"-06-"),1,0)|||||
|760|[occur_month_jul]|Occurrence Month (July)|calc||
|Calculation: if(contains([occur_date],"-07-"),1,0)|||||
|761|[occur_sx_month_jul]|Occurrence Surgery Month (July)|calc||
|Calculation: if(contains([occur_sx_date],"-07-"),1,0)|||||
|762|[occur_month_aug]|Occurrence Month (August)|calc||
|Calculation: if(contains([occur_date],"-08-"),1,0)|||||
|763|[occur_sx_month_aug]|Occurrence Surgery Month (August)|calc||
|Calculation: if(contains([occur_sx_date],"-08-"),1,0)|||||
|764|[occur_month_sep]|Occurrence Month (September)|calc||
|Calculation: if(contains([occur_date],"-09-"),1,0)|||||
|765|[occur_sx_month_sep]|Occurrence Surgery Month (September)|calc||
|Calculation: if(contains([occur_sx_date],"-09-"),1,0)|||||
|766|[occur_month_oct]|Occurrence Month (October)|calc||
|Calculation: if(contains([occur_date],"-10-"),1,0)|||||
|767|[occur_sx_month_oct]|Occurrence Month (October)|calc||
|Calculation: if(contains([occur_sx_date],"-10-"),1,0)|||||
|768|[occur_month_nov]|Occurrence Month (November)|calc||
|Calculation: if(contains([occur_date],"-11-"),1,0)|||||
|769|[occur_sx_month_nov]|Occurrence Surgery Month (November)|calc||
|Calculation: if(contains([occur_sx_date],"-11-"),1,0)|||||
|770|[occur_month_dec]|Occurrence Month (December)|calc||
|Calculation: if(contains([occur_date],"-12-"),1,0)|||||
|771|[occur_sx_month_dec]|Occurrence Surgery Month (December)|calc||
|Calculation: if(contains([occur_sx_date],"-12-"),1,0)|||||
|772|[occurrence_complete]|Complete?|dropdown||
|0, Incomplete|||||
|1, Unverified|||||
|2, COmplete|||||

---


> [!INFO] GENERAL RULES
> The consulting provider (MD, NP, RD) should always be the first person the patient saw
> If the patient was never seen but has multiple rescheduled appointments, the consulting provider should be the last person they were scheduled with and the location should be the last location they were scheduled for.
> The initial interest should go based on when speaking to the patient when they are fist scheduled but afterwards should be confirmed by the New Bariatric Patient Packet and that should be priority for what their initial interest and who referred them
> - The exception to this would be a direct referral via Cerner by a provider or a faxed referral script from an outside practice
> - The initial interest and post-op interest should never change from what the patient was originally interested in and what the provider and patient agreed in the initial consult; should the patient and/or provider change the pathway, the STATUS on the demographic page should be what changes
> - If the patient had a previous procedure at an outside facility, was seen in our office but stopped coming without any procedure performed by our practice, their status would still remain “Post Op LTF” instead of “Dropped Out”
> - The medication option should be marked off as “Yes” if medication was discussed as a plausible option for the patient regardless if the medication is approved or denied or if the patient does not have coverage
 >   - avoid the mislabeling based on the template language used by the doctors: “They will begin with our medically supervised multidisciplinary weight-loss program, if they are unsuccessful with this program then surgical intervention will be considered.”
> - The only dates that will reflect a restart in the process are the Group Sessions
 >    - These should be under the discretion of the staff for when a new “Group Sessions” form should be completed when the patient restarts the process and groups need to be ‘restarted’
> If there are multiple “groups” performed within the same month (i.e. the patient attended a group but the dietitian also completed a group module for their scheduled nutrition follow-up), use the first group attended for that month to enter in the groups and do not include the other group attended.
 >    - THERE SHOULD ONLY EVERY BE 1 ARRIVED GROUP PER MONTH UNLESS IT IS AN INSURANCE THAT REQUIRES MULTIPLE GROUPS PER MONTH

