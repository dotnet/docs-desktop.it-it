---
title: Simulare eventi di tastiera
description: Informazioni su come simulare gli eventi di tastiera in Windows Forms per .NET.
ms.date: 10/26/2020
dev_langs:
- csharp
- vb
helpviewer_keywords:
- keyboards [Windows Forms], event simulation
- user input [Windows Forms], simulating
- SendKeys [Windows Forms], using
ms.openlocfilehash: 5ac62ca4311461ba95a2c31876d038baffe678a2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969259"
---
# <a name="how-to-simulate-keyboard-events-windows-forms-net"></a>Come simulare gli eventi di tastiera (Windows Forms .NET)

Windows Forms fornisce alcune opzioni per simulare a livello di codice l'input da tastiera. Questo articolo fornisce una panoramica di queste opzioni.

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="use-sendkeys"></a>USA SendKeys

Windows Forms fornisce la <xref:System.Windows.Forms.SendKeys?displayProperty=fullName> classe per l'invio di sequenze di tasti all'applicazione attiva. Esistono due metodi per inviare le sequenze di tasti a un'applicazione: <xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> e <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> . La differenza tra i due metodi è che `SendWait` blocca il thread corrente quando viene inviata la sequenza di tasti, in attesa di una risposta, mentre non lo è `Send` . Per ulteriori informazioni su `SendWait` , vedere [per inviare una sequenza di tasti a un'altra applicazione](#to-send-a-keystroke-to-a-different-application).

> [!CAUTION]
> Se l'applicazione verrà usata a livello internazionale con un'ampia gamma di tastiere, è opportuno evitare l'uso di <xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> perché potrebbe generare risultati imprevedibili.

Dietro le quinte, `SendKeys` Usa un'implementazione di Windows precedente per l'invio dell'input, che può avere esito negativo nelle finestre moderne in cui si prevede che l'applicazione non sia in esecuzione con diritti amministrativi. Se l'implementazione precedente ha esito negativo, il codice tenta automaticamente l'implementazione di Windows più recente per l'invio dell'input. Inoltre, quando la <xref:System.Windows.Forms.SendKeys> classe usa la nuova implementazione, il <xref:System.Windows.Forms.SendKeys.SendWait%2A> metodo non blocca più il thread corrente durante l'invio di sequenze di tasti a un'altra applicazione.

> [!IMPORTANT]
> Se l'applicazione si basa su un comportamento coerente indipendentemente dal sistema operativo, è possibile forzare la classe <xref:System.Windows.Forms.SendKeys> a usare la nuova implementazione aggiungendo la seguente impostazione applicazione al file app.config.
>
> ```xml
> <appSettings>
>   <add key="SendKeys" value="SendInput"/>
> </appSettings>
> ```
>
> Per forzare la <xref:System.Windows.Forms.SendKeys> classe a usare _solo_ l'implementazione precedente, usare invece il valore `"JournalHook"` .

### <a name="to-send-a-keystroke-to-the-same-application"></a>Per inviare una pressione di tasto alla stessa applicazione

Chiamare il metodo <xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> o <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> della classe <xref:System.Windows.Forms.SendKeys> . Le pressioni di tasti specificate verranno ricevute dal controllo attivo dell'applicazione.

Nell'esempio di codice seguente viene usato `Send` per simulare la pressione dei tasti <kbd>ALT</kbd> e <kbd>giù</kbd> insieme. Queste sequenze di tasti fanno sì <xref:System.Windows.Forms.ComboBox> che il controllo visualizzi l'elenco a discesa. In questo esempio si presuppone una <xref:System.Windows.Forms.Form> con <xref:System.Windows.Forms.Button> e <xref:System.Windows.Forms.ComboBox> .

:::code language="csharp" source="snippets/how-to-simulate-events/csharp/Form1.cs" id="ShowDropDown":::
:::code language="vb" source="snippets/how-to-simulate-events/vb/Form1.vb" id="ShowDropDown":::

### <a name="to-send-a-keystroke-to-a-different-application"></a>Per inviare una pressione di tasto a un'applicazione diversa

I <xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> <xref:System.Windows.Forms.SendKeys.SendWait%2A?displayProperty=nameWithType> metodi e inviano sequenze di tasti all'applicazione attiva, che in genere è l'applicazione da cui si stanno inviando le sequenze di tasti. Per inviare sequenze di tasti a un'altra applicazione, è prima necessario attivarla. Poiché non esiste alcun metodo gestito per attivare un'altra applicazione, è necessario usare i metodi Windows nativi per concentrare l'altra applicazione. Il seguente esempio di codice usa platform invoke per chiamare i metodi `FindWindow` e `SetForegroundWindow` per attivare la finestra dell'applicazione Calculator e quindi chiama `Send` per inviare una serie di calcoli all'applicazione Calculator.

L'esempio di codice seguente usa `Send` per simulare la pressione dei tasti nell'applicazione Windows 10 Calculator. Cerca innanzitutto una finestra dell'applicazione con titolo `Calculator` e quindi la attiva. Una volta attivato, le sequenze di tasti vengono inviate per calcolare 10 più 10.

:::code language="csharp" source="snippets/how-to-simulate-events/csharp/Form2.cs" id="Calculator":::
:::code language="vb" source="snippets/how-to-simulate-events/vb/Form2.vb" id="Calculator":::

## <a name="use-oneventname-methods"></a>Usare i metodi OnEventName

Il modo più semplice per simulare gli eventi della tastiera consiste nel chiamare un metodo sull'oggetto che genera l'evento. La maggior parte degli eventi dispone di un metodo corrispondente che li richiama, denominato nel modello di `On` seguito da `EventName` , ad esempio `OnKeyPress` . Questa opzione è possibile solo all'interno di controlli o moduli personalizzati, perché questi metodi sono protetti e non è possibile accedervi dall'esterno del contesto del controllo o del form.

Questi metodi protetti sono disponibili per simulare gli eventi della tastiera.

- `OnKeyDown`
- `OnKeyPress`
- `OnKeyUp`

Per ulteriori informazioni su questi eventi, vedere [utilizzo degli eventi di tastiera (Windows Forms .NET)](events.md).

## <a name="see-also"></a>Vedere anche

- [Panoramica dell'uso della tastiera (Windows Forms .NET)](overview.md)
- [Utilizzo degli eventi di tastiera (Windows Forms .NET)](events.md)
- [Utilizzo degli eventi del mouse (Windows Forms .NET)](../input-mouse/events.md)
- <xref:System.Windows.Forms.SendKeys>
- <xref:System.Windows.Forms.Keys>
- <xref:System.Windows.Forms.Control.KeyDown>
- <xref:System.Windows.Forms.Control.KeyPress>
