---
title: 'Procedura: Usare una matrice di colori per trasformare un singolo colore'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image colors [Windows Forms], transforming
- color matrices [Windows Forms], using
ms.assetid: 44df4556-a433-49c0-ac0f-9a12063a5860
ms.openlocfilehash: 2df74e022b842f7e5c9ff80f6aeddfce51af5eab
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963247"
---
# <a name="how-to-use-a-color-matrix-to-transform-a-single-color"></a><span data-ttu-id="f5bfe-102">Procedura: Usare una matrice di colori per trasformare un singolo colore</span><span class="sxs-lookup"><span data-stu-id="f5bfe-102">How to: Use a Color Matrix to Transform a Single Color</span></span>
<span data-ttu-id="f5bfe-103">GDI+ fornisce le <xref:System.Drawing.Image> <xref:System.Drawing.Bitmap> classi e per l'archiviazione e la manipolazione delle immagini.</span><span class="sxs-lookup"><span data-stu-id="f5bfe-103">GDI+ provides the <xref:System.Drawing.Image> and <xref:System.Drawing.Bitmap> classes for storing and manipulating images.</span></span> <span data-ttu-id="f5bfe-104"><xref:System.Drawing.Image><xref:System.Drawing.Bitmap>gli oggetti e archiviano il colore di ogni pixel come numero a 32 bit: 8 bit per colore rosso, verde, blu e alfa.</span><span class="sxs-lookup"><span data-stu-id="f5bfe-104"><xref:System.Drawing.Image> and <xref:System.Drawing.Bitmap> objects store the color of each pixel as a 32-bit number: 8 bits each for red, green, blue, and alpha.</span></span> <span data-ttu-id="f5bfe-105">Ognuno dei quattro componenti è un numero compreso tra 0 e 255, 0 che rappresenta nessuna intensità e 255 che rappresenta l'intensità completa.</span><span class="sxs-lookup"><span data-stu-id="f5bfe-105">Each of the four components is a number from 0 through 255, with 0 representing no intensity and 255 representing full intensity.</span></span> <span data-ttu-id="f5bfe-106">Il componente alfa specifica la trasparenza del colore: 0 è completamente trasparente e 255 è completamente opaco.</span><span class="sxs-lookup"><span data-stu-id="f5bfe-106">The alpha component specifies the transparency of the color: 0 is fully transparent, and 255 is fully opaque.</span></span>  
  
 <span data-ttu-id="f5bfe-107">Un vettore di colore è una tupla con 4 elementi del form (rosso, verde, blu, alfa).</span><span class="sxs-lookup"><span data-stu-id="f5bfe-107">A color vector is a 4-tuple of the form (red, green, blue, alpha).</span></span> <span data-ttu-id="f5bfe-108">Ad esempio, il vettore di colore (0, 255, 0, 255) rappresenta un colore opaco che non ha rosso o blu, ma ha un verde a intensità piena.</span><span class="sxs-lookup"><span data-stu-id="f5bfe-108">For example, the color vector (0, 255, 0, 255) represents an opaque color that has no red or blue, but has green at full intensity.</span></span>  
  
 <span data-ttu-id="f5bfe-109">Un'altra convenzione per la rappresentazione dei colori usa il numero 1 per l'intensità piena.</span><span class="sxs-lookup"><span data-stu-id="f5bfe-109">Another convention for representing colors uses the number 1 for full intensity.</span></span> <span data-ttu-id="f5bfe-110">Usando tale convenzione, il colore descritto nel paragrafo precedente verrebbe rappresentato dal vettore (0, 1, 0, 1).</span><span class="sxs-lookup"><span data-stu-id="f5bfe-110">Using that convention, the color described in the preceding paragraph would be represented by the vector (0, 1, 0, 1).</span></span> <span data-ttu-id="f5bfe-111">GDI+ utilizza la convenzione di 1 come intensità completa durante le trasformazioni dei colori.</span><span class="sxs-lookup"><span data-stu-id="f5bfe-111">GDI+ uses the convention of 1 as full intensity when it performs color transformations.</span></span>  
  
 <span data-ttu-id="f5bfe-112">È possibile applicare trasformazioni lineari (rotazione, ridimensionamento e così via) ai vettori colori moltiplicando i vettori di colore per una matrice 4 × 4.</span><span class="sxs-lookup"><span data-stu-id="f5bfe-112">You can apply linear transformations (rotation, scaling, and the like) to color vectors by multiplying the color vectors by a 4×4 matrix.</span></span> <span data-ttu-id="f5bfe-113">Tuttavia, non è possibile utilizzare una matrice 4 × 4 per eseguire una conversione (non lineare).</span><span class="sxs-lookup"><span data-stu-id="f5bfe-113">However, you cannot use a 4×4 matrix to perform a translation (nonlinear).</span></span> <span data-ttu-id="f5bfe-114">Se si aggiunge una quinta coordinata fittizia, ad esempio il numero 1, a ogni vettore di colore, è possibile utilizzare una matrice di 5 × 5 per applicare qualsiasi combinazione di trasformazioni e traduzioni lineari.</span><span class="sxs-lookup"><span data-stu-id="f5bfe-114">If you add a dummy fifth coordinate (for example, the number 1) to each of the color vectors, you can use a 5×5 matrix to apply any combination of linear transformations and translations.</span></span> <span data-ttu-id="f5bfe-115">Una trasformazione costituita da una trasformazione lineare seguita da una traduzione è detta trasformazione affine.</span><span class="sxs-lookup"><span data-stu-id="f5bfe-115">A transformation consisting of a linear transformation followed by a translation is called an affine transformation.</span></span>  
  
 <span data-ttu-id="f5bfe-116">Si supponga, ad esempio, di voler iniziare con il colore (0,2, 0,0, 0,4, 1,0) e applicare le trasformazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f5bfe-116">For example, suppose you want to start with the color (0.2, 0.0, 0.4, 1.0) and apply the following transformations:</span></span>  
  
1. <span data-ttu-id="f5bfe-117">Raddoppiare il componente rosso</span><span class="sxs-lookup"><span data-stu-id="f5bfe-117">Double the red component</span></span>  
  
2. <span data-ttu-id="f5bfe-118">Aggiungere 0,2 ai componenti rosso, verde e blu</span><span class="sxs-lookup"><span data-stu-id="f5bfe-118">Add 0.2 to the red, green, and blue components</span></span>  
  
 <span data-ttu-id="f5bfe-119">La moltiplicazione di matrici seguente eseguirà la coppia di trasformazioni nell'ordine elencato.</span><span class="sxs-lookup"><span data-stu-id="f5bfe-119">The following matrix multiplication will perform the pair of transformations in the order listed.</span></span>  
  
 ![Screenshot di una matrice di moltiplicazione della trasformazione.](./media/how-to-use-a-color-matrix-to-transform-a-single-color/multiplication-color-matrix.gif)
  
 <span data-ttu-id="f5bfe-121">Gli elementi di una matrice di colori sono indicizzati (in base zero) per riga e quindi colonna.</span><span class="sxs-lookup"><span data-stu-id="f5bfe-121">The elements of a color matrix are indexed (zero-based) by row and then column.</span></span> <span data-ttu-id="f5bfe-122">La voce della quinta riga e della terza colonna della matrice M, ad esempio, è indicata da M [4] [2].</span><span class="sxs-lookup"><span data-stu-id="f5bfe-122">For example, the entry in the fifth row and third column of matrix M is denoted by M[4][2].</span></span>  
  
 <span data-ttu-id="f5bfe-123">La matrice di identità 5 × 5 (mostrata nella figura seguente) presenta 1S sulla diagonale e sugli zeri in qualsiasi altra posizione.</span><span class="sxs-lookup"><span data-stu-id="f5bfe-123">The 5×5 identity matrix (shown in the following illustration) has 1s on the diagonal and 0s everywhere else.</span></span> <span data-ttu-id="f5bfe-124">Se si moltiplica un vettore di colore per la matrice di identità, il vettore di colore non cambia.</span><span class="sxs-lookup"><span data-stu-id="f5bfe-124">If you multiply a color vector by the identity matrix, the color vector does not change.</span></span> <span data-ttu-id="f5bfe-125">Un modo pratico per formare la matrice di una trasformazione colore consiste nell'iniziare con la matrice di identità e apportare una piccola modifica che produce la trasformazione desiderata.</span><span class="sxs-lookup"><span data-stu-id="f5bfe-125">A convenient way to form the matrix of a color transformation is to start with the identity matrix and make a small change that produces the desired transformation.</span></span>  
  
 ![Screenshot di una matrice di identità 5x5 per la trasformazione dei colori.](./media/how-to-use-a-color-matrix-to-transform-a-single-color/5x5-identity-matrix-color-transformation.gif)  
  
 <span data-ttu-id="f5bfe-127">Per una descrizione più dettagliata delle matrici e delle trasformazioni, vedere [sistemi di coordinate e trasformazioni](coordinate-systems-and-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="f5bfe-127">For a more detailed discussion of matrices and transformations, see [Coordinate Systems and Transformations](coordinate-systems-and-transformations.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5bfe-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="f5bfe-128">Example</span></span>  
 <span data-ttu-id="f5bfe-129">Nell'esempio seguente viene accettata un'immagine che corrisponde a un solo colore (0,2, 0,0, 0,4, 1,0) e viene applicata la trasformazione descritta nei paragrafi precedenti.</span><span class="sxs-lookup"><span data-stu-id="f5bfe-129">The following example takes an image that is all one color (0.2, 0.0, 0.4, 1.0) and applies the transformation described in the preceding paragraphs.</span></span>  
  
 <span data-ttu-id="f5bfe-130">Nell'illustrazione seguente viene mostrata l'immagine originale a sinistra e l'immagine trasformata a destra.</span><span class="sxs-lookup"><span data-stu-id="f5bfe-130">The following illustration shows the original image on the left and the transformed image on the right.</span></span>  
  
 ![Quadrato viola a sinistra e un quadrato fucsia a destra.](./media/how-to-use-a-color-matrix-to-transform-a-single-color/color-transformation.png)  
  
 <span data-ttu-id="f5bfe-132">Il codice nell'esempio seguente usa i passaggi seguenti per eseguire il ricoloring:</span><span class="sxs-lookup"><span data-stu-id="f5bfe-132">The code in the following example uses the following steps to perform the recoloring:</span></span>  
  
1. <span data-ttu-id="f5bfe-133">Inizializzare un <xref:System.Drawing.Imaging.ColorMatrix> oggetto.</span><span class="sxs-lookup"><span data-stu-id="f5bfe-133">Initialize a <xref:System.Drawing.Imaging.ColorMatrix> object.</span></span>  
  
2. <span data-ttu-id="f5bfe-134">Creare un <xref:System.Drawing.Imaging.ImageAttributes> oggetto e passare l' <xref:System.Drawing.Imaging.ColorMatrix> oggetto al <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> metodo dell' <xref:System.Drawing.Imaging.ImageAttributes> oggetto.</span><span class="sxs-lookup"><span data-stu-id="f5bfe-134">Create an <xref:System.Drawing.Imaging.ImageAttributes> object and pass the <xref:System.Drawing.Imaging.ColorMatrix> object to the <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> method of the <xref:System.Drawing.Imaging.ImageAttributes> object.</span></span>  
  
3. <span data-ttu-id="f5bfe-135">Passare l' <xref:System.Drawing.Imaging.ImageAttributes> oggetto al <xref:System.Drawing.Graphics.DrawImage%2A> metodo di un <xref:System.Drawing.Graphics> oggetto.</span><span class="sxs-lookup"><span data-stu-id="f5bfe-135">Pass the <xref:System.Drawing.Imaging.ImageAttributes> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
 [!code-csharp[System.Drawing.RecoloringImages#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.RecoloringImages/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.RecoloringImages#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.RecoloringImages/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f5bfe-136">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="f5bfe-136">Compiling the Code</span></span>  
 <span data-ttu-id="f5bfe-137">L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro del <xref:System.Windows.Forms.Control.Paint> gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="f5bfe-137">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5bfe-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5bfe-138">See also</span></span>

- [<span data-ttu-id="f5bfe-139">Ricolorazione di immagini</span><span class="sxs-lookup"><span data-stu-id="f5bfe-139">Recoloring Images</span></span>](recoloring-images.md)
- [<span data-ttu-id="f5bfe-140">Sistemi di coordinate e trasformazioni</span><span class="sxs-lookup"><span data-stu-id="f5bfe-140">Coordinate Systems and Transformations</span></span>](coordinate-systems-and-transformations.md)
