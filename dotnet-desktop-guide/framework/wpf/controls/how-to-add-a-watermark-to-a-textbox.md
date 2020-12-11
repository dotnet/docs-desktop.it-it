---
title: 'Procedura: aggiungere una filigrana a un oggetto TextBox'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- displaying a background image inside a text box to aid user input [WPF]
- aid usability of a TextBox using a background image [WPF]
ms.assetid: df89bdd8-a0fb-45e0-b312-dd53332d01a8
ms.openlocfilehash: abe276c686d394ded13ec03f08deae65e4098d03
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966205"
---
# <a name="how-to-add-a-watermark-to-a-textbox"></a>Procedura: aggiungere una filigrana a un oggetto TextBox
Nell'esempio seguente viene illustrato come facilitare l'usabilità di un oggetto <xref:System.Windows.Controls.TextBox> visualizzando un'immagine di sfondo esplicativa all'interno di <xref:System.Windows.Controls.TextBox> fino a quando l'utente non immette testo, a quel punto l'immagine viene rimossa. Inoltre, l'immagine di sfondo viene ripristinata di nuovo se l'utente rimuove il proprio input. Vedere la figura seguente.  
  
 ![TextBox con immagine di sfondo](./media/editing-textbox-using-background-image.png "Editing_TextBox_using_background_image")  
  
> [!NOTE]
> Il motivo per cui un'immagine di sfondo viene utilizzata in questo esempio invece di modificare semplicemente la <xref:System.Windows.Controls.TextBox.Text%2A> proprietà di <xref:System.Windows.Controls.TextBox> , è che un'immagine di sfondo non interferisce con data binding.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[TextBoxMiscSnippets_snip#TextBoxBackgroundExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml#textboxbackgroundexamplewholepage)]  
  
 [!code-csharp[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml.cs#textboxbackgroundcodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/textbox_with_background_image.xaml.vb#textboxbackgroundcodeexamplewholepage)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sulla classe TextBox](textbox-overview.md)
- [Cenni generali sul controllo RichTextBox](richtextbox-overview.md)
