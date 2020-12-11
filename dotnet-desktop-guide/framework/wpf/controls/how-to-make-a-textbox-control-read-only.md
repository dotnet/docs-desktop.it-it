---
title: 'Procedura: impostare la proprietà di sola lettura per un controllo TextBox'
ms.date: 03/30/2017
helpviewer_keywords:
- read-only TextBox controls [WPF]
- TextBox control read-only
ms.assetid: e707ec59-8b22-473e-b77c-3060a237517a
ms.openlocfilehash: 45fda33b5840bd89dac8d9e99f7dd1a8dd065838
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966631"
---
# <a name="how-to-make-a-textbox-control-read-only"></a><span data-ttu-id="87cfd-102">Procedura: impostare la proprietà di sola lettura per un controllo TextBox</span><span class="sxs-lookup"><span data-stu-id="87cfd-102">How to: Make a TextBox Control Read-Only</span></span>
<span data-ttu-id="87cfd-103">Questo esempio illustra come configurare un <xref:System.Windows.Controls.TextBox> controllo in modo da non consentire l'input o la modifica dell'utente.</span><span class="sxs-lookup"><span data-stu-id="87cfd-103">This example shows how to configure a <xref:System.Windows.Controls.TextBox> control to not allow user input or modification.</span></span>  
  
## <a name="example"></a><span data-ttu-id="87cfd-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="87cfd-104">Example</span></span>  
 <span data-ttu-id="87cfd-105">Per impedire agli utenti di modificare il contenuto di un <xref:System.Windows.Controls.TextBox> controllo, impostare l' <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> attributo su **true**.</span><span class="sxs-lookup"><span data-stu-id="87cfd-105">To prevent users from modifying the contents of a <xref:System.Windows.Controls.TextBox> control, set the <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> attribute to **true**.</span></span>  
  
 [!code-xaml[TextBox_MiscCode#_ReadOnlyTextBoxXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBox_MiscCode/CSharp/Window1.xaml#_readonlytextboxxaml)]  
  
 <span data-ttu-id="87cfd-106">L' <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> attributo influisce solo sull'input dell'utente e non influisce sul set di testo nella [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] Descrizione di un <xref:System.Windows.Controls.TextBox> controllo o su un set di testo a livello di codice tramite la <xref:System.Windows.Controls.TextBox.Text%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="87cfd-106">The <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> attribute affects user input only; it does not affect text set in the [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] description of a <xref:System.Windows.Controls.TextBox> control, or text set programmatically through the <xref:System.Windows.Controls.TextBox.Text%2A> property.</span></span>  
  
 <span data-ttu-id="87cfd-107">Il valore predefinito di <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> è **false**.</span><span class="sxs-lookup"><span data-stu-id="87cfd-107">The default value of <xref:System.Windows.Controls.Primitives.TextBoxBase.IsReadOnly%2A> is **false**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87cfd-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="87cfd-108">See also</span></span>

- [<span data-ttu-id="87cfd-109">Cenni preliminari sulla classe TextBox</span><span class="sxs-lookup"><span data-stu-id="87cfd-109">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="87cfd-110">Cenni generali sul controllo RichTextBox</span><span class="sxs-lookup"><span data-stu-id="87cfd-110">RichTextBox Overview</span></span>](richtextbox-overview.md)
