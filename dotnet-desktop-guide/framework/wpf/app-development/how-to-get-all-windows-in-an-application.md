---
title: "Procedura: ottenere tutte le finestre in un'applicazione"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- window objects [WPF], getting
ms.assetid: f120f06e-993b-4a97-9657-af0d1986981f
ms.openlocfilehash: 34316f0c6f81b960a8e00131a30b9a237b9ca938
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969097"
---
# <a name="how-to-get-all-windows-in-an-application"></a><span data-ttu-id="fa7fe-102">Procedura: ottenere tutte le finestre in un'applicazione</span><span class="sxs-lookup"><span data-stu-id="fa7fe-102">How to: Get all Windows in an Application</span></span>
<span data-ttu-id="fa7fe-103">Questo esempio Mostra come ottenere tutti <xref:System.Windows.Window> gli oggetti in un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="fa7fe-103">This example shows how to get all <xref:System.Windows.Window> objects in an application.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fa7fe-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="fa7fe-104">Example</span></span>  
 <span data-ttu-id="fa7fe-105">Ogni oggetto di cui è stata creata un'istanza <xref:System.Windows.Window> , se visibile o meno, viene aggiunto automaticamente a una raccolta di riferimenti di finestra gestiti da <xref:System.Windows.Application> ed esposti da <xref:System.Windows.Application.Windows%2A> .</span><span class="sxs-lookup"><span data-stu-id="fa7fe-105">Every instantiated <xref:System.Windows.Window> object, whether visible or not, is automatically added to a collection of window references that is managed by <xref:System.Windows.Application>, and exposed from <xref:System.Windows.Application.Windows%2A>.</span></span>  
  
 <span data-ttu-id="fa7fe-106">È possibile enumerare <xref:System.Windows.Application.Windows%2A> per ottenere tutte le finestre di cui è stata creata un'istanza usando il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="fa7fe-106">You can enumerate <xref:System.Windows.Application.Windows%2A> to get all instantiated windows using the following code:</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetAllWindows](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/CustomWindow.xaml.cs#getallwindows)]
 [!code-vb[HOWTOWindowManagementSnippets#GetAllWindows](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/customwindow.xaml.vb#getallwindows)]
