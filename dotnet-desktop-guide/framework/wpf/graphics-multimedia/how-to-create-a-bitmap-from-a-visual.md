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
# <a name="how-to-create-a-bitmap-from-a-visual"></a>Procedura: creare un oggetto Bitmap da un oggetto Visual
Questo esempio illustra come creare una bitmap da un oggetto <xref:System.Windows.Media.Visual> . <xref:System.Windows.Media.DrawingVisual>Viene eseguito il rendering di un oggetto con <xref:System.Windows.Media.FormattedText> . <xref:System.Windows.Media.Visual>Viene quindi eseguito il rendering dell'oggetto <xref:System.Windows.Media.Imaging.RenderTargetBitmap> creando una bitmap del testo specificato.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#CreateRTBImage](~/samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/RenderTargetBitmapExample.cs#creatertbimage)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#CreateRTBImage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/RenderTargetBitmapExample.vb#creatertbimage)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Media.DrawingContext>
- [Cenni preliminari sulla creazione dell'immagine](imaging-overview.md)
- [Cenni preliminari sugli oggetti Drawing](drawing-objects-overview.md)
- [Utilizzo degli oggetti DrawingVisual](using-drawingvisual-objects.md)
