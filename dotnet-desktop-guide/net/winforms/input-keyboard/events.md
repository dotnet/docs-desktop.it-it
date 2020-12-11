---
title: Utilizzo degli eventi di tastiera
description: Panoramica dell'uso degli eventi di tastiera per gestire l'input da tastiera. Questo articolo fornisce un elenco di eventi correlati alla tastiera e quando usarli.
ms.date: 10/26/2020
ms.topic: overview
dev_langs:
- csharp
- vb
helpviewer_keywords:
- KeyPress event [Windows Forms]
- keyboards [Windows Forms], keyboard events
- KeyUp event
- KeyDown event
- keyboard events
- events [Windows Forms], keyboard
ms.openlocfilehash: 3e7493c9841fa036aa9d18aa00a1322d9758cbb1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969829"
---
# <a name="using-keyboard-events-windows-forms-net"></a>Utilizzo degli eventi di tastiera (Windows Forms .NET)

La maggioranza dei programmi di Windows Form elabora gli input della tastiera tramite gestione dei relativi eventi. Questo articolo fornisce una panoramica degli eventi della tastiera, inclusi i dettagli su quando usare ogni evento e i dati forniti per ogni evento. Per ulteriori informazioni sugli eventi in generale, vedere [Cenni preliminari sugli eventi (Windows Forms .NET)](../forms/events.md).

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="keyboard-events"></a>Eventi della tastiera

Windows Form include due eventi che si verificano quando un utente preme un tasto e un evento che si verifica quando un utente rilascia un tasto:

- L' <xref:System.Windows.Forms.Control.KeyDown> evento si verifica una volta.
- L'evento <xref:System.Windows.Forms.Control.KeyPress>, che può verificarsi più volte quando un utente tiene premuto lo stesso tasto.
- L'evento <xref:System.Windows.Forms.Control.KeyUp> si verifica una volta quando un utente rilascia un tasto. 

Quando un utente preme un tasto, Windows Form determina quale evento generare in base al fatto che il messaggio della tastiera specifichi un tasto carattere o fisico. Per ulteriori informazioni su caratteri e chiavi fisiche, vedere [Cenni preliminari sulla tastiera, eventi della tastiera](overview.md#keyboard-events).

La tabella seguente illustra i tre eventi di tastiera.

|Evento della tastiera|Descrizione|Risultati|
|--------------------|-----------------|-------------|
|<xref:System.Windows.Forms.Control.KeyDown>|L'evento viene generato quando un utente preme un tasto fisico.|Il gestore per <xref:System.Windows.Forms.Control.KeyDown> riceve:<br /><br /> <ul><li>Un parametro <xref:System.Windows.Forms.KeyEventArgs>, che fornisce la proprietà <xref:System.Windows.Forms.KeyEventArgs.KeyCode%2A> (che specifica un tasto fisico).</li><li>La proprietà <xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> (MAIUSC, CTRL o ALT).</li><li>La proprietà <xref:System.Windows.Forms.KeyEventArgs.KeyData%2A>, che combina il codice tasto e il modificatore. Il parametro <xref:System.Windows.Forms.KeyEventArgs> include inoltre:<br /><br /> <ul><li>La proprietà <xref:System.Windows.Forms.KeyEventArgs.Handled%2A>, che può essere impostata per impedire al controllo sottostante di ricevere il tasto.</li><li>La proprietà <xref:System.Windows.Forms.KeyEventArgs.SuppressKeyPress%2A>, utilizzabile per eliminare gli eventi <xref:System.Windows.Forms.Control.KeyPress> e <xref:System.Windows.Forms.Control.KeyUp> per la sequenza di tasti.</li></ul></li></ul>|
|<xref:System.Windows.Forms.Control.KeyPress>|L'evento viene generato quando il tasto o i tasti premuti corrispondono a un carattere. Ad esempio, se un utente preme i tasti MAIUSC e "a" minuscola, il risultato sarà la lettera "A" maiuscola.|<xref:System.Windows.Forms.Control.KeyPress> viene generato dopo <xref:System.Windows.Forms.Control.KeyDown>.<br /><br /> <ul><li>Il gestore per <xref:System.Windows.Forms.Control.KeyPress> riceve:</li><li>Un parametro <xref:System.Windows.Forms.KeyPressEventArgs>, che include il codice carattere del tasto premuto.  Il codice carattere è univoco per ogni combinazione di tasto carattere e tasto modificatore.<br /><br />     Ad esempio, il tasto "A" avrà il risultato seguente:<br /><br /> <ul><li>Il codice carattere 65, se premuto con il tasto MAIUSC</li><li>Oppure il tasto BLOC MAIUSC, 97 se premuto da solo</li><li>E 1, se premuto con il tasto CTRL</li></ul></li></ul>|
|<xref:System.Windows.Forms.Control.KeyUp>|L'evento viene generato quando un utente rilascia un tasto fisico.|Il gestore per <xref:System.Windows.Forms.Control.KeyUp> riceve:<br /><br /> <ul><li>Un parametro <xref:System.Windows.Forms.KeyEventArgs>:<br /><br /> <ul><li>Che fornisce la proprietà <xref:System.Windows.Forms.KeyEventArgs.KeyCode%2A> (che specifica un tasto fisico).</li><li>La proprietà <xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> (MAIUSC, CTRL o ALT).</li><li>La proprietà <xref:System.Globalization.SortKey.KeyData%2A>, che combina il codice tasto e il modificatore.</li></ul></li></ul>|

## <a name="see-also"></a>Vedere anche

- [Panoramica dell'uso della tastiera (Windows Forms .NET)](overview.md)
- [Come modificare gli eventi del tasto tastiera (Windows Forms .NET)](how-to-change-key-press.md)
- [Come verificare la pressione dei tasti di modifica (Windows Forms .NET)](how-to-check-modifier-key.md)
- [Come simulare gli eventi di tastiera (Windows Forms .NET)](how-to-simulate-events.md)
- [Come gestire i messaggi di input da tastiera nel formato (Windows Forms .NET)](how-to-handle-forms.md)
