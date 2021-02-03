---
title: 'Procedura: Eseguire un disegno personalizzato di un controllo ToolStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- toolbars [Windows Forms], custom drawing
- drawing [Windows Forms], owner
- ProfessionalColorTable class [Windows Forms], overriding
- examples [Windows Forms], toolbars
- drawing [Windows Forms], custom
- toolbars [Windows Forms], changing colors
- ToolStrip control [Windows Forms], drawing
- ToolStrip control [Windows Forms], changing colors
- custom drawing
- owner drawing
ms.assetid: 94e7d7bd-a752-441c-b5b3-7acf98881163
ms.openlocfilehash: 9f34c0d62370b72de2c3ddf68fcc5fada918faa3
ms.sourcegitcommit: d7d89e96c827b6e20d9353d34c0aa329fdae0144
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2021
ms.locfileid: "99506672"
---
# <a name="how-to-custom-draw-a-toolstrip-control"></a>Procedura: Eseguire un disegno personalizzato di un controllo ToolStrip
Ai controlli <xref:System.Windows.Forms.ToolStrip> sono associate le classi di rendering (disegno) seguenti:  
  
- <xref:System.Windows.Forms.ToolStripSystemRenderer> fornisce l'aspetto e lo stile del sistema operativo.  
  
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer> fornisce l'aspetto e lo stile di Microsoft Office.  
  
- <xref:System.Windows.Forms.ToolStripRenderer> è la classe di base astratta per le altre due classi di rendering.  
  
 Per disegnare un controllo <xref:System.Windows.Forms.ToolStrip> personalizzato (modalità nota anche come "Owner Draw"), è possibile eseguire l'override di una delle classi renderer e modificare un aspetto della logica di rendering.  
  
 Le procedure seguenti descrivono vari aspetti del disegno personalizzato.  
  
## <a name="switch-between-the-provided-renderers"></a>Passa tra i renderer forniti
  
- Impostare la proprietà <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> sul valore <xref:System.Windows.Forms.ToolStripRenderMode> desiderato.  
  
     Con <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode> la proprietà statica <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> determina il renderer per l'applicazione. Gli altri valori di <xref:System.Windows.Forms.ToolStripRenderMode> sono <xref:System.Windows.Forms.ToolStripRenderMode.Custom>, <xref:System.Windows.Forms.ToolStripRenderMode.Professional> e <xref:System.Windows.Forms.ToolStripRenderMode.System>.  
  
## <a name="change-the-officestyle-borders"></a>Modificare i bordi di tipo Office
  
- Eseguire l'override di <xref:System.Windows.Forms.ToolStripProfessionalRenderer.OnRenderToolStripBorder%2A?displayProperty=nameWithType>, ma senza chiamare la classe di base.  
  
> [!NOTE]
> Esiste una versione di questo metodo per <xref:System.Windows.Forms.ToolStripRenderer>, <xref:System.Windows.Forms.ToolStripSystemRenderer> e <xref:System.Windows.Forms.ToolStripProfessionalRenderer>.  
  
## <a name="change-the-professionalcolortable"></a>Modificare il ProfessionalColorTable
  
- Eseguire l'override di <xref:System.Windows.Forms.ProfessionalColorTable> e cambiare i colori desiderati.  

  ```csharp
  public partial class Form1 : Form
  {
      public Form1()
      {
          InitializeComponent();
      }
  
      private void Form1_Load(object sender, EventArgs e)
      {
          var colorTable = new MyColorTable();
          toolStrip1.Renderer = new ToolStripProfessionalRenderer(colorTable);
      }
  
      class MyColorTable: ProfessionalColorTable
      {
          public override System.Drawing.Color ButtonPressedGradientBegin => Color.Red;
          public override System.Drawing.Color ButtonPressedGradientMiddle => Color.Blue;
          public override System.Drawing.Color ButtonPressedGradientEnd => Color.Green;
          public override System.Drawing.Color ButtonSelectedGradientBegin => Color.Yellow;
          public override System.Drawing.Color ButtonSelectedGradientMiddle => Color.Orange;
          public override System.Drawing.Color ButtonSelectedGradientEnd => Color.Violet;
      }
  }
  ```

  ```vb
  Public Class Form1
      Private Sub Form1_Load(sender As Object, e As EventArgs) Handles MyBase.Load
          Dim colorTable As New MyColorTable
          ToolStrip1.Renderer = New ToolStripProfessionalRenderer(colorTable)
      End Sub
  
      Class MyColorTable
          Inherits ProfessionalColorTable
  
          Public Overrides ReadOnly Property ButtonPressedGradientBegin() As System.Drawing.Color
              Get
                  Return Color.Red
              End Get
          End Property
  
          Public Overrides ReadOnly Property ButtonPressedGradientMiddle() As System.Drawing.Color
              Get
                  Return Color.Blue
              End Get
          End Property
  
          Public Overrides ReadOnly Property ButtonPressedGradientEnd() As System.Drawing.Color
              Get
                  Return Color.Green
              End Get
          End Property
  
          Public Overrides ReadOnly Property ButtonSelectedGradientBegin() As System.Drawing.Color
              Get
                  Return Color.Yellow
              End Get
          End Property
  
          Public Overrides ReadOnly Property ButtonSelectedGradientMiddle() As System.Drawing.Color
              Get
                  Return Color.Orange
              End Get
          End Property
  
          Public Overrides ReadOnly Property ButtonSelectedGradientEnd() As System.Drawing.Color
              Get
                  Return Color.Violet
              End Get
          End Property
      End Class
  End Class
  ```
  
## <a name="change-rendering-for-all-toolstrips"></a>Modificare il rendering per tutti gli ToolStrip
  
1. Usare la proprietà <xref:System.Windows.Forms.ToolStripManager.RenderMode%2A?displayProperty=nameWithType> per scegliere uno dei renderer forniti.  
  
2. Usare <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> per assegnare un renderer personalizzato.  
  
3. Accertarsi che <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> sia impostata sul valore predefinito di <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>.  
  
## <a name="turn-off-the-office-colors"></a>Disattiva colori Office
  
- Impostare <xref:System.Windows.Forms.ToolStripManager.VisualStylesEnabled%2A?displayProperty=nameWithType> su `false`.  
  
## <a name="turn-off-the-office-colors-for-one-toolstrip"></a>Disattiva i colori dell'ufficio per un ToolStrip
  
- Usare codice simile all'esempio seguente.  

  ```csharp
  ProfessionalColorTable colorTable = new ProfessionalColorTable();
  colorTable.UseSystemColors = true;
  toolStrip1.Renderer = new ToolStripProfessionalRenderer(colorTable);
  ```
  
  ```vb
  Dim colorTable As New ProfessionalColorTable
  colorTable.UseSystemColors = True
  ToolStrip1.Renderer = new ToolStripProfessionalRenderer(colorTable)
  ```
  
## <a name="see-also"></a>Vedi anche

- <xref:System.Windows.Forms.ToolStripSystemRenderer>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
- <xref:System.Windows.Forms.ToolStripRenderer>
- [Controlli con supporto incorporato per la creazione da parte del proprietario](controls-with-built-in-owner-drawing-support.md)
- [Procedura: creare e impostare un renderer personalizzato per il controllo ToolStrip in Windows Form](create-and-set-a-custom-renderer-for-the-toolstrip-control-in-wf.md)
- [Panoramica del controllo ToolStrip](toolstrip-control-overview-windows-forms.md)
