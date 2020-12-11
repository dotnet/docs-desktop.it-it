---
title: 'Procedura: Creare tipi di carattere e famiglie di caratteri'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- font families [Windows Forms], constructing
- fonts [Windows Forms], constructing
ms.assetid: d3a4a223-9492-4b54-9afd-db1c31c3cefd
ms.openlocfilehash: 2d609525858c7a8ff77c0b86900b4fc7d6b4e39a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951498"
---
# <a name="how-to-construct-font-families-and-fonts"></a><span data-ttu-id="51984-102">Procedura: Creare tipi di carattere e famiglie di caratteri</span><span class="sxs-lookup"><span data-stu-id="51984-102">How to: Construct Font Families and Fonts</span></span>
<span data-ttu-id="51984-103">GDI+ raggruppa i tipi di carattere con lo stesso carattere tipografico ma con stili diversi nelle famiglie di caratteri.</span><span class="sxs-lookup"><span data-stu-id="51984-103">GDI+ groups fonts with the same typeface but different styles into font families.</span></span> <span data-ttu-id="51984-104">Ad esempio, la famiglia di caratteri Arial contiene i tipi di carattere seguenti:</span><span class="sxs-lookup"><span data-stu-id="51984-104">For example, the Arial font family contains the following fonts:</span></span>  
  
- <span data-ttu-id="51984-105">Arial Regular</span><span class="sxs-lookup"><span data-stu-id="51984-105">Arial Regular</span></span>  
  
- <span data-ttu-id="51984-106">Arial grassetto</span><span class="sxs-lookup"><span data-stu-id="51984-106">Arial Bold</span></span>  
  
- <span data-ttu-id="51984-107">Arial corsivo</span><span class="sxs-lookup"><span data-stu-id="51984-107">Arial Italic</span></span>  
  
- <span data-ttu-id="51984-108">Arial grassetto corsivo</span><span class="sxs-lookup"><span data-stu-id="51984-108">Arial Bold Italic</span></span>  
  
 <span data-ttu-id="51984-109">GDI+ utilizza quattro stili per formare famiglie: normale, grassetto, corsivo e grassetto corsivo.</span><span class="sxs-lookup"><span data-stu-id="51984-109">GDI+ uses four styles to form families: regular, bold, italic, and bold italic.</span></span> <span data-ttu-id="51984-110">Gli aggettivi come *Narrow* e *arrotondati* non sono considerati stili; ma fanno parte del nome della famiglia.</span><span class="sxs-lookup"><span data-stu-id="51984-110">Adjectives such as *narrow* and *rounded* are not considered styles; rather they are part of the family name.</span></span> <span data-ttu-id="51984-111">Ad esempio, Arial Narrow è una famiglia di caratteri con i membri seguenti:</span><span class="sxs-lookup"><span data-stu-id="51984-111">For example, Arial Narrow is a font family with the following members:</span></span>  
  
- <span data-ttu-id="51984-112">Arial Narrow Regular</span><span class="sxs-lookup"><span data-stu-id="51984-112">Arial Narrow Regular</span></span>  
  
- <span data-ttu-id="51984-113">Arial Narrow Bold</span><span class="sxs-lookup"><span data-stu-id="51984-113">Arial Narrow Bold</span></span>  
  
- <span data-ttu-id="51984-114">Arial Narrow corsivo</span><span class="sxs-lookup"><span data-stu-id="51984-114">Arial Narrow Italic</span></span>  
  
- <span data-ttu-id="51984-115">Arial Narrow Bold corsivo</span><span class="sxs-lookup"><span data-stu-id="51984-115">Arial Narrow Bold Italic</span></span>  
  
 <span data-ttu-id="51984-116">Prima di poter creare un testo con GDI+, è necessario creare un <xref:System.Drawing.FontFamily> oggetto e un <xref:System.Drawing.Font> oggetto.</span><span class="sxs-lookup"><span data-stu-id="51984-116">Before you can draw text with GDI+, you need to construct a <xref:System.Drawing.FontFamily> object and a <xref:System.Drawing.Font> object.</span></span> <span data-ttu-id="51984-117">L' <xref:System.Drawing.FontFamily> oggetto specifica il carattere tipografico (ad esempio, Arial) e l' <xref:System.Drawing.Font> oggetto specifica le dimensioni, lo stile e le unità.</span><span class="sxs-lookup"><span data-stu-id="51984-117">The <xref:System.Drawing.FontFamily> object specifies the typeface (for example, Arial), and the <xref:System.Drawing.Font> object specifies the size, style, and units.</span></span>  
  
## <a name="example"></a><span data-ttu-id="51984-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="51984-118">Example</span></span>  
 <span data-ttu-id="51984-119">Nell'esempio seguente viene costruito un tipo di carattere Arial di stile normale con una dimensione di 16 pixel.</span><span class="sxs-lookup"><span data-stu-id="51984-119">The following example constructs a regular style Arial font with a size of 16 pixels.</span></span> <span data-ttu-id="51984-120">Nel codice seguente, il primo argomento passato al <xref:System.Drawing.Font.%23ctor%2A> costruttore è l' <xref:System.Drawing.FontFamily> oggetto.</span><span class="sxs-lookup"><span data-stu-id="51984-120">In the following code, the first argument passed to the <xref:System.Drawing.Font.%23ctor%2A> constructor is the <xref:System.Drawing.FontFamily> object.</span></span> <span data-ttu-id="51984-121">Il secondo argomento specifica la dimensione del tipo di carattere misurato in unità identificate dal quarto argomento.</span><span class="sxs-lookup"><span data-stu-id="51984-121">The second argument specifies the size of the font measured in units identified by the fourth argument.</span></span> <span data-ttu-id="51984-122">Il terzo argomento identifica lo stile.</span><span class="sxs-lookup"><span data-stu-id="51984-122">The third argument identifies the style.</span></span>  
  
 <span data-ttu-id="51984-123"><xref:System.Drawing.GraphicsUnit.Pixel> è un membro dell' <xref:System.Drawing.GraphicsUnit> enumerazione e <xref:System.Drawing.FontStyle.Regular> è un membro dell' <xref:System.Drawing.FontStyle> enumerazione.</span><span class="sxs-lookup"><span data-stu-id="51984-123"><xref:System.Drawing.GraphicsUnit.Pixel> is a member of the <xref:System.Drawing.GraphicsUnit> enumeration, and <xref:System.Drawing.FontStyle.Regular> is a member of the <xref:System.Drawing.FontStyle> enumeration.</span></span>  
  
 [!code-csharp[System.Drawing.FontsAndText#61](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#61)]
 [!code-vb[System.Drawing.FontsAndText#61](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#61)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="51984-124">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="51984-124">Compiling the Code</span></span>  
 <span data-ttu-id="51984-125">L'esempio precedente è progettato per l'uso con Windows Forms e richiede <xref:System.Windows.Forms.PaintEventArgs> `e` , che è un parametro di <xref:System.Windows.Forms.PaintEventHandler> .</span><span class="sxs-lookup"><span data-stu-id="51984-125">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of <xref:System.Windows.Forms.PaintEventHandler>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51984-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="51984-126">See also</span></span>

- [<span data-ttu-id="51984-127">Utilizzo di tipi di carattere e testo</span><span class="sxs-lookup"><span data-stu-id="51984-127">Using Fonts and Text</span></span>](using-fonts-and-text.md)
- [<span data-ttu-id="51984-128">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="51984-128">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
