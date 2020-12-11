---
title: "Procedura: codificare e decodificare un'immagine TIFF"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- TIFF encoding [WPF]
- encoding TIFF images [WPF]
- encoding image formats [WPF]
- decoding TIFF images [WPF]
- decoding image formats [WPF]
- TIFF decoding [WPF]
ms.assetid: 1dfe3209-fc73-40e6-ad1c-71c1c58b3364
ms.openlocfilehash: 173a30e785b16a3617b82b771c463083356d6e6e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967978"
---
# <a name="how-to-encode-and-decode-a-tiff-image"></a><span data-ttu-id="798b4-102">Procedura: codificare e decodificare un'immagine TIFF</span><span class="sxs-lookup"><span data-stu-id="798b4-102">How to: Encode and Decode a TIFF Image</span></span>
<span data-ttu-id="798b4-103">Negli esempi seguenti viene illustrato come decodificare e codificare un'immagine di Tagged Image File Format (TIFF) utilizzando gli <xref:System.Windows.Media.Imaging.TiffBitmapDecoder> oggetti e specifici <xref:System.Windows.Media.Imaging.TiffBitmapEncoder> .</span><span class="sxs-lookup"><span data-stu-id="798b4-103">The following examples show how to decode and encode a Tagged Image File Format (TIFF) image using the specific <xref:System.Windows.Media.Imaging.TiffBitmapDecoder> and <xref:System.Windows.Media.Imaging.TiffBitmapEncoder> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="798b4-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="798b4-104">Example</span></span>  
 <span data-ttu-id="798b4-105">Questo esempio illustra come decodificare un'immagine TIFF usando un oggetto <xref:System.Windows.Media.Imaging.TiffBitmapDecoder> da un oggetto <xref:System.Uri> .</span><span class="sxs-lookup"><span data-stu-id="798b4-105">This example demonstrates how to decode a TIFF image using a <xref:System.Windows.Media.Imaging.TiffBitmapDecoder> from a <xref:System.Uri>.</span></span>  
  
 [!code-cpp[TiffBitmapDecoderEncoder#1](~/samples/snippets/cpp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CPP/TiffEncoderDecoder.cpp#1)]
 [!code-csharp[TiffBitmapDecoderEncoder#1](~/samples/snippets/csharp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CSharp/TiffEncoderDecoder.cs#1)]
 [!code-vb[TiffBitmapDecoderEncoder#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/VB/TiffEncoderDecoder.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="798b4-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="798b4-106">Example</span></span>  
 <span data-ttu-id="798b4-107">In questo esempio viene illustrato come codificare un oggetto <xref:System.Windows.Media.Imaging.BitmapSource> in un'immagine TIFF utilizzando un oggetto <xref:System.Windows.Media.Imaging.TiffBitmapEncoder> .</span><span class="sxs-lookup"><span data-stu-id="798b4-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a TIFF image using a <xref:System.Windows.Media.Imaging.TiffBitmapEncoder>.</span></span>  
  
 [!code-cpp[TiffBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CPP/TiffEncoderDecoder.cpp#4)]
 [!code-csharp[TiffBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/CSharp/TiffEncoderDecoder.cs#4)]
 [!code-vb[TiffBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TiffBitmapDecoderEncoder/VB/TiffEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="798b4-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="798b4-108">See also</span></span>

- [<span data-ttu-id="798b4-109">Cenni preliminari sulla creazione dell'immagine</span><span class="sxs-lookup"><span data-stu-id="798b4-109">Imaging Overview</span></span>](imaging-overview.md)
