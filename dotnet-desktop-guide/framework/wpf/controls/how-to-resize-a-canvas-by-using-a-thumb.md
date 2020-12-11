---
title: "Procedura: ridimensionare un'area di disegno utilizzando un cursore"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- resizing Canvas control [WPF]
- controls [WPF], Thumb
- controls [WPF], Canvas
- Thumb control [WPF]
- Canvas control [WPF]
ms.assetid: 7dc9f435-726c-4d4d-be41-eb24cfe17bef
ms.openlocfilehash: 84f5ac2b53124b7f4d7c15741e94b40e7ee81526
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966169"
---
# <a name="how-to-resize-a-canvas-by-using-a-thumb"></a>Procedura: ridimensionare un'area di disegno utilizzando un cursore
Questo esempio illustra come usare un <xref:System.Windows.Controls.Primitives.Thumb> controllo per ridimensionare un <xref:System.Windows.Controls.Canvas> controllo.  
  
## <a name="example"></a>Esempio  
 Il <xref:System.Windows.Controls.Primitives.Thumb> controllo fornisce funzionalità di trascinamento che possono essere utilizzate per spostare o ridimensionare i controlli monitorando gli <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> eventi e di <xref:System.Windows.Controls.Primitives.Thumb> .  
  
 L'utente inizia un'operazione di trascinamento premendo il pulsante sinistro del mouse quando il puntatore del mouse viene sospeso sul <xref:System.Windows.Controls.Primitives.Thumb> controllo. L'operazione di trascinamento continua fino a quando il pulsante sinistro del mouse rimane premuto. Durante l'operazione di trascinamento, <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> può verificarsi più di una volta. Ogni volta che si verifica, la <xref:System.Windows.Controls.Primitives.DragDeltaEventArgs> classe fornisce la modifica nella posizione che corrisponde alla modifica della posizione del mouse. Quando l'utente rilascia il pulsante sinistro del mouse, l'operazione di trascinamento viene completata. L'operazione di trascinamento fornisce solo nuove coordinate; non riposiziona automaticamente <xref:System.Windows.Controls.Primitives.Thumb> .  
  
 Nell'esempio seguente viene illustrato un <xref:System.Windows.Controls.Primitives.Thumb> controllo che rappresenta l'elemento figlio di un <xref:System.Windows.Controls.Canvas> controllo. Il gestore eventi per il relativo <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> evento fornisce la logica per spostare <xref:System.Windows.Controls.Primitives.Thumb> e ridimensionare <xref:System.Windows.Controls.Canvas> . I gestori eventi per l' <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> evento e <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> modificano il colore di <xref:System.Windows.Controls.Primitives.Thumb> durante un'operazione di trascinamento. Nell'esempio seguente viene definito <xref:System.Windows.Controls.Primitives.Thumb> .  
  
 [!code-xaml[Thumb#thumb](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml#thumb)]  
  
 Nell'esempio seguente viene illustrato il <xref:System.Windows.Controls.Primitives.Thumb.DragDelta> gestore eventi che sposta l'oggetto <xref:System.Windows.Controls.Primitives.Thumb> e ridimensiona l'oggetto <xref:System.Windows.Controls.Canvas> in risposta a un movimento del mouse.  
  
 [!code-csharp[Thumb#2](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#2)]  
  
 Nell'esempio seguente viene illustrato il <xref:System.Windows.Controls.Primitives.Thumb.DragStarted> gestore eventi.  
  
 [!code-csharp[Thumb#DragStartedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragstartedhandler)]
 [!code-vb[Thumb#DragStartedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragstartedhandler)]  
  
 Nell'esempio seguente viene illustrato il <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted> gestore eventi.  
  
 [!code-csharp[Thumb#DragCompletedHandler](~/samples/snippets/csharp/VS_Snippets_Wpf/Thumb/CSharp/Pane1.xaml.cs#dragcompletedhandler)]
 [!code-vb[Thumb#DragCompletedHandler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/Thumb/VisualBasic/Pane1.xaml.vb#dragcompletedhandler)]  
  
 Per l'esempio completo, vedere [esempio di funzionalità di trascinamento del pollice](https://github.com/Microsoft/WPF-Samples/tree/master/Drag%20and%20Drop/DragDropThumbOps).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.Primitives.Thumb>
- <xref:System.Windows.Controls.Primitives.Thumb.DragStarted>
- <xref:System.Windows.Controls.Primitives.Thumb.DragDelta>
- <xref:System.Windows.Controls.Primitives.Thumb.DragCompleted>
