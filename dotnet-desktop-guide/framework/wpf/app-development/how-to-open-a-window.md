---
title: 'Procedura: aprire una finestra'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- windows [WPF], opening
- opening windows [WPF]
ms.assetid: 6b91b2bb-fda7-491d-a72e-139dd630a5b0
ms.openlocfilehash: 9ce7ffb3f46dd869fda7893745b531bd02d18ee1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969094"
---
# <a name="how-to-open-a-window"></a>Procedura: aprire una finestra
Questo esempio illustra come aprire una finestra.  
  
## <a name="example"></a>Esempio  
 Una finestra viene aperta creando un'istanza <xref:System.Windows.Window> e chiamando il <xref:System.Windows.Window.Show%2A> metodo. <xref:System.Windows.Window.Show%2A> apre una finestra e restituisce immediatamente un valore senza attendere la chiusura della nuova finestra. Questo tipo di finestra è noto anche come finestra non *modale* e non limita l'input dell'utente.  
  
 [!code-csharp[HOWTOWindowManagementSnippets#OpenNewWindowCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#opennewwindowcode)]
 [!code-vb[HOWTOWindowManagementSnippets#OpenNewWindowCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#opennewwindowcode)]  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 La creazione <xref:System.Windows.Window> di istanze richiede l'autorizzazione per chiamare metodi nativi unsafe (vedere <xref:System.Windows.Window.%23ctor%2A> ).
