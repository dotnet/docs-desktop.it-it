---
title: Metafile in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], metafiles
- GDI+, metafiles
- metafiles
ms.assetid: 51da872c-c783-440f-8bf6-1e580a966c31
ms.openlocfilehash: df54289722cf12bad840722c6eafdaa43279a5dc
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96960661"
---
# <a name="metafiles-in-gdi"></a><span data-ttu-id="65024-102">Metafile in GDI+</span><span class="sxs-lookup"><span data-stu-id="65024-102">Metafiles in GDI+</span></span>
<span data-ttu-id="65024-103">GDI+ fornisce la <xref:System.Drawing.Imaging.Metafile> classe in modo che sia possibile registrare e visualizzare i metafile.</span><span class="sxs-lookup"><span data-stu-id="65024-103">GDI+ provides the <xref:System.Drawing.Imaging.Metafile> class so that you can record and display metafiles.</span></span> <span data-ttu-id="65024-104">Un metafile, detto anche immagine vettoriale, è un'immagine archiviata come sequenza di comandi e impostazioni di disegno.</span><span class="sxs-lookup"><span data-stu-id="65024-104">A metafile, also called a vector image, is an image that is stored as a sequence of drawing commands and settings.</span></span> <span data-ttu-id="65024-105">I comandi e le impostazioni registrati in un <xref:System.Drawing.Imaging.Metafile> oggetto possono essere archiviati in memoria o salvati in un file o in un flusso.</span><span class="sxs-lookup"><span data-stu-id="65024-105">The commands and settings recorded in a <xref:System.Drawing.Imaging.Metafile> object can be stored in memory or saved to a file or stream.</span></span>  
  
## <a name="metafile-formats"></a><span data-ttu-id="65024-106">Formati di metafile</span><span class="sxs-lookup"><span data-stu-id="65024-106">Metafile Formats</span></span>  
 <span data-ttu-id="65024-107">GDI+ consente di visualizzare i metafile archiviati nei formati seguenti:</span><span class="sxs-lookup"><span data-stu-id="65024-107">GDI+ can display metafiles that have been stored in the following formats:</span></span>  
  
- <span data-ttu-id="65024-108">Metafile di Windows (WMF)</span><span class="sxs-lookup"><span data-stu-id="65024-108">Windows Metafile (WMF)</span></span>  
  
- <span data-ttu-id="65024-109">Enhanced Metafile (EMF)</span><span class="sxs-lookup"><span data-stu-id="65024-109">Enhanced Metafile (EMF)</span></span>  
  
- <span data-ttu-id="65024-110">EMF +</span><span class="sxs-lookup"><span data-stu-id="65024-110">EMF+</span></span>  
  
 <span data-ttu-id="65024-111">GDI+ può registrare i metafile nei formati EMF e EMF +, ma non nel formato WMF.</span><span class="sxs-lookup"><span data-stu-id="65024-111">GDI+ can record metafiles in the EMF and EMF+ formats, but not in the WMF format.</span></span>  
  
 <span data-ttu-id="65024-112">EMF + è un'estensione di EMF che consente l'archiviazione di record GDI+.</span><span class="sxs-lookup"><span data-stu-id="65024-112">EMF+ is an extension to EMF that allows GDI+ records to be stored.</span></span> <span data-ttu-id="65024-113">Sono disponibili due varianti nel formato EMF +, ovvero EMF + Only e EMF + Dual.</span><span class="sxs-lookup"><span data-stu-id="65024-113">There are two variations on the EMF+ format: EMF+ Only and EMF+ Dual.</span></span> <span data-ttu-id="65024-114">EMF + solo i metafile contengono solo record GDI+.</span><span class="sxs-lookup"><span data-stu-id="65024-114">EMF+ Only metafiles contain only GDI+ records.</span></span> <span data-ttu-id="65024-115">Tali metafile possono essere visualizzati da GDI+ ma non da GDI.</span><span class="sxs-lookup"><span data-stu-id="65024-115">Such metafiles can be displayed by GDI+ but not by GDI.</span></span> <span data-ttu-id="65024-116">I metafile EMF + Dual contengono i record GDI+ e GDI.</span><span class="sxs-lookup"><span data-stu-id="65024-116">EMF+ Dual metafiles contain GDI+ and GDI records.</span></span> <span data-ttu-id="65024-117">Ogni record GDI+ in un metafile EMF + Dual è associato a un record GDI alternativo.</span><span class="sxs-lookup"><span data-stu-id="65024-117">Each GDI+ record in an EMF+ Dual metafile is paired with an alternate GDI record.</span></span> <span data-ttu-id="65024-118">Tali metafile possono essere visualizzati da GDI+ o da GDI.</span><span class="sxs-lookup"><span data-stu-id="65024-118">Such metafiles can be displayed by GDI+ or by GDI.</span></span>  
  
 <span data-ttu-id="65024-119">Nell'esempio seguente viene visualizzato un metafile salvato in precedenza come file.</span><span class="sxs-lookup"><span data-stu-id="65024-119">The following example displays a metafile that was previously saved as a file.</span></span> <span data-ttu-id="65024-120">Il metafile viene visualizzato con l'angolo superiore sinistro in (100, 100).</span><span class="sxs-lookup"><span data-stu-id="65024-120">The metafile is displayed with its upper-left corner at (100, 100).</span></span>  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="65024-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65024-121">See also</span></span>

- [<span data-ttu-id="65024-122">Immagini, bitmap e metafile</span><span class="sxs-lookup"><span data-stu-id="65024-122">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
