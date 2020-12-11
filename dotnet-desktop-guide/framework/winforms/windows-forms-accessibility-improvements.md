---
title: Miglioramenti per l'accessibilità Windows Forms
description: Informazioni sui modi in cui .NET Core Windows Forms tenta di migliorare l'accessibilità in confronto con .NET Framework Windows Forms.
ms.date: 04/20/2020
helpviewer_keywords:
- Windows Forms accessibility
- accessibility
author: M-Lipin
ms.openlocfilehash: 4dc477cebf35435ff2122ce21644135848985d07
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951959"
---
# <a name="accessibility-improvements-in-windows-forms-controls-for-net-core-30"></a>Miglioramenti dell'accessibilità nei controlli Windows Forms per .NET Core 3,0

Windows Forms continua a migliorare il funzionamento con le tecnologie di accessibilità per supportare al meglio i clienti Windows Forms. Questi miglioramenti includono le modifiche seguenti:

- Modifiche apportate a diverse aree di interazione con le applicazioni client di accessibilità, incluso Assistente vocale.
- Modifiche alla gerarchia accessibile grazie al miglioramento della navigazione attraverso l'albero di automazione interfaccia utente.
- Modifiche alla navigazione da tastiera.

> [!IMPORTANT]
> Le modifiche di accessibilità apportate in .NET Framework 4.7.1 tramite .NET Framework 4,8 sono incluse in .NET Core 3,0 e versioni successive e sono abilitate per impostazione predefinita. Il .NET Framework opzioni di compatibilità supportate che consentono alle applicazioni di rifiutare esplicitamente il nuovo comportamento di accessibilità. D'altra parte, .NET Core non supporta queste impostazioni e non consente alle applicazioni di rifiutare esplicitamente il comportamento di accessibilità.
  
A partire da .NET Core 3,0, le applicazioni Windows Forms traggono vantaggio da tutte le nuove funzionalità di accessibilità (introdotte in .NET Framework 4.7.1-4,8) senza alcuna configurazione aggiuntiva.

## <a name="listbox-accessibility-support"></a>Supporto per l'accessibilità ListBox

Le modifiche seguenti si applicano al <xref:System.Windows.Forms.ListBox> controllo:

- Abilitazione del supporto di automazione interfaccia utente per il `ListBox` controllo.
- Miglioramento `ListBox` del supporto per l'accessibilità aggiungendo gli <xref:System.Windows.Automation.ScrollItemPattern> `ListBox` elementi agli elementi e migliorando la generazione e la gestione di eventi di accessibilità e la navigazione dell'Assistente vocale attraverso gli elementi (la navigazione dei blocchi Caps non è corretta e non genera lo spostamento fuori dal controllo involontariamente).

## <a name="checkedlistbox-accessibility-support"></a>Supporto per l'accessibilità di CheckedListBox

Le modifiche seguenti si applicano al <xref:System.Windows.Forms.CheckedListBox> controllo:

- `CheckedListBox`Limiti corretti forniti dalle proprietà di accessibilità per le voci.
- Miglioramento generale `ListBox` e `CheckedListBox` accessibilità: correzione dei valori delle proprietà e del modello di eventi.

## <a name="combobox-accessibility-support"></a>Supporto per l'accessibilità ComboBox

Le modifiche seguenti si applicano al <xref:System.Windows.Forms.ComboBox> controllo:

- Aggiornamento del processo di recupero degli `ComboBox` oggetti di accessibilità degli elementi per consentire la generazione di ID per gli elementi anziché ottenere i codici hash dagli elementi, che potrebbero non essere sicuri nel caso in cui la <xref:System.Object.GetHashCode%2A> funzione venga sottoposta a override.

## <a name="datagridview-accessibility-support"></a>Supporto per l'accessibilità DataGridView

Le modifiche seguenti si applicano al <xref:System.Windows.Forms.DataGridView> controllo:

- Correzione `DataGridView.Bounds` fornita dalle proprietà di accessibilità per colonne, righe, celle e intestazioni corrispondenti, miglioramento delle prestazioni del calcolo del rettangolo di delimitazione. Tutti i limiti di accessibilità sono rappresentati correttamente tenendo conto dei limiti dell'intero controllo, insieme al relativo viewport.
- Correzione `Value.IsReadOnly` del valore della proprietà che fornisce le applicazioni client accessibili. La proprietà Mostra ora `IsReadOnly` lo stato corretto per le celle.
- Correzione del problema <xref:System.Windows.Forms.DataGridView.CellParsing> relativo alla generazione di eventi in caso di modifica della prima cella. Il valore della cella può essere modificato senza problemi, inclusa la prima `DataGridView` interazione del controllo.
- Miglioramento del `DataGridView` contrasto del colore di sfondo quando si utilizzano i temi di Windows contrasto elevato. Il `DataGridView` colore di sfondo predefinito è stato modificato quando si usano i temi neri HC # 1, HC # 2 e HC.

## <a name="propertygrid-accessibility-support"></a>Supporto per l'accessibilità PropertyGrid

Le modifiche seguenti si applicano al <xref:System.Windows.Forms.PropertyGrid> controllo:

- Correzione `PropertyGrid.Bounds` fornita dalle proprietà di accessibilità per le voci della griglia, miglioramento delle prestazioni del calcolo del rettangolo di delimitazione. Per ora tutti i limiti di accessibilità sono rappresentati correttamente tenendo conto dei limiti dell'intero controllo, insieme al relativo viewport.
- Correzione dei nomi accessibili e delle descrizioni dei sottocontrolli in modo da non includere i nomi dei tipi di controllo ed evitare l'annuncio doppio per i nomi dei tipi di controllo.

## <a name="toolstrip-accessibility-support"></a>Supporto per l'accessibilità ToolStrip

Le modifiche seguenti si applicano al <xref:System.Windows.Forms.ToolStrip> controllo:

- Esplorazione migliorata negli `ToolStrip` `MenuStrip` elementi, e `StatusStrip` . `ToolStrip` `MenuStrip` Navigazione con correzione e spostamento della tabulazione, esecuzione di un ciclo indietro delle voci di menu quando si preme MAIUSC + TAB, che consente di passare all'elemento del menu inferiore.
- `MenuStrip`Navigazione accessibile migliorata, tipi di controllo accessibili dal menu corretti per i sottomenu per creare sottomenu di tipo "menu" anziché "MenuItem".

## <a name="printpreviewcontrol-and-printpreviewdialog-accessibility-support"></a>Supporto per l'accessibilità PrintPreviewControl e PrintPreviewDialog

Le modifiche seguenti si applicano ai controlli di stampa:

- Navigazione accessibile migliorata (inclusa la navigazione dell'Assistente vocale) tramite voci di menu.
- Migliorato il supporto di Contrasto elevato temi e rende più contrasto l'elemento del controllo.

## <a name="stringcollectioneditor-accessibility-support"></a>Supporto per l'accessibilità StringCollectionEditor

In Windows Forms Designer viene ora utilizzato l'editor della raccolta di stringhe con supporto migliorato per l'accessibilità.

## <a name="monthcalendar-accessibility-support-available-in-net-core-31"></a>Supporto per l'accessibilità MonthCalendar (disponibile in .NET Core 3,1)

Le modifiche seguenti si applicano al <xref:System.Windows.Forms.MonthCalendar> controllo:

- Aggiunta di provider del server di automazione interfaccia utente per il `MonthCalendar` controllo, aggiunta modello di griglia di automazione interfaccia utente e provider di modelli di tabella
- Modifica del tipo di controllo accessibile da _tabella_ al tipo di controllo _Calendar_ accessible per `MonthCalendar` tranne nel caso in cui il controllo disponga di un controllo Label precedente che definisce il `MonthCalendar` nome accessibile del controllo, in questo tipo di controllo accessibile del case specifico diventa _Table_.
- Annuncio migliorato della data selezionata per il `MonthCalendar` controllo.
- `MonthCalendar`Supporto del controllo migliorato per utilità per la lettura dello schermo e altri strumenti di accessibilità. A questo punto, gli utenti possono spostarsi tra gli elementi del controllo e interagire con questi elementi usando input di solo tastiera. Con Assistente vocale, usare CAPS + tasti di direzione per spostarsi tra gli elementi del controllo e i tasti MAIUSC + INVIO per richiamare l'azione predefinita dell'elemento.
- Esplorazione migliorata dei tasti di direzione tra `MonthCalendar` gli elementi figlio con un rettangolo di messa a fuoco: rettangolo di attivazione blu per Assistente vocale.
- Migliore accessibilità per l'azione di hit test per `MonthCalendar` gli elementi di controllo per consentire l'inserimento `MonthCalendar` di elementi figlio accessibili tramite coordinate fornite.

## <a name="tooltips-accessibility-available-in-net-core-31"></a>Descrizione comando accessibilità (disponibile in .NET Core 3,1)

- Aggiunta della possibilità di annunciare un testo della descrizione comando dalle applicazioni per la lettura dello schermo, ad esempio NVDA e Assistente vocale. L'applicazione per la lettura dello schermo ora può annunciare il testo della descrizione comando della tastiera o del mouse di qualsiasi controllo Windows Forms configurato per visualizzare le descrizioni comandi.

## <a name="ui-automation-support-for-datagridview-propertygrid-listbox-combobox-toolstrip-and-other-controls"></a>Supporto per automazione interfaccia utente per DataGridView, PropertyGrid, ListBox, ComboBox, ToolStrip e altri controlli

Il supporto per automazione interfaccia utente è abilitato per i controlli in fase di esecuzione, ma non viene usato in fase di progettazione Per una panoramica dell'automazione interfaccia utente, vedere [Panoramica di automazione interfaccia utente](/dotnet/framework/ui-automation/ui-automation-overview).

## <a name="see-also"></a>Vedere anche

- [Procedure consigliate per l'accessibilità](/dotnet/framework/ui-automation/accessibility-best-practices).
