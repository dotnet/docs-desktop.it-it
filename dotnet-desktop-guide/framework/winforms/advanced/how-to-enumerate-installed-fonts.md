---
title: 'Procedura: Enumerare i tipi di carattere installati'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- fonts [Windows Forms], enumerating installed
- examples [Windows Forms], fonts
ms.assetid: 26d74ef5-0f39-4eeb-8d20-00e66e014abe
ms.openlocfilehash: 92f27399cce9e03a4679c8a34fbdafcf28c32252
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963409"
---
# <a name="how-to-enumerate-installed-fonts"></a>Procedura: Enumerare i tipi di carattere installati
La <xref:System.Drawing.Text.InstalledFontCollection> classe eredita dalla <xref:System.Drawing.Text.FontCollection> classe di base astratta. È possibile utilizzare un <xref:System.Drawing.Text.InstalledFontCollection> oggetto per enumerare i tipi di carattere installati nel computer. La <xref:System.Drawing.Text.FontCollection.Families%2A> proprietà di un <xref:System.Drawing.Text.InstalledFontCollection> oggetto è una matrice di <xref:System.Drawing.FontFamily> oggetti.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono elencati i nomi di tutte le famiglie di caratteri installate nel computer. Il codice recupera la <xref:System.Drawing.FontFamily.Name%2A> proprietà di ogni <xref:System.Drawing.FontFamily> oggetto nella matrice restituita dalla <xref:System.Drawing.Text.FontCollection.Families%2A> Proprietà. Man mano che vengono recuperati, i nomi delle famiglie vengono concatenati per formare un elenco delimitato da virgole. Il <xref:System.Drawing.Graphics.DrawString%2A> metodo della <xref:System.Drawing.Graphics> classe disegna quindi l'elenco delimitato da virgole in un rettangolo.  
  
 Se si esegue il codice di esempio, l'output sarà simile a quello illustrato nella figura seguente:  
  
 ![Screenshot che mostra le famiglie di caratteri installate.](./media/how-to-enumerate-installed-fonts/list-installed-font-families.png)  
  
 [!code-csharp[System.Drawing.FontsAndText#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.FontsAndText#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro di <xref:System.Windows.Forms.PaintEventHandler> . Inoltre, è necessario importare lo <xref:System.Drawing.Text> spazio dei nomi.  
  
## <a name="see-also"></a>Vedere anche

- [Utilizzo di tipi di carattere e testo](using-fonts-and-text.md)
