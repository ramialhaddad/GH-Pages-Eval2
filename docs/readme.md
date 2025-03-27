|Customer LOGO|**FUNCTIONAL DESIGN DOCUMENT**|Partner LOGO|
| :- | :-: | -: |






FUNCTIONAL / TECHNICAL DESIGN DOCUMENT


Project: 



Prepared by: 




2023



<a name="_hlk529280034"></a>Name of the parties’ POC

**Partner**

|**Title**|**Name**|**Email**|**Contact Number**|
| :- | :- | :- | :- |
|||||
|||||
|||||
|||||


**Customer**

|**Title**|**Name**|**Email**|**Contact Number**|
| :- | :- | :- | :- |
|||||
|||||
|||||
|||||
Sheet accounting changes

|**Version**|**Changes**|**The Initiator**|**Date**|
| :- | :- | :- | :- |
|0\.0|Initial Draft|First Last name|DD/MM/YY|



**Table of Contents**

[1**	**INTRODUCTION	7****](#_toc138859263)**

[1.1	The composition of the document	7](#_toc138859264)

[1.2	Abbreviations	7](#_toc138859265)

[1.3	Transcript schemes of business processes	7](#_toc138859266)

[**2**	**PROJECT OVERVIEW	9****](#_toc138859267)

[2.1	Scope	9](#_toc138859268)

[**3**	**ORGANIZATION STRUCTURE AND FUNCTIONAL RESPONSIBILITIES IN THE SOLUTION	10****](#_toc138859269)

[3.1	Department description 1	10](#_toc138859270)

[*3.1.1*	*Unit 1	10**](#_toc138859271)

[*3.1.2*	*Unit 2	10**](#_toc138859272)

[3.2	Department description 2	10](#_toc138859273)

[*3.2.1*	*Unit 1	10**](#_toc138859274)

[*3.2.2*	*Unit 2	10**](#_toc138859275)

[**4**	**DESCRIPTION OF BUSINESS PROCESSES	11****](#_toc138859276)

[4.1	Common information about organization process	11](#_toc138859277)

[4.2	Accounts	11](#_toc138859278)

[*4.2.1*	*Create Account	11**](#_toc138859279)

[4.3	Leads	13](#_toc138859280)

[*4.3.1*	*Business process N	13**](#_toc138859281)

[**5**	**ARCHITECTURE SOLUTION DESIGN	13****](#_toc138859282)

[5.1	Data requirements (conceptual object model)	13](#_toc138859283)

[*5.1.1*	*Scalability and performance considerations	13**](#_toc138859284)

[5.2	Table structure	14](#_toc138859285)

[*5.2.1*	*Table options that can only be enabled	14**](#_toc138859286)

[*5.2.2*	*Enable or disable table options	14**](#_toc138859287)

[*5.2.3*	*Field properties	15**](#_toc138859288)

[*5.2.4*	*Possible data types for a field	16**](#_toc138859289)

[*5.2.5*	*Data naming (specify names of fields)	17**](#_toc138859290)

[*5.2.6*	*Common fields for all tables	18**](#_toc138859291)

[5.3	Column structure of business objects	19](#_toc138859292)

[*5.3.1*	*Account (OOB)	19**](#_toc138859293)

[*5.3.2*	*Contact (OOB)	20**](#_toc138859294)

[*5.3.3*	*Lead (OOB)	21**](#_toc138859295)

[5.4	Column structure of normative reference information	22](#_toc138859296)

[*5.4.1*	*Table N (Custom)	22**](#_toc138859297)

[**6**	**SECURITY REQUIREMENTS (ROLE MODEL FOR ACCESS)	23****](#_toc138859298)

[6.1	Hierarchy Business Unit in the system	23](#_toc138859299)

[6.2	Security roles	23](#_toc138859300)

[*6.2.1*	*Role 1	23**](#_toc138859301)

[*6.2.2*	*Role 2	24**](#_toc138859302)

[**7**	**ADDITIONAL FUNCTIONALITY	25****](#_toc138859303)

[7.1	Dynamics 365 App for Outlook	25](#_toc138859304)

[7.2	Manage transactions with multiple currencies	25](#_toc138859305)

[7.3	Duplication rules	25](#_toc138859306)

[*7.3.1*	*Account	25**](#_toc138859307)

[*7.3.2*	*Contact	25**](#_toc138859308)

[*7.3.3*	*Lead	26**](#_toc138859309)

[7.4	Support for mobile devices	26](#_toc138859310)

[7.5	Multilingual support	26](#_toc138859311)

[7.6	Editable grids	26](#_toc138859312)

[7.7	System notifications	27](#_toc138859313)

[*7.7.1*	*Email notifications	27**](#_toc138859314)

[*7.7.2*	*Push Notifications	27**](#_toc138859315)

[*7.7.3*	*In-App Notifications	27**](#_toc138859316)

[7.8	Scan business card	27](#_toc138859317)

[7.9	Compliance	27](#_toc138859318)

[7.10	Dynamics 365 Sales Insights (Microsoft solution)	27](#_toc138859319)

[7.11	Enhanced Search to improve search results and performance	27](#_toc138859320)

[**8**	**REPORTING AND ANALYTICS	28****](#_toc138859321)

[8.1	Reports	28](#_toc138859322)

[*8.1.1*	*Report 1	28**](#_toc138859323)

[8.2	Dashboards	28](#_toc138859324)

[8.3	Data warehousing strategy	28](#_toc138859325)

[**9**	**INTEGRATION	30****](#_toc138859326)

[9.1	Logging mechanism	30](#_toc138859327)

[9.2	Integration 1	30](#_toc138859328)

[*9.2.1*	*Scope	30**](#_toc138859329)

[*9.2.2*	*Interface design	30**](#_toc138859330)

[**10**	**MIGRATION	31****](#_toc138859331)


1. # <a name="_introduction"></a><a name="_toc531114941"></a><a name="_toc138859263"></a>**Introduction**
   1. ## <a name="_toc531114943"></a><a name="_toc138859264"></a>**The composition of the document**
The functional design document (FDD) contains:

- Scope
- Organization structure: The functional management of departments for creating a security model of the solution
- Business process: The schema of business process in the solution
- Architecture solution design: Object model, Data model
- Additional customization
- Security Roles
- Integration
- Data Migration
  1. ## ` `**<a name="_toc531114944"></a><a name="_toc138859265"></a>Abbreviations**

|**Abbreviations**|**Transcript**|
| :- | :- |
|Plug-in|Plug-in is a software component that adds a specific feature to an existing software application|
|POC|Point of contact|
|FDD|Functional Design Document|
|TDD|Technical Design Document|
|||
|||
|||
|||
|||
|||
|||
1. ## <a name="_toc531114945"></a><a name="_toc138859266"></a>**Transcript schemes of business processes**

|**Symbol**|**Comment**|
| :-: | :- |
|![](Aspose.Words.a98735c8-b7d5-43bf-83ad-365d5cfefcd7.001.png)|Division of the company using the system and has in its composition subordinates’ other units.|
|![](Aspose.Words.a98735c8-b7d5-43bf-83ad-365d5cfefcd7.002.png)|Department of the company using the system.|
|![](Aspose.Words.a98735c8-b7d5-43bf-83ad-365d5cfefcd7.003.png)|Department of the company, non-automation|
|![](Aspose.Words.a98735c8-b7d5-43bf-83ad-365d5cfefcd7.004.png)|Start of processes|
|![](Aspose.Words.a98735c8-b7d5-43bf-83ad-365d5cfefcd7.005.png)|End of processes|
|![](Aspose.Words.a98735c8-b7d5-43bf-83ad-365d5cfefcd7.006.png)|Link for process «»|
|![](Aspose.Words.a98735c8-b7d5-43bf-83ad-365d5cfefcd7.007.png)|Operation «»|
|![](Aspose.Words.a98735c8-b7d5-43bf-83ad-365d5cfefcd7.008.png)|Integration operation «»|
|![](Aspose.Words.a98735c8-b7d5-43bf-83ad-365d5cfefcd7.009.png)|The logical question «»|
|![](Aspose.Words.a98735c8-b7d5-43bf-83ad-365d5cfefcd7.010.png)|The following function starts only after the end of a previous|
|![](Aspose.Words.a98735c8-b7d5-43bf-83ad-365d5cfefcd7.011.png)|After the end of the function, the following functions are run in parallel|


1. # <a name="_toc531114946"></a><a name="_toc138859267"></a>**Project overview**
   1. ## <a name="_toc531114947"></a><a name="_toc138859268"></a>**Scope**
The scope of the service includes the following:

*Usually, this section contains the FitGap analysis worksheet – see template.*

*Sometimes, the functional design document doesn’t contain all out-of-band features that are available for Dynamics 365 but only changes or critical functions which are going to be used.*


1. # <a name="_project_approach"></a><a name="_toc531114952"></a><a name="_toc138859269"></a>**Organization structure and functional responsibilities in the solution**
![](Aspose.Words.a98735c8-b7d5-43bf-83ad-365d5cfefcd7.012.png)

1. ## <a name="_toc531114953"></a><a name="_toc93560058"></a><a name="_toc138859270"></a>**Department description 1**
   1. ### <a name="_toc93560059"></a><a name="_toc138859271"></a>**Unit 1**
   1. ### <a name="_toc93560060"></a><a name="_toc138859272"></a>**Unit 2**
1. ## <a name="_toc93560061"></a><a name="_toc138859273"></a>**Department description 2**
   1. ### <a name="_toc93560062"></a><a name="_toc138859274"></a>**Unit 1**
   1. ### <a name="_toc93560063"></a><a name="_toc138859275"></a>**Unit 2**
1.
|||Page | **277**|
| :- | :-: | -: |

1. # <a name="_toc138859276"></a>**Description of business processes**
   1. ## <a name="_toc138859277"></a>**Common information about organization process**
This document includes the following business processes to be automated:

1. Accounts 
1. Leads
1. Business process N

Model business processes contained in this document consists of the following components:

- Business process diagram - process diagrams with detailed level of functions and performers;
- Tables of functions / operations - a text description of the business functions / operations, including a description of incoming / outgoing information and performers
  1. ## <a name="_business_requirements_definition"></a><a name="_toc138859278"></a>**Accounts**
     1. ### <a name="_toc138859279"></a>**Create Account**
        1. #### ***Process Flow***
![](Aspose.Words.a98735c8-b7d5-43bf-83ad-365d5cfefcd7.013.png)

|**Step Id**|**Description**|**Remarks**|
| :- | :- | :- |
|ACC-NEW-01|Manual Check if ‘Account’ Exists in the system?|User needs to manually check if the ‘Account’ profile which he / she is going to create has existed in the system already.|
|ACC-NEW-02|Exist?|Based on the input key words, which have been pre-defined as searchable, the system will filter out the similar records to users.|
|ACC-NEW-03|Open existing Account Card|If the account exists already, the system will open the existing account and abort the creation process by user. |
|ACC-NEW-04|Manual Create ‘Account’ Profile in the system.|User needs to manually create the ‘Account Profile in the system if it doesn’t exist already.|
|` `ACC-NEW-05|Duplicate Detect based on the rule|The system will do the duplication detect based on the rule|
|` `ACC-NEW-06|Duplicate?|If duplicate records are found in the system, abort the creation process and go to step ACC-NEW-03.|
|` `ACC-NEW-07|<p>Account Creation Process</p><p> </p>|If duplicated account Profile is not found in the system, then Account profile is created in the system.|

1. #### ***Functional design***

|**ID**|**Description**|**Rules / Examples/ Comments**|
| :- | :- | :- |
||||
||||
1. ## <a name="_toc138859280"></a>**Leads**
   1. ### <a name="_toc138859281"></a>**Business process N**
      1. #### ***Process flow***
![Set customer credit limit process flow diagram.](Aspose.Words.a98735c8-b7d5-43bf-83ad-365d5cfefcd7.014.png)

|**Step Id**|**Description**|**Remarks**|
| :- | :- | :- |
||||
||||
||||
||||

1. #### ***Functional design***

|**ID**|**Description**|**Rules / Examples/ Comments**|
| :- | :- | :- |
||||
||||

1. # <a name="_toc531114979"></a><a name="_toc138859282"></a>**Architecture solution design**
   1. ## <a name="_toc531114980"></a><a name="_toc138859283"></a>**Data requirements (conceptual object model)**
      1. ### <a name="_toc138859284"></a>**Scalability and performance considerations**
Please include metadata relationships in these sections. Also, it would be helpful to have indexes which will be included in the tables. Data archrival strategy / long retention strategy
1. ## <a name="_toc531114981"></a><a name="_toc138859285"></a>**Table structure**
   1. ### <a name="_toc531114982"></a><a name="_toc138859286"></a>**Table options that can only be enabled**

|**Option**|**Comments**|
| :- | :- |
|Business process flows|Create business process flows for this table. More information: [Create a business process flow to standardize processes](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/customize/create-business-process-flow)|
|Notes|Append notes to records for this table. Notes include the ability to add attachments.|
|Activities|Associate activities to records for this table.|
|Connections|Use the connections feature to show how records for this table have connections to records of other tables that also have connections enabled.|
|Sending e-mail (if an e-mail field does not exist, one will be created)|Send emails using an email address stored in one of the fields for this table. If a Single Line of Text field with format set to email doesn’t already exist for this table, a new one will be created when you enable sending email.|
|Queues|Use the table with queues. Queues improve routing and sharing of work by making records for this table available in a central place that everyone can access.|

1. ### <a name="_toc531114983"></a><a name="_toc138859287"></a>**Enable or disable table options**

|**Option**|**Comments**|
| :- | :- |
|Primary Image|<p>System tables that support images will already have an **Image** field. You can choose whether to display data in this field as the image for the record by setting this field to **[None]** or **Default Image**.</p><p><br>For custom tables you must first create an image field. Each table can have only one image field. After you create one, you can change this setting to set the primary image. More information: [Image fields](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/customize/types-of-fields#BKMK_ImageFields)</p>|
|Mail Merge|User can use this table with mail merge.|
|Document Management|After other tasks have been performed to enable document management for your organization, enabling this feature allows for this table to participate in integration with SharePoint.|
|Duplicate Detection|If duplicate detection is enabled for your organization, enabling this allows you to create duplicate detection rules for this table.|
|Allow Quick Create|<p>After you have created and published a **Quick Create Form** for this table, User will have the option to create a new record using the **Create** button in the navigation pane.</p><p>When this is enabled for a custom activity table, the custom activity will be visible in the group of activity tables when people use the **Create** button in the navigation pane. However, because activities don’t support quick create forms, the main form will be used when the custom table icon is clicked.</p>|
|Auditing|When auditing is enabled for your organization, this allows for changes to table records to be captured over time. When you enable auditing for an table, auditing is also enabled on all its fields. You can select or clear fields that you want to enable auditing on.|
|Access Teams|Create team templates for this table.|
|Enable for phone express|Make this table available to the Dynamics 365 for phones app.|
|Enable for mobile|<p>Make this table available to the Dynamics 365 for phones and tablets apps. You also have the option to make this table **Read-only in mobile**.</p><p>If the forms for an table require an extension not supported in Dynamics 365 for phones and tablets, such as iFrame or web resource controls, use this setting to ensure that mobile app users can’t edit the data for these tables.</p><p>**Important:** If you have previously installed any portal solution, to create a case in the Customer Service Hub or to use the Merge cases command, you must turn off the **Read-only in mobile option** for the Case table.</p>|

1. ### <a name="_toc531114984"></a><a name="_toc138859288"></a>**Field properties**

|**Option**|**Comments**|
| :- | :- |
|Display Name|The name that appears as a label in the heading for lists where this attribute is included. It is also the default label when this field is shown in a form, but the label text in each form can be edited separately.|
|Name|This field is prepopulated based on the **Display Name** you entered. It includes the solution publisher customization prefix. You can change the **Display Name** later, but the **Name** can’t be changed after the field is saved.|
|Field Requirement|<p>There are three options:</p><p>- **Optional**</p><p>The record can be saved even if there is no data in this field.</p><p>- **Business Recommended**</p><p>The record can be saved even if there is no data in this field. However, a blue asterisk appears next to the field to indicate it is important.</p><p>- **Business Required**</p><p>The record can’t be saved if there is no data in this field.</p><p>Be careful when you make fields business required. People will resist using the application if they can’t save records because they lack the correct information to enter into a required field. People may enter incorrect data simply to save the record and get on with their work.</p><p>You can use business rules or form scripts to change the requirement level as the data in the record changes as people work on it.</p>|
|Searchable|When a field is searchable it appears in Advanced Find and is available when customizing views. Use this when there are fields for the table that you don’t use. Setting this to **No** will reduce the number of options shown to user using advanced find.|
|Field Security|For custom fields, enable this to allow this field to participate in field-level security.|
|Auditing|Disable this so that data in this field won’t be included with auditing data.|
|Description|Enter text that will appear as a tooltip when the field is displayed in a form. |

1. ### <a name="_toc531114985"></a><a name="_toc138859289"></a>**Possible data types for a field**

|**Data Type**|**Notes**|
| :- | :- |
|Single Line of Text|<p>The following formats are available:</p><p>o **E-mail**. This opens a new e-mail message in the default e-mail software when clicked and also validates an email address.</p><p>&emsp;o **Text**. This creates a text box.</p><p>&emsp;o **Text area**. This creates a scrolling text box.</p><p>&emsp;o **URL**. This opens the URL in the user's default browser when clicked and validates (or adds) a valid protocol (HTTP, HTTPS, FTP, FTPS, OneNote, and TEL) are allowed.</p><p>&emsp;o **Ticker Symbol**. This creates a stock ticker symbol in all capital letters. Click the symbol to open information about the stock in the user's default browser. By default, the MSN website opens.</p><p>&emsp;o Phone. This creates a link that enables Skype or Microsoft Lync users to initiate a call by using the linked number.</p>|
|Option Set|Select an existing option set or define a new one. |
|MultiSelect Option Set|This field provides a set of options, where multiple options can be selected. When added to a form, this field uses a control for users to select multiple options.|
|Two Options|After creating this field, configure it in the form to which it was added. In the form, select whether the field is displayed as option buttons (also known as radio buttons), a check box, or a list.|
|Image|Each table can have one image field. When an table has an image field it can be configured to display the image for the record in the application.|
|Whole Number|<p>The following formats are available for this field:</p><p>o **None.** The defaults are integer values between -2,147,483,648 and 2,147,483,648, although you can set different minimum and maximum values.</p><p>&emsp;o **Duration.** This creates a drop-down list box with values in minutes, hours, and days.</p><p>&emsp;o **Time Zone.** This creates a drop-down list box with options for every available time zone.</p><p>&emsp;o Language. This creates a drop-down list box with options for every language that your organization has made available for users.</p>|
|Floating Point Number|Select up to 5 precision points. You can set the minimum and maximum values.|
|Decimal Number|Select up to 10 decimal points. You can set the minimum and maximum values.|
|Currency|<p>When you add a currency field to an table, a corresponding (Base) field is also created. The (Base) field also has a currency data type.</p><p>If the table does not already have a field with a currency data type, two additional fields are created:</p><p>o **Currency.** A lookup data type whose value must be set before you can set the value of a field with a currency data type.</p><p>&emsp;o **Exchange Rate**. This has a decimal number data type.</p>|
|Multiple Lines of Text|This is a scrolling text box. You can set the maximum number of characters for this field.|
|Date and Time|There are two formats: date only, or date and time.|
|Lookup|You can create a lookup field using an table relationship that has already been created, but not yet used with another lookup field. If you create a lookup field in an table form, the relationship is automatically generated. A lookup field is created as a relationship field.|
1. ### <a name="_toc531114986"></a><a name="_toc138859290"></a>**Data naming (specify names of fields)**

|**Option**|**Description**|
| :- | :- |
|Publisher Display Name|Default publisher|
|Name Publisher (schema name)|new|
|Prefix|new|
|Option Value Prefix|10000|
|Data type – string, money, all types of numbers - schema name|Logical name of fields. For example: Field name – Account; Schema name – new\_account|
|Data type – option set - schema name|Logical name of fields ***+ code***. For example: Field name – Account type; Schema name – new\_accounttype**code**|
|Data type – two options (bit) - schema name|***IS +*** Logical name of fields. For example: Field name – Partner support project; Schema name – new\_***is***partnerproject|
|Data type – date - schema name|Logical name of fields ***+ date***. For example: Field name – Payment date; Schema name – new\_payment***date***|
|Data type – lookup - schema name|Logical name of fields ***+ id***. For example: Field name – Contact; Schema name – new\_contact***id***|
|schema name|All schema name should have small letters|
1. ### <a name="_toc531114987"></a><a name="_toc138859291"></a>**Common fields for all tables**

|**No**|**Display Name**|**Schema Name**|**Field Type**|**Requirement**|**Notes**|**Read Only**|
| :- | :- | :- | :- | :- | :- | :- |
||Owner|ownerid|Lookup (user/team)|+|Owner is only for User/Team ownership type||
||Modified By|modifiedby|Lookup (user)|+|Shows who last updated the record.|+|
||Modified On|modifiedon|Date and Time|+|Shows the date and time when the record was last updated. The date and time are displayed in the time zone selected in Microsoft Dynamics 365 options.|+|
||Created By|createdby|Lookup (user)|+|Shows who created the record.|+|
||Created On|createdon|Date and Time|+|Shows the date and time when the record was created. The date and time are displayed in the time zone selected in Microsoft Dynamics 365 options.|+|
||Status|statecode|<p>States:</p><p>0: Active</p><p>1: Inactive</p>||By default if not we specified for a concrete table (for example Opportunity) ||
||Status Reason|statuscode|<p>States:</p><p>1: Active</p><p>2: Inactive</p>||By default if not we specified for a concrete table (for example Opportunity)||

1. ## <a name="_toc10136690"></a><a name="_toc10110875"></a><a name="_toc10136698"></a><a name="_toc10110883"></a><a name="_toc10136706"></a><a name="_toc10110891"></a><a name="_toc10136714"></a><a name="_toc10110899"></a><a name="_toc531114988"></a><a name="_toc138859292"></a>**Column structure of business objects**
   1. ### <a name="_toc531114989"></a><a name="_toc138859293"></a>**Account (OOB)**
      1. #### ***General***

|**Option**|**Enable / Disable**|
| :- | :- |
|Display Name|Account|
|Plural Name|Accounts|
|Schema name (Table)|account|
|Primary field (schema name)|name|
|Business process flows||
|Notes|Yes|
|Activities|Yes|
|Connections|Yes|
|Sending e-mail (if an e-mail field does not exist, one will be created)|Yes|
|Queues|Yes|
|Primary Image|Yes|
|Mail Merge|Yes|
|Document Management||
|Duplicate Detection|Yes|
|Allow Quick Create|Yes|
|Auditing|Yes|
|Access Teams||
|Enable for phone express|Yes|
|Enable for mobile|Yes|
|Ownership|User or Team|

1. #### ***Form (Main)***
Visible for all roles

|**No**|**Display Name**|**Schema Name**|**Field Type**|**Requirement**|**Notes**|**Read Only**|**Searchable**|
| :- | :- | :- | :- | :- | :- | :- | :- |
||Account Name|Name|Single Line of Text (128)|+|||+|
||Account type|accounttype|<p>Option set:</p><p>1\.Prospect</p><p>2\.Customer</p>|+|||+|
||Address|Address1\_composite|Multiline (1000)||Combine City, Street, ZIP, State, Country/Region on one line|+|+|

1. #### ***Usability and user interface considerations***

1. ### <a name="_toc531114990"></a><a name="_toc138859294"></a>**Contact (OOB)**
   1. #### ***General***

|**Option**|**Enable / Disable**|
| :- | :- |
|Display Name|Contact|
|Plural Name|Contacts|
|Schema name (Table)|contact|
|Primary field (schema name)|fullname|
|Business process flows||
|Notes|Yes|
|Activities|Yes|
|Connections|Yes|
|Sending e-mail (if an e-mail field does not exist, one will be created)|Yes|
|Queues|Yes|
|Primary Image|No|
|Mail Merge|Yes|
|Document Management||
|Duplicate Detection|Yes|
|Allow Quick Create|Yes|
|Auditing|Yes|
|Access Teams||
|Enable for phone express|Yes|
|Enable for mobile|Yes|

1. #### ***Form (Main)*** 

|**No**|**Display Name**|**Schema Name**|**Field Type**|**Requirement**|**Notes**|**Read Only**|**Searchable**|
| :- | :- | :- | :- | :- | :- | :- | :- |
||Full name|name|Single Line of Text (300) Composite|+|Full name of client (First name + Last Name + Middle name)|+|+|
||First name|firstname|Single Line of Text (50)|+|||+|
||Last name|lastname|Single Line of Text (50)|+|||+|
||Middle name|middlename|Single Line of Text (50)||||+|
||Job Title|jobtitle|Single Line of Text (100)||||+|
1. #### <a name="_toc531114991"></a>***Usability and user interface considerations***
1. ### <a name="_toc138859295"></a>**Lead (OOB)**

1. #### ***General***

|**Option**|**Enable / Disable**|
| :- | :- |
|Display Name|Lead|
|Plural Name|Leads|
|Schema name (Table)|lead|
|Primary field (schema name)|name|
|Business process flows||
|Notes|Yes|
|Activities|Yes|
|Connections|Yes|
|Sending e-mail (if an e-mail field does not exist, one will be created)|Yes|
|Queues|Yes|
|Primary Image|No|
|Mail Merge|Yes|
|Document Management||
|Duplicate Detection|Yes|
|Allow Quick Create|Yes|
|Auditing|Yes|
|Access Teams||
|Enable for phone express|Yes|
|Enable for mobile|Yes|

1. #### ***Form (Main)***

|**No**|**Display Name**|**Schema Name**|**Field Type**|**Requirement**|**Notes**|**Read Only**|**Searchable**|
| :- | :- | :- | :- | :- | :- | :- | :- |
||Full name|name|Single Line of Text (300) Composite|+|Full name of lead (First name + Last Name + Middle name)|+|+|
||First name|firstname|Single Line of Text (50)|+|||+|
||Last name|lastname|Single Line of Text (50)|+|||+|
||Middle name|middlename|Single Line of Text (50)||||+|
||Job Title|jobtitle|Single Line of Text (100)||||+|

1. #### ***Usability and user interface considerations***

1. ## <a name="_toc531115000"></a><a name="_toc138859296"></a>**Column structure of normative reference information**
   1. ### <a name="_toc531115001"></a><a name="_toc138859297"></a>**Table N (Custom)**
      1. #### ***General***

|**Option**|**Enable / Disable**|
| :- | :- |
|Display Name||
|Plural Name||
|Schema name (Table)||
|Primary field (schema name)||
|Business process flows||
|Notes||
|Activities||
|Connections||
|Sending e-mail (if an e-mail field does not exist, one will be created)||
|Queues||
|Primary Image||
|Mail Merge||
|Document Management||
|Duplicate Detection||
|Allow Quick Create||
|Auditing||
|Access Teams||
|Enable for phone express||
|Enable for mobile||
|Ownership||
1. #### ***Form***

|**No**|**Display Name**|**Schema Name**|**Field Type**|**Requirement**|**Notes**|**Read Only**|**Searchable**|
| :- | :- | :- | :- | :- | :- | :- | :- |
|||||||||
|||||||||
|||||||||
|||||||||
|||||||||
|||||||||
|||||||||



<a name="_toc10136742"></a><a name="_toc10110927"></a><a name="_toc10136743"></a><a name="_toc10110928"></a><a name="_toc10136744"></a><a name="_toc10110929"></a><a name="_toc10136808"></a><a name="_toc10110993"></a><a name="_toc10136818"></a><a name="_toc10111003"></a><a name="_toc10136827"></a><a name="_toc10111012"></a><a name="_toc10136838"></a><a name="_toc10111023"></a><a name="_toc10136847"></a><a name="_toc10111032"></a><a name="_toc531115012"></a>
1. # <a name="_toc138859298"></a><a name="_hlk57025101"></a>**Security requirements (role model for access)**
   1. ## ` `**<a name="_toc138859299"></a>Hierarchy Business Unit in the system**



![](Aspose.Words.a98735c8-b7d5-43bf-83ad-365d5cfefcd7.015.png)
1. ## <a name="_toc138859300"></a>**Security roles**
Purpose of Security roles in Dynamics 365 is restricted and allows user to access Modules and Tables. By using Security roles, you can define the access level of the user in the system. 

**Access Levels:**

|None Selected|N/A|
| :- | :-: |
|User|U|
|Business Unit|BU|
|Parent-Child BU|BU+|
|Organisation|O|

**Access Teams:**

|Access Team 1|` `AT1|
| :- | :- |
|Access Team 2|` `AT2|
1. ### <a name="_toc138859301"></a>**Role 1**
This role will be assigned to sales representative.

|**Security Role: Sales Rep**|||||||
| :-: | :- | :- | :- | :- | :- | :- |
|**Table**|**Create**|**Read**|**Write**|**Delete**|**Assign**|**Share**|
|**Accounts**|U|O|U||||
|**Contacts**|U|O|U||||
|**Leads**|U|U|U||U||
|**Opportunities**|U|U|U||U|U|
|**Connections**|O|O|O||U|O|
|**Activities**|U|U|U|U|U||
|**Table N**|||||||
|**Table N**|||||||
|**Table N**|||||||
|Miscellaneous Privileges|||||||
|**Bulk Edit**|No||||||
|**Merge**|No||||||
|**Delete Audit Log**|No||||||
|**Delete Audit Record Cange History**|No||||||
|**View Audit History**|Yes||||||
1. ### <a name="_toc138859302"></a>**Role 2**
This role will be assigned to manager.

|**Security Role: P&L Manager**|||||||
| :-: | :- | :- | :- | :- | :- | :- |
|**Table**|**Create**|**Read**|**Write**|**Delete**|**Assign**|**Share**|
||||||||
||||||||
||||||||
||||||||
||||||||
|Miscellaneous Privileges|||||||
|**Bulk Edit**|No||||||
|**Merge**|No||||||
|**Delete Audit Log**|No||||||
|**Delete Audit Record Cange History**|No||||||
|**View Audit History**|Yes||||||
1.
1. # <a name="_toc531115016"></a><a name="_toc138859303"></a>**Additional functionality**
The template includes some sample sections. Additional sections can be added for your project needs, and some can be removed if not applied. This section could include more non-functional requirements, add-ins, ISV solutions, additional or advanced functionality that needed to be specified/configured separately.
1. ## <a name="_toc531968843"></a><a name="_toc531968850"></a><a name="_toc531968862"></a><a name="_toc531968889"></a><a name="_toc531968847"></a><a name="_toc531968814"></a><a name="_toc531968863"></a><a name="_toc531968809"></a><a name="_toc531968802"></a><a name="_toc531968873"></a><a name="_toc531968893"></a><a name="_toc531968796"></a><a name="_toc531968865"></a><a name="_toc531968805"></a><a name="_toc531968864"></a><a name="_toc531968811"></a><a name="_toc531968825"></a><a name="_toc531968801"></a><a name="_toc531968895"></a><a name="_toc531968869"></a><a name="_toc531968820"></a><a name="_toc531968791"></a><a name="_toc531968848"></a><a name="_toc531968826"></a><a name="_toc531968832"></a><a name="_toc531968883"></a><a name="_toc531968870"></a><a name="_toc531968874"></a><a name="_toc531968800"></a><a name="_toc531968894"></a><a name="_toc531968860"></a><a name="_toc531968812"></a><a name="_toc531968795"></a><a name="_toc531968827"></a><a name="_toc531968840"></a><a name="_toc531968804"></a><a name="_toc531968868"></a><a name="_toc531968853"></a><a name="_toc531968822"></a><a name="_toc531968833"></a><a name="_toc531968875"></a><a name="_toc531968834"></a><a name="_toc531968872"></a><a name="_toc531968892"></a><a name="_toc531968845"></a><a name="_toc531968884"></a><a name="_toc531968838"></a><a name="_toc531968849"></a><a name="_toc531968877"></a><a name="_toc531968885"></a><a name="_toc531968897"></a><a name="_toc531968821"></a><a name="_toc531968792"></a><a name="_toc531968839"></a><a name="_toc531968806"></a><a name="_toc531968867"></a><a name="_toc531968852"></a><a name="_toc531968837"></a><a name="_toc531968855"></a><a name="_toc531968817"></a><a name="_toc531968859"></a><a name="_toc531968842"></a><a name="_toc531968815"></a><a name="_toc531968794"></a><a name="_toc531968844"></a><a name="_toc531968816"></a><a name="_toc531968879"></a><a name="_toc531968835"></a><a name="_toc531968797"></a><a name="_toc531968878"></a><a name="_toc531968819"></a><a name="_toc531968880"></a><a name="_toc531968799"></a><a name="_toc531968824"></a><a name="_toc531968830"></a><a name="_toc531968854"></a><a name="_toc531968888"></a><a name="_toc531968857"></a><a name="_toc531968810"></a><a name="_toc531968807"></a><a name="_toc531968858"></a><a name="_toc531968829"></a><a name="_toc531968890"></a><a name="_toc531968882"></a><a name="_toc531968887"></a><a name="_toc531968831"></a><a name="_toc10136883"></a><a name="_toc10111068"></a><a name="_toc10136884"></a><a name="_toc10111069"></a><a name="_toc10136885"></a><a name="_toc10111070"></a><a name="_toc10136886"></a><a name="_toc10111071"></a><a name="_toc10136887"></a><a name="_toc10111072"></a><a name="_toc10136888"></a><a name="_toc10111073"></a><a name="_toc10136889"></a><a name="_toc10111074"></a><a name="_toc10136890"></a><a name="_toc10111075"></a><a name="_toc10136891"></a><a name="_toc10111076"></a><a name="_toc531115021"></a><a name="_toc138859304"></a>**Dynamics 365 App for Outlook**

1. ## <a name="_toc531115022"></a><a name="_toc138859305"></a>**Manage transactions with multiple currencies**
Currencies determine the prices for products in the product catalog and the cost of transactions, such as sales orders. If your customers are spread across geographies, add their currencies in Dynamics 365 to manage your transactions.
1. ## <a name="_toc531115023"></a><a name="_toc138859306"></a>**Duplication rules**
Detect duplicates:

- When a record is created or updated
- When Microsoft Dynamics 365 for Outlook goes from offline to online
- During data import

The max matchcode length is 450 symbols for each rule. Duplicate detection rules work based on access of user who creates a record, i.e. if user has access to see only his own opportunity duplicate detection rule will search for duplicates only from his opportunities. 
1. ### <a name="_toc531115024"></a><a name="_toc138859307"></a>**Account**
Base record type: Account

Matching Record Type: Account

Case-sensitive: No

Exclude inactive matching records: Yes

Duplicate Detection Rule Criteria (Fields): two different rules:

- Address: Street, Address: City, Address: State
- Account name, Address: City, Address: State
  1. ### <a name="_toc531115025"></a><a name="_toc138859308"></a>**Contact**
Base record type: Contact

Matching Record Type: Contact

Case-sensitive: No

Exclude inactive matching records: Yes

Duplicate Detection Rule Criteria (Fields) – two different rules:

- Cell phone (Ignore blank values)
- Email (Ignore blank values)
  1. ### <a name="_toc531115026"></a><a name="_toc138859309"></a>**Lead**
Base record type: Lead

Matching Record Type: Lead

Case-sensitive: No

Exclude inactive matching records: Yes

Duplicate Detection Rule Criteria (Fields): 

- Same address(Ignore blank values)

Matching Record Type: Opportunity

Case-sensitive: No

Exclude inactive matching records: Yes

Duplicate Detection Rule Criteria (Fields): Address: CountryCountry/Region, Address: City, Address: State, Address: Street (Ignore blank values)
1. ## <a name="_toc138859310"></a><a name="_toc531115028"></a>**Support for mobile devices**
1. ## <a name="_toc138859311"></a>**Multilingual support**
1. ## <a name="_toc138859312"></a>**Editable grids**

Switch on editable grid control on the table level and replicate logic from the form
1. ## <a name="_toc138859313"></a>**System notifications**
   1. ### <a name="_toc138859314"></a>**Email notifications**
   1. ### <a name="_toc138859315"></a>**Push Notifications**
   1. ### <a name="_toc138859316"></a>**In-App Notifications**
1. ## <a name="_toc138859317"></a>**Scan business card**
1. ## <a name="_toc138859318"></a>**Compliance**
1. ## <a name="_toc138859319"></a>**Dynamics 365 Sales Insights (Microsoft solution)**
1. ## <a name="_toc138859320"></a>**Enhanced Search to improve search results and performance**

1. # <a name="_toc531115031"></a><a name="_toc138859321"></a>**Reporting and analytics**
   1. ## <a name="_toc531115032"></a><a name="_toc138859322"></a>**Reports**
Please cover Financial and/or Operation reporting strategies in these sections.
1. ### <a name="_toc138859323"></a>**Report 1**
   1. #### ***Purpose***
   1. #### ***Content***
   1. #### ***Field Mapping***
   1. #### ***Filter***
   1. #### ***Report Parameters***
   1. #### ***Report View***
1. ## <a name="_toc138859324"></a>**Dashboards**
Please include Dashboard and workspaces in this section as well as embedded Power BI.

|**Report/Dashboard Name**|**Purpose**|**Content**|**Consumers**|**Data Required**|
| :-: | :-: | :-: | :-: | :-: |
||||||

1. ## <a name="_toc138859325"></a>**Data warehousing strategy**
Please cover here the requirements for Azure Synapse link, Azure Data Lake, and BYOD (Bring your own Database) for Finance & Operations applications. Also, think about the Fabric strategy.






<a name="_toc531115034"></a>Technical design document


1. # <a name="_toc138859326"></a>**Integration**
   1. ## <a name="_toc138859327"></a><a name="_toc531115035"></a>**Logging mechanism**

1. ## <a name="_toc138859328"></a>**Integration 1**
System explanation / Business Use / Criticality / Error handling and Fault tolerance / Performance and Scalability / Security and Privacy / Middleware / Etc.
1. ### <a name="_toc531115036"></a><a name="_toc138859329"></a>**Scope**
Integration scope.
1. ### <a name="_toc138859330"></a>**Interface design**
Please include your integration architecture scheme diagram.
1. #### ***Overview***
1. #### ***Components***
1. #### ***Data Structure***
1. #### ***Mapping***
1. #### ***Request Format***
1. #### ***Response Format***


1. # <a name="_toc531115050"></a><a name="_toc138859331"></a>**Migration**
Use this section to work on the data migration strategy for Setup/Configuration, Master data, Historical data.
|||Page | **279**|
| :- | :-: | -: |

