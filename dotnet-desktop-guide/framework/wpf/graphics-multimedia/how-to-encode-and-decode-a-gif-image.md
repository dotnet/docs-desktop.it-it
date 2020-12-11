---
title: "Procedura: codificare e decodificare un'immagine GIF"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- encoding GIF images [WPF]
- encoding image formats [WPF]
- decoding GIF images [WPF]
- decoding image formats [WPF]
- GIF decoding [WPF]
- GIF encoding [WPF]
ms.assetid: 9cdd9ec7-71eb-444b-b9e3-991958461163
ms.openlocfilehash: ec509a03d95e5f72af0b1f362e253799b07edc1f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967846"
---
# <a name="how-to-encode-and-decode-a-gif-image"></a><span data-ttu-id="79e14-102">Procedura: codificare e decodificare un'immagine GIF</span><span class="sxs-lookup"><span data-stu-id="79e14-102">How to: Encode and Decode a GIF Image</span></span>
<span data-ttu-id="79e14-103">Gli esempi seguenti illustrano come decodificare e codificare un'immagine di Graphics Interchange Format (GIF) usando gli <xref:System.Windows.Media.Imaging.GifBitmapDecoder> oggetti e specifici <xref:System.Windows.Media.Imaging.GifBitmapEncoder> .</span><span class="sxs-lookup"><span data-stu-id="79e14-103">The following examples show how to decode and encode a Graphics Interchange Format (GIF) image using the specific <xref:System.Windows.Media.Imaging.GifBitmapDecoder> and <xref:System.Windows.Media.Imaging.GifBitmapEncoder> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79e14-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="79e14-104">Example</span></span>  
 <span data-ttu-id="79e14-105">Questo esempio illustra come decodificare un'immagine GIF usando un oggetto <xref:System.Windows.Media.Imaging.GifBitmapDecoder> da un oggetto <xref:System.IO.FileStream> .</span><span class="sxs-lookup"><span data-stu-id="79e14-105">This example demonstrates how to decode a GIF image using a <xref:System.Windows.Media.Imaging.GifBitmapDecoder> from a <xref:System.IO.FileStream>.</span></span>  
  
 [!code-cpp[GifBitmapDecoderEncoder#1](~/samples/snippets/cpp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CPP/GifEncoderDecoder.cpp#1)]
 [!code-csharp[GifBitmapDecoderEncoder#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CSharp/GifEncoderDecoder.cs#1)]
 [!code-vb[GifBitmapDecoderEncoder#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GifBitmapDecoderEncoder/VB/GifEncoderDecoder.vb#1)]  
  
## <a name="example"></a><span data-ttu-id="79e14-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="79e14-106">Example</span></span>  
 <span data-ttu-id="79e14-107">Questo esempio illustra come codificare un oggetto <xref:System.Windows.Media.Imaging.BitmapSource> in un'immagine gif usando un oggetto <xref:System.Windows.Media.Imaging.GifBitmapEncoder> .</span><span class="sxs-lookup"><span data-stu-id="79e14-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a GIF image using a <xref:System.Windows.Media.Imaging.GifBitmapEncoder>.</span></span>  
  
 [!code-cpp[GifBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CPP/GifEncoderDecoder.cpp#4)]
 [!code-csharp[GifBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/GifBitmapDecoderEncoder/CSharp/GifEncoderDecoder.cs#4)]
 [!code-vb[GifBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GifBitmapDecoderEncoder/VB/GifEncoderDecoder.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="79e14-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79e14-108">See also</span></span>

- [<span data-ttu-id="79e14-109">Cenni preliminari sulla creazione dell'immagine</span><span class="sxs-lookup"><span data-stu-id="79e14-109">Imaging Overview</span></span>](imaging-overview.md)
