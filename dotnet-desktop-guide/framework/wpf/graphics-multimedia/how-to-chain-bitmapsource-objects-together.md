---
title: 'Procedura: concatenare gli oggetti BitmapSource'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- BitmapSource objects [WPF], chaining
- graphics [WPF], chaining BitmapSource objects
- chaining BitmapSource objects [WPF]
ms.assetid: 32d88853-395b-4855-9685-51a482a3b421
ms.openlocfilehash: 403a2a8683e65fd71df89befd59744ac3fe6200c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968803"
---
# <a name="how-to-chain-bitmapsource-objects-together"></a><span data-ttu-id="38803-102">Procedura: concatenare gli oggetti BitmapSource</span><span class="sxs-lookup"><span data-stu-id="38803-102">How to: Chain BitmapSource Objects Together</span></span>
<span data-ttu-id="38803-103">Questo esempio illustra come applicare un'ampia gamma di effetti a un'origine immagine concatenando più <xref:System.Windows.Media.Imaging.BitmapSource> oggetti derivati insieme.</span><span class="sxs-lookup"><span data-stu-id="38803-103">This example shows how you can apply a variety of effects to an image source by chaining multiple <xref:System.Windows.Media.Imaging.BitmapSource> derived objects together.</span></span>  
  
 <span data-ttu-id="38803-104">L'esempio seguente usa la concatenazione per capovolgere e modificare il formato di pixel dell'origine di un'immagine.</span><span class="sxs-lookup"><span data-stu-id="38803-104">The following example uses chaining to flip and change the pixel format of the source of an image.</span></span>  
  
## <a name="example"></a><span data-ttu-id="38803-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="38803-105">Example</span></span>  
 [!code-xaml[ImagingSnippetGallery_snip#ChainedBitmapSourcesXamlExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_snip/CS/ChainedBitmapSourcesExample.xaml#chainedbitmapsourcesxamlexamplewholepage)]  
  
 [!code-csharp[ImagingSnippetGallery_procedural_snip#ChainedBitmapSourcesCodeExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/CSharp/ChainedBitmapSourcesExample.cs#chainedbitmapsourcescodeexamplewholepage)]
 [!code-vb[ImagingSnippetGallery_procedural_snip#ChainedBitmapSourcesCodeExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ImagingSnippetGallery_procedural_snip/VB/ChainedBitmapSourcesExample.vb#chainedbitmapsourcescodeexamplewholepage)]
