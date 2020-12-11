---
title: 'Procedura: applicare un oggetto FocusVisualStyle a un controllo'
ms.date: 03/30/2017
helpviewer_keywords:
- properties [WPF], FocusVisualStyle
- FocusVisualStyle property [WPF]
ms.assetid: 363de99e-8ecc-438c-ac4a-f9147432ebd6
ms.openlocfilehash: c27994bfbc77f7cbe360ad3aab94827900e52232
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964075"
---
# <a name="how-to-apply-a-focusvisualstyle-to-a-control"></a>Procedura: applicare un oggetto FocusVisualStyle a un controllo
Questo esempio illustra come creare uno stile di visualizzazione dello stato attivo nelle risorse e applicare lo stile a un controllo usando la <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> Proprietà.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene definito uno stile che crea la composizione di controlli aggiuntivi che si applica solo quando il controllo è attivo nella tastiera [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] . Questa operazione viene eseguita definendo uno stile con un oggetto <xref:System.Windows.Controls.ControlTemplate> , quindi facendo riferimento a tale stile come risorsa quando si imposta la <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> Proprietà.  
  
 Un rettangolo esterno simile a un bordo viene inserito all'esterno dell'area rettangolare. Se non diversamente modificato, il dimensionamento dello stile USA <xref:System.Windows.FrameworkElement.ActualHeight%2A> e <xref:System.Windows.FrameworkElement.ActualWidth%2A> del controllo rettangolare in cui viene applicato lo stile di visualizzazione dello stato attivo. In questo esempio vengono impostati i valori negativi per l'oggetto <xref:System.Windows.FrameworkElement.Margin%2A> affinché il bordo appaia leggermente all'esterno del controllo attivo.  
  
 [!code-xaml[FEFocusVisualStyle#XAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FEFocusVisualStyle/CS/page1.xaml#xaml)]  
  
 Un oggetto <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A> è additivo per qualsiasi stile di modello di controllo che deriva da uno stile esplicito o da uno stile del tema; lo stile principale di un controllo può comunque essere creato utilizzando un oggetto <xref:System.Windows.Controls.ControlTemplate> e impostando tale stile sulla <xref:System.Windows.FrameworkElement.Style%2A> Proprietà.  
  
 Gli stili di visualizzazione dello stato attivo devono essere usati in modo coerente in un tema o in un'interfaccia utente, anziché usare uno diverso per ogni elemento attivabile. Per informazioni dettagliate, vedere applicazione di [stili per lo stato attivo nei controlli e FocusVisualStyle](styling-for-focus-in-controls-and-focusvisualstyle.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.FrameworkElement.FocusVisualStyle%2A>
- [Applicazione di stili e modelli](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [Applicazione di stili per lo stato attivo nei controlli e FocusVisualStyle](styling-for-focus-in-controls-and-focusvisualstyle.md)
