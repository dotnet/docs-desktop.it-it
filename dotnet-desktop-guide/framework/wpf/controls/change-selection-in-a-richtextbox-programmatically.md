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
# <a name="change-selection-in-a-richtextbox-programmatically"></a>Modifica della selezione a livello di codice in un oggetto RichTextBox
In questo esempio viene illustrato come modificare a livello di codice la selezione corrente in un oggetto <xref:System.Windows.Controls.RichTextBox> . Questa selezione è identica a quella dell'utente che ha selezionato il contenuto mediante l'interfaccia utente.  
  
## <a name="example"></a>Esempio  
 Il [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] codice seguente descrive un <xref:System.Windows.Controls.RichTextBox> controllo denominato con contenuto semplice.  
  
 [!code-xaml[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/ChangeSelectionProgrammaticaly.xaml#changeselectionprogrammaticalyexamplewholepage)]  
  
## <a name="example"></a>Esempio  
 Il codice seguente seleziona a livello di codice un testo arbitrario quando l'utente fa clic all'interno di <xref:System.Windows.Controls.RichTextBox> .  
  
 [!code-csharp[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/CSharp/ChangeSelectionProgrammaticaly.xaml.cs#changeselectionprogrammaticalycodeexamplewholepage)]
 [!code-vb[RichTextBoxMiscSnippets_snip#ChangeSelectionProgrammaticalyCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxMiscSnippets_snip/VisualBasic/ChangeSelectionProgrammaticaly.xaml.vb#changeselectionprogrammaticalycodeexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni generali sul controllo RichTextBox](richtextbox-overview.md)
- [Cenni preliminari sulla classe TextBox](textbox-overview.md)
