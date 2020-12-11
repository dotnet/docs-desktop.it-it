---
title: Comportamento predefinito di tastiera e mouse nel controllo DataGrid
ms.date: 03/30/2017
helpviewer_keywords:
- DataGrid [WPF], keyboard behavior
- DataGrid [WPF], mouse behavior
- keyboard behavior [WPF], DataGrid
- mouse behavior [WPF], DataGrid
ms.assetid: 563b8854-ca39-4d97-8235-17eaa0f93c8d
ms.openlocfilehash: a518c6123b21ae62742071a0b26c6a09fa272b17
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961105"
---
# <a name="default-keyboard-and-mouse-behavior-in-the-datagrid-control"></a>Comportamento predefinito di tastiera e mouse nel controllo DataGrid
In questo argomento viene descritto come gli utenti possono interagire con il <xref:System.Windows.Controls.DataGrid> controllo utilizzando la tastiera e il mouse.  
  
 Le interazioni tipiche con <xref:System.Windows.Controls.DataGrid> includono navigazione, selezione e modifica. Il comportamento della selezione è influenzato <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> dalle <xref:System.Windows.Controls.DataGrid.SelectionUnit%2A> proprietà e. I valori predefiniti che determinano il comportamento descritto in questo argomento sono <xref:System.Windows.Controls.DataGridSelectionMode.Extended?displayProperty=nameWithType> e <xref:System.Windows.Controls.DataGridSelectionUnit.FullRow?displayProperty=nameWithType> . La modifica di questi valori può causare un comportamento diverso da quello descritto. Quando una cella è in modalità di modifica, il controllo di modifica potrebbe ignorare il comportamento della tastiera standard di <xref:System.Windows.Controls.DataGrid> .  
  
## <a name="default-keyboard-behavior"></a>Comportamento predefinito della tastiera  
 Nella tabella seguente viene elencato il comportamento predefinito della tastiera per <xref:System.Windows.Controls.DataGrid> .  
  
|Tasto o della combinazione|Descrizione|  
|----------------------------|-----------------|  
|Freccia GIÙ|Sposta lo stato attivo sulla cella immediatamente sotto la cella corrente. Se lo stato attivo si trova nell'ultima riga, premendo la freccia giù non viene eseguita alcuna operazione.|  
|FRECCIA SU|Sposta lo stato attivo sulla cella immediatamente sopra la cella corrente. Se lo stato attivo si trova nella prima riga, premendo la freccia su non viene eseguita alcuna operazione.|  
|FRECCIA SINISTRA|Sposta lo stato attivo sulla cella precedente della riga. Se lo stato attivo si trova nella prima cella della riga, fare clic sulla freccia sinistra.|  
|FRECCIA DESTRA|Sposta lo stato attivo sulla cella successiva nella riga. Se lo stato attivo si trova nell'ultima cella della riga, la pressione della freccia destra non esegue alcuna operazione.|  
|HOME|Sposta lo stato attivo sulla prima cella della riga corrente.|  
|FINE|Sposta lo stato attivo sull'ultima cella della riga corrente.|  
|PGGIÙ|Se le righe non sono raggruppate, scorre il controllo verso il basso del numero di righe visualizzate completamente. Sposta lo stato attivo sull'ultima riga completamente visualizzata senza modificare le colonne.<br /><br /> Se le righe sono raggruppate, sposta lo stato attivo sull'ultima riga in <xref:System.Windows.Controls.DataGrid> senza modificare le colonne.|  
|PGSU|Se le righe non sono raggruppate, scorre il controllo verso l'alto in base al numero di righe visualizzate completamente. Sposta lo stato attivo sulla prima riga visualizzata senza modificare le colonne.<br /><br /> Se le righe sono raggruppate, sposta lo stato attivo sulla prima riga in <xref:System.Windows.Controls.DataGrid> senza modificare le colonne.|  
|TAB|Sposta lo stato attivo sulla cella successiva nella riga corrente. Se lo stato attivo si trova nell'ultima cella della riga, sposta lo stato attivo sulla prima cella nella riga successiva. Se lo stato attivo si trova nell'ultima cella del controllo, sposta lo stato attivo sul controllo successivo nell'ordine di tabulazione del contenitore padre.<br /><br /> Se la cella corrente è in modalità di modifica e premendo TAB lo stato attivo viene spostato fuori dalla riga corrente, viene eseguito il commit di tutte le modifiche apportate alla riga prima che lo stato attivo venga modificato.|  
|MAIUSC+TAB|Sposta lo stato attivo sulla cella precedente nella riga corrente. Se lo stato attivo si trova già nella prima cella della riga, sposta lo stato attivo sull'ultima cella della riga precedente. Se lo stato attivo si trova nella prima cella del controllo, sposta lo stato attivo sul controllo precedente nell'ordine di tabulazione del contenitore padre.<br /><br /> Se la cella corrente è in modalità di modifica e premendo TAB lo stato attivo viene spostato fuori dalla riga corrente, viene eseguito il commit di tutte le modifiche apportate alla riga prima che lo stato attivo venga modificato.|  
|CTRL+freccia GIÙ|Sposta lo stato attivo sull'ultima cella della colonna corrente.|  
|CTRL+freccia SU|Sposta lo stato attivo sulla prima cella della colonna corrente.|  
|CTRL+freccia DESTRA|Sposta lo stato attivo sull'ultima cella della riga corrente.|  
|CTRL+freccia SINISTRA|Sposta lo stato attivo sulla prima cella della riga corrente.|  
|CTRL+HOME|Sposta lo stato attivo sulla prima cella del controllo.|  
|CTRL+FINE|Sposta lo stato attivo sull'ultima cella del controllo.|  
|CTRL+PGGIÙ|Uguale a PGGIÙ.|  
|CTRL+PGSU|Uguale a PAGE UP.|  
|F2|Se la <xref:System.Windows.Controls.DataGrid.IsReadOnly%2A?displayProperty=nameWithType> proprietà è `false` e la <xref:System.Windows.Controls.DataGridColumn.IsReadOnly%2A?displayProperty=nameWithType> proprietà è `false` per la colonna corrente, inserisce la cella corrente in modalità di modifica della cella.|  
|INVIO|Consente di eseguire il commit di tutte le modifiche apportate alla cella e alla riga correnti e di spostare lo stato attivo sulla cella immediatamente sotto la cella corrente. Se lo stato attivo si trova nell'ultima riga, viene eseguito il commit di tutte le modifiche senza spostare lo stato attivo.|  
|ESC|Se il controllo è in modalità di modifica, Annulla la modifica e Annulla le modifiche apportate nel controllo. Se l'origine dati sottostante implementa <xref:System.ComponentModel.IEditableObject> , premendo ESC una seconda volta annulla la modalità di modifica per l'intera riga.|  
|BACKSPACE|Elimina il carattere prima del cursore durante la modifica di una cella.|  
|DELETE|Elimina il carattere dopo il cursore durante la modifica di una cella.|  
|CTRL+INVIO|Consente di eseguire il commit di tutte le modifiche apportate alla cella corrente senza spostare lo stato attivo.|  
|CTRL+A|Se <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> è impostato su <xref:System.Windows.Controls.DataGridSelectionMode.Extended> , seleziona tutte le righe in <xref:System.Windows.Controls.DataGrid> .|  
  
## <a name="selection-keys"></a>Tasti di selezione  
 Se la <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> proprietà è impostata su <xref:System.Windows.Controls.DataGridSelectionMode.Extended> , il comportamento di navigazione non cambia, ma lo spostamento con la tastiera mentre si preme MAIUSC (inclusa la combinazione di tasti CTRL + MAIUSC) modifica una selezione a più righe. Prima dell'avvio della navigazione, il controllo contrassegna la riga corrente come una riga di ancoraggio. Quando si sposta mentre si preme MAIUSC, la selezione include tutte le righe tra la riga di ancoraggio e la riga corrente.  
  
 I seguenti tasti di selezione modificano la selezione a più righe.  
  
- MAIUSC+freccia GIÙ  
  
- MAIUSC+freccia SU  
  
- MAIUSC+PGGIÙ  
  
- MAIUSC+PGSU  
  
- CTRL+MAIUSC+freccia GIÙ  
  
- CTRL+MAIUSC+freccia SU  
  
- CTRL+MAIUSC+HOME  
  
- CTRL+MAIUSC+FINE  
  
## <a name="default-mouse-behavior"></a>Comportamento predefinito del mouse  
 Nella tabella seguente viene elencato il comportamento predefinito del mouse per il <xref:System.Windows.Controls.DataGrid> .  
  
|Azione del mouse|Descrizione|  
|------------------|-----------------|  
|Fare clic su una riga non selezionata|Trasforma la riga corrente e la cella su cui è stato fatto clic sulla cella corrente.|  
|Fare clic sulla cella corrente|Inserisce la cella corrente in modalità di modifica.|  
|Trascinare una cella di intestazione di colonna|Se la <xref:System.Windows.Controls.DataGrid.CanUserReorderColumns%2A?displayProperty=nameWithType> proprietà è `true` e la <xref:System.Windows.Controls.DataGridColumn.CanUserReorder%2A?displayProperty=nameWithType> proprietà è `true` per la colonna corrente, sposta la colonna in modo che possa essere rilasciata in una nuova posizione.|  
|Trascinare un separatore di intestazioni di colonna|Se la <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A?displayProperty=nameWithType> proprietà è `true` e la <xref:System.Windows.Controls.DataGridColumn.CanUserResize%2A?displayProperty=nameWithType> proprietà è `true` per la colonna corrente, ridimensiona la colonna.|  
|Fare doppio clic su un separatore di intestazioni di colonna|Se la <xref:System.Windows.Controls.DataGrid.CanUserResizeColumns%2A?displayProperty=nameWithType> proprietà è `true` e la <xref:System.Windows.Controls.DataGridColumn.CanUserResize%2A?displayProperty=nameWithType> proprietà è `true` per la colonna corrente, la colonna viene ridimensionata automaticamente utilizzando la <xref:System.Windows.Controls.DataGridLength.Auto%2A> modalità di ridimensionamento.|  
|Fare clic su una cella di intestazione di colonna|Se la <xref:System.Windows.Controls.DataGrid.CanUserSortColumns%2A?displayProperty=nameWithType> proprietà è `true` e la <xref:System.Windows.Controls.DataGridColumn.CanUserSort%2A?displayProperty=nameWithType> proprietà è `true` per la colonna corrente, ordina la colonna.<br /><br /> Se si fa clic sull'intestazione di una colonna già ordinata, la direzione di ordinamento della colonna verrà invertita.<br /><br /> Premendo il tasto MAIUSC mentre si fa clic su più intestazioni di colonna, le colonne vengono ordinate in base a più colonne nell'ordine selezionato.|  
|CTRL + clic su una riga|Se <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> è impostato su <xref:System.Windows.Controls.DataGridSelectionMode.Extended> , modifica una selezione a più righe non contigua.<br /><br /> Se la riga è già selezionata, deseleziona la riga.|  
|MAIUSC + clic su una riga|Se <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> è impostato su <xref:System.Windows.Controls.DataGridSelectionMode.Extended> , modifica una selezione a più righe contigue.|  
|Fare clic sull'intestazione di un gruppo di righe|Espande o comprime il gruppo.|  
|Fare clic sul pulsante Seleziona tutto nell'angolo superiore sinistro del <xref:System.Windows.Controls.DataGrid>|Se <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> è impostato su <xref:System.Windows.Controls.DataGridSelectionMode.Extended> , seleziona tutte le righe in <xref:System.Windows.Controls.DataGrid> .|  
  
## <a name="mouse-selection"></a>Selezione del mouse  
 Se la <xref:System.Windows.Controls.DataGrid.SelectionMode%2A> proprietà è impostata su <xref:System.Windows.Controls.DataGridSelectionMode.Extended> , facendo clic su una riga durante la pressione di CTRL o Maiusc verrà modificata una selezione a più righe.  
  
 Quando si fa clic su una riga durante la pressione di CTRL, la riga cambierà lo stato di selezione mentre tutte le altre righe manterranno lo stato di selezione corrente. Eseguire questa operazione per selezionare righe non adiacenti.  
  
 Quando si fa clic su una riga durante la pressione di SHIFT, la selezione include tutte le righe tra la riga corrente e una riga di ancoraggio posizionata nella posizione della riga corrente prima del clic. I clic successivi mentre si preme MAIUSC cambiano la riga corrente, ma non la riga di ancoraggio. Eseguire questa operazione per selezionare un intervallo di righe adiacenti.  
  
 È possibile combinare CTRL + MAIUSC per selezionare intervalli non adiacenti di righe adiacenti. A tale scopo, selezionare il primo intervallo usando Maiusc + clic come descritto in precedenza. Dopo aver selezionato il primo intervallo di righe, premere CTRL + clic per selezionare la prima riga nell'intervallo successivo, quindi fare clic sull'ultima riga nell'intervallo successivo tenendo premuto CTRL + MAIUSC.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.DataGrid>
- <xref:System.Windows.Controls.DataGrid.SelectionMode%2A>
