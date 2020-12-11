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
# <a name="how-to-add-a-watermark-to-a-textbox"></a><span data-ttu-id="e692b-102">Procedura: aggiungere una filigrana a un oggetto TextBox</span><span class="sxs-lookup"><span data-stu-id="e692b-102">How to: Add a Watermark to a TextBox</span></span>
<span data-ttu-id="e692b-103">Nell'esempio seguente viene illustrato come facilitare l'usabilità di un oggetto <xref:System.Windows.Controls.TextBox> visualizzando un'immagine di sfondo esplicativa all'interno di <xref:System.Windows.Controls.TextBox> fino a quando l'utente non immette testo, a quel punto l'immagine viene rimossa.</span><span class="sxs-lookup"><span data-stu-id="e692b-103">The following example shows how to aid usability of a <xref:System.Windows.Controls.TextBox> by displaying an explanatory background image inside of the <xref:System.Windows.Controls.TextBox> until the user inputs text, at which point the image is removed.</span></span> <span data-ttu-id="e692b-104">Inoltre, l'immagine di sfondo viene ripristinata di nuovo se l'utente rimuove il proprio input.</span><span class="sxs-lookup"><span data-stu-id="e692b-104">In addition, the background image is restored again if the user removes their input.</span></span> <span data-ttu-id="e692b-105">Vedere la figura seguente.</span><span class="sxs-lookup"><span data-stu-id="e692b-105">See illustration below.</span></span>  
  
 <span data-ttu-id="e692b-106">![TextBox con immagine di sfondo](./media/editing-textbox-using-background-image.png "Editing_TextBox_using_background_image")</span><span class="sxs-lookup"><span data-stu-id="e692b-106">![A TextBox with a background image](./media/editing-textbox-using-background-image.png "Editing_TextBox_using_background_image")</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e692b-107">Il motivo per cui un'immagine di sfondo viene utilizzata in questo esempio invece di modificare semplicemente la <xref:System.Windows.Controls.TextBox.Text%2A> proprietà di <xref:System.Windows.Controls.TextBox> , è che un'immagine di sfondo non interferisce con data binding.</span><span class="sxs-lookup"><span data-stu-id="e692b-107">The reason a background image is used in this example rather then simply manipulating the <xref:System.Windows.Controls.TextBox.Text%2A> property of <xref:System.Windows.Controls.TextBox>, is that a background image will not interfere with data binding.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e692b-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="e692b-108">Example</span></span>  
 [!code-xaml[TextBoxMiscSnippets_snip#TextBoxBackgroundExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml#textboxbackgroundexamplewholepage)]  
  
 [!code-csharp[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/csharp/textbox_with_background_image.xaml.cs#textboxbackgroundcodeexamplewholepage)]
 [!code-vb[TextBoxMiscSnippets_snip#TextBoxBackgroundCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextBoxMiscSnippets_snip/visualbasic/textbox_with_background_image.xaml.vb#textboxbackgroundcodeexamplewholepage)]  
  
## <a name="see-also"></a><span data-ttu-id="e692b-109">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e692b-109">See also</span></span>

- [<span data-ttu-id="e692b-110">Cenni preliminari sulla classe TextBox</span><span class="sxs-lookup"><span data-stu-id="e692b-110">TextBox Overview</span></span>](textbox-overview.md)
- [<span data-ttu-id="e692b-111">Cenni generali sul controllo RichTextBox</span><span class="sxs-lookup"><span data-stu-id="e692b-111">RichTextBox Overview</span></span>](richtextbox-overview.md)
