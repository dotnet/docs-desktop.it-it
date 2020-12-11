---
title: Modifica della selezione a livello di codice in un oggetto RichTextBox
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- changing selections in a text box [WPF]
- changing selections in a RichTextBox [WPF]
ms.assetid: f1213205-1ad7-4cd2-b115-460173cc5aa3
ms.openlocfilehash: e3c76bd244e567857ebf132db5cc19c2d51139bd
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967144"
---
# <a name="change-selection-in-a-richtextbox-programmatically"></a><span data-ttu-id="fbfa2-102">Modifica della selezione a livello di codice in un oggetto RichTextBox</span><span class="sxs-lookup"><span data-stu-id="fbfa2-102">Change Selection in a RichTextBox Programmatically</span></span>
<span data-ttu-id="fbfa2-103">In questo esempio viene illustrato come modificare a livello di codice la selezione corrente in un oggetto <xref:System.Windows.Controls.RichTextBox> .</span><span class="sxs-lookup"><span data-stu-id="fbfa2-103">This example shows how to programmatically change the current selection in a <xref:System.Windows.Controls.RichTextBox>.</span></span> <span data-ttu-id="fbfa2-104">Questa selezione è identica a quella dell'utente che ha selezionato il contenuto mediante l'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="fbfa2-104">This selection is the same as if the user had selected the content by using the user interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fbfa2-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="fbfa2-105">Example</span></span>  
 <span data-ttu-id="fbfa2-106">Il [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] codice seguente descrive un <xref:System.Windows.Controls.RichTextBox> controllo denominato con contenuto semplice.</span><span class="sxs-lookup"><span data-stu-id="fbfa2-106">The following [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] code describes a named <xref:System.Windows.Controls.RichTextBox> control with simple content.</span></span>  
  
 [!code-xaml[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/ChangeSelectionProgrammaticaly.xaml#changeselectionprogrammaticalyexamplewholepage)]  
  
## <a name="example"></a><span data-ttu-id="fbfa2-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="fbfa2-107">Example</span></span>  
 <span data-ttu-id="fbfa2-108">Il codice seguente seleziona a livello di codice un testo arbitrario quando l'utente fa clic all'interno di <xref:System.Windows.Controls.RichTextBox> .</span><span class="sxs-lookup"><span data-stu-id="fbfa2-108">The following code programmatically selects some arbitrary text when the user clicks inside the <xref:System.Windows.Controls.RichTextBox>.</span></span>  
  
 [!code-csharp[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/ChangeSelectionProgrammaticaly.xaml.cs#changeselectionprogrammaticalycodeexamplewholepage)]
 [!code-vb[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/VisualBasic/ChangeSelectionProgrammaticaly.xaml.vb#changeselectionprogrammaticalycodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="fbfa2-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fbfa2-109">See also</span></span>

- [<span data-ttu-id="fbfa2-110">Cenni generali sul controllo RichTextBox</span><span class="sxs-lookup"><span data-stu-id="fbfa2-110">RichTextBox Overview</span></span>](richtextbox-overview.md)
- [<span data-ttu-id="fbfa2-111">Cenni preliminari sulla classe TextBox</span><span class="sxs-lookup"><span data-stu-id="fbfa2-111">TextBox Overview</span></span>](textbox-overview.md)
