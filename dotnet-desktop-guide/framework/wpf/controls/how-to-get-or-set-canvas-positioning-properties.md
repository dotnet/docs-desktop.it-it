---
title: 'Procedura: ottenere o impostare le proprietà di posizionamento delle aree di disegno'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Canvas control [WPF], setting positioning properties
ms.assetid: 1636b950-2b5a-4507-8a10-c5034cc58b1c
ms.openlocfilehash: 06508e1198736ccb1cbda41641dff4bc634ef82b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961369"
---
# <a name="how-to-get-or-set-canvas-positioning-properties"></a>Procedura: ottenere o impostare le proprietà di posizionamento delle aree di disegno
In questo esempio viene illustrato come utilizzare i metodi di posizionamento dell' <xref:System.Windows.Controls.Canvas> elemento per posizionare il contenuto figlio. In questo esempio viene utilizzato il contenuto di un oggetto <xref:System.Windows.Controls.ListBoxItem> per rappresentare i valori di posizionamento e i valori vengono convertiti in istanze di <xref:System.Double> , che è un argomento obbligatorio per il posizionamento. I valori vengono quindi convertiti di nuovo in stringhe e visualizzati come testo in un <xref:System.Windows.Controls.TextBlock> elemento usando il <xref:System.Windows.Controls.Canvas.GetLeft%2A> metodo.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene creato un <xref:System.Windows.Controls.ListBox> elemento con undici elementi selezionabili <xref:System.Windows.Controls.ListBoxItem> . L' <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> evento attiva il `ChangeLeft` metodo personalizzato definito dal blocco di codice successivo.  
  
 Ogni <xref:System.Windows.Controls.ListBoxItem> oggetto rappresenta un <xref:System.Double> valore, ovvero uno degli argomenti <xref:System.Windows.Controls.Canvas.SetLeft%2A> <xref:System.Windows.Controls.Canvas> accettati dal metodo. Per poter utilizzare un oggetto <xref:System.Windows.Controls.ListBoxItem> per rappresentare un'istanza di <xref:System.Double> , è necessario innanzitutto convertire il <xref:System.Windows.Controls.ListBoxItem> tipo nel tipo di dati corretto.  
  
 [!code-xaml[CanvasPositioningProperties#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml#1)]  
  
 Quando un utente modifica la <xref:System.Windows.Controls.ListBox> selezione, richiama il `ChangeLeft` metodo personalizzato. Questo metodo passa <xref:System.Windows.Controls.ListBoxItem> a un <xref:System.Windows.LengthConverter> oggetto, che converte l'oggetto <xref:System.Windows.Controls.ContentControl.Content%2A> di un oggetto <xref:System.Windows.Controls.ListBoxItem> in un'istanza di <xref:System.Double> (si noti che questo valore è già stato convertito in un oggetto <xref:System.String> utilizzando il <xref:System.Windows.Controls.Control.ToString%2A> metodo). Questo valore viene quindi passato nuovamente ai <xref:System.Windows.Controls.Canvas.SetLeft%2A> metodi e <xref:System.Windows.Controls.Canvas.GetLeft%2A> di per <xref:System.Windows.Controls.Canvas> poter modificare la posizione dell' `text1` oggetto.  
  
 [!code-csharp[CanvasPositioningProperties#2](~/samples/snippets/csharp/VS_Snippets_Wpf/CanvasPositioningProperties/CSharp/Window1.xaml.cs#2)]
 [!code-vb[CanvasPositioningProperties#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CanvasPositioningProperties/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.Canvas>
- <xref:System.Windows.Controls.ListBoxItem>
- <xref:System.Windows.LengthConverter>
- [Cenni preliminari sugli elementi Panel](panels-overview.md)
