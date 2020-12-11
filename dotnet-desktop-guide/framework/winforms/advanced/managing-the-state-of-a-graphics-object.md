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
# <a name="managing-the-state-of-a-graphics-object"></a>Gestione dello stato di un oggetto Graphics
La <xref:System.Drawing.Graphics> classe è alla base di GDI+. Per creare qualsiasi elemento, ottenere un <xref:System.Drawing.Graphics> oggetto, impostarne le proprietà e chiamarne <xref:System.Drawing.Graphics.DrawLine%2A> i metodi,, <xref:System.Drawing.Graphics.DrawImage%2A> <xref:System.Drawing.Graphics.DrawString%2A> e like).  
  
 Nell'esempio seguente viene chiamato il <xref:System.Drawing.Graphics.DrawRectangle%2A> metodo di un <xref:System.Drawing.Graphics> oggetto. Il primo argomento passato al <xref:System.Drawing.Graphics.DrawRectangle%2A> metodo è un <xref:System.Drawing.Pen> oggetto.  
  
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
  
## <a name="graphics-state"></a>Stato grafica  
 Un <xref:System.Drawing.Graphics> oggetto non fornisce più di metodi di disegno, ad esempio <xref:System.Drawing.Graphics.DrawLine%2A> e <xref:System.Drawing.Graphics.DrawRectangle%2A> . Un <xref:System.Drawing.Graphics> oggetto gestisce anche lo stato della grafica, che può essere suddiviso nelle categorie seguenti:  
  
- Impostazioni qualità  
  
- Trasformazioni  
  
- Area di visualizzazione  
  
### <a name="quality-settings"></a>Impostazioni qualità  
 Un <xref:System.Drawing.Graphics> oggetto dispone di diverse proprietà che influiscono sulla qualità degli elementi disegnati. Ad esempio, è possibile impostare la <xref:System.Drawing.Graphics.TextRenderingHint%2A> proprietà per specificare il tipo di anti-aliasing applicato al testo. Altre proprietà che influenzano la qualità sono <xref:System.Drawing.Graphics.SmoothingMode%2A> ,, <xref:System.Drawing.Graphics.CompositingMode%2A> <xref:System.Drawing.Graphics.CompositingQuality%2A> e <xref:System.Drawing.Graphics.InterpolationMode%2A> .  
  
 L'esempio seguente disegna due ellissi, una con la modalità di smussamento impostata su <xref:System.Drawing.Drawing2D.SmoothingMode.AntiAlias> e una con la modalità di smussatura impostata su <xref:System.Drawing.Drawing2D.SmoothingMode.HighSpeed> :  
  
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
  
### <a name="transformations"></a>Trasformazioni  
 Un <xref:System.Drawing.Graphics> oggetto gestisce due trasformazioni (mondo e pagina) che vengono applicate a tutti gli elementi disegnati da tale <xref:System.Drawing.Graphics> oggetto. Qualsiasi trasformazione affine può essere archiviata nella trasformazione globale. Le trasformazioni affini includono il ridimensionamento, la rotazione, la reflection, la distorsione e la conversione. La trasformazione pagina può essere utilizzata per la scalabilità e per la modifica delle unità, ad esempio da pixel a pollici. Per ulteriori informazioni, vedere [sistemi di coordinate e trasformazioni](coordinate-systems-and-transformations.md).  
  
 Nell'esempio seguente vengono impostate le trasformazioni globali e di pagina di un <xref:System.Drawing.Graphics> oggetto. La trasformazione globale è impostata su una rotazione di 30 gradi. La trasformazione pagina viene impostata in modo che le coordinate passate al secondo <xref:System.Drawing.Graphics.DrawEllipse%2A> verranno considerate millimetri anziché pixel. Il codice effettua due chiamate identiche al <xref:System.Drawing.Graphics.DrawEllipse%2A> metodo. La trasformazione globale viene applicata alla prima <xref:System.Drawing.Graphics.DrawEllipse%2A> chiamata ed entrambe le trasformazioni (mondo e pagina) vengono applicate alla seconda <xref:System.Drawing.Graphics.DrawEllipse%2A> chiamata.  
  
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
  
 Nella figura seguente sono illustrati i due ellissi. Si noti che la rotazione di 30 gradi riguarda l'origine del sistema di coordinate (angolo superiore sinistro dell'area client), non dei centri dei puntini di sospensione. Si noti inoltre che la larghezza della penna di 1 indica 1 pixel per la prima ellisse e 1 millimetro per la seconda ellisse.  
  
 ![Illustrazione che mostra due ellissi: rotazione e larghezza della penna.](./media/managing-the-state-of-a-graphics-object/set-rotation-pen-width-drawellipse-method.png)  
  
### <a name="clipping-region"></a>Area di visualizzazione  
 Un <xref:System.Drawing.Graphics> oggetto mantiene un'area di ridimensionamento che si applica a tutti gli elementi disegnati da tale <xref:System.Drawing.Graphics> oggetto. È possibile impostare l'area di ridimensionamento chiamando il <xref:System.Drawing.Graphics.SetClip%2A> metodo.  
  
 Nell'esempio seguente viene creata un'area con più forme formando l'Unione di due rettangoli. Tale area viene designata come area di visualizzazione di un <xref:System.Drawing.Graphics> oggetto. Il codice disegna quindi due righe limitate all'interno dell'area di visualizzazione.  
  
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
  
 Nella figura seguente sono illustrate le righe ritagliate:  
  
 ![Diagramma che mostra l'area di ritaglio limitata.](./media/managing-the-state-of-a-graphics-object/set-clipping-region-setclip-method.png)  
  
## <a name="see-also"></a>Vedere anche

- [Grafica e disegno in Windows Form](graphics-and-drawing-in-windows-forms.md)
- [Utilizzo di contenitori di grafica annidati](using-nested-graphics-containers.md)
