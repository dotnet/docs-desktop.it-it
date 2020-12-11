---
title: 'Procedura: posizionare un menu di scelta rapida personalizzato in un controllo RichTextBox'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom context menus [WPF], positioning
- positioning custom context menus [WPF]
- RichTextBox control [WPF], positioning custom context menus
- context menus [WPF], positioning
ms.assetid: bf77c930-a546-4573-9a56-9af345ba189a
ms.openlocfilehash: f9407f59c3daafd09fa5b84006f33ef2f3ebd31f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969769"
---
# <a name="how-to-position-a-custom-context-menu-in-a-richtextbox"></a><span data-ttu-id="25471-102">Procedura: posizionare un menu di scelta rapida personalizzato in un controllo RichTextBox</span><span class="sxs-lookup"><span data-stu-id="25471-102">How to: Position a Custom Context Menu in a RichTextBox</span></span>
<span data-ttu-id="25471-103">Questo esempio illustra come posizionare un menu di scelta rapida personalizzato per un oggetto <xref:System.Windows.Controls.RichTextBox> .</span><span class="sxs-lookup"><span data-stu-id="25471-103">This example shows how to position a custom context menu for a <xref:System.Windows.Controls.RichTextBox>.</span></span>  
  
 <span data-ttu-id="25471-104">Quando si implementa un menu contestuale personalizzato per un oggetto **RichTextBox**, si è responsabili della gestione del posizionamento del menu contestuale.</span><span class="sxs-lookup"><span data-stu-id="25471-104">When you implement a custom context menu for a **RichTextBox**, you are responsible for handling the placement of the context menu.</span></span>  <span data-ttu-id="25471-105">Per impostazione predefinita, un menu contestuale personalizzato si apre al centro dell'oggetto **RichTextBox**.</span><span class="sxs-lookup"><span data-stu-id="25471-105">By default, a custom context menu is opened at the center of the **RichTextBox**.</span></span>  
  
## <a name="example"></a><span data-ttu-id="25471-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="25471-106">Example</span></span>  
 <span data-ttu-id="25471-107">Per eseguire l'override del comportamento di selezione host predefinito, aggiungere un listener per l' <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> evento.</span><span class="sxs-lookup"><span data-stu-id="25471-107">To override the default placement behavior, add a listener for the <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> event.</span></span>  <span data-ttu-id="25471-108">L'esempio seguente illustra come eseguire questa operazione a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="25471-108">The following example shows how to do this programmatically.</span></span>  
  
 [!code-csharp[RichTextBox_ContextMenu#_AddListener](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_ContextMenu/CSharp/app.xaml.cs#_addlistener)]
 [!code-vb[RichTextBox_ContextMenu#_AddListener](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBox_ContextMenu/VisualBasic/app.xaml.vb#_addlistener)]  
  
## <a name="example"></a><span data-ttu-id="25471-109">Esempio</span><span class="sxs-lookup"><span data-stu-id="25471-109">Example</span></span>  
 <span data-ttu-id="25471-110">Nell'esempio seguente viene illustrata un'implementazione del <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> listener di eventi corrispondente.</span><span class="sxs-lookup"><span data-stu-id="25471-110">The following example shows an implementation the corresponding <xref:System.Windows.FrameworkContentElement.ContextMenuOpening> event listener.</span></span>  
  
 [!code-csharp[RichTextBox_ContextMenu#_ListenerBody](~/samples/snippets/csharp/VS_Snippets_Wpf/RichTextBox_ContextMenu/CSharp/app.xaml.cs#_listenerbody)]
 [!code-vb[RichTextBox_ContextMenu#_ListenerBody](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RichTextBox_ContextMenu/VisualBasic/app.xaml.vb#_listenerbody)]  
  
## <a name="see-also"></a><span data-ttu-id="25471-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25471-111">See also</span></span>

- [<span data-ttu-id="25471-112">Cenni generali sul controllo RichTextBox</span><span class="sxs-lookup"><span data-stu-id="25471-112">RichTextBox Overview</span></span>](richtextbox-overview.md)
- [<span data-ttu-id="25471-113">Cenni preliminari sulla classe TextBox</span><span class="sxs-lookup"><span data-stu-id="25471-113">TextBox Overview</span></span>](textbox-overview.md)
