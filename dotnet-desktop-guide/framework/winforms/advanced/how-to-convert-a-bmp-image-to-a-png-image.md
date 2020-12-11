---
title: "Procedura: Convertire un'immagine BMP in un'immagine PNG"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- BMP images [Windows Forms], converting to PNG
- image formats [Windows Forms], converting between
ms.assetid: 9d4a692d-73ac-4ce3-9e05-9ec321e8fbd6
ms.openlocfilehash: 59200941aa0f872a0bd99510bfaa8a8b878a9061
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952428"
---
# <a name="how-to-convert-a-bmp-image-to-a-png-image"></a><span data-ttu-id="a2ed5-102">Procedura: Convertire un'immagine BMP in un'immagine PNG</span><span class="sxs-lookup"><span data-stu-id="a2ed5-102">How to: Convert a BMP image to a PNG image</span></span>
<span data-ttu-id="a2ed5-103">Spesso può essere opportuno convertire un formato di file immagine in un altro.</span><span class="sxs-lookup"><span data-stu-id="a2ed5-103">Oftentimes, you will want to convert from one image file format to another.</span></span> <span data-ttu-id="a2ed5-104">È possibile eseguire questa conversione chiamando il metodo <xref:System.Drawing.Image.Save%2A> della classe <xref:System.Drawing.Image> e specificando l'oggetto <xref:System.Drawing.Imaging.ImageFormat> per il formato di file immagine desiderato.</span><span class="sxs-lookup"><span data-stu-id="a2ed5-104">You can do this conversion easily by calling the <xref:System.Drawing.Image.Save%2A> method of the <xref:System.Drawing.Image> class and specifying the <xref:System.Drawing.Imaging.ImageFormat> for the desired image file format.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a2ed5-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="a2ed5-105">Example</span></span>  
 <span data-ttu-id="a2ed5-106">Nell'esempio seguente viene caricata un'immagine BMP da un tipo e quindi salvata nel formato PNG.</span><span class="sxs-lookup"><span data-stu-id="a2ed5-106">The following example loads a BMP image from a type, and saves the image in the PNG format.</span></span>  
  
 [!code-csharp[UsingImageEncodersDecoders#4](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#4)]
 [!code-vb[UsingImageEncodersDecoders#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#4)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a2ed5-107">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="a2ed5-107">Compiling the Code</span></span>  
 <span data-ttu-id="a2ed5-108">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="a2ed5-108">This example requires:</span></span>  
  
- <span data-ttu-id="a2ed5-109">Applicazione Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="a2ed5-109">A Windows Forms application.</span></span>  
  
- <span data-ttu-id="a2ed5-110">Un riferimento allo spazio dei nomi `System.Drawing.Imaging`.</span><span class="sxs-lookup"><span data-stu-id="a2ed5-110">A reference to the `System.Drawing.Imaging` namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2ed5-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a2ed5-111">See also</span></span>

- [<span data-ttu-id="a2ed5-112">Procedura: Elencare i codificatori installati</span><span class="sxs-lookup"><span data-stu-id="a2ed5-112">How to: List Installed Encoders</span></span>](how-to-list-installed-encoders.md)
- [<span data-ttu-id="a2ed5-113">Utilizzo di codificatori e decodificatori di immagini nel codice gestito GDI+</span><span class="sxs-lookup"><span data-stu-id="a2ed5-113">Using Image Encoders and Decoders in Managed GDI+</span></span>](using-image-encoders-and-decoders-in-managed-gdi.md)
- [<span data-ttu-id="a2ed5-114">Tipi di bitmap</span><span class="sxs-lookup"><span data-stu-id="a2ed5-114">Types of Bitmaps</span></span>](types-of-bitmaps.md)
