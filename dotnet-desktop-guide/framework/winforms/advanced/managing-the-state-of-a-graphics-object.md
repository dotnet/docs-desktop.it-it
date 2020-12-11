---
title: Gestione dello stato di un oggetto Graphics
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- graphics [Windows Forms], managing state
- graphics [Windows Forms], clipping
ms.assetid: 6207cad1-7a34-4bd6-bfc1-db823ca7a73e
ms.openlocfilehash: d1e7e6eac775ca779fb68605adcc9bc2b9915e49
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962404"
---
# <a name="managing-the-state-of-a-graphics-object"></a><span data-ttu-id="c087a-102">Gestione dello stato di un oggetto Graphics</span><span class="sxs-lookup"><span data-stu-id="c087a-102">Managing the State of a Graphics Object</span></span>
<span data-ttu-id="c087a-103">La <xref:System.Drawing.Graphics> classe è alla base di GDI+.</span><span class="sxs-lookup"><span data-stu-id="c087a-103">The <xref:System.Drawing.Graphics> class is at the heart of GDI+.</span></span> <span data-ttu-id="c087a-104">Per creare qualsiasi elemento, ottenere un <xref:System.Drawing.Graphics> oggetto, impostarne le proprietà e chiamarne <xref:System.Drawing.Graphics.DrawLine%2A> i metodi,, <xref:System.Drawing.Graphics.DrawImage%2A> <xref:System.Drawing.Graphics.DrawString%2A> e like).</span><span class="sxs-lookup"><span data-stu-id="c087a-104">To draw anything, you obtain a <xref:System.Drawing.Graphics> object, set its properties, and call its methods <xref:System.Drawing.Graphics.DrawLine%2A>, <xref:System.Drawing.Graphics.DrawImage%2A>, <xref:System.Drawing.Graphics.DrawString%2A>, and the like).</span></span>  
  
 <span data-ttu-id="c087a-105">Nell'esempio seguente viene chiamato il <xref:System.Drawing.Graphics.DrawRectangle%2A> metodo di un <xref:System.Drawing.Graphics> oggetto.</span><span class="sxs-lookup"><span data-stu-id="c087a-105">The following example calls the <xref:System.Drawing.Graphics.DrawRectangle%2A> method of a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="c087a-106">Il primo argomento passato al <xref:System.Drawing.Graphics.DrawRectangle%2A> metodo è un <xref:System.Drawing.Pen> oggetto.</span><span class="sxs-lookup"><span data-stu-id="c087a-106">The first argument passed to the <xref:System.Drawing.Graphics.DrawRectangle%2A> method is a <xref:System.Drawing.Pen> object.</span></span>  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Blue) ' Opaque blue  
graphics.DrawRectangle(pen, 10, 10, 200, 100)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Blue);  // Opaque blue  
graphics.DrawRectangle(pen, 10, 10, 200, 100);  
```  
  
## <a name="graphics-state"></a><span data-ttu-id="c087a-107">Stato grafica</span><span class="sxs-lookup"><span data-stu-id="c087a-107">Graphics State</span></span>  
 <span data-ttu-id="c087a-108">Un <xref:System.Drawing.Graphics> oggetto non fornisce più di metodi di disegno, ad esempio <xref:System.Drawing.Graphics.DrawLine%2A> e <xref:System.Drawing.Graphics.DrawRectangle%2A> .</span><span class="sxs-lookup"><span data-stu-id="c087a-108">A <xref:System.Drawing.Graphics> object does more than provide drawing methods, such as <xref:System.Drawing.Graphics.DrawLine%2A> and <xref:System.Drawing.Graphics.DrawRectangle%2A>.</span></span> <span data-ttu-id="c087a-109">Un <xref:System.Drawing.Graphics> oggetto gestisce anche lo stato della grafica, che può essere suddiviso nelle categorie seguenti:</span><span class="sxs-lookup"><span data-stu-id="c087a-109">A <xref:System.Drawing.Graphics> object also maintains graphics state, which can be divided into the following categories:</span></span>  
  
- <span data-ttu-id="c087a-110">Impostazioni qualità</span><span class="sxs-lookup"><span data-stu-id="c087a-110">Quality settings</span></span>  
  
- <span data-ttu-id="c087a-111">Trasformazioni</span><span class="sxs-lookup"><span data-stu-id="c087a-111">Transformations</span></span>  
  
- <span data-ttu-id="c087a-112">Area di visualizzazione</span><span class="sxs-lookup"><span data-stu-id="c087a-112">Clipping region</span></span>  
  
### <a name="quality-settings"></a><span data-ttu-id="c087a-113">Impostazioni qualità</span><span class="sxs-lookup"><span data-stu-id="c087a-113">Quality Settings</span></span>  
 <span data-ttu-id="c087a-114">Un <xref:System.Drawing.Graphics> oggetto dispone di diverse proprietà che influiscono sulla qualità degli elementi disegnati.</span><span class="sxs-lookup"><span data-stu-id="c087a-114">A <xref:System.Drawing.Graphics> object has several properties that influence the quality of the items that are drawn.</span></span> <span data-ttu-id="c087a-115">Ad esempio, è possibile impostare la <xref:System.Drawing.Graphics.TextRenderingHint%2A> proprietà per specificare il tipo di anti-aliasing applicato al testo.</span><span class="sxs-lookup"><span data-stu-id="c087a-115">For example, you can set the <xref:System.Drawing.Graphics.TextRenderingHint%2A> property to specify the type of antialiasing (if any) applied to text.</span></span> <span data-ttu-id="c087a-116">Altre proprietà che influenzano la qualità sono <xref:System.Drawing.Graphics.SmoothingMode%2A> ,, <xref:System.Drawing.Graphics.CompositingMode%2A> <xref:System.Drawing.Graphics.CompositingQuality%2A> e <xref:System.Drawing.Graphics.InterpolationMode%2A> .</span><span class="sxs-lookup"><span data-stu-id="c087a-116">Other properties that influence quality are <xref:System.Drawing.Graphics.SmoothingMode%2A>, <xref:System.Drawing.Graphics.CompositingMode%2A>, <xref:System.Drawing.Graphics.CompositingQuality%2A>, and <xref:System.Drawing.Graphics.InterpolationMode%2A>.</span></span>  
  
 <span data-ttu-id="c087a-117">L'esempio seguente disegna due ellissi, una con la modalità di smussamento impostata su <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> e una con la modalità di smussatura impostata su <xref:System.Drawing.Drawing2D.SmoothingMode.HighSpeed> :</span><span class="sxs-lookup"><span data-stu-id="c087a-117">The following example draws two ellipses, one with the smoothing mode set to <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> and one with the smoothing mode set to <xref:System.Drawing.Drawing2D.SmoothingMode.HighSpeed>:</span></span>  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Blue)  
  
graphics.SmoothingMode = SmoothingMode.AntiAlias  
graphics.DrawEllipse(pen, 0, 0, 200, 100)  
graphics.SmoothingMode = SmoothingMode.HighSpeed  
graphics.DrawEllipse(pen, 0, 150, 200, 100)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Blue);  
  
graphics.SmoothingMode = SmoothingMode.AntiAlias;  
graphics.DrawEllipse(pen, 0, 0, 200, 100);  
graphics.SmoothingMode = SmoothingMode.HighSpeed;  
graphics.DrawEllipse(pen, 0, 150, 200, 100);  
```  
  
### <a name="transformations"></a><span data-ttu-id="c087a-118">Trasformazioni</span><span class="sxs-lookup"><span data-stu-id="c087a-118">Transformations</span></span>  
 <span data-ttu-id="c087a-119">Un <xref:System.Drawing.Graphics> oggetto gestisce due trasformazioni (mondo e pagina) che vengono applicate a tutti gli elementi disegnati da tale <xref:System.Drawing.Graphics> oggetto.</span><span class="sxs-lookup"><span data-stu-id="c087a-119">A <xref:System.Drawing.Graphics> object maintains two transformations (world and page) that are applied to all items drawn by that <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="c087a-120">Qualsiasi trasformazione affine può essere archiviata nella trasformazione globale.</span><span class="sxs-lookup"><span data-stu-id="c087a-120">Any affine transformation can be stored in the world transformation.</span></span> <span data-ttu-id="c087a-121">Le trasformazioni affini includono il ridimensionamento, la rotazione, la reflection, la distorsione e la conversione.</span><span class="sxs-lookup"><span data-stu-id="c087a-121">Affine transformations include scaling, rotating, reflecting, skewing, and translating.</span></span> <span data-ttu-id="c087a-122">La trasformazione pagina può essere utilizzata per la scalabilità e per la modifica delle unità, ad esempio da pixel a pollici.</span><span class="sxs-lookup"><span data-stu-id="c087a-122">The page transformation can be used for scaling and for changing units (for example, pixels to inches).</span></span> <span data-ttu-id="c087a-123">Per ulteriori informazioni, vedere [sistemi di coordinate e trasformazioni](coordinate-systems-and-transformations.md).</span><span class="sxs-lookup"><span data-stu-id="c087a-123">For more information, see [Coordinate Systems and Transformations](coordinate-systems-and-transformations.md).</span></span>  
  
 <span data-ttu-id="c087a-124">Nell'esempio seguente vengono impostate le trasformazioni globali e di pagina di un <xref:System.Drawing.Graphics> oggetto.</span><span class="sxs-lookup"><span data-stu-id="c087a-124">The following example sets the world and page transformations of a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="c087a-125">La trasformazione globale è impostata su una rotazione di 30 gradi.</span><span class="sxs-lookup"><span data-stu-id="c087a-125">The world transformation is set to a 30-degree rotation.</span></span> <span data-ttu-id="c087a-126">La trasformazione pagina viene impostata in modo che le coordinate passate al secondo <xref:System.Drawing.Graphics.DrawEllipse%2A> verranno considerate millimetri anziché pixel.</span><span class="sxs-lookup"><span data-stu-id="c087a-126">The page transformation is set so that the coordinates passed to the second <xref:System.Drawing.Graphics.DrawEllipse%2A> will be treated as millimeters instead of pixels.</span></span> <span data-ttu-id="c087a-127">Il codice effettua due chiamate identiche al <xref:System.Drawing.Graphics.DrawEllipse%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="c087a-127">The code makes two identical calls to the <xref:System.Drawing.Graphics.DrawEllipse%2A> method.</span></span> <span data-ttu-id="c087a-128">La trasformazione globale viene applicata alla prima <xref:System.Drawing.Graphics.DrawEllipse%2A> chiamata ed entrambe le trasformazioni (mondo e pagina) vengono applicate alla seconda <xref:System.Drawing.Graphics.DrawEllipse%2A> chiamata.</span><span class="sxs-lookup"><span data-stu-id="c087a-128">The world transformation is applied to the first <xref:System.Drawing.Graphics.DrawEllipse%2A> call, and both transformations (world and page) are applied to the second <xref:System.Drawing.Graphics.DrawEllipse%2A> call.</span></span>  
  
```vb  
Dim graphics As Graphics = e.Graphics  
Dim pen As New Pen(Color.Red)  
  
graphics.ResetTransform()  
graphics.RotateTransform(30) ' world transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50)  
graphics.PageUnit = GraphicsUnit.Millimeter ' page transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
Pen pen = new Pen(Color.Red);
  
graphics.ResetTransform();  
graphics.RotateTransform(30);                    // world transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50);  
graphics.PageUnit = GraphicsUnit.Millimeter;     // page transformation  
graphics.DrawEllipse(pen, 0, 0, 100, 50);  
```  
  
 <span data-ttu-id="c087a-129">Nella figura seguente sono illustrati i due ellissi.</span><span class="sxs-lookup"><span data-stu-id="c087a-129">The following illustration shows the two ellipses.</span></span> <span data-ttu-id="c087a-130">Si noti che la rotazione di 30 gradi riguarda l'origine del sistema di coordinate (angolo superiore sinistro dell'area client), non dei centri dei puntini di sospensione.</span><span class="sxs-lookup"><span data-stu-id="c087a-130">Note that the 30-degree rotation is about the origin of the coordinate system (upper-left corner of the client area), not about the centers of the ellipses.</span></span> <span data-ttu-id="c087a-131">Si noti inoltre che la larghezza della penna di 1 indica 1 pixel per la prima ellisse e 1 millimetro per la seconda ellisse.</span><span class="sxs-lookup"><span data-stu-id="c087a-131">Also note that the pen width of 1 means 1 pixel for the first ellipse and 1 millimeter for the second ellipse.</span></span>  
  
 ![Illustrazione che mostra due ellissi: rotazione e larghezza della penna.](./media/managing-the-state-of-a-graphics-object/set-rotation-pen-width-drawellipse-method.png)  
  
### <a name="clipping-region"></a><span data-ttu-id="c087a-133">Area di visualizzazione</span><span class="sxs-lookup"><span data-stu-id="c087a-133">Clipping Region</span></span>  
 <span data-ttu-id="c087a-134">Un <xref:System.Drawing.Graphics> oggetto mantiene un'area di ridimensionamento che si applica a tutti gli elementi disegnati da tale <xref:System.Drawing.Graphics> oggetto.</span><span class="sxs-lookup"><span data-stu-id="c087a-134">A <xref:System.Drawing.Graphics> object maintains a clipping region that applies to all items drawn by that <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="c087a-135">È possibile impostare l'area di ridimensionamento chiamando il <xref:System.Drawing.Graphics.SetClip%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="c087a-135">You can set the clipping region by calling the <xref:System.Drawing.Graphics.SetClip%2A> method.</span></span>  
  
 <span data-ttu-id="c087a-136">Nell'esempio seguente viene creata un'area con più forme formando l'Unione di due rettangoli.</span><span class="sxs-lookup"><span data-stu-id="c087a-136">The following example creates a plus-shaped region by forming the union of two rectangles.</span></span> <span data-ttu-id="c087a-137">Tale area viene designata come area di visualizzazione di un <xref:System.Drawing.Graphics> oggetto.</span><span class="sxs-lookup"><span data-stu-id="c087a-137">That region is designated as the clipping region of a <xref:System.Drawing.Graphics> object.</span></span> <span data-ttu-id="c087a-138">Il codice disegna quindi due righe limitate all'interno dell'area di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="c087a-138">Then the code draws two lines that are restricted to the interior of the clipping region.</span></span>  
  
```vb  
Dim graphics As Graphics = e.Graphics  
  
' Opaque red, width 5  
Dim pen As New Pen(Color.Red, 5)  
  
' Opaque aqua  
Dim brush As New SolidBrush(Color.FromArgb(255, 180, 255, 255))  
  
' Create a plus-shaped region by forming the union of two rectangles.  
Dim [region] As New [Region](New Rectangle(50, 0, 50, 150))  
[region].Union(New Rectangle(0, 50, 150, 50))  
graphics.FillRegion(brush, [region])  
  
' Set the clipping region.  
graphics.SetClip([region], CombineMode.Replace)  
  
' Draw two clipped lines.  
graphics.DrawLine(pen, 0, 30, 150, 160)  
graphics.DrawLine(pen, 40, 20, 190, 150)  
```  
  
```csharp  
Graphics graphics = e.Graphics;  
  
// Opaque red, width 5  
Pen pen = new Pen(Color.Red, 5);
  
// Opaque aqua  
SolidBrush brush = new SolidBrush(Color.FromArgb(255, 180, 255, 255));
  
// Create a plus-shaped region by forming the union of two rectangles.  
Region region = new Region(new Rectangle(50, 0, 50, 150));  
region.Union(new Rectangle(0, 50, 150, 50));  
graphics.FillRegion(brush, region);  
  
// Set the clipping region.  
graphics.SetClip(region, CombineMode.Replace);  
  
// Draw two clipped lines.  
graphics.DrawLine(pen, 0, 30, 150, 160);  
graphics.DrawLine(pen, 40, 20, 190, 150);  
```  
  
 <span data-ttu-id="c087a-139">Nella figura seguente sono illustrate le righe ritagliate:</span><span class="sxs-lookup"><span data-stu-id="c087a-139">The following illustration shows the clipped lines:</span></span>  
  
 ![Diagramma che mostra l'area di ritaglio limitata.](./media/managing-the-state-of-a-graphics-object/set-clipping-region-setclip-method.png)  
  
## <a name="see-also"></a><span data-ttu-id="c087a-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c087a-141">See also</span></span>

- [<span data-ttu-id="c087a-142">Grafica e disegno in Windows Form</span><span class="sxs-lookup"><span data-stu-id="c087a-142">Graphics and Drawing in Windows Forms</span></span>](graphics-and-drawing-in-windows-forms.md)
- [<span data-ttu-id="c087a-143">Utilizzo di contenitori di grafica annidati</span><span class="sxs-lookup"><span data-stu-id="c087a-143">Using Nested Graphics Containers</span></span>](using-nested-graphics-containers.md)
