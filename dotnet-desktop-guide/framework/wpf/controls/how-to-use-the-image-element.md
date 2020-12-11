---
title: "Procedura: utilizzare l'elemento Image"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [WPF], Image
- Image control [WPF]
- rendering images [WPF]
ms.assetid: 5b92e74b-1b56-4756-ac64-d5e9e08d9854
ms.openlocfilehash: e267aec4d8a1632f77d756bd94d077efcbb2e10c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966328"
---
# <a name="how-to-use-the-image-element"></a>Procedura: utilizzare l'elemento Image
Questo esempio illustra come includere immagini in un'applicazione usando l' <xref:System.Windows.Controls.Image> elemento.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra come eseguire il rendering di un'immagine con una larghezza di 200 pixel. In questo esempio [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)], per definire l'immagine vengono usate sia la sintassi degli attributi e che la sintassi di tag di proprietà. Per altre informazioni sulla sintassi degli attributi e la sintassi di proprietà, vedere [Cenni preliminari sulle proprietà di dipendenza](../advanced/dependency-properties-overview.md). Un <xref:System.Windows.Media.Imaging.BitmapImage> viene usato per definire i dati di origine dell'immagine ed è definito in modo esplicito per l'esempio di sintassi dei tag della proprietà. Inoltre, l'oggetto <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> di <xref:System.Windows.Media.Imaging.BitmapImage> viene impostato sulla stessa larghezza dell'oggetto <xref:System.Windows.FrameworkElement.Width%2A> di <xref:System.Windows.Controls.Image> . In questo modo per il rendering dell'immagine viene usata la quantità minima di memoria.  
  
> [!NOTE]
> In generale, se si desidera specificare le dimensioni di un'immagine sottoposta a rendering, specificare solo <xref:System.Windows.FrameworkElement.Width%2A> o <xref:System.Windows.FrameworkElement.Height%2A> ma non entrambi. Se si specifica solo uno di questi oggetti, le proporzioni dell'immagine vengono mantenute. In caso contrario, l'immagine potrebbe apparire inaspettatamente allungata o distorta. Per controllare il comportamento di estensione dell'immagine, usare le <xref:System.Windows.Controls.Image.Stretch%2A> <xref:System.Windows.Controls.Image.StretchDirection%2A> proprietà e.  
  
> [!NOTE]
> Quando si specificano le dimensioni di un'immagine con <xref:System.Windows.FrameworkElement.Width%2A> o <xref:System.Windows.FrameworkElement.Height%2A> , è necessario impostare anche <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelWidth%2A> o <xref:System.Windows.Media.Imaging.BitmapImage.DecodePixelHeight%2A> sulla stessa dimensione corrispondente.  
  
 La <xref:System.Windows.Controls.Image.Stretch%2A> proprietà determina il modo in cui l'origine dell'immagine viene adattata per riempire l'elemento immagine. Per altre informazioni, vedere l'enumerazione <xref:System.Windows.Media.Stretch>.  
  
 [!code-xaml[ImageElementExample_snip#ImageSimpleExampleInlineMarkup](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml#imagesimpleexampleinlinemarkup)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra come eseguire il rendering di un'immagine con una larghezza di 200 pixel usando il codice.  
  
> [!NOTE]
> L'impostazione delle <xref:System.Windows.Media.Imaging.BitmapImage> proprietà deve essere eseguita all'interno di un <xref:System.Windows.Media.Imaging.BitmapImage.BeginInit%2A> <xref:System.Windows.Media.Imaging.BitmapImage.EndInit%2A> blocco e.  
  
 [!code-csharp[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/csharp/VS_Snippets_Wpf/ImageElementExample_snip/CSharp/ImageSimpleExample.xaml.cs#imagesimpleexampleinlinecode1)]
 [!code-vb[ImageElementExample_snip#ImageSimpleExampleInlineCode1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImageElementExample_snip/VB/ImageSimpleExample.xaml.vb#imagesimpleexampleinlinecode1)]  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sulla creazione dell'immagine](../graphics-multimedia/imaging-overview.md)
