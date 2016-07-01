
###Synopsis
   Robert Allen - @TheMasterPrawn 30/06/2016
   
   Converts a user on AD to a MailUser
   
###EXAMPLE
    .\Convert-ToMailUser.ps1 -SamAccountName bwayne -ExchangeVersion Exchange2010 cloudMailDomain "contoso.mail.onmicrosoft.com"
	
###INPUTS
   SamAccountName   : Active Directory Account Name
   
   ExchangeVersion  : Name of the exchange server version
   
   cloudDomain      : the @*.onmicrosoft.com, typically contoso.mail.onmicrosoft.com without the @ symbol
   
###FUNCTIONALITY
	Converts a user to a Mail enabled user (remote mailbox) locally while keeping the X500 address.
    You may need to do this if you get failures in a hybrid exchange move, or have other Office 365 related
    challenges in hybrid where a mailbox move failed but is valid at the target. 

    msExchRecipientTypeDetails = “2147483648” Remote user mailbox
	
    msExchRecipientDisplayType = “-2147483642” Synced mailbox user
	
    msExchRemoteRecipientType = “4” migrated mailbox
	
    Exchange 2007  = “4535486012416”
	
    Exchange 2010 = “44220983382016”
	
    Exchange 2013 = “88218628259840”
	