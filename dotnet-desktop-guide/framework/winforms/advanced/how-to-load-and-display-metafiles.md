---
title: 'Procedura: Caricare e visualizzare metafile'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], metafiles
- metafiles [Windows Forms], displaying
ms.assetid: 60af1714-f148-4d85-a739-0557965ffa73
ms.openlocfilehash: 6c17e0b2d023ccf80b0d32301b7ee6765edcae9f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962593"
---
# <a name="how-to-load-and-display-metafiles"></a><span data-ttu-id="40ebf-102">Procedura: Caricare e visualizzare metafile</span><span class="sxs-lookup"><span data-stu-id="40ebf-102">How to: Load and Display Metafiles</span></span>
<span data-ttu-id="40ebf-103">La <xref:System.Drawing.Imaging.Metafile> classe, che eredita dalla <xref:System.Drawing.Image> classe, fornisce metodi per la registrazione, la visualizzazione e l'analisi di immagini vettoriali.</span><span class="sxs-lookup"><span data-stu-id="40ebf-103">The <xref:System.Drawing.Imaging.Metafile> class, which inherits from the <xref:System.Drawing.Image> class, provides methods for recording, displaying, and examining vector images.</span></span>  
  
## <a name="example"></a><span data-ttu-id="40ebf-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="40ebf-104">Example</span></span>  
 <span data-ttu-id="40ebf-105">Per visualizzare un'immagine vettoriale (Metafile) sullo schermo, sono necessari un <xref:System.Drawing.Imaging.Metafile> oggetto e un <xref:System.Drawing.Graphics> oggetto.</span><span class="sxs-lookup"><span data-stu-id="40ebf-105">To display a vector image (metafile) on the screen, you need a <xref:System.Drawing.Imaging.Metafile> object and a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="40ebf-106">Passare il nome di un file (o di un flusso) a un <xref:System.Drawing.Imaging.Metafile> costruttore.</span><span class="sxs-lookup"><span data-stu-id="40ebf-106">Pass the name of a file (or a stream) to a <xref:System.Drawing.Imaging.Metafile> constructor.</span></span> <span data-ttu-id="40ebf-107">Dopo aver creato un <xref:System.Drawing.Imaging.Metafile> oggetto, passare <xref:System.Drawing.Imaging.Metafile> l'oggetto al <xref:System.Drawing.Graphics.DrawImage%2A> metodo di un <xref:System.Drawing.Graphics> oggetto.</span><span class="sxs-lookup"><span data-stu-id="40ebf-107">After you have created a <xref:System.Drawing.Imaging.Metafile> object, pass that <xref:System.Drawing.Imaging.Metafile> object to the <xref:System.Drawing.Graphics.DrawImage%2A> method of a <xref:System.Drawing.Graphics> object.</span></span>  
  
 <span data-ttu-id="40ebf-108">Nell'esempio viene creato un <xref:System.Drawing.Imaging.Metafile> oggetto da un file EMF (Enhanced Metafile), quindi viene disegnata l'immagine con l'angolo superiore sinistro in (60, 10).</span><span class="sxs-lookup"><span data-stu-id="40ebf-108">The example creates a <xref:System.Drawing.Imaging.Metafile> object from an EMF (enhanced metafile) file and then draws the image with its upper-left corner at (60, 10).</span></span>  
  
 <span data-ttu-id="40ebf-109">Nella figura seguente viene illustrato il metafile disegnato nella posizione specificata.</span><span class="sxs-lookup"><span data-stu-id="40ebf-109">The following illustration shows the metafile drawn at the specified location.</span></span>  
  
 <span data-ttu-id="40ebf-110">![Screenshot che mostra la posizione dell'immagine.](./media/how-to-load-and-display-metafiles/metafile-drawn-specified-location.png "imageposition2")</span><span class="sxs-lookup"><span data-stu-id="40ebf-110">![Screenshot showing image position.](./media/how-to-load-and-display-metafiles/metafile-drawn-specified-location.png "imageposition2")</span></span>  
  
 [!code-csharp[System.Drawing.WorkingWithImages#41](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#41)]
 [!code-vb[System.Drawing.WorkingWithImages#41](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#41)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="40ebf-111">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="40ebf-111">Compiling the Code</span></span>  
 <span data-ttu-id="40ebf-112">L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro del <xref:System.Windows.Forms.Control.Paint> gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="40ebf-112">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40ebf-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="40ebf-113">See also</span></span>

- [<span data-ttu-id="40ebf-114">Utilizzo di immagini, bitmap, icone e metafile</span><span class="sxs-lookup"><span data-stu-id="40ebf-114">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
