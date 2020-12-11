---
title: Cenni preliminari sugli eventi
description: Una breve panoramica sugli eventi con .NET Windows Forms.
ms.date: 10/26/2020
ms.topic: overview
helpviewer_keywords:
- Windows Forms, event handling
- events [Windows Forms], about events
- delegates [Windows Forms], multicast
- delegates [Windows Forms], events and
- multicast event delegates
- Windows Forms controls, events
ms.openlocfilehash: aed33b7b856da210855a5b06ccf53610a6551b47
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968788"
---
# <a name="events-overview-windows-forms-net"></a>Cenni preliminari sugli eventi (Windows Forms .NET)

Un evento è un'azione che è possibile rispondere o "gestire" nel codice. Gli eventi possono essere generati da un'azione dell'utente, ad esempio il clic del mouse o la pressione di un tasto, dal codice del programma o dal sistema.

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

Le applicazioni basate su eventi eseguono codice in risposta a un evento. Ogni form e ogni controllo espone un set predefinito di eventi per cui è possibile creare codice. Se si verifica uno di questi eventi ed è presente codice associato a un gestore eventi, il codice viene richiamato.

Un oggetto può generare diversi tipi di eventi, ma molti tipi sono comuni alla maggior parte dei controlli. Ad esempio, la maggior parte degli oggetti gestirà un evento <xref:System.Windows.Forms.Control.Click>. Se un utente fa clic su un form, sarà eseguito il codice disponibile nel gestore eventi <xref:System.Windows.Forms.Control.Click> del codice.

> [!NOTE]
> Molti eventi si verificano insieme ad altri eventi. Ad esempio, quando si verifica l'evento <xref:System.Windows.Forms.Control.DoubleClick>, si verificano anche gli eventi <xref:System.Windows.Forms.Control.MouseDown>, <xref:System.Windows.Forms.Control.MouseUp> e <xref:System.Windows.Forms.Control.Click>.

Per informazioni su come generare e utilizzare un evento, vedere [gestione e generazione di eventi](/dotnet/standard/events/index).

## <a name="delegates-and-their-role"></a>Delegati e relativo ruolo

I delegati sono classi comunemente usate in .NET per compilare meccanismi di gestione degli eventi. Delegati approssimativamente equivalgono ai puntatori a funzione, comunemente utilizzati in Visual C++ e in altri linguaggi orientati agli oggetti. A differenza dei puntatori a funzioni, tuttavia, i delegati sono orientati ad oggetti, indipendenti dai tipi e sicuri. Inoltre, quando un puntatore a funzione contiene solo un riferimento a una funzione specifica, un delegato è costituito da un riferimento a un oggetto e fa riferimento a uno o più metodi all'interno dell'oggetto.

Questo modello di eventi USA i *delegati* per associare gli eventi ai metodi usati per gestirli. Il delegato permette alle altre classi di effettuare la registrazione per la notifica di eventi specificando un metodo del gestore. Quando si verifica l'evento, il delegato chiama il metodo associato. Per ulteriori informazioni su come definire i delegati, vedere [gestione e generazione di eventi](/dotnet/standard/events/index).

I delegati possono essere associati a un singolo metodo o a più metodi (multicast). Quando si crea un delegato per un evento, si crea in genere un evento multicast. Un'eccezione rara potrebbe essere un evento che produce una procedura specifica, ad esempio la visualizzazione di una finestra di dialogo, che non si ripete logicamente più volte per ogni evento. Per informazioni su come creare un delegato multicast, vedere [come combinare delegati (](/dotnet/csharp/programming-guide/delegates/how-to-combine-delegates-multicast-delegates)delegati multicast).

Un delegato multicast gestisce un elenco chiamate dei metodi a cui è associato. Il delegato multicast supporta un metodo <xref:System.Delegate.Combine%2A> per aggiungere un metodo all'elenco di chiamate e un metodo <xref:System.Delegate.Remove%2A> per rimuoverlo.

Quando un evento è registrato dall'applicazione, il controllo genera l'evento richiamando il delegato corrispondente. Il delegato chiama a sua volta il metodo associato. Nel caso più comune (un delegato multicast), il delegato chiama a sua volta ogni metodo associato nell'elenco chiamate, che fornisce una notifica uno-a-molti. Questa strategia indica che non è necessario che il controllo gestisca un elenco di oggetti di destinazione per la notifica degli eventi, perché il delegato gestisce tutte le registrazioni e le notifiche.

I delegati permettono anche l'associazione di più eventi allo stesso metodo, offrendo una notifica di tipo molti-a-uno. Ad esempio, un evento di selezione di un pulsante e un evento di selezione di un comando di menu possono richiamare lo stesso delegato, che quindi chiama un singolo metodo per gestire questi eventi separati nello stesso modo.

Il meccanismo di associazione utilizzato con i delegati è dinamico: un delegato può essere associato in fase di esecuzione a qualsiasi metodo la cui firma corrisponda a quella del gestore eventi. Questa funzionalità consente di impostare o modificare il metodo associato in base a una condizione e di collegare in modo dinamico un gestore eventi a un controllo.

## <a name="see-also"></a>Vedere anche

- [Gestione e generazione di eventi](/dotnet/standard/events/index)

<!-- TODO
- [Creating Event Handlers in Windows Forms](creating-event-handlers-in-windows-forms.md)
- [Event Handlers Overview](event-handlers-overview-windows-forms.md)-->
