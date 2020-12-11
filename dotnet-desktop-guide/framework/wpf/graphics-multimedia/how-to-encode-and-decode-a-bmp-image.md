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
# <a name="how-to-encode-and-decode-a-bmp-image"></a>Procedura: codificare e decodificare un'immagine BMP
Negli esempi seguenti viene illustrato come decodificare e codificare un'immagine bitmap (BMP) utilizzando <xref:System.Windows.Media.Imaging.BmpBitmapDecoder> gli <xref:System.Windows.Media.Imaging.BmpBitmapEncoder> oggetti e specifici.  
  
## <a name="example"></a>Esempio  
 Questo esempio illustra come decodificare un'immagine BMP usando un oggetto <xref:System.Windows.Media.Imaging.BmpBitmapDecoder> da un oggetto <xref:System.Uri> .  
  
 [!code-cpp[BmpBitmapDecoderEncoder#5](~/samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#5)]
 [!code-csharp[BmpBitmapDecoderEncoder#5](~/samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#5)]
 [!code-vb[BmpBitmapDecoderEncoder#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#5)]  
  
## <a name="example"></a>Esempio  
 Questo esempio illustra come codificare un oggetto <xref:System.Windows.Media.Imaging.BitmapSource> in un'immagine bmp usando un oggetto <xref:System.Windows.Media.Imaging.BmpBitmapEncoder> .  
  
 [!code-cpp[BmpBitmapDecoderEncoder#4](~/samples/snippets/cpp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CPP/anotherfile.cpp#4)]
 [!code-csharp[BmpBitmapDecoderEncoder#4](~/samples/snippets/csharp/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/CSharp/BitmapFrame.cs#4)]
 [!code-vb[BmpBitmapDecoderEncoder#4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BmpBitmapDecoderEncoder/VB/BitmapFrame.vb#4)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sulla creazione dell'immagine](imaging-overview.md)
