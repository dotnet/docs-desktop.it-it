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
# <a name="how-to-extract-the-text-content-from-a-richtextbox"></a><span data-ttu-id="351cc-102">Procedura: estrarre il contenuto di testo da un oggetto RichTextBox</span><span class="sxs-lookup"><span data-stu-id="351cc-102">How to: Extract the Text Content from a RichTextBox</span></span>
<span data-ttu-id="351cc-103">Questo esempio Mostra come estrarre il contenuto di un <xref:System.Windows.Controls.RichTextBox> come testo normale.</span><span class="sxs-lookup"><span data-stu-id="351cc-103">This example shows how to extract the contents of a <xref:System.Windows.Controls.RichTextBox> as plain text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="351cc-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="351cc-104">Example</span></span>  
 <span data-ttu-id="351cc-105">Il [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] codice seguente descrive un <xref:System.Windows.Controls.RichTextBox> controllo denominato con contenuto semplice.</span><span class="sxs-lookup"><span data-stu-id="351cc-105">The following [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] code describes a named <xref:System.Windows.Controls.RichTextBox> control with simple content.</span></span>  
  
 [!code-xaml[RichTextBoxSnippets#_RTB_XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml#_rtb_xaml)]  
  
## <a name="example"></a><span data-ttu-id="351cc-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="351cc-106">Example</span></span>  
 <span data-ttu-id="351cc-107">Il codice seguente implementa un metodo che accetta <xref:System.Windows.Controls.RichTextBox> come argomento e restituisce una stringa che rappresenta il contenuto di testo normale dell'oggetto <xref:System.Windows.Controls.RichTextBox> .</span><span class="sxs-lookup"><span data-stu-id="351cc-107">The following code implements a method that takes a <xref:System.Windows.Controls.RichTextBox> as an argument, and returns a string representing the plain text contents of the <xref:System.Windows.Controls.RichTextBox>.</span></span>  
  
 <span data-ttu-id="351cc-108">Il metodo crea un nuovo oggetto <xref:System.Windows.Documents.TextRange> dal contenuto dell'oggetto <xref:System.Windows.Controls.RichTextBox> , usando <xref:System.Windows.Documents.FlowDocument.ContentStart%2A> e <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> per indicare l'intervallo del contenuto da estrarre.</span><span class="sxs-lookup"><span data-stu-id="351cc-108">The method creates a new <xref:System.Windows.Documents.TextRange> from the contents of the <xref:System.Windows.Controls.RichTextBox>, using the <xref:System.Windows.Documents.FlowDocument.ContentStart%2A> and <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> to indicate the range of the contents to extract.</span></span>  <span data-ttu-id="351cc-109"><xref:System.Windows.Documents.FlowDocument.ContentStart%2A><xref:System.Windows.Documents.FlowDocument.ContentEnd%2A>le proprietà e restituiscono ogni oggetto <xref:System.Windows.Documents.TextPointer> e sono accessibili nell'oggetto FlowDocument sottostante che rappresenta il contenuto di <xref:System.Windows.Controls.RichTextBox> .</span><span class="sxs-lookup"><span data-stu-id="351cc-109"><xref:System.Windows.Documents.FlowDocument.ContentStart%2A> and <xref:System.Windows.Documents.FlowDocument.ContentEnd%2A> properties each return a <xref:System.Windows.Documents.TextPointer>, and are accessible on the underlying FlowDocument that represents the contents of the <xref:System.Windows.Controls.RichTextBox>.</span></span>  <span data-ttu-id="351cc-110"><xref:System.Windows.Documents.TextRange> fornisce una proprietà di testo, che restituisce le parti di testo normale di <xref:System.Windows.Documents.TextRange> sotto forma di stringa.</span><span class="sxs-lookup"><span data-stu-id="351cc-110"><xref:System.Windows.Documents.TextRange> provides a Text property, which returns the plain text portions of the <xref:System.Windows.Documents.TextRange> as a string.</span></span>  
  
 [!code-csharp[RichTextBoxSnippets#_RTB_StringFrom](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBoxSnippets/CSharp/Window1.xaml.cs#_rtb_stringfrom)]
 [!code-vb[RichTextBoxSnippets#_RTB_StringFrom](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBoxSnippets/visualbasic/window1.xaml.vb#_rtb_stringfrom)]  
  
## <a name="see-also"></a><span data-ttu-id="351cc-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="351cc-111">See also</span></span>

- [<span data-ttu-id="351cc-112">Cenni generali sul controllo RichTextBox</span><span class="sxs-lookup"><span data-stu-id="351cc-112">RichTextBox Overview</span></span>](richtextbox-overview.md)
- [<span data-ttu-id="351cc-113">Cenni preliminari sulla classe TextBox</span><span class="sxs-lookup"><span data-stu-id="351cc-113">TextBox Overview</span></span>](textbox-overview.md)
