---
title: 'Procedura: aprire una finestra di dialogo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- opening dialog boxes [WPF]
- dialog boxes [WPF], opening
ms.assetid: 6b1557d2-da98-4ef4-9f68-4089f04ab9ea
ms.openlocfilehash: 70ac31285dd22244b4bd6ad0d188d182eb6e6264
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965890"
---
# <a name="how-to-open-a-dialog-box"></a>Procedura: aprire una finestra di dialogo
In questo esempio viene illustrato come aprire una finestra di dialogo.  
  
## <a name="example"></a>Esempio  
 Una finestra di dialogo è una finestra che viene aperta creando un'istanza di <xref:System.Windows.Window> e chiamando il <xref:System.Windows.Window.ShowDialog%2A> metodo. <xref:System.Windows.Window.ShowDialog%2A> apre una finestra e non viene restituita fino a quando non viene chiusa la nuova finestra di dialogo. Questo tipo di finestra è noto anche come finestra *modale* e limita l'input dell'utente.  
  
 [!code-csharp[HOWTOWindowManagementSnippets#OpenNewDialogBoxCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#opennewdialogboxcode)]
 [!code-vb[HOWTOWindowManagementSnippets#OpenNewDialogBoxCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#opennewdialogboxcode)]  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 La chiamata <xref:System.Windows.Window.ShowDialog%2A> a richiede l'autorizzazione per utilizzare tutte le finestre e gli eventi di input utente senza restrizioni.  
  
## <a name="see-also"></a>Vedere anche

- [Restituire il risultato di una finestra di dialogo](how-to-return-a-dialog-box-result.md)
