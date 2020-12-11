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
# <a name="contextmenu-overview"></a>Cenni preliminari sull'oggetto ContextMenu
La <xref:System.Windows.Controls.ContextMenu> classe rappresenta l'elemento che espone la funzionalità utilizzando un oggetto specifico del contesto <xref:System.Windows.Controls.Menu> . In genere, un utente espone <xref:System.Windows.Controls.ContextMenu> in [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] facendo clic con il pulsante destro del mouse sul pulsante del mouse. Questo argomento introduce l' <xref:System.Windows.Controls.ContextMenu> elemento e fornisce esempi su come usarlo in [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] e nel codice.  

<a name="contextmenu_control"></a>
## <a name="contextmenu-control"></a>Controllo ContextMenu  
 Un oggetto <xref:System.Windows.Controls.ContextMenu> è associato a un controllo specifico. L' <xref:System.Windows.Controls.ContextMenu> elemento consente di presentare agli utenti un elenco di elementi che specificano i comandi o le opzioni associate a un particolare controllo, ad esempio un oggetto <xref:System.Windows.Controls.Button> . Gli utenti possono fare clic con il pulsante destro del mouse sul controllo per visualizzare il menu. In genere, quando <xref:System.Windows.Controls.MenuItem> si fa clic su un sottomenu viene aperto un sottomenu o viene eseguita un'applicazione per eseguire un comando.  
  
<a name="creating_contextmenus"></a>
## <a name="creating-contextmenus"></a>Creazione di elementi ContextMenu  
 Gli esempi seguenti illustrano come creare un <xref:System.Windows.Controls.ContextMenu> con i sottomenu. I <xref:System.Windows.Controls.ContextMenu> controlli sono collegati ai controlli Button.  
  
 [!code-xaml[ContextMenu#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml#1)]  
  
 [!code-csharp[ContextMenu#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenu/CSharp/Pane1.xaml.cs#2)]
 [!code-vb[ContextMenu#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ContextMenu/VisualBasic/Pane1.xaml.vb#2)]  
  
<a name="applying_styles_to_contextmenu"></a>
## <a name="applying-styles-to-a-contextmenu"></a>Applicazione di stili a un elemento ContextMenu  
 Utilizzando un controllo <xref:System.Windows.Style> , è possibile modificare in modo significativo l'aspetto e il comportamento di un <xref:System.Windows.Controls.ContextMenu> senza scrivere un controllo personalizzato. Oltre a impostare proprietà visive, è anche possibile applicare stili alle parti di un controllo. Ad esempio, è possibile modificare il comportamento delle parti del controllo utilizzando le proprietà oppure è possibile aggiungere parti o modificare il layout di un oggetto <xref:System.Windows.Controls.ContextMenu> . Negli esempi seguenti vengono illustrati diversi modi per aggiungere stili ai <xref:System.Windows.Controls.ContextMenu> controlli.  
  
 Nel primo esempio viene definito uno stile denominato `SimpleSysResources`, che illustra come usare le impostazioni di sistema correnti nello stile. Nell'esempio viene assegnato <xref:System.Windows.SystemColors.MenuHighlightBrushKey%2A> come <xref:System.Windows.Controls.Control.Background%2A> colore e <xref:System.Windows.SystemColors.MenuTextBrushKey%2A> come <xref:System.Windows.Controls.Control.Foreground%2A> colore dell'oggetto <xref:System.Windows.Controls.ContextMenu> .  
  
```xaml  
<Style x:Key="SimpleSysResources" TargetType="{x:Type MenuItem}">  
  <Setter Property = "Background" Value=
    "{DynamicResource {x:Static SystemColors.MenuHighlightBrushKey}}"/>  
  <Setter Property = "Foreground" Value=
    "{DynamicResource {x:Static SystemColors.MenuTextBrushKey}}"/>  
</Style>  
```  
  
 Nell'esempio seguente viene usato l' <xref:System.Windows.Trigger> elemento per modificare l'aspetto di un oggetto <xref:System.Windows.Controls.Menu> in risposta a eventi generati in <xref:System.Windows.Controls.ContextMenu> . Quando un utente sposta il puntatore del mouse sul menu, viene modificato l'aspetto degli <xref:System.Windows.Controls.ContextMenu> elementi.  
  
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
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.ContextMenu>
- <xref:System.Windows.Style>
- <xref:System.Windows.Controls.Menu>
- <xref:System.Windows.Controls.MenuItem>
- [ContextMenu](contextmenu.md)
- [Stili e modelli di ContextMenu](contextmenu-styles-and-templates.md)
- [Esempio di raccolta di controlli WPF](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout)
