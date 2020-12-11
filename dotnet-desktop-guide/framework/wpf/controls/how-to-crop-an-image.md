---
title: "Procedura: ritagliare un'immagine"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [WPF], cropping
- cropping images [WPF]
ms.assetid: c6bba109-c6e7-4cf8-bfe6-9cf8d01bb4fc
ms.openlocfilehash: 09a8dd01dec8bf93be627520b1c4700263427411
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968635"
---
# <a name="how-to-crop-an-image"></a>Procedura: ritagliare un'immagine

Questo esempio illustra come ritagliare un'immagine usando <xref:System.Windows.Media.Imaging.CroppedBitmap> .  
  
 <xref:System.Windows.Media.Imaging.CroppedBitmap> viene usato principalmente quando si codifica una versione ritagliata di un'immagine per salvarla in un file. Per ritagliare un'immagine a scopo di visualizzazione, vedere l'argomento [procedura: creare un'area di ritaglio](/previous-versions/dotnet/netframework-3.5/ms746710(v=vs.90)) .  
  
## <a name="example"></a>Esempio  

 Di seguito vengono [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] definite le risorse utilizzate negli esempi riportati di seguito.  
  
 [!code-xaml[imageelementexample#CroppedXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml1)]  
  
 Nell'esempio seguente viene creata un'immagine utilizzando <xref:System.Windows.Media.Imaging.CroppedBitmap> come origine.  
  
 [!code-xaml[imageelementexample#CroppedXAML2](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml2)]  
  
 [!code-csharp[imageelementexample#CroppedCSharp1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml.cs#croppedcsharp1)]
 [!code-vb[imageelementexample#CroppedCSharp1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/CroppedImageExample.xaml.vb#croppedcsharp1)]  
  
 <xref:System.Windows.Media.Imaging.CroppedBitmap>Può anche essere usato come origine di un altro <xref:System.Windows.Media.Imaging.CroppedBitmap> , concatenando il ritaglio. Si noti che <xref:System.Windows.Media.Imaging.CroppedBitmap.SourceRect%2A> Usa i valori relativi alla bitmap ritagliata di origine e non all'immagine iniziale.  
  
 [!code-xaml[imageelementexample#CroppedXAML3](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml#croppedxaml3)]  
  
 [!code-csharp[imageelementexample#CroppedCSharp2](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample/CSharp/CroppedImageExample.xaml.cs#croppedcsharp2)]
 [!code-vb[imageelementexample#CroppedCSharp2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample/VB/CroppedImageExample.xaml.vb#croppedcsharp2)]  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: creare un'area di ritaglio](/previous-versions/dotnet/netframework-3.5/ms746710(v=vs.90))
