---
title: 'Procedura: rilevare se è installato il .NET Framework 3,5'
ms.date: 03/30/2017
helpviewer_keywords:
- verifying whether.NET Framework 3.5 is installed [WPF]
- detecting .NET Framework 3.5 installation [WPF]
- detecting whether.NET Framework 3.5 is installed [WPF]
- determining whether.NET Framework 3.5 is installed [WPF]
ms.assetid: 8556a9d2-1eb8-48ef-919c-5baf22a2a9a2
ms.openlocfilehash: 5b714b686f160f6cbb42f5dbf5d7d7b5875e1a2f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963469"
---
# <a name="how-to-detect-whether-the-net-framework-35-is-installed"></a><span data-ttu-id="7bd48-102">Procedura: rilevare se è installato il .NET Framework 3,5</span><span class="sxs-lookup"><span data-stu-id="7bd48-102">How to: Detect Whether the .NET Framework 3.5 Is Installed</span></span>
<span data-ttu-id="7bd48-103">Prima che gli amministratori possano distribuire le applicazioni Windows Presentation Foundation (WPF) in un sistema destinato al .NET Framework 3,5, devono prima verificare che sia presente il runtime di .NET Framework 3,5.</span><span class="sxs-lookup"><span data-stu-id="7bd48-103">Before administrators can deploy Windows Presentation Foundation (WPF) applications on a system that targets the .NET Framework 3.5, they must first confirm that the .NET Framework 3.5 runtime is present.</span></span> <span data-ttu-id="7bd48-104">In questo argomento viene fornito uno script scritto in HTML/JavaScript che gli amministratori possono utilizzare per determinare se il .NET Framework 3,5 è presente in un sistema.</span><span class="sxs-lookup"><span data-stu-id="7bd48-104">This topic provides a script written in HTML/JavaScript that administrators can use to determine whether the .NET Framework 3.5 is present on a system.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7bd48-105">Per informazioni più dettagliate sull'installazione, la distribuzione e il rilevamento del .NET Framework, vedere [Install the .NET Framework for Developers](/dotnet/framework/install/guide-for-developers).</span><span class="sxs-lookup"><span data-stu-id="7bd48-105">For more detailed information on installing, deploying, and detecting the .NET Framework, see [Install the .NET Framework for developers](/dotnet/framework/install/guide-for-developers).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7bd48-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="7bd48-106">Example</span></span>  
 <span data-ttu-id="7bd48-107">Quando viene installato il .NET Framework 3,5, il file MSI aggiunge ".NET CLR" e il numero di versione alla stringa UserAgent.</span><span class="sxs-lookup"><span data-stu-id="7bd48-107">When the .NET Framework 3.5 is installed, the MSI adds ".NET CLR" and the version number to the UserAgent string.</span></span> <span data-ttu-id="7bd48-108">Nell'esempio seguente viene illustrato uno script incorporato in una pagina HTML semplice.</span><span class="sxs-lookup"><span data-stu-id="7bd48-108">The following example shows a script embedded in a simple HTML page.</span></span> <span data-ttu-id="7bd48-109">Lo script cerca la stringa UserAgent per determinare se il .NET Framework 3,5 è installato e visualizza un messaggio di stato sui risultati della ricerca.</span><span class="sxs-lookup"><span data-stu-id="7bd48-109">The script searches the UserAgent string to determine whether the .NET Framework 3.5 is installed, and displays a status message on the results of the search.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7bd48-110">Questo script è progettato per Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="7bd48-110">This script is designed for Internet Explorer.</span></span> <span data-ttu-id="7bd48-111">È possibile che altri browser non includano informazioni CLR .NET nella stringa UserAgent.</span><span class="sxs-lookup"><span data-stu-id="7bd48-111">Other browsers may not include .NET CLR information in the UserAgent string.</span></span>  
  
```html  
<HTML>  
  <HEAD>  
    <TITLE>Test for the .NET Framework 3.5</TITLE>  
    <META HTTP-EQUIV="Content-Type" CONTENT="text/html; charset=utf-8" />  
    <SCRIPT LANGUAGE="JavaScript">  
    <!--  
    var dotNETRuntimeVersion = "3.5.0.0";  
  
    function window::onload()  
    {  
      if (HasRuntimeVersion(dotNETRuntimeVersion))  
      {  
        result.innerText =   
          "This machine has the correct version of the .NET Framework 3.5."  
      }   
      else  
      {  
        result.innerText =   
          "This machine does not have the correct version of the .NET Framework 3.5." +  
          " The required version is v" + dotNETRuntimeVersion + ".";  
      }  
      result.innerText += "\n\nThis machine's userAgent string is: " +   
        navigator.userAgent + ".";  
    }  
  
    //  
    // Retrieve the version from the user agent string and   
    // compare with the specified version.  
    //  
    function HasRuntimeVersion(versionToCheck)  
    {  
      var userAgentString =   
        navigator.userAgent.match(/.NET CLR [0-9.]+/g);  
  
      if (userAgentString != null)  
      {  
        var i;  
  
        for (i = 0; i < userAgentString.length; ++i)  
        {  
          if (CompareVersions(GetVersion(versionToCheck),   
            GetVersion(userAgentString[i])) <= 0)  
            return true;  
        }  
      }  
  
      return false;  
    }  
  
    //  
    // Extract the numeric part of the version string.  
    //  
    function GetVersion(versionString)  
    {  
      var numericString =   
        versionString.match(/([0-9]+)\.([0-9]+)\.([0-9]+)/i);  
      return numericString.slice(1);  
    }  
  
    //  
    // Compare the 2 version strings by converting them to numeric format.  
    //  
    function CompareVersions(version1, version2)  
    {  
      for (i = 0; i < version1.length; ++i)  
      {  
        var number1 = new Number(version1[i]);  
        var number2 = new Number(version2[i]);  
  
        if (number1 < number2)  
          return -1;  
  
        if (number1 > number2)  
          return 1;  
      }  
  
      return 0;  
    }  
  
    -->  
    </SCRIPT>  
  </HEAD>  
  
  <BODY>  
    <div id="result" />  
  </BODY>  
</HTML>  
```  
  
 <span data-ttu-id="7bd48-112">Se la ricerca della versione ".NET CLR" ha esito positivo, viene visualizzato il seguente tipo di messaggio di stato:</span><span class="sxs-lookup"><span data-stu-id="7bd48-112">If the search for the ".NET CLR " version is successful, the following type of status message appears:</span></span>  
  
 `This machine has the correct version of the .NET Framework 3.5.`  
  
 `This machine's userAgent string is: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0; SLCC1; .NET CLR 2.0.50727; .NET CLR 1.1.4322; InfoPath.2; .NET CLR 3.0.590; .NET CLR 3.5.20726; MS-RTC LM 8).`  
  
 <span data-ttu-id="7bd48-113">In caso contrario, viene visualizzato il seguente tipo di messaggio di stato:</span><span class="sxs-lookup"><span data-stu-id="7bd48-113">Otherwise, the following type of status message appears:</span></span>  
  
 `This machine does not have the correct version of the .NET Framework 3.5. The required version is v3.5.0.0.`  
  
 `This machine's userAgent string is: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0; SLCC1; .NET CLR 2.0.50727; .NET CLR 1.1.4322; InfoPath.2; .NET CLR 3.0.590; MS-RTC LM 8).`  
  
## <a name="see-also"></a><span data-ttu-id="7bd48-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7bd48-114">See also</span></span>

- [<span data-ttu-id="7bd48-115">Verificare se .NET Framework 3.0 è installato</span><span class="sxs-lookup"><span data-stu-id="7bd48-115">Detect Whether the .NET Framework 3.0 Is Installed</span></span>](how-to-detect-whether-the-net-framework-3-0-is-installed.md)
