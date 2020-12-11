---
title: 'Procedura: restituire un risultato della finestra di dialogo'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dialog boxes [WPF], returning results
ms.assetid: 4c5cf286-746b-4052-934d-d80cbf8acba3
ms.openlocfilehash: 5e3670006762bcd09634b29314ecf2d05b1a44da
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969100"
---
# <a name="how-to-return-a-dialog-box-result"></a>Procedura: restituire un risultato della finestra di dialogo
Questo esempio Mostra come recuperare il risultato della finestra di dialogo per una finestra aperta chiamando <xref:System.Windows.Window.ShowDialog%2A> .  
  
## <a name="example"></a>Esempio  
 Prima della chiusura di una finestra di dialogo, la relativa <xref:System.Windows.Window.DialogResult%2A> proprietà deve essere impostata con un valore <xref:System.Nullable%601> <xref:System.Boolean> che indica il modo in cui l'utente ha chiuso la finestra di dialogo. Questo valore viene restituito da <xref:System.Windows.Window.ShowDialog%2A> per consentire al codice client di determinare la modalità di chiusura della finestra di dialogo e, di conseguenza, come elaborare il risultato.  
  
> [!NOTE]
> <xref:System.Windows.Window.DialogResult%2A> può essere impostato solo se una finestra è stata aperta chiamando <xref:System.Windows.Window.ShowDialog%2A> .  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetDialogResultCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#getdialogresultcode)]
 [!code-vb[HOWTOWindowManagementSnippets#GetDialogResultCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#getdialogresultcode)]  
  
## <a name="net-framework-security"></a>Sicurezza di .NET Framework  
 La chiamata <xref:System.Windows.Window.ShowDialog%2A> a richiede l'autorizzazione per utilizzare tutte le finestre e gli eventi di input utente senza restrizioni.
