---
title: Comportamenti del mouse di trascinamento della selezione
description: Informazioni sul funzionamento del trascinamento della selezione in Windows Forms, tra cui come eseguire il trascinamento della selezione con il mouse.
ms.date: 10/26/2020
ms.topic: conceptual
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag and drop [Windows Forms], Windows Forms
- Windows Forms, drag and drop
ms.openlocfilehash: d434b0f0e80c610fffeea26a6fff44b43ca07fed
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952530"
---
# <a name="drag-and-drop-mouse-behavior-overview-windows-forms-net"></a>Panoramica sul comportamento del mouse di trascinamento della selezione (Windows Forms .NET)

Windows Forms include un set di metodi, eventi e classi che implementano il comportamento di trascinamento e rilascio. Questo argomento fornisce una panoramica del supporto per il trascinamento della selezione in Windows Forms.<!-- TODO Also see [Drag-and-Drop Operations and Clipboard Support](./advanced/drag-and-drop-operations-and-clipboard-support.md).-->

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="drag-and-drop-events"></a>Eventi di trascinamento della selezione

Esistono due categorie di eventi in un'operazione di trascinamento della selezione: eventi che si verificano sulla destinazione corrente ed eventi che si verificano sull'origine dell'operazione di trascinamento della selezione. Per eseguire operazioni di trascinamento della selezione, è necessario gestire questi eventi. Usando le informazioni disponibili negli argomenti di questi eventi, è possibile facilitare le operazioni di trascinamento della selezione.

## <a name="events-on-the-current-drop-target"></a>Eventi sulla destinazione di rilascio corrente

La tabella seguente illustra gli eventi che si verificano sulla destinazione corrente di un'operazione di trascinamento della selezione.

| Evento del mouse                                   | Descrizione                                                                                                                                                                                            |
|-----------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <xref:System.Windows.Forms.Control.DragEnter> | Questo evento si verifica quando un oggetto viene trascinato all'interno dei limiti del controllo. Il gestore di questo evento riceve un argomento di tipo <xref:System.Windows.Forms.DragEventArgs>.                              |
| <xref:System.Windows.Forms.Control.DragOver>  | Questo evento si verifica quando un oggetto viene trascinato mentre il puntatore del mouse è all'interno dei limiti del controllo. Il gestore di questo evento riceve un argomento di tipo <xref:System.Windows.Forms.DragEventArgs>. |
| <xref:System.Windows.Forms.Control.DragDrop>  | Questo evento si verifica quando viene completata un'operazione di trascinamento della selezione. Il gestore di questo evento riceve un argomento di tipo <xref:System.Windows.Forms.DragEventArgs>.                                      |
| <xref:System.Windows.Forms.Control.DragLeave> | Questo evento si verifica quando un oggetto viene trascinato all'esterno dei limiti del controllo. Il gestore di questo evento riceve un argomento di tipo <xref:System.EventArgs>.                                              |

La classe <xref:System.Windows.Forms.DragEventArgs> fornisce la posizione del puntatore del mouse, lo stato corrente dei pulsanti del mouse e dei tasti di modifica della tastiera, i dati trascinati e i valori dell'enumerazione <xref:System.Windows.Forms.DragDropEffects> che specificano le operazioni consentite dall'origine dell'evento di trascinamento e l'effetto del rilascio sulla destinazione per l'operazione.

## <a name="events-on-the-drop-source"></a>Eventi nell'origine di rilascio

La tabella seguente illustra gli eventi che si verificano sull'origine di un'operazione di trascinamento e rilascio.

|Evento del mouse|Descrizione|
|-----------------|-----------------|
|<xref:System.Windows.Forms.Control.GiveFeedback>|Questo evento si verifica durante un'operazione di trascinamento. Permette di fornire all'utente un'indicazione visiva dell'operazione di trascinamento della selezione in corso, ad esempio cambiando l'aspetto del puntatore del mouse. Il gestore di questo evento riceve un argomento di tipo <xref:System.Windows.Forms.GiveFeedbackEventArgs>.|
|<xref:System.Windows.Forms.Control.QueryContinueDrag>|Questo evento si verifica durante un'operazione di trascinamento della selezione e consente all'origine del trascinamento di determinare se l'operazione deve essere annullata. Il gestore di questo evento riceve un argomento di tipo <xref:System.Windows.Forms.QueryContinueDragEventArgs>.|

La classe <xref:System.Windows.Forms.QueryContinueDragEventArgs> fornisce lo stato corrente dei pulsanti del mouse e dei tasti di modifica della tastiera, un valore che specifica se è stato premuto il tasto ESC e un valore dell'enumerazione <xref:System.Windows.Forms.DragAction> che è possibile impostare per specificare se l'operazione di trascinamento della selezione deve continuare.

## <a name="performing-drag-and-drop"></a>Esecuzione del trascinamento della selezione

Le operazioni di trascinamento della selezione coinvolgono sempre due componenti, l' **origine di trascinamento** e l' **obiettivo di rilascio**. Per avviare un'operazione di trascinamento della selezione, designare un controllo come origine e gestire l' <xref:System.Windows.Forms.Control.MouseDown> evento. Nel gestore eventi chiamare il <xref:System.Windows.DragDrop.DoDragDrop%2A> Metodo fornendo i dati associati all'eliminazione e al <xref:System.Windows.DragDropEffects> valore.

Impostare la proprietà del controllo di destinazione su <xref:System.Windows.Forms.Control.AllowDrop> `true` per consentire al controllo di accettare un'operazione di trascinamento della selezione. La destinazione gestisce due eventi, prima un evento in risposta al trascinamento sul controllo, ad esempio <xref:System.Windows.Forms.Control.DragOver> . E un secondo evento che rappresenta l'azione di rilascio, <xref:System.Windows.Forms.Control.DragDrop> .

Nell'esempio seguente viene illustrato un trascinamento da un <xref:System.Windows.Forms.Label> controllo a un <xref:System.Windows.Forms.TextBox> . Al termine del trascinamento, `TextBox` risponde assegnando il testo dell'etichetta a se stesso.

```csharp
// Initiate the drag
private void label1_MouseDown(object sender, MouseEventArgs e) =>
    DoDragDrop(((Label)sender).Text, DragDropEffects.All);

// Set the effect filter and allow the drop on this control
private void textBox1_DragOver(object sender, DragEventArgs e) =>
    e.Effect = DragDropEffects.All;

// React to the drop on this control
private void textBox1_DragDrop(object sender, DragEventArgs e) =>
    textBox1.Text = (string)e.Data.GetData(typeof(string));
```

```vb
' Initiate the drag
Private Sub Label1_MouseDown(sender As Object, e As MouseEventArgs)
    DoDragDrop(DirectCast(sender, Label).Text, DragDropEffects.All)
End Sub

' Set the effect filter and allow the drop on this control
Private Sub TextBox1_DragOver(sender As Object, e As DragEventArgs)
    e.Effect = DragDropEffects.All
End Sub

' React to the drop on this control
Private Sub TextBox1_DragDrop(sender As Object, e As DragEventArgs)
    TextBox1.Text = e.Data.GetData(GetType(String))
End Sub
```

Per ulteriori informazioni sugli effetti di trascinamento, vedere <xref:System.Windows.Forms.DragEventArgs.Data%2A> e <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A> .

## <a name="see-also"></a>Vedere anche

- [Panoramica dell'uso del mouse (Windows Forms .NET)](overview.md)
- <xref:System.Windows.Forms.Control.DragDrop?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.DragEnter?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.DragLeave?displayProperty=nameWithType>
- <xref:System.Windows.Forms.Control.DragOver?displayProperty=nameWithType>
