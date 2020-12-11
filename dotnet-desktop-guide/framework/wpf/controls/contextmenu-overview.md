---
title: Cenni preliminari sull'oggetto ContextMenu
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], ContextMenu
- ContextMenu controls [WPF], about ContextMenu controls
ms.assetid: 16909c42-799a-4561-91e0-7d69dcfeea91
ms.openlocfilehash: c9e63efb37c8847f27ca4b3616f6f1b5323ac3e5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967102"
---
# <a name="contextmenu-overview"></a><span data-ttu-id="0b32e-102">Cenni preliminari sull'oggetto ContextMenu</span><span class="sxs-lookup"><span data-stu-id="0b32e-102">ContextMenu Overview</span></span>
<span data-ttu-id="0b32e-103">La <xref:System.Windows.Controls.ContextMenu> classe rappresenta l'elemento che espone la funzionalità utilizzando un oggetto specifico del contesto <xref:System.Windows.Controls.Menu> .</span><span class="sxs-lookup"><span data-stu-id="0b32e-103">The <xref:System.Windows.Controls.ContextMenu> class represents the element that exposes functionality by using a context-specific <xref:System.Windows.Controls.Menu>.</span></span> <span data-ttu-id="0b32e-104">In genere, un utente espone <xref:System.Windows.Controls.ContextMenu> in [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] facendo clic con il pulsante destro del mouse sul pulsante del mouse.</span><span class="sxs-lookup"><span data-stu-id="0b32e-104">Typically, a user exposes the <xref:System.Windows.Controls.ContextMenu> in the [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] by right-clicking the mouse button.</span></span> <span data-ttu-id="0b32e-105">Questo argomento introduce l' <xref:System.Windows.Controls.ContextMenu> elemento e fornisce esempi su come usarlo in [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] e nel codice.</span><span class="sxs-lookup"><span data-stu-id="0b32e-105">This topic introduces the <xref:System.Windows.Controls.ContextMenu> element and provides examples of how to use it in [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] and code.</span></span>  

<a name="contextmenu_control"></a>
## <a name="contextmenu-control"></a><span data-ttu-id="0b32e-106">Controllo ContextMenu</span><span class="sxs-lookup"><span data-stu-id="0b32e-106">ContextMenu Control</span></span>  
 <span data-ttu-id="0b32e-107">Un oggetto <xref:System.Windows.Controls.ContextMenu> è associato a un controllo specifico.</span><span class="sxs-lookup"><span data-stu-id="0b32e-107">A <xref:System.Windows.Controls.ContextMenu> is attached to a specific control.</span></span> <span data-ttu-id="0b32e-108">L' <xref:System.Windows.Controls.ContextMenu> elemento consente di presentare agli utenti un elenco di elementi che specificano i comandi o le opzioni associate a un particolare controllo, ad esempio un oggetto <xref:System.Windows.Controls.Button> .</span><span class="sxs-lookup"><span data-stu-id="0b32e-108">The <xref:System.Windows.Controls.ContextMenu> element enables you to present users with a list of items that specify commands or options that are associated with a particular control, for example, a <xref:System.Windows.Controls.Button>.</span></span> <span data-ttu-id="0b32e-109">Gli utenti possono fare clic con il pulsante destro del mouse sul controllo per visualizzare il menu.</span><span class="sxs-lookup"><span data-stu-id="0b32e-109">Users right-click the control to make the menu appear.</span></span> <span data-ttu-id="0b32e-110">In genere, quando <xref:System.Windows.Controls.MenuItem> si fa clic su un sottomenu viene aperto un sottomenu o viene eseguita un'applicazione per eseguire un comando.</span><span class="sxs-lookup"><span data-stu-id="0b32e-110">Typically, clicking a <xref:System.Windows.Controls.MenuItem> opens a submenu or causes an application to carry out a command.</span></span>  
  
<a name="creating_contextmenus"></a>
## <a name="creating-contextmenus"></a><span data-ttu-id="0b32e-111">Creazione di elementi ContextMenu</span><span class="sxs-lookup"><span data-stu-id="0b32e-111">Creating ContextMenus</span></span>  
 <span data-ttu-id="0b32e-112">Gli esempi seguenti illustrano come creare un <xref:System.Windows.Controls.ContextMenu> con i sottomenu.</span><span class="sxs-lookup"><span data-stu-id="0b32e-112">The following examples show how to create a <xref:System.Windows.Controls.ContextMenu> with submenus.</span></span> <span data-ttu-id="0b32e-113">I <xref:System.Windows.Controls.ContextMenu> controlli sono collegati ai controlli Button.</span><span class="sxs-lookup"><span data-stu-id="0b32e-113">The <xref:System.Windows.Controls.ContextMenu> controls are attached to button controls.</span></span>  
  
 [!code-xaml[ContextMenu#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml#1)]  
  
 [!code-csharp[ContextMenu#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ContextMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ContextMenu/VisualBasic/Pane1.xaml.vb#2)]  
  
<a name="applying_styles_to_contextmenu"></a>
## <a name="applying-styles-to-a-contextmenu"></a><span data-ttu-id="0b32e-114">Applicazione di stili a un elemento ContextMenu</span><span class="sxs-lookup"><span data-stu-id="0b32e-114">Applying Styles to a ContextMenu</span></span>  
 <span data-ttu-id="0b32e-115">Utilizzando un controllo <xref:System.Windows.Style> , è possibile modificare in modo significativo l'aspetto e il comportamento di un <xref:System.Windows.Controls.ContextMenu> senza scrivere un controllo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="0b32e-115">By using a control <xref:System.Windows.Style>, you can dramatically change the appearance and behavior of a <xref:System.Windows.Controls.ContextMenu> without writing a custom control.</span></span> <span data-ttu-id="0b32e-116">Oltre a impostare proprietà visive, è anche possibile applicare stili alle parti di un controllo.</span><span class="sxs-lookup"><span data-stu-id="0b32e-116">In addition to setting visual properties, you can also apply styles to parts of a control.</span></span> <span data-ttu-id="0b32e-117">Ad esempio, è possibile modificare il comportamento delle parti del controllo utilizzando le proprietà oppure è possibile aggiungere parti o modificare il layout di un oggetto <xref:System.Windows.Controls.ContextMenu> .</span><span class="sxs-lookup"><span data-stu-id="0b32e-117">For example, you can change the behavior of parts of the control by using properties, or you can add parts to, or change the layout of, a <xref:System.Windows.Controls.ContextMenu>.</span></span> <span data-ttu-id="0b32e-118">Negli esempi seguenti vengono illustrati diversi modi per aggiungere stili ai <xref:System.Windows.Controls.ContextMenu> controlli.</span><span class="sxs-lookup"><span data-stu-id="0b32e-118">The following examples show several ways to add styles to <xref:System.Windows.Controls.ContextMenu> controls.</span></span>  
  
 <span data-ttu-id="0b32e-119">Nel primo esempio viene definito uno stile denominato `SimpleSysResources`, che illustra come usare le impostazioni di sistema correnti nello stile.</span><span class="sxs-lookup"><span data-stu-id="0b32e-119">The first example defines a style called `SimpleSysResources`, which shows how to use the current system settings in your style.</span></span> <span data-ttu-id="0b32e-120">Nell'esempio viene assegnato <xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A> come <xref:System.Windows.Controls.Control.Background%2A> colore e <xref:System.Windows.SystemColors.MenuTextBrushKey%2A> come <xref:System.Windows.Controls.Control.Foreground%2A> colore dell'oggetto <xref:System.Windows.Controls.ContextMenu> .</span><span class="sxs-lookup"><span data-stu-id="0b32e-120">The example assigns <xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A> as the <xref:System.Windows.Controls.Control.Background%2A> color and <xref:System.Windows.SystemColors.MenuTextBrushKey%2A> as the <xref:System.Windows.Controls.Control.Foreground%2A> color of the <xref:System.Windows.Controls.ContextMenu>.</span></span>  
  
```xaml  
<Style x:Key="SimpleSysResources" TargetType="{x:Type MenuItem}">  
  <Setter Property = "Background" Value=
    "{DynamicResource {x:Static SystemColors.MenuHighlightBrushKey}}"/>  
  <Setter Property = "Foreground" Value=
    "{DynamicResource {x:Static SystemColors.MenuTextBrushKey}}"/>  
</Style>  
```  
  
 <span data-ttu-id="0b32e-121">Nell'esempio seguente viene usato l' <xref:System.Windows.Trigger> elemento per modificare l'aspetto di un oggetto <xref:System.Windows.Controls.Menu> in risposta a eventi generati in <xref:System.Windows.Controls.ContextMenu> .</span><span class="sxs-lookup"><span data-stu-id="0b32e-121">The following example uses the <xref:System.Windows.Trigger> element to change the appearance of a <xref:System.Windows.Controls.Menu> in response to events that are raised on the <xref:System.Windows.Controls.ContextMenu>.</span></span> <span data-ttu-id="0b32e-122">Quando un utente sposta il puntatore del mouse sul menu, viene modificato l'aspetto degli <xref:System.Windows.Controls.ContextMenu> elementi.</span><span class="sxs-lookup"><span data-stu-id="0b32e-122">When a user moves the mouse over the menu, the appearance of the <xref:System.Windows.Controls.ContextMenu> items changes.</span></span>  
  
```xaml  
<Style x:Key="Triggers" TargetType="{x:Type MenuItem}">  
  <Style.Triggers>  
    <Trigger Property="MenuItem.IsMouseOver" Value="true">  
      <Setter Property = "FontSize" Value="16"/>  
      <Setter Property = "FontStyle" Value="Italic"/>  
      <Setter Property = "Foreground" Value="Red"/>  
    </Trigger>  
  </Style.Triggers>  
</Style>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0b32e-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b32e-123">See also</span></span>

- <xref:System.Windows.Controls.ContextMenu>
- <xref:System.Windows.Style>
- <xref:System.Windows.Controls.Menu>
- <xref:System.Windows.Controls.MenuItem>
- [<span data-ttu-id="0b32e-124">ContextMenu</span><span class="sxs-lookup"><span data-stu-id="0b32e-124">ContextMenu</span></span>](contextmenu.md)
- [<span data-ttu-id="0b32e-125">Stili e modelli di ContextMenu</span><span class="sxs-lookup"><span data-stu-id="0b32e-125">ContextMenu Styles and Templates</span></span>](contextmenu-styles-and-templates.md)
- [<span data-ttu-id="0b32e-126">Esempio di raccolta di controlli WPF</span><span class="sxs-lookup"><span data-stu-id="0b32e-126">WPF Controls Gallery Sample</span></span>](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout)
