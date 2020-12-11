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
# <a name="how-to-get-all-windows-in-an-application"></a>Procedura: ottenere tutte le finestre in un'applicazione
Questo esempio Mostra come ottenere tutti <xref:System.Windows.Window> gli oggetti in un'applicazione.  
  
## <a name="example"></a>Esempio  
 Ogni oggetto di cui è stata creata un'istanza <xref:System.Windows.Window> , se visibile o meno, viene aggiunto automaticamente a una raccolta di riferimenti di finestra gestiti da <xref:System.Windows.Application> ed esposti da <xref:System.Windows.Application.Windows%2A> .  
  
 È possibile enumerare <xref:System.Windows.Application.Windows%2A> per ottenere tutte le finestre di cui è stata creata un'istanza usando il codice seguente:  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetAllWindows](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/CustomWindow.xaml.cs#getallwindows)]
 [!code-vb[HOWTOWindowManagementSnippets#GetAllWindows](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/customwindow.xaml.vb#getallwindows)]
