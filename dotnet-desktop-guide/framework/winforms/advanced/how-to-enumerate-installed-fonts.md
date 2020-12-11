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
# <a name="how-to-enumerate-installed-fonts"></a><span data-ttu-id="9ce0a-102">Procedura: Enumerare i tipi di carattere installati</span><span class="sxs-lookup"><span data-stu-id="9ce0a-102">How to: Enumerate Installed Fonts</span></span>
<span data-ttu-id="9ce0a-103">La <xref:System.Drawing.Text.InstalledFontCollection> classe eredita dalla <xref:System.Drawing.Text.FontCollection> classe di base astratta.</span><span class="sxs-lookup"><span data-stu-id="9ce0a-103">The <xref:System.Drawing.Text.InstalledFontCollection> class inherits from the <xref:System.Drawing.Text.FontCollection> abstract base class.</span></span> <span data-ttu-id="9ce0a-104">È possibile utilizzare un <xref:System.Drawing.Text.InstalledFontCollection> oggetto per enumerare i tipi di carattere installati nel computer.</span><span class="sxs-lookup"><span data-stu-id="9ce0a-104">You can use an <xref:System.Drawing.Text.InstalledFontCollection> object to enumerate the fonts installed on the computer.</span></span> <span data-ttu-id="9ce0a-105">La <xref:System.Drawing.Text.FontCollection.Families%2A> proprietà di un <xref:System.Drawing.Text.InstalledFontCollection> oggetto è una matrice di <xref:System.Drawing.FontFamily> oggetti.</span><span class="sxs-lookup"><span data-stu-id="9ce0a-105">The <xref:System.Drawing.Text.FontCollection.Families%2A> property of an <xref:System.Drawing.Text.InstalledFontCollection> object is an array of <xref:System.Drawing.FontFamily> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ce0a-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="9ce0a-106">Example</span></span>  
 <span data-ttu-id="9ce0a-107">Nell'esempio seguente vengono elencati i nomi di tutte le famiglie di caratteri installate nel computer.</span><span class="sxs-lookup"><span data-stu-id="9ce0a-107">The following example lists the names of all the font families installed on the computer.</span></span> <span data-ttu-id="9ce0a-108">Il codice recupera la <xref:System.Drawing.FontFamily.Name%2A> proprietà di ogni <xref:System.Drawing.FontFamily> oggetto nella matrice restituita dalla <xref:System.Drawing.Text.FontCollection.Families%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="9ce0a-108">The code retrieves the <xref:System.Drawing.FontFamily.Name%2A> property of each <xref:System.Drawing.FontFamily> object in the array returned by the <xref:System.Drawing.Text.FontCollection.Families%2A> property.</span></span> <span data-ttu-id="9ce0a-109">Man mano che vengono recuperati, i nomi delle famiglie vengono concatenati per formare un elenco delimitato da virgole.</span><span class="sxs-lookup"><span data-stu-id="9ce0a-109">As the family names are retrieved, they are concatenated to form a comma-separated list.</span></span> <span data-ttu-id="9ce0a-110">Il <xref:System.Drawing.Graphics.DrawString%2A> metodo della <xref:System.Drawing.Graphics> classe disegna quindi l'elenco delimitato da virgole in un rettangolo.</span><span class="sxs-lookup"><span data-stu-id="9ce0a-110">Then the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> class draws the comma-separated list in a rectangle.</span></span>  
  
 <span data-ttu-id="9ce0a-111">Se si esegue il codice di esempio, l'output sarà simile a quello illustrato nella figura seguente:</span><span class="sxs-lookup"><span data-stu-id="9ce0a-111">If you run the example code, the output will be similar to that shown in the following illustration:</span></span>  
  
 ![Screenshot che mostra le famiglie di caratteri installate.](./media/how-to-enumerate-installed-fonts/list-installed-font-families.png)  
  
 [!code-csharp[System.Drawing.FontsAndText#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.FontsAndText#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9ce0a-113">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="9ce0a-113">Compiling the Code</span></span>  
 <span data-ttu-id="9ce0a-114">L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro di <xref:System.Windows.Forms.PaintEventHandler> .</span><span class="sxs-lookup"><span data-stu-id="9ce0a-114">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span> <span data-ttu-id="9ce0a-115">Inoltre, è necessario importare lo <xref:System.Drawing.Text> spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="9ce0a-115">In addition, you should import the <xref:System.Drawing.Text> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ce0a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ce0a-116">See also</span></span>

- [<span data-ttu-id="9ce0a-117">Utilizzo di tipi di carattere e testo</span><span class="sxs-lookup"><span data-stu-id="9ce0a-117">Using Fonts and Text</span></span>](using-fonts-and-text.md)
