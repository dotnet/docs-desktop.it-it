---
title: "Procedura: creare un pulsante con un'immagine"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Button controls [WPF], creating
ms.assetid: 607a193c-4098-4dd8-8dc0-51256cec2020
ms.openlocfilehash: 5be928ac75ad727feabcde07ac0c6dc76ed130e6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969481"
---
# <a name="how-to-create-a-button-that-has-an-image"></a><span data-ttu-id="9639b-102">Procedura: creare un pulsante con un'immagine</span><span class="sxs-lookup"><span data-stu-id="9639b-102">How to: Create a Button That Has an Image</span></span>
<span data-ttu-id="9639b-103">Questo esempio illustra come includere un'immagine in un oggetto <xref:System.Windows.Controls.Button> .</span><span class="sxs-lookup"><span data-stu-id="9639b-103">This example shows how to include an image on a <xref:System.Windows.Controls.Button>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9639b-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="9639b-104">Example</span></span>  
 <span data-ttu-id="9639b-105">Nell'esempio seguente vengono creati due <xref:System.Windows.Controls.Button> controlli.</span><span class="sxs-lookup"><span data-stu-id="9639b-105">The following example creates two <xref:System.Windows.Controls.Button> controls.</span></span> <span data-ttu-id="9639b-106">Una <xref:System.Windows.Controls.Button> contiene testo e l'altra contiene un'immagine.</span><span class="sxs-lookup"><span data-stu-id="9639b-106">One <xref:System.Windows.Controls.Button> contains text and the other contains an image.</span></span> <span data-ttu-id="9639b-107">L'immagine si trova in una cartella denominata data, ovvero una sottocartella della cartella del progetto dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="9639b-107">The image is in a folder called data, which is a subfolder of the example’s project folder.</span></span> <span data-ttu-id="9639b-108">Quando un utente fa clic sull'oggetto <xref:System.Windows.Controls.Button> con l'immagine, lo sfondo e il testo dell'altra <xref:System.Windows.Controls.Button> modifica.</span><span class="sxs-lookup"><span data-stu-id="9639b-108">When a user clicks the <xref:System.Windows.Controls.Button> that has the image, the background and the text of the other <xref:System.Windows.Controls.Button> change.</span></span>  
  
 <span data-ttu-id="9639b-109">Questo esempio crea <xref:System.Windows.Controls.Button> controlli usando il markup, ma usa il codice per scrivere i <xref:System.Windows.Controls.Primitives.ButtonBase.Click> gestori eventi.</span><span class="sxs-lookup"><span data-stu-id="9639b-109">This example creates <xref:System.Windows.Controls.Button> controls by using markup but uses code to write the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handlers.</span></span>  
  
 [!code-xaml[BtnColor#4](~/samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml#4)]  
  
 [!code-csharp[BtnColor#6](~/samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml.cs#6)]
 [!code-vb[BtnColor#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BtnColor/VisualBasic/Pane1.xaml.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="9639b-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9639b-110">See also</span></span>

- [<span data-ttu-id="9639b-111">Controlli</span><span class="sxs-lookup"><span data-stu-id="9639b-111">Controls</span></span>](index.md)
- [<span data-ttu-id="9639b-112">Libreria di controlli</span><span class="sxs-lookup"><span data-stu-id="9639b-112">Control Library</span></span>](control-library.md)
