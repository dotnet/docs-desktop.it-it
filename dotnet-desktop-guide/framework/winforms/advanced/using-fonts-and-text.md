---
title: Utilizzo di tipi di carattere e testo
ms.date: 03/30/2017
helpviewer_keywords:
- GDI [Windows Forms], drawing text [Windows Forms]
- text [Windows Forms], drawing in Windows Forms
- examples [Windows Forms], fonts and text
- fonts [Windows Forms], using in Windows Forms
- strings [Windows Forms], drawing in Windows Forms
ms.assetid: d43640f3-da94-4df2-a29d-a9d021a1c069
ms.openlocfilehash: 73a4af5fe7367e777fcb83af8c84c09be91e5b1e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963034"
---
# <a name="using-fonts-and-text"></a><span data-ttu-id="1aa52-102">Utilizzo di tipi di carattere e testo</span><span class="sxs-lookup"><span data-stu-id="1aa52-102">Using Fonts and Text</span></span>
<span data-ttu-id="1aa52-103">Sono disponibili diverse classi offerte da GDI+ e GDI per il disegno di testo in Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="1aa52-103">There are several classes offered by GDI+ and GDI for drawing text on Windows Forms.</span></span> <span data-ttu-id="1aa52-104">La <xref:System.Drawing.Graphics> classe GDI+ dispone di diversi <xref:System.Drawing.Graphics.DrawString%2A> metodi che consentono di specificare varie caratteristiche del testo, ad esempio la posizione, il rettangolo di delimitazione, il tipo di carattere e il formato.</span><span class="sxs-lookup"><span data-stu-id="1aa52-104">The GDI+ <xref:System.Drawing.Graphics> class has several <xref:System.Drawing.Graphics.DrawString%2A> methods that allow you to specify various features of text, such as location, bounding rectangle, font, and format.</span></span> <span data-ttu-id="1aa52-105">Inoltre, è possibile creare e misurare il testo con GDI usando i <xref:System.Windows.Forms.TextRenderer.DrawText%2A> metodi statici e <xref:System.Windows.Forms.TextRenderer.MeasureText%2A> offerti dalla `TextRenderer` classe.</span><span class="sxs-lookup"><span data-stu-id="1aa52-105">In addition, you can draw and measure text with GDI using the static <xref:System.Windows.Forms.TextRenderer.DrawText%2A> and <xref:System.Windows.Forms.TextRenderer.MeasureText%2A> methods offered by the `TextRenderer` class.</span></span> <span data-ttu-id="1aa52-106">I metodi GDI consentono inoltre di specificare il percorso, il tipo di carattere e il formato.</span><span class="sxs-lookup"><span data-stu-id="1aa52-106">The GDI methods also allow you to specify location, font, and format.</span></span> <span data-ttu-id="1aa52-107">È possibile scegliere GDI o GDI+ per il rendering del testo; Tuttavia, GDI offre in genere prestazioni migliori e misurazioni del testo più accurate.</span><span class="sxs-lookup"><span data-stu-id="1aa52-107">You can choose either GDI or GDI+ for text rendering; however, GDI generally offers better performance and more accurate text measuring.</span></span> <span data-ttu-id="1aa52-108">Altre classi che contribuiscono al rendering del testo includono `FontFamily` ,, `Font` <xref:System.Drawing.StringFormat> e `TextFormatFlags` .</span><span class="sxs-lookup"><span data-stu-id="1aa52-108">Other classes that contribute to text rendering include `FontFamily`, `Font`, <xref:System.Drawing.StringFormat>, and `TextFormatFlags`.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1aa52-109">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="1aa52-109">In This Section</span></span>  
 [<span data-ttu-id="1aa52-110">Procedura: Creare tipi di carattere e famiglie di caratteri</span><span class="sxs-lookup"><span data-stu-id="1aa52-110">How to: Construct Font Families and Fonts</span></span>](how-to-construct-font-families-and-fonts.md)  
 <span data-ttu-id="1aa52-111">Viene illustrato come creare `Font` `FontFamily` oggetti e.</span><span class="sxs-lookup"><span data-stu-id="1aa52-111">Shows how to create `Font` and `FontFamily` objects.</span></span>  
  
 [<span data-ttu-id="1aa52-112">Procedura: Disegnare testo in una posizione specificata</span><span class="sxs-lookup"><span data-stu-id="1aa52-112">How to: Draw Text at a Specified Location</span></span>](how-to-draw-text-at-a-specified-location.md)  
 <span data-ttu-id="1aa52-113">Viene descritto come creare testo in una determinata posizione utilizzando GDI+ e GDI.</span><span class="sxs-lookup"><span data-stu-id="1aa52-113">Describes how to draw text in a certain location using GDI+ and GDI.</span></span>  
  
 [<span data-ttu-id="1aa52-114">Procedura: Disegnare testo disposto su più righe in un rettangolo</span><span class="sxs-lookup"><span data-stu-id="1aa52-114">How to: Draw Wrapped Text in a Rectangle</span></span>](how-to-draw-wrapped-text-in-a-rectangle.md)  
 <span data-ttu-id="1aa52-115">Viene illustrato come creare testo in un rettangolo utilizzando GDI+ e GDI.</span><span class="sxs-lookup"><span data-stu-id="1aa52-115">Explains how to draw text in a rectangle using GDI+ and GDI.</span></span>  
  
 [<span data-ttu-id="1aa52-116">Procedura: Disegnare testo con GDI</span><span class="sxs-lookup"><span data-stu-id="1aa52-116">How to: Draw Text with GDI</span></span>](how-to-draw-text-with-gdi.md)  
 <span data-ttu-id="1aa52-117">Viene illustrato come utilizzare GDI per il disegno di testo.</span><span class="sxs-lookup"><span data-stu-id="1aa52-117">Demonstrates how to use GDI for drawing text.</span></span>  
  
 [<span data-ttu-id="1aa52-118">Procedura: Allineare il testo disegnato</span><span class="sxs-lookup"><span data-stu-id="1aa52-118">How to: Align Drawn Text</span></span>](how-to-align-drawn-text.md)  
 <span data-ttu-id="1aa52-119">Viene illustrato come formattare il testo GDI+ e il testo GDI.</span><span class="sxs-lookup"><span data-stu-id="1aa52-119">Shows how to format GDI+ and GDI text.</span></span>  
  
 [<span data-ttu-id="1aa52-120">Procedura: Creare testo verticale</span><span class="sxs-lookup"><span data-stu-id="1aa52-120">How to: Create Vertical Text</span></span>](how-to-create-vertical-text.md)  
 <span data-ttu-id="1aa52-121">Viene descritto come creare testo allineato verticalmente con GDI+.</span><span class="sxs-lookup"><span data-stu-id="1aa52-121">Describes how to draw vertically aligned text with GDI+.</span></span>  
  
 [<span data-ttu-id="1aa52-122">Procedura: Impostare tabulazioni nel testo disegnato</span><span class="sxs-lookup"><span data-stu-id="1aa52-122">How to: Set Tab Stops in Drawn Text</span></span>](how-to-set-tab-stops-in-drawn-text.md)  
 <span data-ttu-id="1aa52-123">Mostra come creare un testo con tabulazioni con GDI+.</span><span class="sxs-lookup"><span data-stu-id="1aa52-123">Shows how draw text with tab stops with GDI+.</span></span>  
  
 [<span data-ttu-id="1aa52-124">Procedura: Enumerare i tipi di carattere installati</span><span class="sxs-lookup"><span data-stu-id="1aa52-124">How to: Enumerate Installed Fonts</span></span>](how-to-enumerate-installed-fonts.md)  
 <span data-ttu-id="1aa52-125">Viene illustrato come elencare i nomi dei tipi di carattere installati.</span><span class="sxs-lookup"><span data-stu-id="1aa52-125">Explains how to list the names of installed fonts.</span></span>  
  
 [<span data-ttu-id="1aa52-126">Procedura: Creare una raccolta di tipi di carattere privata</span><span class="sxs-lookup"><span data-stu-id="1aa52-126">How to: Create a Private Font Collection</span></span>](how-to-create-a-private-font-collection.md)  
 <span data-ttu-id="1aa52-127">Viene descritto come creare un <xref:System.Drawing.Text.PrivateFontCollection> oggetto.</span><span class="sxs-lookup"><span data-stu-id="1aa52-127">Describes how to create a <xref:System.Drawing.Text.PrivateFontCollection> object.</span></span>  
  
 [<span data-ttu-id="1aa52-128">Procedura: Ottenere le misure dei tipi di carattere</span><span class="sxs-lookup"><span data-stu-id="1aa52-128">How to: Obtain Font Metrics</span></span>](how-to-obtain-font-metrics.md)  
 <span data-ttu-id="1aa52-129">Viene illustrato come ottenere le metriche dei tipi di carattere, ad esempio l'ascesa e la discesa delle celle.</span><span class="sxs-lookup"><span data-stu-id="1aa52-129">Shows how to obtain font metrics such as cell ascent and descent.</span></span>  
  
 [<span data-ttu-id="1aa52-130">Procedura: Usare l'antialiasing nel testo</span><span class="sxs-lookup"><span data-stu-id="1aa52-130">How to: Use Antialiasing with Text</span></span>](how-to-use-antialiasing-with-text.md)  
 <span data-ttu-id="1aa52-131">Viene illustrato come utilizzare l'anti-aliasing durante il disegno di testo.</span><span class="sxs-lookup"><span data-stu-id="1aa52-131">Explains how to use antialiasing when drawing text.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="1aa52-132">Informazioni di riferimento</span><span class="sxs-lookup"><span data-stu-id="1aa52-132">Reference</span></span>  
 <xref:System.Drawing.Font>  
 <span data-ttu-id="1aa52-133">Descrive questa classe e contiene i collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="1aa52-133">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Drawing.FontFamily>  
 <span data-ttu-id="1aa52-134">Descrive questa classe e contiene i collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="1aa52-134">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Drawing.Text.PrivateFontCollection>  
 <span data-ttu-id="1aa52-135">Descrive questa classe e contiene i collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="1aa52-135">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.TextRenderer>  
 <span data-ttu-id="1aa52-136">Descrive questa classe e contiene i collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="1aa52-136">Describes this class and contains links to all of its members.</span></span>  
  
 <xref:System.Windows.Forms.TextFormatFlags>  
 <span data-ttu-id="1aa52-137">Descrive questa classe e contiene i collegamenti a tutti i relativi membri.</span><span class="sxs-lookup"><span data-stu-id="1aa52-137">Describes this class and contains links to all of its members.</span></span>
