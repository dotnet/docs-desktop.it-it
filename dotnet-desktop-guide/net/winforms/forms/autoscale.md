---
title: Ridimensionamento automatico del modulo
description: Esaminare il modo in cui Windows Forms per .NET gestisce il ridimensionamento dell'interfaccia utente.
ms.date: 10/26/2020
ms.topic: overview
helpviewer_keywords:
- scalability [Windows Forms], automatic in Windows Forms
- Windows Forms, automatic scaling
ms.openlocfilehash: c414575c83723dc1930a0bfe298534eee9aa48c8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969262"
---
# <a name="automatic-scaling-windows-forms-net"></a>Ridimensionamento automatico (Windows Forms .NET)

La scalabilità automatica consente di visualizzare in modo appropriato un modulo e i relativi controlli, progettati su un computer con una determinata risoluzione dello schermo o tipo di carattere, in un altro computer con una risoluzione o un tipo di carattere diverso. Questa funzionalità assicura che il form e i controlli vengano ridimensionati in modo coerente con le finestre native e le altre applicazioni presenti sia sui computer degli utenti che su quelli di altri sviluppatori. Il ridimensionamento automatico e gli stili di visualizzazione consentono alle applicazioni Windows Forms di mantenere un aspetto coerente rispetto alle applicazioni Windows native sul computer di ogni utente.

Nella maggior parte dei casi, il ridimensionamento automatico funziona come previsto in Windows Forms. Le modifiche delle combinazioni tipi di carattere tuttavia possono essere problematiche.<!-- TODO For an example of how to resolve this, see [How to: Respond to Font Scheme Changes in a Windows Forms Application](how-to-respond-to-font-scheme-changes-in-a-windows-forms-application.md). -->

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="need-for-automatic-scaling"></a>Necessità di ridimensionamento automatico

Senza ridimensionamento automatico, un'applicazione progettata per un'unica risoluzione dello schermo o tipo di carattere apparirà troppo piccola o troppo grande quando si modifica tale risoluzione o tipo di carattere. Ad esempio, se l'applicazione viene progettata con Tahoma a 9 punti come base, senza regolazione apparirà troppo piccola se eseguita su un computer in cui il tipo di carattere del sistema è Tahoma a 12 punti. Gli elementi di testo, ad esempio titoli, menu, contenuti delle caselle di testo e così via, verranno visualizzati più in piccolo che nelle altre applicazioni. Inoltre, le dimensioni degli elementi dell'interfaccia utente contenenti testo, ad esempio la barra del titolo, i menu e molti controlli, dipendono dal tipo di carattere usato. In questo esempio, tali elementi appariranno anche relativamente più piccoli.

Una situazione analoga si verifica quando un'applicazione è progettata per una determinata risoluzione dello schermo. La risoluzione dello schermo più comune è di 96 punti per pollice (DPI), che equivale alla scalabilità dello schermo 100%, ma Visualizza una risoluzione più elevata che supporta 125%, 150%, 200% (rispettivamente uguali a 120, 144 e 192 DPI) e versioni successive stanno diventando più comuni. Senza regolazione, un'applicazione, soprattutto una con molti elementi grafici, progettata per un'unica risoluzione apparirà troppo grande o troppo piccola se eseguita con un'altra risoluzione.

Il ridimensionamento automatico cerca di risolvere questi problemi ridimensionando automaticamente il form e i relativi controlli figlio in base alla dimensione del carattere relativa o alla risoluzione dello schermo. Per supportare il ridimensionamento automatico delle finestre di dialogo, il sistema operativo Windows usa un'unità di misura relativa, chiamata DLU. Una DLU si basa sul tipo di carattere del sistema e la relazione con i pixel può essere determinata attraverso la funzione `GetDialogBaseUnits` di Win32 SDK. Quando un utente cambia il tema usato da Windows, tutte le finestre di dialogo vengono automaticamente adattate di conseguenza. Inoltre, Windows Forms supporta il ridimensionamento automatico in base al tipo di carattere di sistema predefinito o alla risoluzione dello schermo. Facoltativamente, il ridimensionamento automatico può essere disabilitato in un'applicazione.

> [!CAUTION]
> Non sono supportate combinazioni arbitrarie di DPI e modalità di ridimensionamento dei tipi di carattere. Anche se è possibile ridimensionare un controllo utente con una sola modalità (ad esempio, DPI) e inserirlo in un form con un'altra modalità (Font) senza problemi, tuttavia, se si combinano un form di base in una modalità e un form derivato in un'altra, è possibile che si verifichino risultati imprevisti.

## <a name="automatic-scaling-in-action"></a>Ridimensionamento automatico in azione

Windows Forms usa la logica seguente per ridimensionare automaticamente i moduli e il relativo contenuto:

01. In fase di progettazione, ogni <xref:System.Windows.Forms.ContainerControl> registra la modalità di ridimensionamento e la risoluzione corrente rispettivamente in <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A> e <xref:System.Windows.Forms.ContainerControl.AutoScaleDimensions%2A>.

01. In fase di esecuzione, la risoluzione effettiva viene archiviata nella proprietà <xref:System.Windows.Forms.ContainerControl.CurrentAutoScaleDimensions%2A>. La proprietà <xref:System.Windows.Forms.ContainerControl.AutoScaleFactor%2A> calcola in modo dinamico il rapporto tra la risoluzione di ridimensionamento in fase di esecuzione e in fase di progettazione.

01. Quando il form viene caricato, se i valori di <xref:System.Windows.Forms.ContainerControl.CurrentAutoScaleDimensions%2A> e <xref:System.Windows.Forms.ContainerControl.AutoScaleDimensions%2A> sono diversi, viene chiamato il metodo <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A> per ridimensionare il controllo e gli elementi figlio. Questo metodo sospende il layout e chiama il metodo <xref:System.Windows.Forms.Control.Scale%2A> per eseguire il ridimensionamento effettivo. Successivamente, il valore di <xref:System.Windows.Forms.ContainerControl.AutoScaleDimensions%2A> viene aggiornato per evitare il ridimensionamento progressivo.

01. <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A> viene richiamato automaticamente anche nelle situazioni seguenti:

    - In risposta all'evento <xref:System.Windows.Forms.Control.OnFontChanged%2A> se la modalità di ridimensionamento è <xref:System.Windows.Forms.AutoScaleMode.Font>.

    - Quando il layout del controllo contenitore viene ripristinato e viene rilevata una modifica nelle proprietà <xref:System.Windows.Forms.ContainerControl.AutoScaleDimensions%2A> o <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A>.

    - Come accennato in precedenza, quando è in corso il ridimensionamento di un <xref:System.Windows.Forms.ContainerControl> padre. Ogni controllo contenitore è responsabile del ridimensionamento degli elementi figlio con i propri fattori di scala e non con quello del contenitore padre.

01. I controlli figlio possono modificare il comportamento di ridimensionamento in più modi:

    - È possibile eseguire l'override della proprietà <xref:System.Windows.Forms.Control.ScaleChildren%2A> per determinare se i controlli figlio devono essere ridimensionati.

    - È possibile eseguire l'override del metodo <xref:System.Windows.Forms.Control.GetScaledBounds%2A> per regolare i limiti in base a cui il controllo viene ridimensionato, ma non la logica di ridimensionamento.

    - È possibile eseguire l'override del metodo <xref:System.Windows.Forms.Control.ScaleControl%2A> per cambiare la logica di ridimensionamento per il controllo corrente.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.ContainerControl.AutoScaleMode%2A>
- <xref:System.Windows.Forms.Control.Scale%2A>
- <xref:System.Windows.Forms.ContainerControl.PerformAutoScale%2A>
- <xref:System.Windows.Forms.ContainerControl.AutoScaleDimensions%2A>

<!-- TODO
- [Rendering Controls with Visual Styles](controls/rendering-controls-with-visual-styles.md)
- [How to: Improve Performance by Avoiding Automatic Scaling](advanced/how-to-improve-performance-by-avoiding-automatic-scaling.md)-->
