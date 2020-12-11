---
title: 'Procedura: creare un oggetto Bitmap da un oggetto Visual'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- bitmaps [WPF], rendering from visuals
- visuals [WPF], rendering to bitmaps
ms.assetid: 103fc7f5-7306-4026-9d61-2005e79959f3
ms.openlocfilehash: a622d99f7c477f8654526ed399f1eb37288682fe
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968020"
---
# <a name="how-to-create-a-bitmap-from-a-visual"></a><span data-ttu-id="28cf8-102">Procedura: creare un oggetto Bitmap da un oggetto Visual</span><span class="sxs-lookup"><span data-stu-id="28cf8-102">How to: Create a Bitmap from a Visual</span></span>
<span data-ttu-id="28cf8-103">Questo esempio illustra come creare una bitmap da un oggetto <xref:System.Windows.Media.Visual> .</span><span class="sxs-lookup"><span data-stu-id="28cf8-103">This example shows how you can create a bitmap from a <xref:System.Windows.Media.Visual>.</span></span> <span data-ttu-id="28cf8-104"><xref:System.Windows.Media.DrawingVisual>Viene eseguito il rendering di un oggetto con <xref:System.Windows.Media.FormattedText> .</span><span class="sxs-lookup"><span data-stu-id="28cf8-104">A <xref:System.Windows.Media.DrawingVisual> is rendered with <xref:System.Windows.Media.FormattedText>.</span></span> <span data-ttu-id="28cf8-105"><xref:System.Windows.Media.Visual>Viene quindi eseguito il rendering dell'oggetto <xref:System.Windows.Media.Imaging.RenderTargetBitmap> creando una bitmap del testo specificato.</span><span class="sxs-lookup"><span data-stu-id="28cf8-105">The <xref:System.Windows.Media.Visual> is then rendered to the <xref:System.Windows.Media.Imaging.RenderTargetBitmap> creating a bitmap of the given text.</span></span>  
  
## <a name="example"></a><span data-ttu-id="28cf8-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="28cf8-106">Example</span></span>  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#CreateRTBImage](~/samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample.cs#creatertbimage)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#CreateRTBImage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample.vb#creatertbimage)]  
  
## <a name="see-also"></a><span data-ttu-id="28cf8-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="28cf8-107">See also</span></span>

- <xref:System.Windows.Media.DrawingContext>
- [<span data-ttu-id="28cf8-108">Cenni preliminari sulla creazione dell'immagine</span><span class="sxs-lookup"><span data-stu-id="28cf8-108">Imaging Overview</span></span>](imaging-overview.md)
- [<span data-ttu-id="28cf8-109">Cenni preliminari sugli oggetti Drawing</span><span class="sxs-lookup"><span data-stu-id="28cf8-109">Drawing Objects Overview</span></span>](drawing-objects-overview.md)
- [<span data-ttu-id="28cf8-110">Utilizzo degli oggetti DrawingVisual</span><span class="sxs-lookup"><span data-stu-id="28cf8-110">Using DrawingVisual Objects</span></span>](using-drawingvisual-objects.md)
