---
title: 'Procedura: creare testo con contorni'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- typography [WPF], linear gradient brush
- outlined text [WPF]
- gradient brush [WPF]
- linear gradient brush [WPF]
- typography [WPF], outline effects
ms.assetid: 4aa3cf6e-1953-4f26-8230-7c1409e5f28d
ms.openlocfilehash: 12da12320a09fa825d9c75d4a6e5e3264724de77
ms.sourcegitcommit: 069786bcadbf9cd931d7dc3d892262cd852d2ffb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/10/2021
ms.locfileid: "102604352"
---
# <a name="how-to-create-outlined-text"></a>Procedura: creare testo delineato

Nella maggior parte dei casi, quando si aggiunge l'ornamento alle stringhe di testo nell' [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] applicazione, si usa il testo in termini di una raccolta di caratteri discreti o di glifi. Ad esempio, è possibile creare un pennello sfumato lineare e applicarlo alla <xref:System.Windows.Controls.Control.Foreground%2A> proprietà di un <xref:System.Windows.Controls.TextBox> oggetto. Quando si visualizza o si modifica la casella di testo, il pennello sfumatura lineare viene applicato automaticamente al set di caratteri corrente nella stringa di testo.  
  
 ![Testo visualizzato con pennello sfumato lineare](./media/how-to-create-outlined-text/text-linear-gradient.jpg)
  
 Tuttavia, è anche possibile convertire il testo in <xref:System.Windows.Media.Geometry> oggetti, consentendo di creare altri tipi di testo visivamente RTF. Ad esempio, è possibile creare un <xref:System.Windows.Media.Geometry> oggetto in base alla struttura di una stringa di testo.  
  
 ![Struttura di testo con pennello sfumato lineare](./media/how-to-create-outlined-text/text-outline-linear-gradient.jpg)  
  
 Quando il testo viene convertito in un <xref:System.Windows.Media.Geometry> oggetto, non è più una raccolta di caratteri, non è possibile modificare i caratteri nella stringa di testo. Tuttavia, è possibile intervenire sull'aspetto del testo convertito modificandone le proprietà del tratto e del riempimento. Il tratto fa riferimento alla struttura del testo convertito, mentre il riempimento fa riferimento all'area all'interno della struttura del testo convertito.  
  
 Negli esempi seguenti vengono illustrati diversi modi per creare effetti visivi modificando il tratto e il riempimento del testo convertito.  
  
 ![Testo con colori diversi per tratto e riempimento](./media/how-to-create-outlined-text/fill-stroke-text-effect.jpg)  
  
 ![Testo con tratto con immagine applicato](./media/how-to-create-outlined-text/image-brush-application.jpg)
  
 È anche possibile modificare il rettangolo delimitatore del testo convertito o evidenziarlo. Nell'esempio seguente viene illustrato un modo per creare effetti visivi modificando il tratto e l'evidenziazione del testo convertito.  
  
 ![Testo con pennello immagine applicato al tratto ed evidenziato](./media/how-to-create-outlined-text/image-brush-text-application.jpg)

## <a name="example"></a>Esempio  
 La chiave per la conversione di testo in un <xref:System.Windows.Media.Geometry> oggetto consiste nell'utilizzare l' <xref:System.Windows.Media.FormattedText> oggetto. Dopo aver creato questo oggetto, è possibile usare i <xref:System.Windows.Media.FormattedText.BuildGeometry%2A> metodi e <xref:System.Windows.Media.FormattedText.BuildHighlightGeometry%2A> per convertire il testo in <xref:System.Windows.Media.Geometry> oggetti. Il primo metodo restituisce la geometria del testo formattato; il secondo metodo restituisce la geometria del rettangolo di delimitazione del testo formattato. Nell'esempio di codice seguente viene illustrato come creare un <xref:System.Windows.Media.FormattedText> oggetto e recuperare le geometrie del testo formattato e il relativo rettangolo di delimitazione.  
  
 [!code-csharp[OutlineTextControlViewer#CreateText](~/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#createtext)]
 [!code-vb[OutlineTextControlViewer#CreateText](~/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#createtext)]  
  
 Per visualizzare gli oggetti recuperati <xref:System.Windows.Media.Geometry> , è necessario accedere al <xref:System.Windows.Media.DrawingContext> dell'oggetto che sta visualizzando il testo convertito. In questi esempi di codice, questo accesso viene ottenuto creando un oggetto controllo personalizzato derivato da una classe che supporta il rendering definito dall'utente.  
  
 Per visualizzare <xref:System.Windows.Media.Geometry> gli oggetti nel controllo personalizzato, specificare una sostituzione per il <xref:System.Windows.UIElement.OnRender%2A> metodo. Il metodo sottoposto a override deve usare il <xref:System.Windows.Media.DrawingContext.DrawGeometry%2A> metodo per creare gli <xref:System.Windows.Media.Geometry> oggetti.  
  
 [!code-csharp[OutlineTextControlViewer#OnRender](~/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs#onrender)]
 [!code-vb[OutlineTextControlViewer#OnRender](~/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb#onrender)]  
  
  Per l'origine dell'oggetto controllo utente personalizzato di esempio, vedere [OutlineTextControl.cs per C#](https://github.com/dotnet/docs-desktop/tree/main/dotnet-desktop-guide/samples/snippets/csharp/VS_Snippets_Wpf/OutlineTextControlViewer/CSharp/OutlineTextControl.cs) e [OutlineTextControl. vb per Visual Basic](https://github.com/dotnet/docs/blob/master/samples/snippets/visualbasic/VS_Snippets_Wpf/OutlineTextControlViewer/visualbasic/outlinetextcontrol.vb).
  
## <a name="see-also"></a>Vedi anche

- [Disegno di testo formattato](drawing-formatted-text.md)
