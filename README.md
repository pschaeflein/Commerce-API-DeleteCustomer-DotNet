# Commerce-API-DeleteCustomer-DotNet
Sample code for Cloud Solution Provider partners who are using the limited Integration Sandbox

## App Configuration

The sample application has several configurable settings in the app.config file. Set the values as
appropriate for your tenant.

Configuration Key | Description
------------ | -------------
AppId | The id of the application registered in the Partner Center. This id is used to access the CREST APIs.
Key | The key of the application registered in the Partner Center. 
MicrosoftId | The Microsoft Id of the reseller. Used to access CREST APIs.
DefaultDomain | The default domain of the reseller in Microsoft Azure. (This is typically an "onmicrosoft.com" domain.)

## Scenarios

This sample contains three scenarios:

  1. Export - export all customers to a CSV file. The information exported is documented below
  2. Delete - delete customer found in the specified csv file. Use teh Export scenario to create the file, and remove entries for customers you wish to keep.
  3. DeleteAll - delete all customer entries in the integration sandbox.


## Usage

    Microsoft.Partner.CSP.IntSandbox.Customer.Sample.exe /?
    /operation:{Export|Delete|DeleteAll}  Operation to perform (short form /op)
    /file:<string>                        File to write (export) or read
                                          (DeleteSelected) (short form /f)
    /confirm[+|-]                         Suppress confirmation prompt on delete
                                          operations; Overwrite file on Export
                                          (short form /c)


The Export file will contain four attributes of the customer:

Attribute | Description
----------|-------------
displayName | The display name of the customer as entered in the Partner Center
defaultDomainName | The domain name of the customer tenant as entered in the Partner Center
cspCustomerCid | The customer Cid in the Partner Center. This value uniquely identifies the customer and must be present for the delete operation.
customerContextId | The context id of the contract object in the reseller directory.


 