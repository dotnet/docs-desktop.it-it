---
title: Raccogli input penna digitale
ms.date: 08/15/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ink [WPF], collecting
- InkCanvas element [WPF]
- properties [WPF], DrawingAttributes
- collecting digital ink [WPF]
- digital ink [WPF], collecting
- properties [WPF], DefaultDrawingAttributes
- DefaultDrawingAttributes property [WPF]
ms.assetid: 66a3129d-9577-43eb-acbd-56c147282016
ms.openlocfilehash: 813a5313a6fbf83c36cdbed1f64ce69a217ad788
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964171"
---
# <a name="collect-ink"></a>Raccogli input penna

La raccolta di input penna è una delle funzionalità principali della piattaforma [Windows Presentation Foundation](../index.md). In questo argomento vengono illustrati i metodi per la raccolta di input penna in Windows Presentation Foundation (WPF).

## <a name="prerequisites"></a>Prerequisiti

Per usare gli esempi seguenti, è necessario innanzitutto installare Visual Studio e il Windows SDK. È inoltre necessario comprendere come scrivere applicazioni per WPF. Per ulteriori informazioni su come iniziare a usare WPF, vedere [procedura dettagliata: applicazione desktop WPF](../getting-started/walkthrough-my-first-wpf-desktop-application.md).

## <a name="use-the-inkcanvas-element"></a>Usare l'elemento InkCanvas

L' <xref:System.Windows.Controls.InkCanvas?displayProperty=fullName> elemento fornisce il modo più semplice per raccogliere input penna in WPF. Usare un <xref:System.Windows.Controls.InkCanvas> elemento per ricevere e visualizzare input penna. In genere, l'input penna viene effettuato tramite uno stilo che interagisce con un digitalizzatore per produrre i tratti. È anche possibile usare un mouse al posto dello stilo. I tratti creati sono rappresentati come <xref:System.Windows.Ink.Stroke> oggetti e possono essere modificati sia a livello di codice sia in base all'input dell'utente. <xref:System.Windows.Controls.InkCanvas>Consente agli utenti di selezionare, modificare o eliminare un oggetto esistente <xref:System.Windows.Ink.Stroke> .

Usando XAML, è possibile configurare la raccolta di input penna con la stessa facilità con cui si aggiunge un elemento **InkCanvas** all'albero. Nell'esempio seguente viene aggiunto un oggetto <xref:System.Windows.Controls.InkCanvas> a un progetto WPF predefinito creato in Visual Studio:

[!code-xaml[DigitalInkTopics#6](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#6)]

L'elemento **InkCanvas** può inoltre contenere elementi figlio, rendendo possibile l'aggiunta di funzionalità di annotazione Ink a quasi tutti i tipi di elementi XAML. Ad esempio, per aggiungere le funzionalità di Inking a un elemento di testo, è sufficiente impostarlo come figlio di un oggetto <xref:System.Windows.Controls.InkCanvas> :

[!code-xaml[DigitalInkTopics#5](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#5)]

L'aggiunta del supporto per contrassegnare un'immagine con input penna è semplice:

[!code-xaml[DigitalInkTopics#7](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window2.xaml#7)]

### <a name="inkcollection-modes"></a>Modalità InkCollection

<xref:System.Windows.Controls.InkCanvas>Fornisce supporto per varie modalità di input tramite la relativa <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> Proprietà.

### <a name="manipulate-ink"></a>Modificare l'input penna

<xref:System.Windows.Controls.InkCanvas>Fornisce supporto per molte operazioni di modifica dell'input penna. Ad esempio, <xref:System.Windows.Controls.InkCanvas> supporta la cancellazione della penna indietro e non è necessario alcun codice aggiuntivo per aggiungere la funzionalità all'elemento.

#### <a name="selection"></a>Selezione

Per impostare la modalità di selezione è sufficiente impostare la <xref:System.Windows.Controls.InkCanvasEditingMode> proprietà su **Seleziona**.

Il codice seguente imposta la modalità di modifica in base al valore di un oggetto <xref:System.Windows.Forms.CheckBox> :

[!code-csharp[DigitalInkTopics#8](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#8)]
[!code-vb[DigitalInkTopics#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#8)]

#### <a name="drawingattributes"></a>DrawingAttributes

Utilizzare la <xref:System.Windows.Ink.Stroke.DrawingAttributes%2A> proprietà per modificare l'aspetto dei tratti di input penna. Ad esempio, il <xref:System.Windows.Ink.DrawingAttributes.Color%2A> membro di <xref:System.Windows.Ink.DrawingAttributes> imposta il colore dell'oggetto di cui è stato eseguito il rendering <xref:System.Windows.Ink.Stroke> .

Nell'esempio seguente il colore dei tratti selezionati viene modificato in rosso:

[!code-csharp[DigitalInkTopics#9](~/samples/snippets/csharp/VS_Snippets_Wpf/DigitalInkTopics/CSharp/Window1.xaml.cs#9)]
[!code-vb[DigitalInkTopics#9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DigitalInkTopics/VisualBasic/Window1.xaml.vb#9)]

### <a name="defaultdrawingattributes"></a>DefaultDrawingAttributes

La <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> proprietà fornisce l'accesso a proprietà quali l'altezza, la larghezza e il colore dei tratti da creare in un oggetto <xref:System.Windows.Controls.InkCanvas> . Una volta modificato <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> , tutti i tratti successivi immessi in <xref:System.Windows.Controls.InkCanvas> vengono sottoposti a rendering con i nuovi valori delle proprietà.

Oltre a modificare <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> nel file code-behind, è possibile usare la sintassi XAML per specificare le <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> Proprietà.

Nell'esempio seguente viene illustrato come impostare la <xref:System.Windows.Ink.DrawingAttributes.Color%2A> Proprietà. Per usare questo codice, creare un nuovo progetto WPF denominato "HelloInkCanvas" in Visual Studio. Sostituire il codice nel file *MainWindow. XAML* con il codice seguente:

[!code-xaml[HelloInkCanvas#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml#1)]

Successivamente, aggiungere i gestori eventi del pulsante seguenti al file code-behind, all'interno della classe MainWindow:

[!code-csharp[HelloInkCanvas#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HelloInkCanvas/CSharp/Window1.xaml.cs#2)]

Dopo aver copiato il codice, premere **F5** in Visual Studio per eseguire il programma nel debugger.

Si noti il modo <xref:System.Windows.Controls.StackPanel> in cui posiziona i pulsanti sulla parte superiore del <xref:System.Windows.Controls.InkCanvas> . Se si tenta di eseguire l'input penna sulla parte superiore dei pulsanti, <xref:System.Windows.Controls.InkCanvas> raccoglie ed esegue il rendering dell'input penna dietro i pulsanti. Questo è dovuto al fatto che i pulsanti sono di pari livello <xref:System.Windows.Controls.InkCanvas> rispetto agli elementi figlio. Il rendering dell'input penna viene eseguito dietro i pulsanti anche perché si trovano più in alto nel z order.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Ink.DrawingAttributes>
- <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A>
- <xref:System.Windows.Ink>
