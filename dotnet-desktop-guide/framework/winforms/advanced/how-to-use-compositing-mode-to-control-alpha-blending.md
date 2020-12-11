---
title: 'Procedura: Usare la modalità di composizione per controllare la fusione alfa'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- alpha blending [Windows Forms], compositing
- colors [Windows Forms], blending
- colors [Windows Forms], controlling transparency
ms.assetid: f331df2d-b395-4b0a-95be-24fec8c9bbb5
ms.openlocfilehash: 6863e59efa25323f80933bf8ab595316b430ef53
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963205"
---
# <a name="how-to-use-compositing-mode-to-control-alpha-blending"></a>Procedura: Usare la modalità di composizione per controllare la fusione alfa
A volte può essere necessario creare una bitmap fuori schermo con le caratteristiche seguenti:  
  
- I colori hanno valori alfa minori di 255.  
  
- Quando si crea la bitmap, i colori non vengono combinati con l'alfa.  
  
- Quando si visualizza la bitmap completata, i colori nella bitmap sono alpha blended con i colori di sfondo sul dispositivo di visualizzazione.  
  
 Per creare una bitmap di questo tipo, costruire un <xref:System.Drawing.Bitmap> oggetto vuoto e quindi costruire un <xref:System.Drawing.Graphics> oggetto in base alla bitmap. Impostare la modalità di composizione dell' <xref:System.Drawing.Graphics> oggetto su <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy?displayProperty=nameWithType> .  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene creato un <xref:System.Drawing.Graphics> oggetto in base a un <xref:System.Drawing.Bitmap> oggetto. Il codice usa l' <xref:System.Drawing.Graphics> oggetto insieme a due pennelli semitrasparenti (Alpha = 160) per disegnare sulla bitmap. Il codice riempie un'ellisse rossa e un'ellisse verde usando i pennelli semitrasparenti. L'ellisse verde si sovrappone all'ellisse rossa, ma il verde non viene mescolato con il rosso perché la modalità di composizione dell' <xref:System.Drawing.Graphics> oggetto è impostata su <xref:System.Drawing.Drawing2D.CompositingMode.SourceCopy> .  
  
 Il codice disegna la bitmap sullo schermo due volte: una volta su uno sfondo bianco e una volta su uno sfondo a più colori. I pixel nella bitmap che fanno parte dei due ellissi hanno un componente alfa di 160, quindi i puntini di sospensione vengono combinati con i colori di sfondo sullo schermo.  
  
 La figura seguente mostra l'output dell'esempio di codice. Si noti che i puntini di sospensione vengono combinati con lo sfondo, ma non sono combinati tra loro.  
  
 ![Diagramma che mostra i puntini di sospensione combinati con lo sfondo.](./media/how-to-use-compositing-mode-to-control-alpha-blending/ellipses-blended-background.png)  
  
 L'esempio di codice contiene questa istruzione:  
  
 [!code-csharp[System.Drawing.AlphaBlending#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.AlphaBlending#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#41)]  
  
 Se si desidera che i puntini di sospensione vengano combinati tra loro e con lo sfondo, modificare l'istruzione seguente:  
  
 [!code-csharp[System.Drawing.AlphaBlending#42](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#42)]
 [!code-vb[System.Drawing.AlphaBlending#42](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#42)]  
  
 Nella figura seguente viene illustrato l'output del codice modificato.  
  
 ![Diagramma che mostra le ellissi combinate insieme e con sfondo.](./media/how-to-use-compositing-mode-to-control-alpha-blending/blend-ellipses-background.png)  
  
 [!code-csharp[System.Drawing.AlphaBlending#43](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#43)]
 [!code-vb[System.Drawing.AlphaBlending#43](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#43)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro di <xref:System.Windows.Forms.PaintEventHandler> .  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Color.FromArgb%2A>
- [Linee e riempimenti con fusione alfa](alpha-blending-lines-and-fills.md)
