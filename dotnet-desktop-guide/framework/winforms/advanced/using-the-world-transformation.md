---
title: Utilizzo della trasformazione di tipo World
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], world transformation
- world transformation [Windows Forms], examples
ms.assetid: 1e717711-1361-448e-aa49-0f3ec43110c9
ms.openlocfilehash: f40d7e8cb814344365e8b88c2659751903b79d77
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962380"
---
# <a name="using-the-world-transformation"></a><span data-ttu-id="69b68-102">Utilizzo della trasformazione di tipo World</span><span class="sxs-lookup"><span data-stu-id="69b68-102">Using the World Transformation</span></span>
<span data-ttu-id="69b68-103">La trasformazione globale è una proprietà della <xref:System.Drawing.Graphics> classe.</span><span class="sxs-lookup"><span data-stu-id="69b68-103">The world transformation is a property of the <xref:System.Drawing.Graphics> class.</span></span> <span data-ttu-id="69b68-104">I numeri che specificano la trasformazione globale vengono archiviati in un <xref:System.Drawing.Drawing2D.Matrix> oggetto, che rappresenta una matrice 3 × 3.</span><span class="sxs-lookup"><span data-stu-id="69b68-104">The numbers that specify the world transformation are stored in a <xref:System.Drawing.Drawing2D.Matrix> object, which represents a 3×3 matrix.</span></span> <span data-ttu-id="69b68-105">Le <xref:System.Drawing.Drawing2D.Matrix> <xref:System.Drawing.Graphics> classi e hanno diversi metodi per impostare i numeri nella matrice di trasformazione mondiale.</span><span class="sxs-lookup"><span data-stu-id="69b68-105">The <xref:System.Drawing.Drawing2D.Matrix> and <xref:System.Drawing.Graphics> classes have several methods for setting the numbers in the world transformation matrix.</span></span>  
  
## <a name="different-types-of-transformations"></a><span data-ttu-id="69b68-106">Tipi diversi di trasformazioni</span><span class="sxs-lookup"><span data-stu-id="69b68-106">Different Types of Transformations</span></span>  
 <span data-ttu-id="69b68-107">Nell'esempio seguente, il codice crea prima un rettangolo 50 × 50 e lo individua all'origine (0,0).</span><span class="sxs-lookup"><span data-stu-id="69b68-107">In the following example, the code first creates a 50×50 rectangle and locates it at the origin (0, 0).</span></span> <span data-ttu-id="69b68-108">L'origine si trova nell'angolo superiore sinistro dell'area client.</span><span class="sxs-lookup"><span data-stu-id="69b68-108">The origin is at the upper-left corner of the client area.</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#11](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.MiscLegacyTopics#11](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#11)]  
  
 <span data-ttu-id="69b68-109">Il codice seguente applica una trasformazione di ridimensionamento che espande il rettangolo per un fattore di 1,75 nella direzione x e compatta il rettangolo per un fattore di 0,5 nella direzione y:</span><span class="sxs-lookup"><span data-stu-id="69b68-109">The following code applies a scaling transformation that expands the rectangle by a factor of 1.75 in the x direction and shrinks the rectangle by a factor of 0.5 in the y direction:</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#12](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#12)]
 [!code-vb[System.Drawing.MiscLegacyTopics#12](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#12)]  
  
 <span data-ttu-id="69b68-110">Il risultato è un rettangolo più lungo nella direzione x e più breve nella direzione y rispetto all'originale.</span><span class="sxs-lookup"><span data-stu-id="69b68-110">The result is a rectangle that is longer in the x direction and shorter in the y direction than the original.</span></span>  
  
 <span data-ttu-id="69b68-111">Per ruotare il rettangolo anziché ridimensionarlo, usare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="69b68-111">To rotate the rectangle instead of scaling it, use the following code:</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#13](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#13)]
 [!code-vb[System.Drawing.MiscLegacyTopics#13](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#13)]  
  
 <span data-ttu-id="69b68-112">Per tradurre il rettangolo, usare il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="69b68-112">To translate the rectangle, use the following code:</span></span>  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#14](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#14)]
 [!code-vb[System.Drawing.MiscLegacyTopics#14](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#14)]  
  
## <a name="see-also"></a><span data-ttu-id="69b68-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="69b68-113">See also</span></span>

- <xref:System.Drawing.Drawing2D.Matrix>
- [<span data-ttu-id="69b68-114">Sistemi di coordinate e trasformazioni</span><span class="sxs-lookup"><span data-stu-id="69b68-114">Coordinate Systems and Transformations</span></span>](coordinate-systems-and-transformations.md)
- [<span data-ttu-id="69b68-115">Utilizzo di trasformazioni nel codice gestito GDI+</span><span class="sxs-lookup"><span data-stu-id="69b68-115">Using Transformations in Managed GDI+</span></span>](using-transformations-in-managed-gdi.md)
