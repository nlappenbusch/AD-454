# Lab 1 - Exercice 3 - Lizenzzuweisung automatisieren, Dynamische Gruppen, AccountSKU


## Task 1 - Assign User Licence
1. User „Hans Dampf“ lizenzieren
2.	Vorführen, wie die einzelnen Lizenzbestandteile zugewiesen werden können
3.	Dem User abschließend eine vollständige E5 Lizenz zuweisen
4.	Login mit dem User und zeigen, welche Dienste im Portal zur Verfügung stehen

## Task 2 - Assign User Licence via PowerShell
Informationen zum Zuweisen der Lizenzen: https://docs.microsoft.com/en-us/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell
Installation: https://docs.microsoft.com/en-us/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module

## Task 3 - Setzen der UsageLocation
<code>Set-MsolUser -UserPrincipalName <UPN> -UsageLocation DE</code> <br>
<code>Get-AzureADSubscribedSku | Select SkuPartNumber</code> <br>
<code>Set-MsolUserLicense -UserPrincipalName -AddLicenses <SkuId></code> <br>

## Task 4 - Automatische Lizenzierung anhand einer AD-Gruppe
  
1. Neue Gruppe anlegen „E5 Lizenzierung“
2. Azure AD Oberfläche öffnen
3. Azure AD > Lizenzen > Produkte > Zuweisung einer Gruppe „E5 Lizenzierung“ auswählen
4. Auswählen, welche Lizenzen durch die Gruppe zugewiesen werden – es können alle Optionen aktiviert bleiben / ist später nicht relevant. 
  <br>
  
Stolpersteine in der Praxis -> Gruppenverschachtelungen sind im Azure AD nicht bekannt


## Task 5 - Dynamische Gruppenmitgliedschaft 
  
1. Azure AD Oberfläche öffnen
2. Neue Security Gruppe anlegen „E5 IT Dynamic“ als Membership "Dynamic User" auswählen und als Bedindung "Department" mit dem Wert "IT" wählen
3. Azure AD > Lizenzen > Produkte > Zuweisung einer Gruppe „E5 Lizenzierung“ auswählen
4. Auswählen, welche Lizenzen durch die Gruppe zugewiesen werden 
5. Hans Dampf Department Value auf "IT" setzen
  <br>
  
Stolpersteine in der Praxis -> Gruppenverschachtelungen sind im Azure AD nicht bekannt
