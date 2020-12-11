---
title: 'Procedura: impostare lo stato attivo in un controllo TextBox'
description: Informazioni su come usare il metodo Focus per impostare lo stato attivo su un controllo TextBox Windows Presentation Foundation.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- focus [WPF], setting
- TextBox control [WPF], setting focus
ms.assetid: 24b61b45-dc2d-425e-9839-b017af7ab86f
ms.openlocfilehash: e4c6a174ba0353b89225d2337f138f9feeac947c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965614"
---
# <a name="how-to-set-focus-in-a-textbox-control"></a><span data-ttu-id="ab987-103">Procedura: impostare lo stato attivo in un controllo TextBox</span><span class="sxs-lookup"><span data-stu-id="ab987-103">How to: Set Focus in a TextBox Control</span></span>
<span data-ttu-id="ab987-104">Questo esempio illustra come usare il <xref:System.Windows.UIElement.Focus%2A> metodo per impostare lo stato attivo su un <xref:System.Windows.Controls.TextBox> controllo.</span><span class="sxs-lookup"><span data-stu-id="ab987-104">This example shows how to use the <xref:System.Windows.UIElement.Focus%2A> method to set focus on a <xref:System.Windows.Controls.TextBox> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ab987-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="ab987-105">Example</span></span>  
 <span data-ttu-id="ab987-106">Nell' [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] esempio seguente viene descritto un semplice <xref:System.Windows.Controls.TextBox> controllo denominato *tbFocusMe*</span><span class="sxs-lookup"><span data-stu-id="ab987-106">The following [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] example describes a simple <xref:System.Windows.Controls.TextBox> control named *tbFocusMe*</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_TextBoxFocusXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_textboxfocusxaml)]  
  
## <a name="example"></a><span data-ttu-id="ab987-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="ab987-107">Example</span></span>  
 <span data-ttu-id="ab987-108">Nell'esempio seguente viene chiamato il <xref:System.Windows.UIElement.Focus%2A> metodo per impostare lo stato attivo sul <xref:System.Windows.Controls.TextBox> controllo con il nome *tbFocusMe*.</span><span class="sxs-lookup"><span data-stu-id="ab987-108">The following example calls the <xref:System.Windows.UIElement.Focus%2A> method to set the focus on the <xref:System.Windows.Controls.TextBox> control with the Name *tbFocusMe*.</span></span>  
  
 [!code-csharp[TextBox_MiscCode#_FocusTextBox](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml.cs#_focustextbox)]
 [!code-vb[TextBox_MiscCode#_FocusTextBox](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBox_MiscCode/VisualBasic/Window1.xaml.vb#_focustextbox)]  
  
## <a name="see-also"></a><span data-ttu-id="ab987-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ab987-109">See also</span></span>

- <xref:System.Windows.UIElement.Focusable%2A>
- <xref:System.Windows.UIElement.IsFocused%2A>
- [<span data-ttu-id="ab987-110">Cenni preliminari sulla classe TextBox</span><span class="sxs-lookup"><span data-stu-id="ab987-110">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="ab987-111">Cenni generali sul controllo RichTextBox</span><span class="sxs-lookup"><span data-stu-id="ab987-111">RichTextBox Overview</span></span>](richtextbox-overview.md)
