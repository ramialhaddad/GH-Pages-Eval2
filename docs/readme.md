FUNCTIONAL / TECHNICAL DESIGN DOCUMENT

Project:

Prepared by:

2023

Name of the parties’ POC

Partner

|  |  |  |  |
| --- | --- | --- | --- |
| Title | Name | Email | Contact Number |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |

Customer

|  |  |  |  |
| --- | --- | --- | --- |
| Title | Name | Email | Contact Number |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |

Sheet accounting changes

| Version | Changes | The Initiator | Date |
| --- | --- | --- | --- |
| 0.0 | Initial Draft | First Last name | DD/MM/YY |

**Table of Contents**

[1 Introduction 7](#_Toc138859263)

[1.1 The composition of the document 7](#_Toc138859264)

[1.2 Abbreviations 7](#_Toc138859265)

[1.3 Transcript schemes of business processes 7](#_Toc138859266)

[2 Project overview 9](#_Toc138859267)

[2.1 Scope 9](#_Toc138859268)

[3 Organization structure and functional responsibilities in the solution 10](#_Toc138859269)

[3.1 Department description 1 10](#_Toc138859270)

[3.1.1 Unit 1 10](#_Toc138859271)

[3.1.2 Unit 2 10](#_Toc138859272)

[3.2 Department description 2 10](#_Toc138859273)

[3.2.1 Unit 1 10](#_Toc138859274)

[3.2.2 Unit 2 10](#_Toc138859275)

[4 Description of business processes 11](#_Toc138859276)

[4.1 Common information about organization process 11](#_Toc138859277)

[4.2 Accounts 11](#_Toc138859278)

[4.2.1 Create Account 11](#_Toc138859279)

[4.3 Leads 13](#_Toc138859280)

[4.3.1 Business process N 13](#_Toc138859281)

[5 Architecture solution design 13](#_Toc138859282)

[5.1 Data requirements (conceptual object model) 13](#_Toc138859283)

[5.1.1 Scalability and performance considerations 13](#_Toc138859284)

[5.2 Table structure 14](#_Toc138859285)

[5.2.1 Table options that can only be enabled 14](#_Toc138859286)

[5.2.2 Enable or disable table options 14](#_Toc138859287)

[5.2.3 Field properties 15](#_Toc138859288)

[5.2.4 Possible data types for a field 16](#_Toc138859289)

[5.2.5 Data naming (specify names of fields) 17](#_Toc138859290)

[5.2.6 Common fields for all tables 18](#_Toc138859291)

[5.3 Column structure of business objects 19](#_Toc138859292)

[5.3.1 Account (OOB) 19](#_Toc138859293)

[5.3.2 Contact (OOB) 20](#_Toc138859294)

[5.3.3 Lead (OOB) 21](#_Toc138859295)

[5.4 Column structure of normative reference information 22](#_Toc138859296)

[5.4.1 Table N (Custom) 22](#_Toc138859297)

[6 Security requirements (role model for access) 23](#_Toc138859298)

[6.1 Hierarchy Business Unit in the system 23](#_Toc138859299)

[6.2 Security roles 23](#_Toc138859300)

[6.2.1 Role 1 23](#_Toc138859301)

[6.2.2 Role 2 24](#_Toc138859302)

[7 Additional functionality 25](#_Toc138859303)

[7.1 Dynamics 365 App for Outlook 25](#_Toc138859304)

[7.2 Manage transactions with multiple currencies 25](#_Toc138859305)

[7.3 Duplication rules 25](#_Toc138859306)

[7.3.1 Account 25](#_Toc138859307)

[7.3.2 Contact 25](#_Toc138859308)

[7.3.3 Lead 26](#_Toc138859309)

[7.4 Support for mobile devices 26](#_Toc138859310)

[7.5 Multilingual support 26](#_Toc138859311)

[7.6 Editable grids 26](#_Toc138859312)

[7.7 System notifications 27](#_Toc138859313)

[7.7.1 Email notifications 27](#_Toc138859314)

[7.7.2 Push Notifications 27](#_Toc138859315)

[7.7.3 In-App Notifications 27](#_Toc138859316)

[7.8 Scan business card 27](#_Toc138859317)

[7.9 Compliance 27](#_Toc138859318)

[7.10 Dynamics 365 Sales Insights (Microsoft solution) 27](#_Toc138859319)

[7.11 Enhanced Search to improve search results and performance 27](#_Toc138859320)

[8 Reporting and analytics 28](#_Toc138859321)

[8.1 Reports 28](#_Toc138859322)

[8.1.1 Report 1 28](#_Toc138859323)

[8.2 Dashboards 28](#_Toc138859324)

[8.3 Data warehousing strategy 28](#_Toc138859325)

[9 Integration 30](#_Toc138859326)

[9.1 Logging mechanism 30](#_Toc138859327)

[9.2 Integration 1 30](#_Toc138859328)

[9.2.1 Scope 30](#_Toc138859329)

[9.2.2 Interface design 30](#_Toc138859330)

[10 Migration 31](#_Toc138859331)

# Introduction

## The composition of the document

The functional design document (FDD) contains:

* Scope
* Organization structure: The functional management of departments for creating a security model of the solution
* Business process: The schema of business process in the solution
* Architecture solution design: Object model, Data model
* Additional customization
* Security Roles
* Integration
* Data Migration

## Abbreviations

| Abbreviations | Transcript |
| --- | --- |
| Plug-in | Plug-in is a software component that adds a specific feature to an existing software application |
| POC | Point of contact |
| FDD | Functional Design Document |
| TDD | Technical Design Document |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |
|  |  |

## Transcript schemes of business processes

|  |  |
| --- | --- |
| Symbol | Comment |
| ![](data:image/x-emf;base64...) | Division of the company using the system and has in its composition subordinates’ other units. |
| ![](data:image/x-emf;base64...) | Department of the company using the system. |
| ![](data:image/x-emf;base64...) | Department of the company, non-automation |
| ![](data:image/x-emf;base64...) | Start of processes |
| ![](data:image/x-emf;base64...) | End of processes |
| ![](data:image/x-emf;base64...) | Link for process «» |
| ![](data:image/x-emf;base64...) | Operation «» |
| ![](data:image/x-emf;base64...) | Integration operation «» |
| ![](data:image/x-emf;base64...) | The logical question «» |
| ![](data:image/x-emf;base64...) | The following function starts only after the end of a previous |
| ![](data:image/x-emf;base64...) | After the end of the function, the following functions are run in parallel |

# Project overview

## Scope

The scope of the service includes the following:

*Usually, this section contains the FitGap analysis worksheet – see template.*

*Sometimes, the functional design document doesn’t contain all out-of-band features that are available for Dynamics 365 but only changes or critical functions which are going to be used.*

# Organization structure and functional responsibilities in the solution

![](data:image/x-emf;base64...)

## Department description 1

### Unit 1

### Unit 2

## Department description 2

### Unit 1

### Unit 2

# Description of business processes

## Common information about organization process

This document includes the following business processes to be automated:

1. Accounts
2. Leads
3. Business process N

Model business processes contained in this document consists of the following components:

* Business process diagram - process diagrams with detailed level of functions and performers;
* Tables of functions / operations - a text description of the business functions / operations, including a description of incoming / outgoing information and performers

## Accounts

### Create Account

#### Process Flow

![](data:image/x-emf;base64...)

|  |  |  |
| --- | --- | --- |
| **Step Id** | **Description** | **Remarks** |
| ACC-NEW-01 | Manual Check if ‘Account’ Exists in the system? | User needs to manually check if the ‘Account’ profile which he / she is going to create has existed in the system already. |
| ACC-NEW-02 | Exist? | Based on the input key words, which have been pre-defined as searchable, the system will filter out the similar records to users. |
| ACC-NEW-03 | Open existing Account Card | If the account exists already, the system will open the existing account and abort the creation process by user. |
| ACC-NEW-04 | Manual Create ‘Account’ Profile in the system. | User needs to manually create the ‘Account Profile in the system if it doesn’t exist already. |
| ACC-NEW-05 | Duplicate Detect based on the rule | The system will do the duplication detect based on the rule |
| ACC-NEW-06 | Duplicate? | If duplicate records are found in the system, abort the creation process and go to step ACC-NEW-03. |
| ACC-NEW-07 | Account Creation Process | If duplicated account Profile is not found in the system, then Account profile is created in the system. |

#### Functional design

| **ID** | **Description** | **Rules / Examples/ Comments** |
| --- | --- | --- |
|  |  |  |
|  |  |  |

## Leads

### Business process N

#### Process flow

![Set customer credit limit process flow diagram.](data:image/png;base64...)

| **Step Id** | **Description** | **Remarks** |
| --- | --- | --- |
|  |  |  |
|  |  |  |
|  |  |  |
|  |  |  |

#### Functional design

| **ID** | **Description** | **Rules / Examples/ Comments** |
| --- | --- | --- |
|  |  |  |
|  |  |  |

# Architecture solution design

## Data requirements (conceptual object model)

### Scalability and performance considerations

Please include metadata relationships in these sections. Also, it would be helpful to have indexes which will be included in the tables. Data archrival strategy / long retention strategy

## Table structure

### Table options that can only be enabled

| Option | Comments |
| --- | --- |
| Business process flows | Create business process flows for this table. More information: [Create a business process flow to standardize processes](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/customize/create-business-process-flow) |
| Notes | Append notes to records for this table. Notes include the ability to add attachments. |
| Activities | Associate activities to records for this table. |
| Connections | Use the connections feature to show how records for this table have connections to records of other tables that also have connections enabled. |
| Sending e-mail (if an e-mail field does not exist, one will be created) | Send emails using an email address stored in one of the fields for this table. If a Single Line of Text field with format set to email doesn’t already exist for this table, a new one will be created when you enable sending email. |
| Queues | Use the table with queues. Queues improve routing and sharing of work by making records for this table available in a central place that everyone can access. |

### Enable or disable table options

| Option | Comments |
| --- | --- |
| Primary Image | System tables that support images will already have an **Image** field. You can choose whether to display data in this field as the image for the record by setting this field to **[None]** or **Default Image**.  For custom tables you must first create an image field. Each table can have only one image field. After you create one, you can change this setting to set the primary image. More information: [Image fields](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/customize/types-of-fields#BKMK_ImageFields) |
| Mail Merge | User can use this table with mail merge. |
| Document Management | After other tasks have been performed to enable document management for your organization, enabling this feature allows for this table to participate in integration with SharePoint. |
| Duplicate Detection | If duplicate detection is enabled for your organization, enabling this allows you to create duplicate detection rules for this table. |
| Allow Quick Create | After you have created and published a **Quick Create Form** for this table, User will have the option to create a new record using the **Create** button in the navigation pane.  When this is enabled for a custom activity table, the custom activity will be visible in the group of activity tables when people use the **Create** button in the navigation pane. However, because activities don’t support quick create forms, the main form will be used when the custom table icon is clicked. |
| Auditing | When auditing is enabled for your organization, this allows for changes to table records to be captured over time. When you enable auditing for an table, auditing is also enabled on all its fields. You can select or clear fields that you want to enable auditing on. |
| Access Teams | Create team templates for this table. |
| Enable for phone express | Make this table available to the Dynamics 365 for phones app. |
| Enable for mobile | Make this table available to the Dynamics 365 for phones and tablets apps. You also have the option to make this table **Read-only in mobile**.  If the forms for an table require an extension not supported in Dynamics 365 for phones and tablets, such as iFrame or web resource controls, use this setting to ensure that mobile app users can’t edit the data for these tables.  **Important:** If you have previously installed any portal solution, to create a case in the Customer Service Hub or to use the Merge cases command, you must turn off the **Read-only in mobile option** for the Case table. |

### Field properties

| Option | Comments |
| --- | --- |
| Display Name | The name that appears as a label in the heading for lists where this attribute is included. It is also the default label when this field is shown in a form, but the label text in each form can be edited separately. |
| Name | This field is prepopulated based on the **Display Name** you entered. It includes the solution publisher customization prefix. You can change the **Display Name** later, but the **Name** can’t be changed after the field is saved. |
| Field Requirement | There are three options:  - **Optional**  The record can be saved even if there is no data in this field.  - **Business Recommended**  The record can be saved even if there is no data in this field. However, a blue asterisk appears next to the field to indicate it is important.  - **Business Required**  The record can’t be saved if there is no data in this field.  Be careful when you make fields business required. People will resist using the application if they can’t save records because they lack the correct information to enter into a required field. People may enter incorrect data simply to save the record and get on with their work.  You can use business rules or form scripts to change the requirement level as the data in the record changes as people work on it. |
| Searchable | When a field is searchable it appears in Advanced Find and is available when customizing views. Use this when there are fields for the table that you don’t use. Setting this to **No** will reduce the number of options shown to user using advanced find. |
| Field Security | For custom fields, enable this to allow this field to participate in field-level security. |
| Auditing | Disable this so that data in this field won’t be included with auditing data. |
| Description | Enter text that will appear as a tooltip when the field is displayed in a form. |

### Possible data types for a field

| Data Type | Notes |
| --- | --- |
| Single Line of Text | The following formats are available:   * + **E-mail**. This opens a new e-mail message in the default e-mail software when clicked and also validates an email address.   + **Text**. This creates a text box.   + **Text area**. This creates a scrolling text box.   + **URL**. This opens the URL in the user's default browser when clicked and validates (or adds) a valid protocol (HTTP, HTTPS, FTP, FTPS, OneNote, and TEL) are allowed.   + **Ticker Symbol**. This creates a stock ticker symbol in all capital letters. Click the symbol to open information about the stock in the user's default browser. By default, the MSN website opens.   + Phone. This creates a link that enables Skype or Microsoft Lync users to initiate a call by using the linked number. |
| Option Set | Select an existing option set or define a new one. |
| MultiSelect Option Set | This field provides a set of options, where multiple options can be selected. When added to a form, this field uses a control for users to select multiple options. |
| Two Options | After creating this field, configure it in the form to which it was added. In the form, select whether the field is displayed as option buttons (also known as radio buttons), a check box, or a list. |
| Image | Each table can have one image field. When an table has an image field it can be configured to display the image for the record in the application. |
| Whole Number | The following formats are available for this field:   * + **None.** The defaults are integer values between -2,147,483,648 and 2,147,483,648, although you can set different minimum and maximum values.   + **Duration.** This creates a drop-down list box with values in minutes, hours, and days.   + **Time Zone.** This creates a drop-down list box with options for every available time zone.   + Language. This creates a drop-down list box with options for every language that your organization has made available for users. |
| Floating Point Number | Select up to 5 precision points. You can set the minimum and maximum values. |
| Decimal Number | Select up to 10 decimal points. You can set the minimum and maximum values. |
| Currency | When you add a currency field to an table, a corresponding (Base) field is also created. The (Base) field also has a currency data type.  If the table does not already have a field with a currency data type, two additional fields are created:   * + **Currency.** A lookup data type whose value must be set before you can set the value of a field with a currency data type.   + **Exchange Rate**. This has a decimal number data type. |
| Multiple Lines of Text | This is a scrolling text box. You can set the maximum number of characters for this field. |
| Date and Time | There are two formats: date only, or date and time. |
| Lookup | You can create a lookup field using an table relationship that has already been created, but not yet used with another lookup field. If you create a lookup field in an table form, the relationship is automatically generated. A lookup field is created as a relationship field. |

### Data naming (specify names of fields)

| Option | Description |
| --- | --- |
| Publisher Display Name | Default publisher |
| Name Publisher (schema name) | new |
| Prefix | new |
| Option Value Prefix | 10000 |
| Data type – string, money, all types of numbers - schema name | Logical name of fields. For example: Field name – Account; Schema name – new\_account |
| Data type – option set - schema name | Logical name of fields ***+ code***. For example: Field name – Account type; Schema name – new\_accounttype**code** |
| Data type – two options (bit) - schema name | ***IS +*** Logical name of fields. For example: Field name – Partner support project; Schema name – new\_***is***partnerproject |
| Data type – date - schema name | Logical name of fields ***+ date***. For example: Field name – Payment date; Schema name – new\_payment***date*** |
| Data type – lookup - schema name | Logical name of fields ***+ id***. For example: Field name – Contact; Schema name – new\_contact***id*** |
| schema name | All schema name should have small letters |

### Common fields for all tables

| No | Display Name | Schema Name | Field Type | Requirement | Notes | Read Only |
| --- | --- | --- | --- | --- | --- | --- |
|  | Owner | ownerid | Lookup (user/team) | + | Owner is only for User/Team ownership type |  |
|  | Modified By | modifiedby | Lookup (user) | + | Shows who last updated the record. | + |
|  | Modified On | modifiedon | Date and Time | + | Shows the date and time when the record was last updated. The date and time are displayed in the time zone selected in Microsoft Dynamics 365 options. | + |
|  | Created By | createdby | Lookup (user) | + | Shows who created the record. | + |
|  | Created On | createdon | Date and Time | + | Shows the date and time when the record was created. The date and time are displayed in the time zone selected in Microsoft Dynamics 365 options. | + |
|  | Status | statecode | States:  0: Active  1: Inactive |  | By default if not we specified for a concrete table (for example Opportunity) |  |
|  | Status Reason | statuscode | States:  1: Active  2: Inactive |  | By default if not we specified for a concrete table (for example Opportunity) |  |

## Column structure of business objects

### Account (OOB)

#### General

| Option | Enable / Disable |
| --- | --- |
| Display Name | Account |
| Plural Name | Accounts |
| Schema name (Table) | account |
| Primary field (schema name) | name |
| Business process flows |  |
| Notes | Yes |
| Activities | Yes |
| Connections | Yes |
| Sending e-mail (if an e-mail field does not exist, one will be created) | Yes |
| Queues | Yes |
| Primary Image | Yes |
| Mail Merge | Yes |
| Document Management |  |
| Duplicate Detection | Yes |
| Allow Quick Create | Yes |
| Auditing | Yes |
| Access Teams |  |
| Enable for phone express | Yes |
| Enable for mobile | Yes |
| Ownership | User or Team |

#### Form (Main)

Visible for all roles

| No | Display Name | Schema Name | Field Type | Requirement | Notes | Read Only | Searchable |
| --- | --- | --- | --- | --- | --- | --- | --- |
|  | Account Name | Name | Single Line of Text (128) | + |  |  | + |
|  | Account type | accounttype | Option set:  1.Prospect  2.Customer | + |  |  | + |
|  | Address | Address1\_composite | Multiline (1000) |  | Combine City, Street, ZIP, State, Country/Region on one line | + | + |

#### Usability and user interface considerations

### Contact (OOB)

#### General

| Option | Enable / Disable |
| --- | --- |
| Display Name | Contact |
| Plural Name | Contacts |
| Schema name (Table) | contact |
| Primary field (schema name) | fullname |
| Business process flows |  |
| Notes | Yes |
| Activities | Yes |
| Connections | Yes |
| Sending e-mail (if an e-mail field does not exist, one will be created) | Yes |
| Queues | Yes |
| Primary Image | No |
| Mail Merge | Yes |
| Document Management |  |
| Duplicate Detection | Yes |
| Allow Quick Create | Yes |
| Auditing | Yes |
| Access Teams |  |
| Enable for phone express | Yes |
| Enable for mobile | Yes |

#### Form (Main)

| No | Display Name | Schema Name | Field Type | Requirement | Notes | Read Only | Searchable |
| --- | --- | --- | --- | --- | --- | --- | --- |
|  | Full name | name | Single Line of Text (300) Composite | + | Full name of client (First name + Last Name + Middle name) | + | + |
|  | First name | firstname | Single Line of Text (50) | + |  |  | + |
|  | Last name | lastname | Single Line of Text (50) | + |  |  | + |
|  | Middle name | middlename | Single Line of Text (50) |  |  |  | + |
|  | Job Title | jobtitle | Single Line of Text (100) |  |  |  | + |

#### Usability and user interface considerations

### Lead (OOB)

#### General

| Option | Enable / Disable |
| --- | --- |
| Display Name | Lead |
| Plural Name | Leads |
| Schema name (Table) | lead |
| Primary field (schema name) | name |
| Business process flows |  |
| Notes | Yes |
| Activities | Yes |
| Connections | Yes |
| Sending e-mail (if an e-mail field does not exist, one will be created) | Yes |
| Queues | Yes |
| Primary Image | No |
| Mail Merge | Yes |
| Document Management |  |
| Duplicate Detection | Yes |
| Allow Quick Create | Yes |
| Auditing | Yes |
| Access Teams |  |
| Enable for phone express | Yes |
| Enable for mobile | Yes |

#### Form (Main)

| No | Display Name | Schema Name | Field Type | Requirement | Notes | Read Only | Searchable |
| --- | --- | --- | --- | --- | --- | --- | --- |
|  | Full name | name | Single Line of Text (300) Composite | + | Full name of lead (First name + Last Name + Middle name) | + | + |
|  | First name | firstname | Single Line of Text (50) | + |  |  | + |
|  | Last name | lastname | Single Line of Text (50) | + |  |  | + |
|  | Middle name | middlename | Single Line of Text (50) |  |  |  | + |
|  | Job Title | jobtitle | Single Line of Text (100) |  |  |  | + |

#### Usability and user interface considerations

## Column structure of normative reference information

### Table N (Custom)

#### General

| Option | Enable / Disable |
| --- | --- |
| Display Name |  |
| Plural Name |  |
| Schema name (Table) |  |
| Primary field (schema name) |  |
| Business process flows |  |
| Notes |  |
| Activities |  |
| Connections |  |
| Sending e-mail (if an e-mail field does not exist, one will be created) |  |
| Queues |  |
| Primary Image |  |
| Mail Merge |  |
| Document Management |  |
| Duplicate Detection |  |
| Allow Quick Create |  |
| Auditing |  |
| Access Teams |  |
| Enable for phone express |  |
| Enable for mobile |  |
| Ownership |  |

#### Form

| No | Display Name | Schema Name | Field Type | Requirement | Notes | Read Only | Searchable |
| --- | --- | --- | --- | --- | --- | --- | --- |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |

# Security requirements (role model for access)

## Hierarchy Business Unit in the system

![](data:image/x-emf;base64...)

## Security roles

Purpose of Security roles in Dynamics 365 is restricted and allows user to access Modules and Tables. By using Security roles, you can define the access level of the user in the system.

**Access Levels:**

|  |  |
| --- | --- |
| None Selected | N/A |
| User | U |
| Business Unit | BU |
| Parent-Child BU | BU+ |
| Organisation | O |

**Access Teams:**

|  |  |
| --- | --- |
| Access Team 1 | AT1 |
| Access Team 2 | AT2 |

### Role 1

This role will be assigned to sales representative.

| **Security Role: Sales Rep** | | | | | | |
| --- | --- | --- | --- | --- | --- | --- |
| **Table** | **Create** | **Read** | **Write** | **Delete** | **Assign** | **Share** |
| **Accounts** | U | O | U |  |  |  |
| **Contacts** | U | O | U |  |  |  |
| **Leads** | U | U | U |  | U |  |
| **Opportunities** | U | U | U |  | U | U |
| **Connections** | O | O | O |  | U | O |
| **Activities** | U | U | U | U | U |  |
| **Table N** |  |  |  |  |  |  |
| **Table N** |  |  |  |  |  |  |
| **Table N** |  |  |  |  |  |  |
| Miscellaneous Privileges | | | | | | |
| **Bulk Edit** | No |  |  |  |  |  |
| **Merge** | No |  |  |  |  |  |
| **Delete Audit Log** | No |  |  |  |  |  |
| **Delete Audit Record Cange History** | No |  |  |  |  |  |
| **View Audit History** | Yes |  |  |  |  |  |

### Role 2

This role will be assigned to manager.

| **Security Role: P&L Manager** | | | | | | |
| --- | --- | --- | --- | --- | --- | --- |
| **Table** | **Create** | **Read** | **Write** | **Delete** | **Assign** | **Share** |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |
| Miscellaneous Privileges | | | | | | |
| **Bulk Edit** | No |  |  |  |  |  |
| **Merge** | No |  |  |  |  |  |
| **Delete Audit Log** | No |  |  |  |  |  |
| **Delete Audit Record Cange History** | No |  |  |  |  |  |
| **View Audit History** | Yes |  |  |  |  |  |

# Additional functionality

The template includes some sample sections. Additional sections can be added for your project needs, and some can be removed if not applied. This section could include more non-functional requirements, add-ins, ISV solutions, additional or advanced functionality that needed to be specified/configured separately.

## Dynamics 365 App for Outlook

## Manage transactions with multiple currencies

Currencies determine the prices for products in the product catalog and the cost of transactions, such as sales orders. If your customers are spread across geographies, add their currencies in Dynamics 365 to manage your transactions.

## Duplication rules

Detect duplicates:

* When a record is created or updated
* When Microsoft Dynamics 365 for Outlook goes from offline to online
* During data import

The max matchcode length is 450 symbols for each rule. Duplicate detection rules work based on access of user who creates a record, i.e. if user has access to see only his own opportunity duplicate detection rule will search for duplicates only from his opportunities.

### Account

Base record type: Account

Matching Record Type: Account

Case-sensitive: No

Exclude inactive matching records: Yes

Duplicate Detection Rule Criteria (Fields): two different rules:

* Address: Street, Address: City, Address: State
* Account name, Address: City, Address: State

### Contact

Base record type: Contact

Matching Record Type: Contact

Case-sensitive: No

Exclude inactive matching records: Yes

Duplicate Detection Rule Criteria (Fields) – two different rules:

* Cell phone (Ignore blank values)
* Email (Ignore blank values)

### Lead

Base record type: Lead

Matching Record Type: Lead

Case-sensitive: No

Exclude inactive matching records: Yes

Duplicate Detection Rule Criteria (Fields):

* Same address(Ignore blank values)

Matching Record Type: Opportunity

Case-sensitive: No

Exclude inactive matching records: Yes

Duplicate Detection Rule Criteria (Fields): Address: CountryCountry/Region, Address: City, Address: State, Address: Street (Ignore blank values)

## Support for mobile devices

## Multilingual support

## Editable grids

Switch on editable grid control on the table level and replicate logic from the form

## System notifications

### Email notifications

### Push Notifications

### In-App Notifications

## Scan business card

## Compliance

## Dynamics 365 Sales Insights (Microsoft solution)

## Enhanced Search to improve search results and performance

# Reporting and analytics

## Reports

Please cover Financial and/or Operation reporting strategies in these sections.

### Report 1

#### Purpose

#### Content

#### Field Mapping

#### Filter

#### Report Parameters

#### Report View

## Dashboards

Please include Dashboard and workspaces in this section as well as embedded Power BI.

| **Report/Dashboard Name** | **Purpose** | **Content** | **Consumers** | **Data Required** |
| --- | --- | --- | --- | --- |
|  |  |  |  |  |

## Data warehousing strategy

Please cover here the requirements for Azure Synapse link, Azure Data Lake, and BYOD (Bring your own Database) for Finance & Operations applications. Also, think about the Fabric strategy.

Technical design document

# Integration

## Logging mechanism

## Integration 1

System explanation / Business Use / Criticality / Error handling and Fault tolerance / Performance and Scalability / Security and Privacy / Middleware / Etc.

### Scope

Integration scope.

### Interface design

Please include your integration architecture scheme diagram.

#### Overview

#### Components

#### Data Structure

#### Mapping

#### Request Format

#### Response Format

# Migration

Use this section to work on the data migration strategy for Setup/Configuration, Master data, Historical data.
