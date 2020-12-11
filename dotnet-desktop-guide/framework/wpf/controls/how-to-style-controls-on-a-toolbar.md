---
title: 'Procedura: applicare uno stile ai controlli di un oggetto ToolBar'
ms.date: 03/30/2017
helpviewer_keywords:
- styling controls on toolbar [WPF]
- toolbars [WPF]
- customizing controls on toolbar [WPF]
ms.assetid: ba6ae056-d6a9-4c24-90f8-467ab0bc0b1a
ms.openlocfilehash: 22d3375b1177e13a1673e9720c1c241d7d3bfa08
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951887"
---
# <a name="how-to-style-controls-on-a-toolbar"></a><span data-ttu-id="62df6-102">Procedura: applicare uno stile ai controlli di un oggetto ToolBar</span><span class="sxs-lookup"><span data-stu-id="62df6-102">How to: Style Controls on a ToolBar</span></span>
<span data-ttu-id="62df6-103"><xref:System.Windows.Controls.ToolBar>Definisce <xref:System.Windows.ResourceKey> gli oggetti per specificare lo stile dei controlli all'interno di <xref:System.Windows.Controls.ToolBar> .</span><span class="sxs-lookup"><span data-stu-id="62df6-103">The <xref:System.Windows.Controls.ToolBar> defines <xref:System.Windows.ResourceKey> objects to specify the style of controls within the <xref:System.Windows.Controls.ToolBar>.</span></span>  <span data-ttu-id="62df6-104">Per applicare uno stile a un controllo in un oggetto <xref:System.Windows.Controls.ToolBar> , impostare l' `x:key` attributo dello stile su un oggetto <xref:System.Windows.ResourceKey> definito in <xref:System.Windows.Controls.ToolBar> .</span><span class="sxs-lookup"><span data-stu-id="62df6-104">To style a control in a <xref:System.Windows.Controls.ToolBar>, set the `x:key` attribute of the style to a <xref:System.Windows.ResourceKey> defined in <xref:System.Windows.Controls.ToolBar>.</span></span>  
  
 <span data-ttu-id="62df6-105"><xref:System.Windows.Controls.ToolBar>Definisce gli oggetti seguenti <xref:System.Windows.ResourceKey> :</span><span class="sxs-lookup"><span data-stu-id="62df6-105">The <xref:System.Windows.Controls.ToolBar> defines the following <xref:System.Windows.ResourceKey> objects:</span></span>  
  
- <xref:System.Windows.Controls.ToolBar.ButtonStyleKey%2A>  
  
- <xref:System.Windows.Controls.ToolBar.CheckBoxStyleKey%2A>  
  
- <xref:System.Windows.Controls.ToolBar.ComboBoxStyleKey%2A>  
  
- <xref:System.Windows.Controls.ToolBar.MenuStyleKey%2A>  
  
- <xref:System.Windows.Controls.ToolBar.RadioButtonStyleKey%2A>  
  
- <xref:System.Windows.Controls.ToolBar.SeparatorStyleKey%2A>  
  
- <xref:System.Windows.Controls.ToolBar.TextBoxStyleKey%2A>  
  
- <xref:System.Windows.Controls.ToolBar.ToggleButtonStyleKey%2A>  
  
## <a name="example"></a><span data-ttu-id="62df6-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="62df6-106">Example</span></span>  
 <span data-ttu-id="62df6-107">Nell'esempio seguente vengono definiti gli stili per i controlli all'interno di un oggetto <xref:System.Windows.Controls.ToolBar> .</span><span class="sxs-lookup"><span data-stu-id="62df6-107">The following example defines styles for the controls within a <xref:System.Windows.Controls.ToolBar>.</span></span>  
  
 [!code-xaml[ToolBar_snip#ToolBarAllStyles](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolBar_snip/CS/pane1.xaml#toolbarallstyles)]  
[!code-xaml[ToolBar_snip#ToolBar](~/samples/snippets/csharp/VS_Snippets_Wpf/ToolBar_snip/CS/pane1.xaml#toolbar)]  
  
## <a name="see-also"></a><span data-ttu-id="62df6-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="62df6-108">See also</span></span>

- [<span data-ttu-id="62df6-109">Applicazione di stili e modelli</span><span class="sxs-lookup"><span data-stu-id="62df6-109">Styling and Templating</span></span>](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
