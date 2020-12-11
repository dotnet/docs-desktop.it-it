---
title: Sicurezza
ms.date: 03/30/2017
helpviewer_keywords:
- designer access security [Windows Forms]
- permissions [Windows Forms], Windows Forms
- Windows Forms, security
- security [Windows Forms]
- access control [Windows Forms], Windows Forms
- security policy [Windows Forms], Windows Forms
ms.assetid: 932d438a-5285-46d8-a958-8c93d0ad6cae
ms.openlocfilehash: 2ead74987769649e8defd69ceb929ca685baa51e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951936"
---
# <a name="windows-forms-security"></a><span data-ttu-id="5ad83-102">Sicurezza di Windows Form</span><span class="sxs-lookup"><span data-stu-id="5ad83-102">Windows Forms Security</span></span>

<span data-ttu-id="5ad83-103">Windows Forms offre un modello di sicurezza basato sul codice (i livelli di sicurezza sono impostati per il codice, indipendentemente dall'utente che esegue il codice).</span><span class="sxs-lookup"><span data-stu-id="5ad83-103">Windows Forms features a security model that is code-based (security levels are set for code, regardless of the user running the code).</span></span> <span data-ttu-id="5ad83-104">Questa operazione è aggiunta agli schemi di sicurezza che possono essere già presenti nel computer.</span><span class="sxs-lookup"><span data-stu-id="5ad83-104">This is in addition to any security schemas that may be in place already on your computer system.</span></span> <span data-ttu-id="5ad83-105">Questi possono includere quelli del browser, ad esempio la sicurezza basata sulla zona disponibile in Internet Explorer, o il sistema operativo, ad esempio la sicurezza basata sulle credenziali di Windows NT.</span><span class="sxs-lookup"><span data-stu-id="5ad83-105">These can include those in the browser (such as the zone-based security available in Internet Explorer) or the operating system (such as the credential-based security of Windows NT).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5ad83-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="5ad83-106">In This Section</span></span>  

 [<span data-ttu-id="5ad83-107">Cenni preliminari sulla sicurezza in Windows Form</span><span class="sxs-lookup"><span data-stu-id="5ad83-107">Security in Windows Forms Overview</span></span>](security-in-windows-forms-overview.md)  
 <span data-ttu-id="5ad83-108">Illustra brevemente il modello di sicurezza .NET Framework e i passaggi di base necessari per garantire la sicurezza dei Windows Forms nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="5ad83-108">Briefly explains the .NET Framework security model and the basic steps necessary to ensure the Windows Forms in your application are secure.</span></span>  
  
 [<span data-ttu-id="5ad83-109">File e accesso ai dati più protetti in Windows Form</span><span class="sxs-lookup"><span data-stu-id="5ad83-109">More Secure File and Data Access in Windows Forms</span></span>](more-secure-file-and-data-access-in-windows-forms.md)  
 <span data-ttu-id="5ad83-110">Viene descritto come accedere ai file e ai dati in un ambiente parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="5ad83-110">Describes how to access files and data in a semi-trusted environment.</span></span>  
  
 [<span data-ttu-id="5ad83-111">Stampa più protetta in Windows Form</span><span class="sxs-lookup"><span data-stu-id="5ad83-111">More Secure Printing in Windows Forms</span></span>](more-secure-printing-in-windows-forms.md)  
 <span data-ttu-id="5ad83-112">Viene descritto come accedere alle funzionalità di stampa in un ambiente parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="5ad83-112">Describes how to access printing features in a semi-trusted environment.</span></span>  
  
 [<span data-ttu-id="5ad83-113">Considerazioni aggiuntive sulla sicurezza in Windows Form</span><span class="sxs-lookup"><span data-stu-id="5ad83-113">Additional Security Considerations in Windows Forms</span></span>](additional-security-considerations-in-windows-forms.md)  
 <span data-ttu-id="5ad83-114">Viene descritto come eseguire la manipolazione delle finestre, utilizzare gli appunti ed effettuare chiamate a codice non gestito in un ambiente parzialmente attendibile.</span><span class="sxs-lookup"><span data-stu-id="5ad83-114">Describes performing window manipulation, using the Clipboard, and making calls to unmanaged code in a semi-trusted environment.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="5ad83-115">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="5ad83-115">Related Sections</span></span>  

 <span data-ttu-id="5ad83-116">[Criteri di sicurezza predefiniti](/previous-versions/dotnet/netframework-4.0/03kwzyfc(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="5ad83-116">[Default Security Policy](/previous-versions/dotnet/netframework-4.0/03kwzyfc(v=vs.100))</span></span>  
 <span data-ttu-id="5ad83-117">Elenca le autorizzazioni predefinite concesse nei set di autorizzazioni attendibilità totale, Intranet locale e Internet.</span><span class="sxs-lookup"><span data-stu-id="5ad83-117">Lists the default permissions granted in the Full Trust, Local Intranet, and Internet permission sets.</span></span>  
  
 <span data-ttu-id="5ad83-118">[Amministrazione generale dei criteri di sicurezza](/previous-versions/dotnet/netframework-4.0/ed5htz45(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="5ad83-118">[General Security Policy Administration](/previous-versions/dotnet/netframework-4.0/ed5htz45(v=vs.100))</span></span>  
 <span data-ttu-id="5ad83-119">Fornisce informazioni sull'amministrazione dei criteri di sicurezza .NET Framework e sull'elevazione delle autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="5ad83-119">Gives information about the administering the .NET Framework security policy and elevating permissions.</span></span>  
  
 [<span data-ttu-id="5ad83-120">Autorizzazioni pericolose e amministrazione dei criteri</span><span class="sxs-lookup"><span data-stu-id="5ad83-120">Dangerous Permissions and Policy Administration</span></span>](/dotnet/framework/misc/dangerous-permissions-and-policy-administration)  
 <span data-ttu-id="5ad83-121">Vengono illustrate alcune delle autorizzazioni di the.NET Framework che possono potenzialmente consentire l'elusione del sistema di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="5ad83-121">Discusses some of the.NET Framework permissions that can potentially allow the security system to be circumvented.</span></span>  
  
 [<span data-ttu-id="5ad83-122">Linee guida per la generazione di codice sicuro</span><span class="sxs-lookup"><span data-stu-id="5ad83-122">Secure Coding Guidelines</span></span>](/dotnet/standard/security/secure-coding-guidelines)  
 <span data-ttu-id="5ad83-123">Collegamenti ad argomenti che illustrano le procedure consigliate per la scrittura sicura del codice rispetto ai .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="5ad83-123">Links to topics that explain the best practices for securely writing code against the .NET Framework.</span></span>  
  
 <span data-ttu-id="5ad83-124">[Richiesta di autorizzazioni](/previous-versions/dotnet/netframework-4.0/yd267cce(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="5ad83-124">[Requesting Permissions](/previous-versions/dotnet/netframework-4.0/yd267cce(v=vs.100))</span></span>  
 <span data-ttu-id="5ad83-125">Viene illustrato l'utilizzo degli attributi per consentire al runtime di conoscere le autorizzazioni necessarie per l'esecuzione del codice.</span><span class="sxs-lookup"><span data-stu-id="5ad83-125">Discusses the use of attributes to let the runtime know what permissions your code needs to run.</span></span>  
  
 [<span data-ttu-id="5ad83-126">Concetti principali sulla sicurezza</span><span class="sxs-lookup"><span data-stu-id="5ad83-126">Key Security Concepts</span></span>](/dotnet/standard/security/key-security-concepts)  
 <span data-ttu-id="5ad83-127">Collegamenti ad argomenti che coprono gli aspetti di base della sicurezza del codice.</span><span class="sxs-lookup"><span data-stu-id="5ad83-127">Links to topics that cover the basic aspects of code security.</span></span>  
  
 [<span data-ttu-id="5ad83-128">Nozioni fondamentali sulla sicurezza per l’accesso al codice</span><span class="sxs-lookup"><span data-stu-id="5ad83-128">Code Access Security Basics</span></span>](/dotnet/framework/misc/code-access-security-basics)  
 <span data-ttu-id="5ad83-129">Vengono illustrate le nozioni di base sull'utilizzo dei criteri di sicurezza .NET Framework Runtime.</span><span class="sxs-lookup"><span data-stu-id="5ad83-129">Discusses the basics of working with the .NET Framework run time security policy.</span></span>  
  
 <span data-ttu-id="5ad83-130">[Determinazione della modifica dei criteri di sicurezza](/previous-versions/dotnet/netframework-4.0/xky659fc(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="5ad83-130">[Determining When to Modify Security Policy](/previous-versions/dotnet/netframework-4.0/xky659fc(v=vs.100))</span></span>  
 <span data-ttu-id="5ad83-131">Viene illustrato come determinare quando è necessario che le applicazioni differiscano dai criteri di sicurezza predefiniti.</span><span class="sxs-lookup"><span data-stu-id="5ad83-131">Explains how to determine when your applications need to diverge from the default security policy.</span></span>  
  
 <span data-ttu-id="5ad83-132">[Distribuzione dei criteri di sicurezza](/previous-versions/dotnet/netframework-4.0/13wcxx6y(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="5ad83-132">[Deploying Security Policy](/previous-versions/dotnet/netframework-4.0/13wcxx6y(v=vs.100))</span></span>  
 <span data-ttu-id="5ad83-133">Viene illustrato il modo migliore per distribuire le modifiche ai criteri di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="5ad83-133">Discusses the best manner for deploying security policy changes.</span></span>
