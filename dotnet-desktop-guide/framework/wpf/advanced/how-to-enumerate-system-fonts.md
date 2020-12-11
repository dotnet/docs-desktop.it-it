---
title: 'Procedura: enumerare i caratteri del sistema'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- typography [WPF], enumerating system fonts
- fonts [WPF], enumerating
- system fonts [WPF], enumerating
- enumerating [WPF], system fonts
ms.assetid: 36e37791-55b9-4f01-a496-5cc10335e6a6
ms.openlocfilehash: 7ea16afa12233ad5f8268ec048bed187f6081299
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966481"
---
# <a name="how-to-enumerate-system-fonts"></a><span data-ttu-id="a89c9-102">Procedura: enumerare i caratteri del sistema</span><span class="sxs-lookup"><span data-stu-id="a89c9-102">How to: Enumerate System Fonts</span></span>
## <a name="example"></a><span data-ttu-id="a89c9-103">Esempio</span><span class="sxs-lookup"><span data-stu-id="a89c9-103">Example</span></span>  
 <span data-ttu-id="a89c9-104">Nell'esempio seguente viene illustrato come enumerare i tipi di carattere nella raccolta di tipi di carattere di sistema.</span><span class="sxs-lookup"><span data-stu-id="a89c9-104">The following example shows how to enumerate the fonts in the system font collection.</span></span> <span data-ttu-id="a89c9-105">Il nome della famiglia di caratteri di ogni <xref:System.Windows.Media.FontFamily> all'interno di <xref:System.Windows.Media.Fonts.SystemFontFamilies%2A> viene aggiunto come elemento a una casella combinata.</span><span class="sxs-lookup"><span data-stu-id="a89c9-105">The font family name of each <xref:System.Windows.Media.FontFamily> within <xref:System.Windows.Media.Fonts.SystemFontFamilies%2A> is added as an item to a combo box.</span></span>  
  
 [!code-csharp[TextOverview#100](~/samples/snippets/csharp/VS_Snippets_Wpf/TextOverview/CSharp/Window1.xaml.cs#100)]
 [!code-vb[TextOverview#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextOverview/visualbasic/window1.xaml.vb#100)]  
  
 <span data-ttu-id="a89c9-106">Se più versioni della stessa famiglia di caratteri si trovano nella stessa directory, l' [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] enumerazione del tipo di carattere restituisce la versione più recente del tipo di carattere.</span><span class="sxs-lookup"><span data-stu-id="a89c9-106">If multiple versions of the same font family reside in the same directory, the [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] font enumeration returns the most recent version of the font.</span></span> <span data-ttu-id="a89c9-107">Se le informazioni sulla versione non forniscono la risoluzione, viene restituito il tipo di carattere con il timestamp più recente.</span><span class="sxs-lookup"><span data-stu-id="a89c9-107">If the version information does not provide resolution, the font with latest timestamp is returned.</span></span> <span data-ttu-id="a89c9-108">Se le informazioni sul timestamp sono equivalenti, viene restituito il file del tipo di carattere prima in ordine alfabetico.</span><span class="sxs-lookup"><span data-stu-id="a89c9-108">If the timestamp information is equivalent, the font file that is first in alphabetical order is returned.</span></span>
