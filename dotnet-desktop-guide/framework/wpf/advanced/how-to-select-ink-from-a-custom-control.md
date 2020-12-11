---
title: "Procedura: selezionare l'input penna da un controllo personalizzato"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], ink selection
- ink [WPF], selecting from custom control
- custom controls [WPF], ink selection
ms.assetid: 5f3a45c6-6d40-4017-9b47-933f134ceba3
ms.openlocfilehash: 5c9b2f3d64e4cbb309772d6a1d9fa88f589df84c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968551"
---
# <a name="how-to-select-ink-from-a-custom-control"></a>Procedura: selezionare l'input penna da un controllo personalizzato
Aggiungendo un <xref:System.Windows.Ink.IncrementalLassoHitTester> al controllo personalizzato, è possibile abilitare il controllo in modo che un utente possa selezionare l'input penna con uno strumento lazo, in modo analogo al modo in cui il <xref:System.Windows.Controls.InkCanvas> Seleziona l'input penna con un lazo.  
  
 Questo esempio presuppone che si abbia familiarità con la creazione di un controllo personalizzato abilitato per l'input penna.  Per creare un controllo personalizzato che accetti input penna, vedere [creazione di un controllo input penna](creating-an-ink-input-control.md).  
  
## <a name="example"></a>Esempio  
 Quando l'utente disegna un lazo, il <xref:System.Windows.Ink.IncrementalLassoHitTester> stima quali tratti si troveranno entro i limiti del percorso del lazo dopo che l'utente ha completato il lazo.  I tratti che sono determinati all'interno dei limiti del percorso lazo possono essere considerati come selezionati.  I tratti selezionati possono anche essere deselezionati.  Se, ad esempio, l'utente inverte la direzione durante il disegno del lazo, <xref:System.Windows.Ink.IncrementalLassoHitTester> può deselezionare alcuni tratti.  
  
 <xref:System.Windows.Ink.IncrementalLassoHitTester>Genera l' <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> evento, che consente al controllo personalizzato di rispondere mentre l'utente sta disegnando il lazo.  Ad esempio, è possibile modificare l'aspetto dei tratti quando l'utente seleziona e deselezionarli.  
  
## <a name="managing-the-ink-mode"></a>Gestione della modalità input penna  
 È utile per l'utente se il lazo viene visualizzato in modo diverso dall'input penna sul controllo. A tale scopo, il controllo personalizzato deve tenere traccia dell'eventuale scrittura o selezione dell'input penna da parte dell'utente. Il modo più semplice per eseguire questa operazione è dichiarare un'enumerazione con due valori: uno per indicare che l'utente sta scrivendo input penna e uno per indicare che l'utente sta selezionando input penna.  
  
 [!code-csharp[HowToSelectInk#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#2)]
 [!code-vb[HowToSelectInk#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#2)]  
  
 Aggiungere quindi due <xref:System.Windows.Ink.DrawingAttributes> alla classe: una da usare quando l'utente scrive l'input penna, una da usare quando l'utente seleziona l'input penna.  Nel costruttore inizializzare <xref:System.Windows.Ink.DrawingAttributes> e alleghino entrambi <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> gli eventi allo stesso gestore eventi. Impostare quindi la <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> proprietà dell'oggetto sull' <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> input penna <xref:System.Windows.Ink.DrawingAttributes> .  
  
 [!code-csharp[HowToSelectInk#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#3)]
 [!code-vb[HowToSelectInk#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#3)]  
[!code-csharp[HowToSelectInk#4](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#4)]
[!code-vb[HowToSelectInk#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#4)]  
  
 Aggiungere una proprietà che espone la modalità di selezione. Quando l'utente modifica la modalità di selezione, impostare la <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.DrawingAttributes%2A> proprietà di sull' <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer> oggetto appropriato <xref:System.Windows.Ink.DrawingAttributes> e quindi alleghi la <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> proprietà a <xref:System.Windows.Controls.InkPresenter> .  
  
 [!code-csharp[HowToSelectInk#5](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#5)]
 [!code-vb[HowToSelectInk#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#5)]  
  
 Esporre le <xref:System.Windows.Ink.DrawingAttributes> Proprietà As, in modo che le applicazioni possano determinare l'aspetto dei tratti di input penna e dei tratti di selezione.  
  
 [!code-csharp[HowToSelectInk#6](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#6)]
 [!code-vb[HowToSelectInk#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#6)]  
  
 Quando viene modificata una proprietà di un <xref:System.Windows.Ink.DrawingAttributes> oggetto, <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> deve essere ricollegato a <xref:System.Windows.Controls.InkPresenter> .  Nel gestore eventi per l' <xref:System.Windows.Ink.DrawingAttributes.AttributeChanged> evento, riconnettersi <xref:System.Windows.Input.StylusPlugIns.DynamicRenderer.RootVisual%2A> a <xref:System.Windows.Controls.InkPresenter> .  
  
 [!code-csharp[HowToSelectInk#7](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#7)]
 [!code-vb[HowToSelectInk#7](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#7)]  
  
## <a name="using-the-incrementallassohittester"></a>Uso di IncrementalLassoHitTester  
 Crea e Inizializza un oggetto <xref:System.Windows.Ink.StrokeCollection> che contiene i tratti selezionati.  
  
 [!code-csharp[HowToSelectInk#8](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#8)]
 [!code-vb[HowToSelectInk#8](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#8)]  
  
 Quando l'utente inizia a disegnare un tratto, ovvero input penna o lazo, deseleziona tutti i tratti selezionati. Quindi, se l'utente sta disegnando un lazo, creare un chiamando <xref:System.Windows.Ink.IncrementalLassoHitTester> <xref:System.Windows.Ink.StrokeCollection.GetIncrementalLassoHitTester%2A> , sottoscrivere l' <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> evento e chiamare <xref:System.Windows.Ink.IncrementalHitTester.AddPoints%2A> . Questo codice può essere un metodo separato e viene chiamato dai <xref:System.Windows.UIElement.OnStylusDown%2A> <xref:System.Windows.UIElement.OnMouseDown%2A> metodi e.  
  
 [!code-csharp[HowToSelectInk#9](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#9)]
 [!code-vb[HowToSelectInk#9](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#9)]  
  
 Aggiungere i punti dello stilo a <xref:System.Windows.Ink.IncrementalLassoHitTester> mentre l'utente disegna il lazo.  Chiamare il metodo seguente dai <xref:System.Windows.UIElement.OnStylusMove%2A> metodi, <xref:System.Windows.UIElement.OnStylusUp%2A> , <xref:System.Windows.UIElement.OnMouseMove%2A> e <xref:System.Windows.UIElement.OnMouseLeftButtonUp%2A> .  
  
 [!code-csharp[HowToSelectInk#10](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#10)]
 [!code-vb[HowToSelectInk#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#10)]  
  
 Gestire l' <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged?displayProperty=nameWithType> evento per rispondere quando l'utente seleziona e deseleziona i tratti.  La <xref:System.Windows.Ink.LassoSelectionChangedEventArgs> classe dispone delle <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.SelectedStrokes%2A> <xref:System.Windows.Ink.LassoSelectionChangedEventArgs.DeselectedStrokes%2A> proprietà e che ottengono rispettivamente i tratti selezionati e deselezionati.  
  
 [!code-csharp[HowToSelectInk#11](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#11)]
 [!code-vb[HowToSelectInk#11](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#11)]  
  
 Quando l'utente completa il disegno del lazo, Annulla la sottoscrizione all' <xref:System.Windows.Ink.IncrementalLassoHitTester.SelectionChanged> evento e chiama <xref:System.Windows.Ink.IncrementalHitTester.EndHitTesting%2A> .  
  
 [!code-csharp[HowToSelectInk#12](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#12)]
 [!code-vb[HowToSelectInk#12](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#12)]  
  
## <a name="putting-it-all-together"></a>Riunendoli tutti.  
 L'esempio seguente è un controllo personalizzato che consente a un utente di selezionare l'input penna con un lazo.  
  
 [!code-csharp[HowToSelectInk#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToSelectInk/CSharp/InkSelector.cs#1)]
 [!code-vb[HowToSelectInk#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToSelectInk/VisualBasic/InkSelector.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Ink.IncrementalLassoHitTester>
- <xref:System.Windows.Ink.StrokeCollection>
- <xref:System.Windows.Input.StylusPointCollection>
- [Creazione di un controllo di input penna](creating-an-ink-input-control.md)
