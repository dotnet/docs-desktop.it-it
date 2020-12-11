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
# <a name="how-to-return-a-dialog-box-result"></a><span data-ttu-id="fda16-102">Procedura: restituire un risultato della finestra di dialogo</span><span class="sxs-lookup"><span data-stu-id="fda16-102">How to: Return a Dialog Box Result</span></span>
<span data-ttu-id="fda16-103">Questo esempio Mostra come recuperare il risultato della finestra di dialogo per una finestra aperta chiamando <xref:System.Windows.Window.ShowDialog%2A> .</span><span class="sxs-lookup"><span data-stu-id="fda16-103">This example shows how to retrieve the dialog result for a window that is opened by calling <xref:System.Windows.Window.ShowDialog%2A>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fda16-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="fda16-104">Example</span></span>  
 <span data-ttu-id="fda16-105">Prima della chiusura di una finestra di dialogo, la relativa <xref:System.Windows.Window.DialogResult%2A> proprietà deve essere impostata con un valore <xref:System.Nullable%601> <xref:System.Boolean> che indica il modo in cui l'utente ha chiuso la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="fda16-105">Before a dialog box closes, its <xref:System.Windows.Window.DialogResult%2A> property should be set with a <xref:System.Nullable%601><xref:System.Boolean> that indicates how the user closed the dialog box.</span></span> <span data-ttu-id="fda16-106">Questo valore viene restituito da <xref:System.Windows.Window.ShowDialog%2A> per consentire al codice client di determinare la modalità di chiusura della finestra di dialogo e, di conseguenza, come elaborare il risultato.</span><span class="sxs-lookup"><span data-stu-id="fda16-106">This value is returned by <xref:System.Windows.Window.ShowDialog%2A> to allow client code to determine how the dialog box was closed and, consequently, how to process the result.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fda16-107"><xref:System.Windows.Window.DialogResult%2A> può essere impostato solo se una finestra è stata aperta chiamando <xref:System.Windows.Window.ShowDialog%2A> .</span><span class="sxs-lookup"><span data-stu-id="fda16-107"><xref:System.Windows.Window.DialogResult%2A> can only be set if a window was opened by calling <xref:System.Windows.Window.ShowDialog%2A>.</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#GetDialogResultCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#getdialogresultcode)]
 [!code-vb[HOWTOWindowManagementSnippets#GetDialogResultCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#getdialogresultcode)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="fda16-108">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="fda16-108">.NET Framework Security</span></span>  
 <span data-ttu-id="fda16-109">La chiamata <xref:System.Windows.Window.ShowDialog%2A> a richiede l'autorizzazione per utilizzare tutte le finestre e gli eventi di input utente senza restrizioni.</span><span class="sxs-lookup"><span data-stu-id="fda16-109">Calling <xref:System.Windows.Window.ShowDialog%2A> requires permission to use all windows and user input events without restriction.</span></span>
