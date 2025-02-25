---
title: "SQLValidDSN Function"
description: "SQLValidDSN Function"
author: David-Engel
ms.author: davidengel
ms.date: "01/19/2017"
ms.service: sql
ms.subservice: connectivity
ms.topic: reference
f1_keywords:
  - "SQLValidDSN"
helpviewer_keywords:
  - "SQLValidDSN [ODBC]"
apilocation: "sqlsrv32.dll"
apiname: "SQLValidDSN"
apitype: "dllExport"
---
# SQLValidDSN Function
**Conformance**  
 Version Introduced: ODBC 2.0  
  
 **Summary**  
 **SQLValidDSN** checks the length and validity of the data source name before the name is added to the system information.  
  
## Syntax  
  
```cpp  
  
BOOL SQLValidDSN(  
     LPCSTR    lpszDSN);  
```  
  
## Arguments  
 *lpszDSN*  
 [Input] Data source name to be checked.  
  
## Returns  
 The function returns TRUE if the data source name is valid. It returns FALSE if the data source name is invalid or the function call failed.  
  
## Diagnostics  
 When **SQLValidDSN** returns FALSE, an associated *\*pfErrorCode* value can be obtained by calling **SQLInstallerError**. A *\*pfErrorCode* is returned only if the function call failed, not if FALSE was returned because the data source name is invalid. The following table lists the *\*pfErrorCode* values that can be returned by **SQLInstallerError** and explains each one in the context of this function.  
  
|*\*pfErrorCode*|Error|Description|  
|---------------------|-----------|-----------------|  
|ODBC_ERROR_GENERAL_ERR|General installer error|An error occurred for which there was no specific installer error.|  
|ODBC_ERROR_OUT_OF_MEM|Out of memory|The installer could not perform the function because of a lack of memory.|  
  
## Comments  
 **SQLValidDSN** is called by a driver's [ConfigDSN](../../../odbc/reference/syntax/configdsn-function.md) to check the length of the data source name and the validity of the individual characters in the data source name. It checks whether the length of the name is greater than SQL_MAX_DSN_LENGTH, as defined in Sqlext.h. (The length of the data source name is also checked by [SQLWriteDSNToIni](../../../odbc/reference/syntax/sqlwritedsntoini-function.md).) **SQLValidDSN** checks whether any of the following invalid characters are included in the data source name:  
  
 [ ] { } ( ) , ; ? * = ! \@ \  
  
## Related Functions  
  
|For information about|See|  
|---------------------------|---------|  
|Adding, modifying, or removing a data source|[ConfigDSN](../../../odbc/reference/syntax/configdsn-function.md) (in the Setup DLL)|  
|Adding, modifying, or removing a data source|[SQLConfigDataSource](../../../odbc/reference/syntax/sqlconfigdatasource-function.md)|  
|Writing a data source name to the system information|[SQLWriteDSNToIni](../../../odbc/reference/syntax/sqlwritedsntoini-function.md)|
