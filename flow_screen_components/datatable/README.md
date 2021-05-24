# Datatable

Lightning Web Component for Flow Screens:       **Datatable**

**This component allows the user to configure and display a datatable in a Flow screen.**

Additional components packaged with this LWC:

                Apex Classes:       ers_QueryNRecords
                                    ers_QueryNRecordsTest
                                    ers_DatatableController 
                                    ers_DatatableControllerTest

                LWCs:               ers_comboboxColumnType
                                    ers_customLightningDatatable
                                    ers_datatableUtils
                                    ers_datatableCPE
                                    ers_richTextColumnType

                StaticResources:    ers_customLightningDatatableStyles

                Flows:              Datatable_Configuration_Wizard

                Permission Set:     USF Flow Screen Component - Datatable          
                                                  
**Documentation:**  https://unofficialsf.com/datatable-lightning-web-component-for-flow-screens-2/ 
  
**Created by:**	Eric Smith  
**Date:**		2019 - 2021
  
LinkedIn: 	https://www.linkedin.com/in/ericrsmith2  
Salesforce: https://trailblazer.me/id/ericsmith  
Blog:		https://ericsplayground.wordpress.com/blog/  
Twitter: 	https://twitter.com/esmith35  

---
**You must install these components FIRST in order to install and use the Datatable component**     
FlowActionsBasePack Version 2.17 or later  
FlowScreenComponentsBasePack Version 2.2.1 or later  
  
Both Base Packs are available here:   
https://unofficialsf.com/flow-action-and-screen-component-basepacks/
  
---
**Install Datatable**  
[Version 3.2.1 (Production or Developer)](https://login.salesforce.com/packaging/installPackage.apexp?p0=04t5G0000047xH8QAI)   
[Version 3.2.1 (Sandbox)](https://test.salesforce.com/packaging/installPackage.apexp?p0=04t5G0000047xH8QAI)
 
---
**Starting with the Winter '21 Release, Salesforce requires that a User's Profile or Permission Set is given specific permission to access any @AuraEnabled Apex Method.**  

Release Notes: https://releasenotes.docs.salesforce.com/en-us/winter21/release-notes/rn_lc_restrict_apex_authenticated_users.htm  

This will affect any Aura or Lightning Web Component that uses @AuraEnabled Apex Classes.  

In order to use **datatable**, permission must be given to access the following Apex Classes:  

    ers_QueryNRecords   
    ers_DatatableController  

A Permission Set (**USF Flow Screen Component - Datatable**) is included with the install package.  
    
---
# Release Notes
 
## 05/18/21 -  Eric Smith -    Version 3.2.1 
**Updates:** 
-   Picklist values can now be restricted to a single record type 
 
**Bug Fixes:** 
-   Text formula fields will now wrap correctly (This had regressed in v3.2.0) 
-   Output Selected Rows is no longer null if the screen containing the Datatable also has a Section 
 
## 05/03/21 -  Eric Smith -    Version 3.2.0 
**Updates:** 
-   Picklist fields are now editable.  Big thanks to Jerry Poon and Guillaume Davies.
    (Does not yet support Dependent picklists nor filtering by Record Type)
-   Changed Table Header font from 1.5em to 1.2em to match the format of List Views
-   Renamed components used by Datatable to reduce conflicts and allow easier upgrading from older versions

**Bug Fixes:**
-   Do not display a header if there is a Header Label value but the Display Table Header attribute is not checked
-   Make output attributes available to visibility filters (this was inadvertantly removed from some prior releases)
-   Better handling of number & percent fields from different locales (Thanks to GDuboc-hub)
    (Edited percent fields must be the actual number ie: .25 = 25%)
    (Edited percent fields lose 2 decimal places during the edit from what is defined for the field)
-   Edited date fields will stay in the User's local time-zone rather than switching to UTC

## 04/15/21 -  Eric Smith -    Version 3.1.1 
**Updates:** 
-   Moved the "Display ALL Objects for Selection" choice in the CPE from Advanced to Data Source
-   Added an attribute to hide all column header actions such as Sort, Clip/Wrap Text and Filters
-   If Multi-Currency is enabled, convert currency field values to the User's currency (Thanks to Novarg1)

**Bug Fixes:**
-   Text formula fields will now wrap correctly
-   Display ALL Objects for Selection attribute is now persistent
-   Input data is Apex-Defined attribute is now persistent
-   The number of pre-selected rows will now not exceed the maximum number of records to be displayed attribute value
-   Don't require the key field to be explicitly listed in the Column Edits attribute for Apex Defined Objects
-   Clear Selection button will no longer appear on single row tables when Disallow row selection is checked
-   Clear Selection button will clear the Output Selected Record String for Apex Defined Objects
-   Fixed Column Filter on Checkbox Fields when the filter value is 'false' 
-   Fixed vertical alignment of table header text
  
## 02/27/21 -  Eric Smith -    Version 3.0.10 
**Updates:** 
-   Record links updated to support a Flow running in a Community
-   Added a new Table Behavior option to specify if Links should open in the same Tab
-   Allow the use of a Flow variable to set the Maximum Number of Rows value 
-   Changed display of error messages to match Salesforce standard
-   Allow full TypeAttibutes for Date fields (This will switch datetime fields to UTC)
-   Added a Permission Set that gives access to the @AuraEnabled Apex Classes that are part of the Datatable Flow Screen LWC
  
**Bug Fixes:**
-   Fixed links when running in a Sandbox whose name started with the letter c
-   Stop requiring Checkbox column if any columns are selected for editing 
-   Set the Number of Rows Selected to 0 when clearing the row selections
-   Retain the setting when clearing a checkbox in the CPE
-   Fixed error when trying to exit the CPE after selecting the Apex Defined Object option
-   Fixed delay when selecting a large (>200) number of records
-   Fixed delay when editing multiple (>20) number of records
-   Fixed issue with being unable to edit Apex-Defined columns unless Type was specified
-   Made sure that the Key Field could not be edited
-   Allow regular Textarea fields of 255 characters or less to be edited
  
## 01/19/21 -  Eric Smith -    Version 3.0.9 
**Updates:** 
-   Add option to Display Row Numbers (default=false)
-   Allow setting of Table Header for Apex Defined Objects
-   Display the current Version # at the bottom of the CPE
  
**Bug Fixes:**
-   Allow a TypeAttribute to set the Maximum number of decimal places to display to be less than the field default Minimum
-   Fix initial attribute display in the CPE when using an Apex Defined Object
-   Fix attribute corruption when updating multiple times
  
## 01/08/21 -  Eric Smith -    Version 3.0.8 
**Updates:** 
-   Relocate to correct packaging org
-   Users with version 3.0.3 through 3.0.6 will need to uninstall & reinstall
  
## 01/06/21 -  Eric Smith -    Version 3.0.6  
**Bug Fixes:**  
-   Fixed checkbox behavior in the CPE 
-   Fixed an error selecting checkboxes in the CPE  
-   Fixed an error with attributes not being able to be cleared  
-   Fixed an error with Textarea not showing Rich Text correctly  
   
## 01/01/21 -  Eric Smith -    Version 3.0.5 
**Updates:**
-   Added Icon Pickers to the CPE and Column Wizard  (Requires FlowScreenComponentBasePack v2.1.2 or later)
-   Changed 'Display ALL Objects for Selection' checkbox to default to unchecked  
 
**Bug Fixes:**
-   Removed field names from Empty Table Header
-   Fixed "Apex CPU time limit exceeded" error (FlowActionsBasePack v2.9 or greater)    
  
## 12/14/20 -  Eric Smith -    Version 3.0.0 
**Updates:**
-   New Custom Property Editor for Configuration  
-   Clear button added when using single record selection  
-   Fixed row number display when >99 rows
 
**Bug Fixes:**
-   Sandbox URLs with __c in their name will now provide valid links for lookups  
  
## 10/14/20 -  Eric Smith -    Version 2.47 
**Bug Fix:**
-   Display correct icon for Table Header (was always showing standard:account icon)
  
## 10/07/20 -  Eric Smith -    Version 2.46 
**Updates:**
-   Added new Output Parameter for the # of Selected Records 
-   (this can be used for conditional visibility on the same screen as the datatable)   
-   New Selected Record Output Parameter - Returns an SObject record if just a single record is selected 
-   New Required? Parameter - Requires the user to select at least 1 row to proceed  
-   New option to suppress the link for the object's standard Name field  
-   New optional Table Header with Table Icon and Table Label Parameters  
-   Switched DualListbox to the fbc version  
-   Added spinners while sorting & filtering data  
-   Allow case insensitive field API names  
-   Allow custom field API names w/o the __c suffix  
 
**Bug Fixes:**
-   Display Picklist Labels instead of API Names for Picklist and Multipicklist fields  
-   Added a Clear Selection button for tables with just a single record
  
## 09/22/20 -  Eric Smith -    Version 2.45 
**Bug Fix:**
-   Fixed inability to edit some field types (introduced by v2.44)
  
## 09/20/20 -  Kevin Hart -    Version 2.44 
**Updates:**
-   Added ability to display Rich Text fields  
 
**Bug Fix:** - Eric Smith
-   Fixed error when selecting column action of WrapText or ClipText  
                
## 09/01/20 -  Eric Smith -    Version 2.43 
**Bug Fix:**
-   Update Percent Field Handling and set Formula Fields to be Non-Editable  
              
## 08/26/20 -  Eric Smith -    Version 2.42 
**Bug Fixes:**
-   Update Time fields with the User's Timezone Offset value so they display as intended  
-   Fix field type so Datetime fields display correctly    
                
## 08/14/20 -  Eric Smith -    Version 2.41 
**Bug Fix:**
-   Fixed issue with time and date-time fields being displayed as a day earlier     
               
## 08/11/20 -  Eric Smith -    Version 2.40 
**Updates:**
-   Added attribute to allow the suppression of the record link on the SObject's 'Name' field  
 
**Bug Fix:**
-   Fixed code so the 'Name' Field column now sorts correctly  
              
## 07/31/20 -  Eric Smith -    Version 2.39 
**Updates:**
-   Added Datatable Configuration Helper Flow  
**REQUIRES:**
-   Flow Base Components (https://unofficialsf.com/introducing-flowbasecomponents/)  
-   Dual List Box (https://unofficialsf.com/duallistbox/)   
-   Remote Site Setting (Setup)
                  
## 07/31/20 -  Andy Hass -     Version 2.38 
**Updates:**
-   Added support for Checkbox Field Type
                
## 07/07/20 -  Eric Smith -    Version 2.37 
**Bug Fix:**
-   Fixed issue with the date being displayed as a day earlier   
              
## 07/01/20 -  Eric Smith -    Version 2.36 
**Updates:**
-   Now displays the primary "Name" field as a Link (textWrap = true)  
-   Added button in Config Mode to round off Column Width values  
              
## 06/30/20 -  Eric Smith -    Version 2.35 
**Updates:**
-   Extended Configuration Mode to handle Column Alignments, Labels, Widths, Allow Edit & Allow Filter  
-   Added Configuration Mode buttons to select all columns for Edit and/or Filter  
-   Selecting an attribute string now copies the contents into the system Clipboard  
                              
## 06/24/20 -  Eric Smith -    Version 2.34 
**Updates:**
-   Added Configuration Mode parameter (Used by Datatable Configuration Flow)  
 
 **Bug Fix:**
-   Fixed issue with column widths resetting when filtering  
  
## 06/19/20 -  Eric Smith -    Version 2.33 
**Updates:**
-   Removed default value for Table Height
 
 **Bug Fix:**
 -   Fixed issue with lookup fields being blank in the first record                                                    
  
## 06/03/20 -  Eric Smith -    Version 2.32 
**Bug Fix:**
-   Fixed error when editing more than one column in a single row while suppressing the Cancel/Save buttons
  
## 06/03/20 -  Eric Smith -    Version 2.31 
**Updates:**
-   Changed SObjectController to SObjectController2 to allow for easier deployment to orgs that already have an earlier version of the datatable component    
                                                                                   
## 06/03/20 -  Eric Smith -    Version 2.3 
**Updates:**
-   Changed SObjectController to SObjectController2 to allow for easier deployment to orgs that already have an earlier version of the datatable component
  
## 06/03/20 -  Eric Smith -    Version 2.2 
**Enhancements:**
-   Added datatable border attribute
 
**Updates:**
-   Fixed attribute parsing, Fixed Spinner
  
## 06/01/20 -  Eric Smith -    Version 2.1 
**Enhancements:**
-   Updated with features from v1.2 & v1.3                                                
  
## 04/22/20 -  Eric Smith -    Version 2.0 (Summer '20) 
**Enhancements:**
-   Summer '20 New Feature - Dynamic Object Type
-   One version of the component now supports ALL Standard & Custom SObjects
  
## 05/23/20 -  Eric Smith -    Version 1.3 
**Updates:**
-   Added support for a serialized JSON string of records of a user defined object
-   Added an attribute to specify the height of the datatable
-   Bug Fix - Fixed error when editing multiple rows           
  
## 05/06/20 -  Eric Smith -    Version 1.2 
**Updates:**
-   Handle lookup Objects without a Name field & 
-   Trap non-updatable Master/Detail fields
  
## 04/14/20 -  Eric Smith -    Version 1.1 
**Enhancements:**
-   New Column Attribute to support column filtering  
  
## 04/01/20 -  Eric Smith -    Version 1.0 
**Features:**
-   The only required paramters are the SObject collection of records and a list of field API names  
-   The field label and field type will default to what is defined in the object  
-   Numeric fields will display with the correct number of decimal places as defined in the object  
-   Lookup fields are supported and will display the referenced record's name field as a clickable link  
-   All columns are sortable, including lookups (by name)  
-   The selection column can be multi-select (Checkboxes), single-select (Radio Buttons), or hidden  
-   A collection of pre-selected rows can be passed into the component  
-   Inline editing is supported with changed values passed back to the flow  
-   Unlike the original datatable component, only the edited records will be passed back to the flow  
-   The maximum number of rows to display can be set by the user  
-   Optional attribute overrides are supported and can be specified by list, column # or by field name, including:  

                - Alignment               
                - Editable
                - Header Icon
                - Header Label
                - Initial Column Width
                - Custom Cell Attributes including those with nested values {name: {name:value}}               
                - Custom Type Attributes including those with nested values {name: {name:value}}
                - Other Custom Column Attributes including those with nested values {name: {name:value}}
  
---
