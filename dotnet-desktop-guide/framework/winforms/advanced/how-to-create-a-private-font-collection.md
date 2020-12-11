---
title: 'Procedura: Creare una raccolta di tipi di carattere privata'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- private font collections [Windows Forms], creating
- fonts [Windows Forms], creating private collections
ms.assetid: 6533d5e5-a8dc-4b76-9fc4-3bf75c8b9212
ms.openlocfilehash: 0bb7293a5423004a13cf98b79bba0a6c411a7c97
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952146"
---
# <a name="how-to-create-a-private-font-collection"></a>Procedura: Creare una raccolta di tipi di carattere privata
La <xref:System.Drawing.Text.PrivateFontCollection> classe eredita dalla <xref:System.Drawing.Text.FontCollection> classe di base astratta. È possibile utilizzare un <xref:System.Drawing.Text.PrivateFontCollection> oggetto per mantenere un set di tipi di carattere specifici per l'applicazione. Una raccolta di tipi di carattere privata può includere i tipi di carattere del sistema installato e i tipi di carattere che non sono stati installati nel computer. Per aggiungere un file del tipo di carattere a una raccolta di tipi di carattere privata, chiamare il <xref:System.Drawing.Text.PrivateFontCollection.AddFontFile%2A> metodo di un <xref:System.Drawing.Text.PrivateFontCollection> oggetto.  
  
 La <xref:System.Drawing.Text.FontCollection.Families%2A> proprietà di un <xref:System.Drawing.Text.PrivateFontCollection> oggetto contiene una matrice di <xref:System.Drawing.FontFamily> oggetti.  
  
 Il numero di famiglie di caratteri in una raccolta di tipi di carattere privata non è necessariamente uguale al numero di file del tipo di carattere aggiunti alla raccolta. Si supponga, ad esempio, di aggiungere i file ArialBd. TFF, Times. tff e TimesBd. TFF a una raccolta. Saranno presenti tre file, ma solo due famiglie della raccolta, poiché Times. tff e TimesBd. tff appartengono alla stessa famiglia.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente vengono aggiunti i tre file dei tipi di carattere seguenti a un <xref:System.Drawing.Text.PrivateFontCollection> oggetto:  
  
- C: \\ *systemroot*\Fonts\Arial.tff (Arial, Regular)  
  
- C: \\ *systemroot*\Fonts\CourBI.tff (Courier New, Bold Italic)  
  
- C: \\ *systemroot*\Fonts\TimesBd.tff (Times New Roman, Bold)  
  
 Il codice recupera una matrice di <xref:System.Drawing.FontFamily> oggetti dalla <xref:System.Drawing.Text.FontCollection.Families%2A> proprietà dell' <xref:System.Drawing.Text.PrivateFontCollection> oggetto.  
  
 Per ogni <xref:System.Drawing.FontFamily> oggetto della raccolta, il codice chiama il <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> metodo per determinare se sono disponibili diversi stili (Regular, Bold, Italic, Bold Italic, Underline e Strike). Gli argomenti passati al <xref:System.Drawing.FontFamily.IsStyleAvailable%2A> metodo sono membri dell' <xref:System.Drawing.FontStyle> enumerazione.  
  
 Se una determinata combinazione di gruppo/stile è disponibile, un <xref:System.Drawing.Font> oggetto viene costruito usando tale famiglia e stile. Il primo argomento passato al <xref:System.Drawing.Font.%23ctor%2A> costruttore è il nome della famiglia di caratteri (non un <xref:System.Drawing.FontFamily> oggetto come avviene per altre varianti del <xref:System.Drawing.Font.%23ctor%2A> costruttore). Dopo che l' <xref:System.Drawing.Font> oggetto è stato costruito, viene passato al <xref:System.Drawing.Graphics.DrawString%2A> metodo della <xref:System.Drawing.Graphics> classe per visualizzare il nome della famiglia insieme al nome dello stile.  
  
 L'output del codice seguente è simile all'output illustrato nella figura seguente:  
  
 ![Screenshot che mostra il testo in vari tipi di carattere.](./media/how-to-create-a-private-font-collection/various-fonts-text-output.png)  
  
 Arial. TFF, che è stato aggiunto alla raccolta di tipi di carattere privati nell'esempio di codice seguente, è il file del tipo di carattere per lo stile normale Arial. Si noti, tuttavia, che l'output del programma mostra diversi stili disponibili diversi da Regular per la famiglia di caratteri Arial. Ciò è dovuto al fatto che GDI+ è in grado di simulare gli stili in grassetto, corsivo e corsivo in grassetto dallo stile normale. GDI+ può inoltre produrre sottolineature e strikeouts dallo stile normale.  
  
 Analogamente, GDI+ è in grado di simulare lo stile corsivo grassetto dallo stile grassetto o corsivo. L'output del programma mostra che lo stile corsivo in grassetto è disponibile per la famiglia Times anche se TimesBd. tff (Times New Roman, Bold) è l'unico file di volte nella raccolta.  
  
 [!code-csharp[System.Drawing.FontsAndText#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#51)]
 [!code-vb[System.Drawing.FontsAndText#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#51)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro di <xref:System.Windows.Forms.PaintEventHandler> .  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Drawing.Text.PrivateFontCollection>
- [Utilizzo di tipi di carattere e testo](using-fonts-and-text.md)
