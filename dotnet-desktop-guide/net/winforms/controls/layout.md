---
title: Opzioni di layout del controllo
description: Informazioni sulle diverse impostazioni di un controllo che influiscono sul layout e sul posizionamento in Windows Forms per .NET. Informazioni sui diversi tipi di contenitori di controllo che interessano il layout.
ms.date: 10/26/2020
ms.topic: overview
helpviewer_keywords:
- forms [Windows Forms], aligning controls
- Windows Forms, aligning controls
- controls [Windows Forms], positioning
- controls [Windows Forms], aligning
- TabControl control [Windows Forms], about TabControl control
- SplitContainer control [Windows Forms], about SplitContainer control
- Panel control [Windows Forms], about Panel control
- GroupBox control [Windows Forms], about GroupBox control
- FlowLayoutPanel control [Windows Forms], about FlowLayoutPanel control
- TableLayoutPanel control [Windows Forms], about TableLayoutPanel control
- sizing [Windows Forms], automatic
- layout [Windows Forms], AutoSize
- automatic sizing
- AutoSizeMode property
ms.openlocfilehash: 542decdf2555dcc01ff544a370f59ac73269ab6c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965482"
---
# <a name="position-and-layout-of-controls-windows-forms-net"></a>Posizione e layout dei controlli (Windows Forms .NET)

La posizione del controllo in Windows Forms viene determinata non solo dal controllo, ma anche dall'elemento padre del controllo. Questo articolo descrive le diverse impostazioni fornite dai controlli e i diversi tipi di contenitori padre che interessano il layout.

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="fixed-position-and-size"></a>Posizione e dimensioni fisse

La posizione in cui un controllo viene visualizzato in un elemento padre è determinata dal valore della <xref:System.Windows.Forms.Control.Location> proprietà rispetto alla parte superiore sinistra della superficie padre. La coordinata della posizione in alto a sinistra nell'elemento padre è `(x0,y0)` . La dimensione del controllo è determinata dalla <xref:System.Windows.Forms.Control.Size> proprietà e rappresenta la larghezza e l'altezza del controllo.

:::image type="content" source="media/layout/location+container.png" alt-text="Posizione del controllo rispetto al contenitore":::

Quando un controllo viene aggiunto a un elemento padre che impone la selezione host automatica, la posizione e le dimensioni del controllo vengono modificate. In questo caso, la posizione e le dimensioni del controllo potrebbero non essere regolate manualmente, a seconda del tipo di elemento padre.

Le <xref:System.Windows.Forms.Control.MaximumSize%2A> <xref:System.Windows.Forms.Control.MinimumSize%2A> proprietà e consentono di impostare lo spazio minimo e massimo che può essere utilizzato da un controllo.

## <a name="automatic-placement-and-size"></a>Selezione host e dimensioni automatiche

I controlli possono essere inseriti automaticamente all'interno dell'elemento padre. Alcuni contenitori padre forzano la selezione host mentre altri rispettano le impostazioni di controllo che guidano il posizionamento. In un controllo sono disponibili due proprietà che consentono di posizionare e ridimensionare automaticamente all'interno di un elemento padre: <xref:System.Windows.Forms.Control.Dock%2A> e <xref:System.Windows.Forms.Control.Anchor> .

L'ordine di disegno può influire sulla selezione host automatica. Ordine in cui un controllo viene disegnato determinato dall'indice del controllo nella raccolta dell'elemento padre <xref:System.Windows.Forms.Control.Controls> . Questo indice è noto come **:::no-loc text="Z-order":::** . Ogni controllo viene disegnato nell'ordine inverso visualizzato nella raccolta. Ciò significa che la raccolta è una raccolta creata per la prima volta e l'ultima volta.

Le <xref:System.Windows.Forms.Control.MinimumSize%2A> <xref:System.Windows.Forms.Control.MaximumSize%2A> proprietà e consentono di impostare lo spazio minimo e massimo che può essere utilizzato da un controllo.

### <a name="dock"></a>Dock

La `Dock` proprietà imposta il bordo del controllo allineato al lato corrispondente dell'elemento padre e il modo in cui il controllo viene ridimensionato all'interno dell'elemento padre.

:::image type="content" source="media/layout/dock-modes.png" alt-text="Windows Form con pulsanti con impostazioni di ancoraggio.":::

Quando un controllo è ancorato, il contenitore determina lo spazio che deve occupare e ridimensionare e posizionare il controllo. La larghezza e l'altezza del controllo vengono comunque rispettate in base allo stile di ancoraggio. Se, ad esempio, il controllo è ancorato alla parte superiore, l'oggetto <xref:System.Windows.Forms.Control.Height> del controllo viene rispettato, ma <xref:System.Windows.Forms.Control.Width> viene regolato automaticamente. Se un controllo è ancorato a sinistra, l'oggetto <xref:System.Windows.Forms.Control.Width> del controllo viene rispettato, ma <xref:System.Windows.Forms.Control.Height> viene regolato automaticamente.

L'oggetto <xref:System.Windows.Forms.Control.Location> del controllo non può essere impostato manualmente come ancoraggio. un controllo ne controlla automaticamente la posizione.

L'oggetto **:::no-loc text="Z-order":::** del controllo influisce sull'ancoraggio. Poiché i controlli ancorati sono disposti, usano lo spazio disponibile. Se, ad esempio, un controllo viene disegnato per primo e ancorato alla parte superiore, l'intera larghezza del contenitore sarà occupata. Se un controllo successivo è ancorato a sinistra, lo spazio disponibile è meno verticale.

:::image type="content" source="media/layout/dock-top-then-left.png" alt-text="Windows Form con pulsanti ancorati a sinistra e in alto con la parte superiore più grande.":::

Se l'oggetto del controllo **:::no-loc text="Z-order":::** è invertito, il controllo ancorato a sinistra dispone dello spazio iniziale disponibile. Il controllo utilizza l'intera altezza del contenitore. Il controllo ancorato alla parte superiore ha meno spazio orizzontale disponibile.

:::image type="content" source="media/layout/dock-left-then-top.png" alt-text="Windows Form con pulsanti ancorati a sinistra e in alto con la parte sinistra più grande.":::

Man mano che il contenitore si espande e si riduce, i controlli ancorati al contenitore vengono riposizionati e ridimensionati per mantenere le posizioni e le dimensioni applicabili.

:::image type="content" source="media/layout/dock-resize.gif" alt-text="Animazione che mostra il ridimensionamento di un Windows Form con pulsanti ancorati in tutte le posizioni.":::

Se più controlli sono ancorati allo stesso lato del contenitore, vengono impilati in base ai rispettivi **:::no-loc text="Z-order":::** .

:::image type="content" source="media/layout/dock-left-left.png" alt-text="Windows Form con due pulsanti ancorati a sinistra.":::

### <a name="anchor"></a>Ancoraggio

L'ancoraggio di un controllo consente di associare il controllo a uno o più lati del contenitore padre. Quando le dimensioni del contenitore cambiano, qualsiasi controllo figlio manterrà la distanza al lato ancorato.

Un controllo può essere ancorato a uno o più lati, senza alcuna restrizione. L'ancoraggio viene impostato con la <xref:System.Windows.Forms.Control.Anchor> Proprietà.

:::image type="content" source="media/layout/anchor-resize.gif" alt-text="Animazione che mostra il ridimensionamento di un Windows Form con pulsanti ancorati in tutte le posizioni.":::

### <a name="automatic-sizing"></a>Dimensionamento automatico

La <xref:System.Windows.Forms.Control.AutoSize> proprietà consente a un controllo di modificare le dimensioni, se necessario, per adattarle alla dimensione specificata dalla <xref:System.Windows.Forms.Control.PreferredSize> Proprietà. Per modificare il comportamento di ridimensionamento per controlli specifici, impostare la `AutoSizeMode` Proprietà.

Solo alcuni controlli supportano la <xref:System.Windows.Forms.Control.AutoSize%2A> Proprietà. Inoltre, alcuni controlli che supportano la <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà supportano anche la `AutoSizeMode` Proprietà.

| Comportamento sempre reale | Descrizione |
|--|--|
| Il dimensionamento automatico è una funzionalità di run-time. | Ciò significa che non cresce né compatta un controllo e quindi non ha alcun effetto. |
| Se un controllo cambia dimensione, il valore della relativa <xref:System.Windows.Forms.Control.Location%2A> proprietà rimane sempre costante. | Quando il contenuto di un controllo ne determina la crescita, il controllo si estende verso destra e verso il basso. I controlli non crescono verso sinistra. |
| Le <xref:System.Windows.Forms.Control.Dock%2A> <xref:System.Windows.Forms.Control.Anchor%2A> proprietà e vengono rispettate quando <xref:System.Windows.Forms.Control.AutoSize%2A> è `true` . | Il valore della proprietà del controllo <xref:System.Windows.Forms.Control.Location%2A> viene regolato sul valore corretto.<br /><br /> Il <xref:System.Windows.Forms.Label> controllo rappresenta l'eccezione a questa regola. Quando si imposta il valore della proprietà di un <xref:System.Windows.Forms.Label> controllo ancorato <xref:System.Windows.Forms.Control.AutoSize%2A> su `true` , il <xref:System.Windows.Forms.Label> controllo non viene esteso. |
| <xref:System.Windows.Forms.Control.MaximumSize%2A>Le proprietà e di un controllo <xref:System.Windows.Forms.Control.MinimumSize%2A> vengono sempre rispettate, indipendentemente dal valore della relativa <xref:System.Windows.Forms.Control.AutoSize%2A> Proprietà. | Le <xref:System.Windows.Forms.Control.MaximumSize%2A> <xref:System.Windows.Forms.Control.MinimumSize%2A> proprietà e non sono interessate dalla <xref:System.Windows.Forms.Control.AutoSize%2A> Proprietà. |
| Per impostazione predefinita, non sono impostate dimensioni minime. | Ciò significa che se un controllo è impostato su compatta in <xref:System.Windows.Forms.Control.AutoSize%2A> e non contiene contenuto, il valore della <xref:System.Windows.Forms.Control.Size%2A> proprietà è `(0x,0y)` . In questo caso, il controllo ridurrà fino a un punto e non sarà immediatamente visibile. |
| Se un controllo non implementa il <xref:System.Windows.Forms.Control.GetPreferredSize%2A> metodo, il <xref:System.Windows.Forms.Control.GetPreferredSize%2A> metodo restituisce l'ultimo valore assegnato alla <xref:System.Windows.Forms.Control.Size%2A> Proprietà. | Ciò significa che l'impostazione <xref:System.Windows.Forms.Control.AutoSize%2A> di su `true` non avrà alcun effetto. |
| Un controllo in una <xref:System.Windows.Forms.TableLayoutPanel> cella viene sempre compattato per adattarsi alla cella fino a quando non viene raggiunto il relativo oggetto <xref:System.Windows.Forms.Control.MinimumSize%2A> . | Questa dimensione viene applicata come dimensione massima. Questa situazione non si verifica quando la cella fa parte di una <xref:System.Windows.Forms.SizeType.AutoSize> riga o di una colonna. |

## <a name="container-form"></a>Contenitore: form

<xref:System.Windows.Forms.Form>È l'oggetto principale di Windows Forms. In un Windows Forms Application in genere viene visualizzato un form in qualsiasi momento. I moduli contengono controlli e rispettano le <xref:System.Windows.Forms.Control.Location> <xref:System.Windows.Forms.Control.Size> proprietà e del controllo per la selezione host manuale. I moduli rispondono anche alla proprietà [Dock](#dock) per la selezione host automatica.

Nella maggior parte dei casi un modulo avrà grip sui bordi che consentono all'utente di ridimensionare il form. La <xref:System.Windows.Forms.Control.Anchor> proprietà di un controllo consente di aumentare e ridurre il controllo quando il form viene ridimensionato.

## <a name="container-panel"></a>Contenitore: pannello

Il <xref:System.Windows.Forms.Panel> controllo è simile a un modulo in quanto raggruppa semplicemente i controlli. Supporta gli stessi stili di posizionamento manuale e automatico che un modulo esegue. Per ulteriori informazioni, vedere la sezione [contenitore: modulo](#container-form) .

Un pannello si integra senza problemi con l'elemento padre e taglia qualsiasi area di un controllo che non rientra nei limiti del pannello. Se un controllo non è compreso nei limiti del pannello e <xref:System.Windows.Forms.Form.AutoScroll> è impostato su `true` , vengono visualizzate le barre di scorrimento e l'utente può scorrere il pannello.

A differenza del controllo [casella di gruppo](#container-group-box) , un pannello non ha una didascalia e un bordo.

:::image type="content" source="media/layout/panel-groupbox.png" alt-text="Windows Form con un pannello e una casella di gruppo.":::

Nell'immagine precedente è presente un pannello con la <xref:System.Windows.Forms.Panel.BorderStyle%2A> proprietà impostata per illustrare i limiti del pannello.

## <a name="container-group-box"></a>Contenitore: casella di gruppo

Il <xref:System.Windows.Forms.GroupBox> controllo fornisce un raggruppamento identificabile per gli altri controlli. In genere, si usa una casella di gruppo per suddividere un form per funzione. Ad esempio, potrebbe essere presente un modulo che rappresenta le informazioni personali e i campi correlati a un indirizzo verranno raggruppati insieme. In fase di progettazione, è facile spostare la casella di gruppo insieme ai controlli contenuti.

La casella di gruppo supporta gli stessi stili di posizionamento manuali e automatici di un form. Per ulteriori informazioni, vedere la sezione [contenitore: modulo](#container-form) . Una casella di gruppo taglia anche una parte di un controllo che non rientra nei limiti del pannello.

A differenza del controllo [Panel](#container-panel) , una casella di gruppo non è in grado di scorrere il contenuto e visualizzare le barre di scorrimento.

:::image type="content" source="media/layout/panel-groupbox.png" alt-text="Windows Form con un pannello e una casella di gruppo.":::

## <a name="container-flow-layout"></a>Contenitore: layout di flusso

Il controllo <xref:System.Windows.Forms.FlowLayoutPanel> dispone i contenuti in una direzione di flusso orizzontale o verticale. È possibile eseguire il wrapping dei contenuti del controllo da una riga a quella successiva o da una colonna a quella successiva. In alternativa, è possibile troncare i contenuti.  
  
È possibile specificare la direzione del flusso impostando il valore della proprietà <xref:System.Windows.Forms.FlowLayoutPanel.FlowDirection%2A>. Il controllo <xref:System.Windows.Forms.FlowLayoutPanel> inverte correttamente la direzione del flusso nei layout da destra a sinistra (RTL, Right-To-Left). È anche possibile specificare se i contenuti del controllo <xref:System.Windows.Forms.FlowLayoutPanel> vengono sottoposti a wrapping o troncati impostando il valore della proprietà <xref:System.Windows.Forms.FlowLayoutPanel.WrapContents%2A>.  

Il controllo <xref:System.Windows.Forms.FlowLayoutPanel> viene automaticamente ridimensionato in base ai contenuti quando si imposta la proprietà <xref:System.Windows.Forms.Control.AutoSize%2A> su `true`. Fornisce inoltre una `FlowBreak` proprietà ai relativi controlli figlio. Impostando il valore della `FlowBreak` proprietà su `true` , il <xref:System.Windows.Forms.FlowLayoutPanel> controllo interrompe il layout dei controlli nella direzione di flusso corrente ed esegue il wrapping alla riga o alla colonna successiva.  

:::image type="content" source="media/layout/flow.png" alt-text="Windows Form con due controlli pannello di flusso.":::

Nell'immagine precedente sono presenti due `FlowLayoutPanel` controlli con la <xref:System.Windows.Forms.Panel.BorderStyle> proprietà impostata per illustrare i limiti del controllo.

## <a name="container-table-layout"></a>Contenitore: layout tabella

Il controllo <xref:System.Windows.Forms.TableLayoutPanel> dispone il contenuto in una griglia. Poiché il layout viene eseguito sia in fase di progettazione che in fase di esecuzione, può cambiare dinamicamente in seguito alla modifica dell'ambiente dell'applicazione. In questo modo i controlli nel pannello possono ridimensionare proporzionalmente, in modo che possano rispondere a modifiche quali il ridimensionamento del controllo padre o la modifica della lunghezza del testo a causa della localizzazione.

Qualsiasi controllo Windows Form può essere figlio del controllo <xref:System.Windows.Forms.TableLayoutPanel>, tra cui altre istanze di <xref:System.Windows.Forms.TableLayoutPanel>. consentendo la creazione di layout sofisticati che si adattano alle modifiche in fase di esecuzione.

È anche possibile controllare la direzione di espansione, orizzontale o verticale, per quando il controllo <xref:System.Windows.Forms.TableLayoutPanel> non riesce più a contenere i controlli figlio. Per impostazione predefinita, il controllo <xref:System.Windows.Forms.TableLayoutPanel> si espande verso il basso aggiungendo delle righe.

È possibile controllare le dimensioni e lo stile delle righe e delle colonne usando le <xref:System.Windows.Forms.TableLayoutPanel.RowStyles%2A> <xref:System.Windows.Forms.TableLayoutPanel.ColumnStyles%2A> proprietà e. Le proprietà delle righe possono essere impostate separatamente da quelle delle colonne.

Il controllo <xref:System.Windows.Forms.TableLayoutPanel> aggiunge ai propri controlli figlio le proprietà `Cell`, `Column`. `Row`, `ColumnSpan` e `RowSpan`.

:::image type="content" source="media/layout/table.png" alt-text="Windows Form con controllo del layout di tabella.":::

Nell'immagine precedente è presente una tabella con la <xref:System.Windows.Forms.TableLayoutPanel.CellBorderStyle> proprietà impostata per illustrare i limiti di ciascuna cella.

## <a name="container-split-container"></a>Contenitore: Split container

Il <xref:System.Windows.Forms.SplitContainer> controllo Windows Forms può essere considerato come un controllo composto. si tratta di due pannelli separati da una barra mobile. Quando il puntatore del mouse viene posizionato sopra la barra, assume una forma diversa per indicare che la barra è mobile.  

Con il <xref:System.Windows.Forms.SplitContainer> controllo è possibile creare interfacce utente complesse. spesso una selezione in un pannello determina quali oggetti vengono visualizzati nell'altro pannello. Questa disposizione è efficace per la visualizzazione e l'esplorazione delle informazioni. La presenza di due pannelli che consentono di aggregare le informazioni in aree, la barra o il "Splitter" consente agli utenti di ridimensionare facilmente i pannelli.

:::image type="content" source="media/layout/splitcontainer.png" alt-text="Windows Form con un contenitore di suddivisione annidato.":::

Nell'immagine precedente è presente un contenitore suddiviso per creare un riquadro sinistro e destro. Il riquadro destro contiene un secondo contenitore suddiviso con <xref:System.Windows.Forms.SplitContainer.Orientation> impostato su <xref:System.Windows.Forms.Orientation.Vertical> . La <xref:System.Windows.Forms.SplitContainer.BorderStyle> proprietà è impostata in modo da illustrare i limiti di ogni pannello.

## <a name="container-tab-control"></a>Contenitore: controllo Tab

Il <xref:System.Windows.Forms.TabControl> Visualizza più schede, ad esempio i divisori in un notebook o le etichette in un set di cartelle in un archivio di archiviazione. Le schede possono contenere immagini e altri controlli. Utilizzare il controllo TAB per produrre il tipo di finestra di dialogo a più pagine che viene visualizzata in molte posizioni del sistema operativo Windows, ad esempio il pannello di controllo e le proprietà di visualizzazione. Inoltre, <xref:System.Windows.Forms.TabControl> può essere utilizzato per creare pagine delle proprietà, utilizzate per impostare un gruppo di proprietà correlate.

La proprietà più importante di <xref:System.Windows.Forms.TabControl> è <xref:System.Windows.Forms.TabControl.TabPages%2A> , che contiene le singole schede. Ogni singola scheda è un <xref:System.Windows.Forms.TabPage> oggetto.

:::image type="content" source="media/layout/tabcontrol.png" alt-text="Windows Form con un controllo struttura a schede con due schede.":::
