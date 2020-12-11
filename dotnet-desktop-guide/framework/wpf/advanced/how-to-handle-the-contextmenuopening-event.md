---
title: "Procedura: gestire l'evento ContextMenuOpening"
ms.date: 03/30/2017
helpviewer_keywords:
- ContextMenuOpening properties [WPF]
ms.assetid: 789652fb-1951-4217-934a-7843e355adf4
ms.openlocfilehash: b3d0f5c77ebf8527e4854d4edf12d6fa8a4b5f0c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964972"
---
# <a name="how-to-handle-the-contextmenuopening-event"></a>Procedura: gestire l'evento ContextMenuOpening
L' <xref:System.Windows.FrameworkElement.ContextMenuOpening> evento può essere gestito in un'applicazione per modificare un menu di scelta rapida esistente prima di visualizzare o per escludere il menu che altrimenti verrebbe visualizzato impostando la <xref:System.Windows.RoutedEventArgs.Handled%2A> proprietà su `true` nei dati dell'evento. Il motivo tipico per impostare <xref:System.Windows.RoutedEventArgs.Handled%2A> su `true` nei dati dell'evento consiste nel sostituire il menu interamente con un nuovo <xref:System.Windows.Controls.ContextMenu> oggetto, a volte è necessario annullare l'operazione e avviare una nuova apertura. Se si scrivono i gestori per l' <xref:System.Windows.FrameworkElement.ContextMenuOpening> evento, è necessario tenere presenti i problemi di temporizzazione tra un <xref:System.Windows.Controls.ContextMenu> controllo e il servizio responsabile dell'apertura e del posizionamento dei menu di scelta rapida per i controlli in generale. In questo argomento vengono illustrate alcune delle tecniche di codice per vari scenari di apertura del menu di scelta rapida e viene illustrato un caso in cui si verifica il problema di temporizzazione.  
  
 Esistono diversi scenari per la gestione dell' <xref:System.Windows.FrameworkElement.ContextMenuOpening> evento:  
  
- Modifica delle voci di menu prima della visualizzazione.  
  
- Sostituzione dell'intero menu prima della visualizzazione.  
  
- Eliminazione completa di qualsiasi menu di scelta rapida esistente e visualizzazione di nessun menu di scelta rapida.  
  
## <a name="example"></a>Esempio  
  
## <a name="adjusting-the-menu-items-before-display"></a>Modifica delle voci di menu prima della visualizzazione  
 Modificare le voci di menu esistenti è piuttosto semplice ed è probabilmente lo scenario più comune. È possibile eseguire questa operazione per aggiungere o sottrarre le opzioni del menu di scelta rapida in risposta alle informazioni sullo stato corrente dell'applicazione o a informazioni di stato specifiche disponibili come proprietà nell'oggetto in cui è richiesto il menu di scelta rapida.  
  
 La tecnica generale è quella di ottenere l'origine dell'evento, ovvero il controllo specifico su cui è stato fatto clic con il pulsante destro del mouse e di ottenere la <xref:System.Windows.FrameworkElement.ContextMenu%2A> Proprietà. In genere si vuole controllare la <xref:System.Windows.Controls.ItemsControl.Items%2A> raccolta per visualizzare le voci del menu di scelta rapida già presenti nel menu e quindi aggiungere o rimuovere <xref:System.Windows.Controls.MenuItem> i nuovi elementi appropriati da o verso la raccolta.  
  
 [!code-csharp[ContextMenuOpeningHandlers#AddItemNoHandle](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#additemnohandle)]  
  
## <a name="replacing-the-entire-menu-before-display"></a>Sostituzione dell'intero menu prima della visualizzazione  
 Uno scenario alternativo è se si desidera sostituire l'intero menu di scelta rapida. Si può ovviamente usare anche una variante del codice precedente, per rimuovere ogni elemento di un menu di scelta rapida esistente e aggiungerne di nuovi iniziando con l'elemento zero. Tuttavia, l'approccio più intuitivo per sostituire tutti gli elementi nel menu di scelta rapida consiste nel creare un nuovo oggetto <xref:System.Windows.Controls.ContextMenu> , popolarlo con gli elementi, quindi impostare la <xref:System.Windows.FrameworkElement.ContextMenu%2A?displayProperty=nameWithType> proprietà di un controllo come nuovo <xref:System.Windows.Controls.ContextMenu> .  
  
 Di seguito è riportato il semplice codice del gestore per la sostituzione di un oggetto <xref:System.Windows.Controls.ContextMenu> . Il codice fa riferimento a un `BuildMenu` metodo personalizzato, che è separato perché viene chiamato da più gestori di esempio.  
  
 [!code-csharp[ContextMenuOpeningHandlers#ReplaceNoReopen](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#replacenoreopen)]  
  
 [!code-csharp[ContextMenuOpeningHandlers#BuildMenu](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#buildmenu)]  
  
 Tuttavia, se si usa questo stile di gestione per <xref:System.Windows.FrameworkElement.ContextMenuOpening> , è possibile esporre un problema di temporizzazione se l'oggetto in cui si sta impostando <xref:System.Windows.Controls.ContextMenu> non dispone di un menu di scelta rapida preesistente. Quando un utente fa clic con il pulsante destro del mouse su un controllo, <xref:System.Windows.FrameworkElement.ContextMenuOpening> viene generato anche se l'oggetto esistente <xref:System.Windows.Controls.ContextMenu> è vuoto o null. Tuttavia, in questo caso, qualsiasi <xref:System.Windows.Controls.ContextMenu> elemento nuovo impostato sull'elemento di origine arriva troppo tardi per essere visualizzato. Inoltre, se l'utente fa clic con il pulsante destro del mouse su una seconda volta, questa volta <xref:System.Windows.Controls.ContextMenu> viene visualizzato il valore non null e il gestore sostituirà correttamente e visualizzerà il menu quando il gestore verrà eseguito una seconda volta. Questo suggerisce due possibili soluzioni alternative:  
  
1. Assicurarsi che <xref:System.Windows.FrameworkElement.ContextMenuOpening> i gestori vengano sempre eseguiti sui controlli con almeno un segnaposto <xref:System.Windows.Controls.ContextMenu> disponibile, che deve essere sostituito dal codice del gestore. In questo caso, è comunque possibile utilizzare il gestore illustrato nell'esempio precedente, ma in genere si desidera assegnare un segnaposto <xref:System.Windows.Controls.ContextMenu> nel markup iniziale:  
  
     [!code-xaml[ContextMenuOpeningHandlers#XAMLWithInitCM](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml#xamlwithinitcm)]  
  
2. Si supponga che il <xref:System.Windows.Controls.ContextMenu> valore iniziale possa essere null, in base a una logica preliminare. È possibile verificare la presenza <xref:System.Windows.Controls.ContextMenu> di valori null o usare un flag nel codice per verificare se il gestore è stato eseguito almeno una volta. Poiché si presuppone che <xref:System.Windows.Controls.ContextMenu> sta per essere visualizzato, il gestore imposta <xref:System.Windows.RoutedEventArgs.Handled%2A> su `true` nei dati dell'evento. Per l'oggetto <xref:System.Windows.Controls.ContextMenuService> che è responsabile della visualizzazione del menu di scelta rapida, un `true` valore per <xref:System.Windows.RoutedEventArgs.Handled%2A> nei dati dell'evento rappresenta una richiesta per annullare la visualizzazione della combinazione di menu di scelta rapida o controllo che ha generato l'evento.  
  
 Ora che il menu di scelta rapida potenzialmente sospetto è stato eliminato, il passaggio successivo consiste nel fornire uno nuovo, quindi visualizzarlo. L'impostazione di un nuovo è fondamentalmente uguale al gestore precedente: si compila un nuovo oggetto <xref:System.Windows.Controls.ContextMenu> e si imposta la proprietà dell'origine del controllo <xref:System.Windows.FrameworkElement.ContextMenu%2A?displayProperty=nameWithType> . Il passaggio aggiuntivo è che ora è necessario forzare la visualizzazione del menu di scelta rapida, perché il primo tentativo è stato eliminato. Per forzare la visualizzazione, impostare la <xref:System.Windows.Controls.Primitives.Popup.IsOpen%2A?displayProperty=nameWithType> proprietà su `true` all'interno del gestore. Prestare attenzione quando si esegue questa operazione, perché aprendo il menu di scelta rapida nel gestore viene generato <xref:System.Windows.FrameworkElement.ContextMenuOpening> nuovamente l'evento. Se si immette nuovamente il gestore, diventa infinitamente ricorsivo. Questo è il motivo per cui è sempre necessario controllare `null` o usare un flag se si apre un menu di scelta rapida dall'interno di un <xref:System.Windows.FrameworkElement.ContextMenuOpening> gestore eventi.  
  
## <a name="suppressing-any-existing-context-menu-and-displaying-no-context-menu"></a>Eliminazione di qualsiasi menu di scelta rapida esistente e visualizzazione di nessun menu di scelta rapida  
 Lo scenario finale, ovvero la scrittura di un gestore che evita completamente un menu, non è comune. Se un determinato controllo non deve visualizzare un menu di scelta rapida, è probabile che si verifichino alcune modalità più appropriate rispetto a quando un utente la richiede. Tuttavia, se si desidera utilizzare il gestore per disattivare un menu di scelta rapida e non visualizzare nulla, il gestore deve semplicemente impostare <xref:System.Windows.RoutedEventArgs.Handled%2A> su `true` nei dati dell'evento. L'oggetto <xref:System.Windows.Controls.ContextMenuService> che è responsabile della visualizzazione di un menu di scelta rapida verificherà i dati dell'evento generato sul controllo. Se l'evento è stato contrassegnato in <xref:System.Windows.RoutedEventArgs.Handled%2A> un punto qualsiasi lungo la route, il menu di scelta rapida Apri azione che ha avviato l'evento viene eliminato.  
  
 [!code-csharp[ContextMenuOpeningHandlers#ReplaceReopen](~/samples/snippets/csharp/VS_Snippets_Wpf/ContextMenuOpeningHandlers/CSharp/Pane1.xaml.cs#replacereopen)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.ContextMenu>
- <xref:System.Windows.FrameworkElement.ContextMenu%2A?displayProperty=nameWithType>
- [Cenni preliminari sugli elementi di base](base-elements-overview.md)
- [Cenni preliminari sull'oggetto ContextMenu](../controls/contextmenu-overview.md)
