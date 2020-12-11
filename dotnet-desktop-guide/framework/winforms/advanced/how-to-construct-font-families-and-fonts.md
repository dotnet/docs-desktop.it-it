---
title: 'Procedura: Creare tipi di carattere e famiglie di caratteri'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- font families [Windows Forms], constructing
- fonts [Windows Forms], constructing
ms.assetid: d3a4a223-9492-4b54-9afd-db1c31c3cefd
ms.openlocfilehash: 2d609525858c7a8ff77c0b86900b4fc7d6b4e39a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951498"
---
# <a name="how-to-construct-font-families-and-fonts"></a>Procedura: Creare tipi di carattere e famiglie di caratteri
GDI+ raggruppa i tipi di carattere con lo stesso carattere tipografico ma con stili diversi nelle famiglie di caratteri. Ad esempio, la famiglia di caratteri Arial contiene i tipi di carattere seguenti:  
  
- Arial Regular  
  
- Arial grassetto  
  
- Arial corsivo  
  
- Arial grassetto corsivo  
  
 GDI+ utilizza quattro stili per formare famiglie: normale, grassetto, corsivo e grassetto corsivo. Gli aggettivi come *Narrow* e *arrotondati* non sono considerati stili; ma fanno parte del nome della famiglia. Ad esempio, Arial Narrow è una famiglia di caratteri con i membri seguenti:  
  
- Arial Narrow Regular  
  
- Arial Narrow Bold  
  
- Arial Narrow corsivo  
  
- Arial Narrow Bold corsivo  
  
 Prima di poter creare un testo con GDI+, è necessario creare un <xref:System.Drawing.FontFamily> oggetto e un <xref:System.Drawing.Font> oggetto. L' <xref:System.Drawing.FontFamily> oggetto specifica il carattere tipografico (ad esempio, Arial) e l' <xref:System.Drawing.Font> oggetto specifica le dimensioni, lo stile e le unità.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene costruito un tipo di carattere Arial di stile normale con una dimensione di 16 pixel. Nel codice seguente, il primo argomento passato al <xref:System.Drawing.Font.%23ctor%2A> costruttore è l' <xref:System.Drawing.FontFamily> oggetto. Il secondo argomento specifica la dimensione del tipo di carattere misurato in unità identificate dal quarto argomento. Il terzo argomento identifica lo stile.  
  
 <xref:System.Drawing.GraphicsUnit.Pixel> è un membro dell' <xref:System.Drawing.GraphicsUnit> enumerazione e <xref:System.Drawing.FontStyle.Regular> è un membro dell' <xref:System.Drawing.FontStyle> enumerazione.  
  
 [!code-csharp[System.Drawing.FontsAndText#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.FontsAndText#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro di <xref:System.Windows.Forms.PaintEventHandler> .  
  
## <a name="see-also"></a>Vedere anche

- [Utilizzo di tipi di carattere e testo](using-fonts-and-text.md)
- [Grafica e disegno in Windows Form](graphics-and-drawing-in-windows-forms.md)
