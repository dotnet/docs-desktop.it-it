---
title: 'Procedura: Usare una matrice di colori per impostare i valori alfa nelle immagini'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], using color matrices for semi-transparent
- transparency [Windows Forms], color matrices
- matrices [Windows Forms], alpha values
- bitmaps [Windows Forms], using color matrices for semi-transparent
ms.assetid: a27121e6-f7e9-4c09-84e2-f05aa9d2a1bb
ms.openlocfilehash: 73e820845d040856a0ae367da8b9371ad6afa142
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962467"
---
# <a name="how-to-use-a-color-matrix-to-set-alpha-values-in-images"></a><span data-ttu-id="775b8-102">Procedura: Usare una matrice di colori per impostare i valori alfa nelle immagini</span><span class="sxs-lookup"><span data-stu-id="775b8-102">How to: Use a Color Matrix to Set Alpha Values in Images</span></span>
<span data-ttu-id="775b8-103">La <xref:System.Drawing.Bitmap> classe, che eredita dalla <xref:System.Drawing.Image> classe, e la <xref:System.Drawing.Imaging.ImageAttributes> classe forniscono funzionalità per ottenere e impostare i valori dei pixel.</span><span class="sxs-lookup"><span data-stu-id="775b8-103">The <xref:System.Drawing.Bitmap> class (which inherits from the <xref:System.Drawing.Image> class) and the <xref:System.Drawing.Imaging.ImageAttributes> class provide functionality for getting and setting pixel values.</span></span> <span data-ttu-id="775b8-104">È possibile utilizzare la <xref:System.Drawing.Imaging.ImageAttributes> classe per modificare i valori alfa per un'intera immagine oppure è possibile chiamare il <xref:System.Drawing.Bitmap.SetPixel%2A> metodo della <xref:System.Drawing.Bitmap> classe per modificare i singoli valori dei pixel.</span><span class="sxs-lookup"><span data-stu-id="775b8-104">You can use the <xref:System.Drawing.Imaging.ImageAttributes> class to modify the alpha values for an entire image, or you can call the <xref:System.Drawing.Bitmap.SetPixel%2A> method of the <xref:System.Drawing.Bitmap> class to modify individual pixel values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="775b8-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="775b8-105">Example</span></span>  
 <span data-ttu-id="775b8-106">La <xref:System.Drawing.Imaging.ImageAttributes> classe dispone di molte proprietà che è possibile utilizzare per modificare le immagini durante il rendering.</span><span class="sxs-lookup"><span data-stu-id="775b8-106">The <xref:System.Drawing.Imaging.ImageAttributes> class has many properties that you can use to modify images during rendering.</span></span> <span data-ttu-id="775b8-107">Nell'esempio seguente <xref:System.Drawing.Imaging.ImageAttributes> viene usato un oggetto per impostare tutti i valori alfa sul 80% di ciò che era.</span><span class="sxs-lookup"><span data-stu-id="775b8-107">In the following example, an <xref:System.Drawing.Imaging.ImageAttributes> object is used to set all the alpha values to 80 percent of what they were.</span></span> <span data-ttu-id="775b8-108">Questa operazione viene eseguita inizializzando una matrice di colori e impostando il valore di scalabilità alfa nella matrice su 0,8.</span><span class="sxs-lookup"><span data-stu-id="775b8-108">This is done by initializing a color matrix and setting the alpha scaling value in the matrix to 0.8.</span></span> <span data-ttu-id="775b8-109">L'indirizzo della matrice di colori viene passato al <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> metodo dell' <xref:System.Drawing.Imaging.ImageAttributes> oggetto e l' <xref:System.Drawing.Imaging.ImageAttributes> oggetto viene passato al <xref:System.Drawing.Graphics.DrawString%2A> metodo dell' <xref:System.Drawing.Graphics> oggetto.</span><span class="sxs-lookup"><span data-stu-id="775b8-109">The address of the color matrix is passed to the <xref:System.Drawing.Imaging.ImageAttributes.SetColorMatrix%2A> method of the <xref:System.Drawing.Imaging.ImageAttributes> object, and the <xref:System.Drawing.Imaging.ImageAttributes> object is passed to the <xref:System.Drawing.Graphics.DrawString%2A> method of the <xref:System.Drawing.Graphics> object.</span></span>  
  
 <span data-ttu-id="775b8-110">Durante il rendering, i valori alfa nella bitmap vengono convertiti nel 80% di ciò che erano.</span><span class="sxs-lookup"><span data-stu-id="775b8-110">During rendering, the alpha values in the bitmap are converted to 80 percent of what they were.</span></span> <span data-ttu-id="775b8-111">In questo modo si ottiene un'immagine che viene fusa con lo sfondo.</span><span class="sxs-lookup"><span data-stu-id="775b8-111">This results in an image that is blended with the background.</span></span> <span data-ttu-id="775b8-112">Come illustrato nella figura seguente, l'immagine bitmap sembra trasparente; è possibile visualizzare la linea nera a tinta unita.</span><span class="sxs-lookup"><span data-stu-id="775b8-112">As the following illustration shows, the bitmap image looks transparent; you can see the solid black line through it.</span></span>  
  
 <span data-ttu-id="775b8-113">![Screenshot della fusione alfa con una matrice.](./media/how-to-use-a-color-matrix-to-set-alpha-values-in-images/alpha-blending-matrix.png "Immagine2")</span><span class="sxs-lookup"><span data-stu-id="775b8-113">![Screenshot of alpha blending using a matrix.](./media/how-to-use-a-color-matrix-to-set-alpha-values-in-images/alpha-blending-matrix.png "image2")</span></span>  
  
 <span data-ttu-id="775b8-114">Quando l'immagine è sulla parte bianca dello sfondo, l'immagine è stata mescolata con il colore bianco.</span><span class="sxs-lookup"><span data-stu-id="775b8-114">Where the image is over the white portion of the background, the image has been blended with the color white.</span></span> <span data-ttu-id="775b8-115">Quando l'immagine incrocia la linea nera, l'immagine viene fusa con il colore nero.</span><span class="sxs-lookup"><span data-stu-id="775b8-115">Where the image crosses the black line, the image is blended with the color black.</span></span>  
  
 [!code-csharp[System.Drawing.AlphaBlending#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.AlphaBlending/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.AlphaBlending#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.AlphaBlending/VB/Class1.vb#21)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="775b8-116">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="775b8-116">Compiling the Code</span></span>  
 <span data-ttu-id="775b8-117">L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro di <xref:System.Windows.Forms.PaintEventHandler> .</span><span class="sxs-lookup"><span data-stu-id="775b8-117">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="775b8-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="775b8-118">See also</span></span>

- [<span data-ttu-id="775b8-119">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="775b8-119">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="775b8-120">Linee e riempimenti con fusione alfa</span><span class="sxs-lookup"><span data-stu-id="775b8-120">Alpha Blending Lines and Fills</span></span>](alpha-blending-lines-and-fills.md)
