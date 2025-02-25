---
title: "Testing the ODBC Connection"
description: "Testing the ODBC Connection"
author: David-Engel
ms.author: davidengel
ms.date: "01/19/2017"
ms.service: sql
ms.subservice: connectivity
ms.topic: reference
helpviewer_keywords:
  - "testing connections [ODBC]"
  - "ODBC driver for Oracle [ODBC], testing connections"
---
# Testing the ODBC Connection
> [!IMPORTANT]  
>  This feature will be removed in a future version of Windows. Avoid using this feature in new development work, and plan to modify applications that currently use this feature. Instead, use the ODBC driver provided by Oracle.  
  
 When troubleshooting ODBC access to Oracle 7.x and Oracle8 RDBMS servers, it might be necessary to verify that the underlying SQL*Net and Oracle Protocol Adapters are correctly installed. To do this, use the Oracle-supplied utility Nettest.exe in the Orawin\Bin directory.  
  
 Nettest is a simple utility that attempts to log on to the selected server using only the installed SQL*Net software that is part of the Oracle client. The utility will ask for a login name, password, and TNS connect string. If the Oracle client is correctly installed, the utility will simply display "Ping Successful." If the login was not successful, you will need to consult with a database administrator.
