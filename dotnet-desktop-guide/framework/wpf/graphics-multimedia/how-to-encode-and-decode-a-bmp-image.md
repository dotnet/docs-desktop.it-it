---
title: "Procedura: codificare e decodificare un'immagine BMP"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- encoding BMP images [WPF]
- BMP encoding [WPF]
- decoding BMP images [WPF]
- encoding image formats [WPF]
- BMP decoding [WPF]
- decoding image formats [WPF]
ms.assetid: feb5ef27-28ac-40ab-bfc2-e0456990d32c
ms.openlocfilehash: 7d3520a1b1913fe68fedb0ea9d76cc138ed661c4
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967318"
---
# <a name="how-to-encode-and-decode-a-bmp-image"></a><span data-ttu-id="8e2c4-102">Procedura: codificare e decodificare un'immagine BMP</span><span class="sxs-lookup"><span data-stu-id="8e2c4-102">How to: Encode and Decode a BMP Image</span></span>
<span data-ttu-id="8e2c4-103">Negli esempi seguenti viene illustrato come decodificare e codificare un'immagine bitmap (BMP) utilizzando <xref:System.Windows.Media.Imaging.BmpBitmapDecoder> gli <xref:System.Windows.Media.Imaging.BmpBitmapEncoder> oggetti e specifici.</span><span class="sxs-lookup"><span data-stu-id="8e2c4-103">The following examples show how to decode and encode a bitmap (BMP) image using the specific <xref:System.Windows.Media.Imaging.BmpBitmapDecoder> and <xref:System.Windows.Media.Imaging.BmpBitmapEncoder> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e2c4-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="8e2c4-104">Example</span></span>  
 <span data-ttu-id="8e2c4-105">Questo esempio illustra come decodificare un'immagine BMP usando un oggetto <xref:System.Windows.Media.Imaging.BmpBitmapDecoder> da un oggetto <xref:System.Uri> .</span><span class="sxs-lookup"><span data-stu-id="8e2c4-105">This example demonstrates how to decode a BMP image using a <xref:System.Windows.Media.Imaging.BmpBitmapDecoder> from a <xref:System.Uri>.</span></span>  
  
 [!code-cpp[BmpBitmapDecoderEncoder#5](~/samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#5)]
 [!code-csharp[BmpBitmapDecoderEncoder#5](~/samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#5)]
 [!code-vb[BmpBitmapDecoderEncoder#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="8e2c4-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="8e2c4-106">Example</span></span>  
 <span data-ttu-id="8e2c4-107">Questo esempio illustra come codificare un oggetto <xref:System.Windows.Media.Imaging.BitmapSource> in un'immagine bmp usando un oggetto <xref:System.Windows.Media.Imaging.BmpBitmapEncoder> .</span><span class="sxs-lookup"><span data-stu-id="8e2c4-107">This example demonstrates how to encode a <xref:System.Windows.Media.Imaging.BitmapSource> into a BMP image using a <xref:System.Windows.Media.Imaging.BmpBitmapEncoder>.</span></span>  
  
 [!code-cpp[BmpBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#4)]
 [!code-csharp[BmpBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#4)]
 [!code-vb[BmpBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="8e2c4-108">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e2c4-108">See also</span></span>

- [<span data-ttu-id="8e2c4-109">Cenni preliminari sulla creazione dell'immagine</span><span class="sxs-lookup"><span data-stu-id="8e2c4-109">Imaging Overview</span></span>](imaging-overview.md)
