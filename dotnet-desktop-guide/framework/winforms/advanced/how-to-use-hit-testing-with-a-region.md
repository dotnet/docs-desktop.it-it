---
title: "Procedura: Eseguire l'hit testing usando una regione"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [Windows Forms], using regions
- regions [Windows Forms], hit testing
ms.assetid: 3a4c07cb-a40a-4d14-ad35-008f531910a8
ms.openlocfilehash: 136f15f1364fb2aed791b4a61d0f11411b055967
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962446"
---
# <a name="how-to-use-hit-testing-with-a-region"></a><span data-ttu-id="a52e7-102">Procedura: Eseguire l'hit testing usando una regione</span><span class="sxs-lookup"><span data-stu-id="a52e7-102">How to: Use Hit Testing with a Region</span></span>
<span data-ttu-id="a52e7-103">Lo scopo dell'hit testing è determinare se il cursore si trova su un determinato oggetto, ad esempio un'icona o un pulsante.</span><span class="sxs-lookup"><span data-stu-id="a52e7-103">The purpose of hit testing is to determine whether the cursor is over a given object, such as an icon or a button.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a52e7-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="a52e7-104">Example</span></span>  
 <span data-ttu-id="a52e7-105">Nell'esempio seguente viene creata un'area con più forme formando l'Unione di due aree rettangolari.</span><span class="sxs-lookup"><span data-stu-id="a52e7-105">The following example creates a plus-shaped region by forming the union of two rectangular regions.</span></span> <span data-ttu-id="a52e7-106">Si supponga che la variabile `point` contenga il percorso del clic più recente.</span><span class="sxs-lookup"><span data-stu-id="a52e7-106">Assume that the variable `point` holds the location of the most recent click.</span></span> <span data-ttu-id="a52e7-107">Il codice verifica se `point` è nell'area a forma di più.</span><span class="sxs-lookup"><span data-stu-id="a52e7-107">The code checks to see whether `point` is in the plus-shaped region.</span></span> <span data-ttu-id="a52e7-108">Se il punto si trova nell'area (un hit), l'area viene riempita con un pennello rosso opaco.</span><span class="sxs-lookup"><span data-stu-id="a52e7-108">If the point is in the region (a hit), the region is filled with an opaque red brush.</span></span> <span data-ttu-id="a52e7-109">In caso contrario, l'area viene riempita con un pennello rosso semitrasparente.</span><span class="sxs-lookup"><span data-stu-id="a52e7-109">Otherwise, the region is filled with a semitransparent red brush.</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.MiscLegacyTopics#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a52e7-110">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="a52e7-110">Compiling the Code</span></span>  
 <span data-ttu-id="a52e7-111">L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro di <xref:System.Windows.Forms.PaintEventHandler> .</span><span class="sxs-lookup"><span data-stu-id="a52e7-111">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a52e7-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a52e7-112">See also</span></span>

- <xref:System.Drawing.Region>
- [<span data-ttu-id="a52e7-113">Regioni in GDI+</span><span class="sxs-lookup"><span data-stu-id="a52e7-113">Regions in GDI+</span></span>](regions-in-gdi.md)
- [<span data-ttu-id="a52e7-114">Procedura: Usare il ritaglio per definire una regione</span><span class="sxs-lookup"><span data-stu-id="a52e7-114">How to: Use Clipping with a Region</span></span>](how-to-use-clipping-with-a-region.md)
