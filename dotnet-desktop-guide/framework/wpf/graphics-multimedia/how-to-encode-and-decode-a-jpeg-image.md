---
title: "Procedura: codificare e decodificare un'immagine JPEG"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- encoding image formats [WPF]
- decoding JPEG images [WPF]
- encoding JPEG images [WPF]
- decoding image formats [WPF]
- JPEG decoding [WPF]
- JPEG encoding [WPF]
ms.assetid: b8cfde37-9f68-4911-a05e-51d8d7bdec7b
ms.openlocfilehash: 0f64ef8537f22ea996cbcf274885de1f3968267a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969880"
---
# <a name="how-to-encode-and-decode-a-jpeg-image"></a><span data-ttu-id="856a2-102">Procedura: codificare e decodificare un'immagine JPEG</span><span class="sxs-lookup"><span data-stu-id="856a2-102">How to: Encode and decode a JPEG image</span></span>

<span data-ttu-id="856a2-103">Gli esempi seguenti illustrano come decodificare e codificare un'immagine JPEG usando <xref:System.Windows.Media.Imaging.JpegBitmapDecoder> gli <xref:System.Windows.Media.Imaging.JpegBitmapEncoder> oggetti e specifici.</span><span class="sxs-lookup"><span data-stu-id="856a2-103">The following examples show how to decode and encode a JPEG image using the specific <xref:System.Windows.Media.Imaging.JpegBitmapDecoder> and <xref:System.Windows.Media.Imaging.JpegBitmapEncoder> objects.</span></span>  
  
## <a name="example---decode-a-jpeg-image"></a><span data-ttu-id="856a2-104">Esempio: decodifica di un'immagine JPEG</span><span class="sxs-lookup"><span data-stu-id="856a2-104">Example - Decode a JPEG image</span></span>

<span data-ttu-id="856a2-105">Questo esempio illustra come decodificare un'immagine JPEG usando un oggetto <xref:System.Windows.Media.Imaging.JpegBitmapDecoder> da un oggetto <xref:System.IO.FileStream> .</span><span class="sxs-lookup"><span data-stu-id="856a2-105">This example demonstrates how to decode a JPEG image using a <xref:System.Windows.Media.Imaging.JpegBitmapDecoder> from a <xref:System.IO.FileStream>.</span></span>  
  
[!code-cpp[JpegBitmapDecoderEncoder#1](~/samples/snippets/cpp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CPP/jpegencoderdecoder.cpp#1)]
[!code-csharp[JpegBitmapDecoderEncoder#1](~/samples/snippets/csharp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CSharp/JpegEncoderDecoder.cs#1)]
[!code-vb[JpegBitmapDecoderEncoder#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/VB/JpegEncoderDecoder.vb#1)]  
  
## <a name="example---encode-a-jpeg-image"></a><span data-ttu-id="856a2-106">Esempio: codificare un'immagine JPEG</span><span class="sxs-lookup"><span data-stu-id="856a2-106">Example - Encode a JPEG image</span></span>

<span data-ttu-id="856a2-107">Questo esempio illustra come codificare un oggetto <xref:System.Windows.Media.Imaging.BitmapSource> in un'immagine JPEG usando un oggetto <xref:System.Windows.Media.Imaging.JpegBitmapEncoder> .</span><span class="sxs-lookup"><span data-stu-id="856a2-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a JPEG image using a <xref:System.Windows.Media.Imaging.JpegBitmapEncoder>.</span></span>  
  
[!code-cpp[JpegBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CPP/jpegencoderdecoder.cpp#4)]
[!code-csharp[JpegBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/CSharp/JpegEncoderDecoder.cs#4)]
[!code-vb[JpegBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/JpegBitmapDecoderEncoder/VB/JpegEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="856a2-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="856a2-108">See also</span></span>

- [<span data-ttu-id="856a2-109">Cenni preliminari sulla creazione dell'immagine</span><span class="sxs-lookup"><span data-stu-id="856a2-109">Imaging Overview</span></span>](imaging-overview.md)
