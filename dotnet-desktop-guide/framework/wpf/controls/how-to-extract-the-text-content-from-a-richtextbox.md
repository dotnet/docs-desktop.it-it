---
title: 'Procedura: estrarre il contenuto di testo da un oggetto RichTextBox'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text content [WPF], extracting
- RichTextBox control [WPF], extracting text content
- content [WPF], extracting
- extracting text content [WPF]
ms.assetid: f13c093f-1a05-45b3-ac8f-c9ea5e4a11c5
ms.openlocfilehash: d1d40f37c23455dfc48206f84bca1b8438fec6c4
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967087"
---
# <a name="how-to-extract-the-text-content-from-a-richtextbox"></a>Procedura: estrarre il contenuto di testo da un oggetto RichTextBox
Questo esempio Mostra come estrarre il contenuto di un <xref:System.Windows.Controls.RichTextBox> come testo normale.  
  
## <a name="example"></a>Esempio  
 Il [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] codice seguente descrive un <xref:System.Windows.Controls.RichTextBox> controllo denominato con contenuto semplice.  
  
 [!code-xaml[RichTextBoxSnippets#_RTB_XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml#_rtb_xaml)]  
  
## <a name="example"></a>Esempio  
 Il codice seguente implementa un metodo che accetta <xref:System.Windows.Controls.RichTextBox> come argomento e restituisce una stringa che rappresenta il contenuto di testo normale dell'oggetto <xref:System.Windows.Controls.RichTextBox> .  
  
 Il metodo crea un nuovo oggetto <xref:System.Windows.Documents.TextRange> dal contenuto dell'oggetto <xref:System.Windows.Controls.RichTextBox> , usando <xref:System.Windows.Documents.FlowDocument.ContentStart%2A> e <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> per indicare l'intervallo del contenuto da estrarre.  <xref:System.Windows.Documents.FlowDocument.ContentStart%2A><xref:System.Windows.Documents.FlowDocument.ContentEnd%2A>le proprietà e restituiscono ogni oggetto <xref:System.Windows.Documents.TextPointer> e sono accessibili nell'oggetto FlowDocument sottostante che rappresenta il contenuto di <xref:System.Windows.Controls.RichTextBox> .  <xref:System.Windows.Documents.TextRange> fornisce una proprietà di testo, che restituisce le parti di testo normale di <xref:System.Windows.Documents.TextRange> sotto forma di stringa.  
  
 [!code-csharp[RichTextBoxSnippets#_RTB_StringFrom](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml.cs#_rtb_stringfrom)]
 [!code-vb[RichTextBoxSnippets#_RTB_StringFrom](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxSnippets/visualbasic/window1.xaml.vb#_rtb_stringfrom)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni generali sul controllo RichTextBox](richtextbox-overview.md)
- [Cenni preliminari sulla classe TextBox](textbox-overview.md)
