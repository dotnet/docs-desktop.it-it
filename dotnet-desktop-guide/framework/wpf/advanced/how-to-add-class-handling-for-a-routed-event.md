---
title: 'Procedura: aggiungere la gestione di classi per un evento indirizzato'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- routed events [WPF], class handlers
- task_core_add_class_handling_routed_properties [WPF]
- class handlers [WPF], routed events
ms.assetid: 15b7b06c-9112-4ee5-b30a-65d10c5c5df6
ms.openlocfilehash: 7b897954cbdab461dc0305c6290e67c1af5282c3
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964621"
---
# <a name="how-to-add-class-handling-for-a-routed-event"></a>Procedura: aggiungere la gestione di classi per un evento indirizzato
Gli eventi indirizzati possono essere gestiti dai gestori di classi o delle istanze in qualsiasi nodo specificato nella route. I gestori di classi vengono richiamati per primi e possono essere usati dalle implementazioni delle classi per evitare gli eventi dalla gestione dell'istanza o introdurre altri comportamenti specifici degli eventi negli eventi di proprietà delle classi di base. In questo esempio vengono illustrate due tecniche strettamente correlate per l'implementazione di gestori di classi.  
  
## <a name="example"></a>Esempio  
 In questo esempio viene usata una classe personalizzata basata sul <xref:System.Windows.Controls.Canvas> pannello. Il presupposto di base dell'applicazione consiste nel fatto che la classe personalizzata introduce comportamenti sui relativi elementi figlio, inclusa l'intercettazione di eventuali clic del pulsante sinistro del mouse e la relativa segnalazione, prima che venga richiamata la classe dell'elemento figlio o qualsiasi gestore di istanza.  
  
 La <xref:System.Windows.UIElement> classe espone un metodo virtuale che consente la gestione delle classi sull' <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> evento, semplicemente eseguendo l'override dell'evento. Questo è il modo più semplice per implementare la gestione delle classi se tale metodo virtuale è disponibile in un punto qualsiasi della gerarchia della classe. Il codice seguente illustra l' <xref:System.Windows.UIElement.OnPreviewMouseLeftButtonDown%2A> implementazione in "MyEditContainer" derivata da <xref:System.Windows.Controls.Canvas> . L'implementazione contrassegna l'evento come gestito negli argomenti, quindi aggiunge del codice per fornire all'elemento di origine una modifica visibile di base.  
  
 [!code-csharp[ClassHandling#OnStarClassHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/ClassHandling/CSharp/SDKSampleLibrary/class1.cs#onstarclasshandler)]
 [!code-vb[ClassHandling#OnStarClassHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ClassHandling/visualbasic/sdksamplelibrary/class1.vb#onstarclasshandler)]  
  
 Se non è disponibile alcuna rete virtuale per le classi base o per quel particolare metodo, la gestione delle classi può essere aggiunta direttamente usando un metodo di utilità della <xref:System.Windows.EventManager> classe, <xref:System.Windows.EventManager.RegisterClassHandler%2A> . Questo metodo deve essere chiamato solo all'interno dell'inizializzazione statica delle classi che aggiungono la gestione delle classi. In questo esempio viene aggiunto un altro gestore per <xref:System.Windows.UIElement.PreviewMouseLeftButtonDown> e in questo caso la classe registrata è la classe personalizzata. Al contrario, quando si usano i virtuali, la classe registrata è effettivamente la <xref:System.Windows.UIElement> classe di base. Nei casi in cui le classi base e la sottoclasse eseguono ogni registrazione della classe, i gestori della sottoclasse vengono richiamati per primi. Il comportamento in un'applicazione sarebbe che prima di questo gestore venisse visualizzata la finestra di messaggio e quindi la modifica visiva nel gestore del metodo virtuale verrebbe visualizzata.  
  
 [!code-csharp[ClassHandling#StaticAndRegisterClassHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/ClassHandling/CSharp/SDKSampleLibrary/class1.cs#staticandregisterclasshandler)]
 [!code-vb[ClassHandling#StaticAndRegisterClassHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ClassHandling/visualbasic/sdksamplelibrary/class1.vb#staticandregisterclasshandler)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.EventManager>
- [Impostazione degli eventi indirizzati come gestiti e gestione delle classi](marking-routed-events-as-handled-and-class-handling.md)
- [Gestire un evento indirizzato](how-to-handle-a-routed-event.md)
- [Cenni preliminari sugli eventi indirizzati](routed-events-overview.md)
