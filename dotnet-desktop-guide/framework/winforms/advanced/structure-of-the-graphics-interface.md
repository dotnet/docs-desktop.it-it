---
title: Struttura dell'interfaccia grafica
ms.date: 03/30/2017
helpviewer_keywords:
- GDI+, using managed interface
- graphics [Windows Forms], class structure
ms.assetid: 010a1e46-656b-40a1-8d5d-87aa05ee1243
ms.openlocfilehash: d3b16249b6bae4a113661f5a3a47097046ba20f1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952806"
---
# <a name="structure-of-the-graphics-interface"></a>Struttura dell'interfaccia grafica
L'interfaccia di classe gestita per GDI+ contiene circa 60 classi, enumerazioni 50 e 8 strutture. La <xref:System.Drawing.Graphics> classe è alla base della funzionalità GDI+; è la classe che disegna effettivamente linee, curve, figure, immagini e testo.  
  
## <a name="important-classes"></a>Classi importanti  
 Molte classi interagiscono con la <xref:System.Drawing.Graphics> classe. Ad esempio, il <xref:System.Drawing.Graphics.DrawLine%2A> metodo riceve un <xref:System.Drawing.Pen> oggetto che include gli attributi (colore, larghezza, stile trattino e il tipo) della linea da disegnare. Il <xref:System.Drawing.Graphics.FillRectangle%2A> metodo può ricevere un puntatore a un <xref:System.Drawing.Drawing2D.LinearGradientBrush> oggetto, che interagisce con l' <xref:System.Drawing.Graphics> oggetto per riempire un rettangolo con un colore a modifica graduale. <xref:System.Drawing.Font><xref:System.Drawing.StringFormat>gli oggetti e influenzano il modo in cui un <xref:System.Drawing.Graphics> oggetto disegna il testo. Un <xref:System.Drawing.Drawing2D.Matrix> oggetto archivia e modifica la trasformazione globale di un <xref:System.Drawing.Graphics> oggetto, che viene usato per ruotare, ridimensionare e capovolgere le immagini.  
  
 GDI+ fornisce diverse strutture (ad esempio, <xref:System.Drawing.Rectangle> , <xref:System.Drawing.Point> e <xref:System.Drawing.Size> ) per l'organizzazione dei dati grafici. Inoltre, alcune classi servono principalmente come tipi di dati strutturati. Ad esempio, la <xref:System.Drawing.Imaging.BitmapData> classe è un helper per la <xref:System.Drawing.Bitmap> classe e la <xref:System.Drawing.Drawing2D.PathData> classe è un helper per la <xref:System.Drawing.Drawing2D.GraphicsPath> classe.  
  
 GDI+ definisce diverse enumerazioni, ovvero raccolte di costanti correlate. L'enumerazione, ad esempio, <xref:System.Drawing.Drawing2D.LineJoin> contiene gli elementi <xref:System.Drawing.Drawing2D.LineJoin.Bevel> , <xref:System.Drawing.Drawing2D.LineJoin.Miter> e <xref:System.Drawing.Drawing2D.LineJoin.Round> , che specificano gli stili che possono essere utilizzati per unire in join due righe.  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica sulla grafica](graphics-overview-windows-forms.md)
- [Informazioni sul codice gestito GDI+](about-gdi-managed-code.md)
- [Utilizzo di classi grafiche gestite](using-managed-graphics-classes.md)
