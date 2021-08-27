<!-- default badges list -->
![](https://img.shields.io/endpoint?url=https://codecentral.devexpress.com/api/v1/VersionRange/187623782/2019.2)
[![](https://img.shields.io/badge/Open_in_DevExpress_Support_Center-FF7200?style=flat-square&logo=DevExpress&logoColor=white)](https://supportcenter.devexpress.com/ticket/details/T828708)
[![](https://img.shields.io/badge/📖_How_to_use_DevExpress_Examples-e9f6fc?style=flat-square)](https://docs.devexpress.com/GeneralInformation/403183)
<!-- default badges end -->
# How to Provide Predefined JsonDataSource Header Parameters in Wizards

When you use the **Report Wizard** / **Data Source Wizard** to bind a report to JSON data, you can specify header parameters for the Web Service Endpoint on the **Specify Request Parameters** page. This example demonstrates how to provide predefined header parameters on this page.

![Predefined Header Parameters](Images/PredefinedHeaderParameters.png)

Steps to implement this task:

- Implement the **IWizardCustomizationService** interface to customize the **Report Wizard** and **Data Source Wizard** (see the *WizardCustomization.cs*/*WizardCustomization.vb* file)  
	Create a [UriJsonSource](https://docs.devexpress.com/CoreLibraries/DevExpress.DataAccess.Json.UriJsonSource) object with the specified [HeaderParameters](https://docs.devexpress.com/CoreLibraries/DevExpress.DataAccess.Json.UriJsonSource.HeaderParameters) and [QueryParameters](https://docs.devexpress.com/CoreLibraries/DevExpress.DataAccess.Json.UriJsonSource.QueryParameters) properties. Assign this object to the **JsonSource** property of the report's wizard model.

- Register the implemented customization service (see the *Form1.cs*/*Form1.vb* file)  
    Add the service to the [DesignMdiController](https://docs.devexpress.com/XtraReports/DevExpress.XtraReports.UserDesigner.XRDesignRibbonForm.DesignMdiController)'s service collection.

Refer to the [JSON Data Source](https://docs.devexpress.com/XtraReports/400377) documentation section for more information on how to bind reports to JSON data.
