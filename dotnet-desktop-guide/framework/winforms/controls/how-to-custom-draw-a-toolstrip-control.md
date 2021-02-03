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
# <a name="how-to-custom-draw-a-toolstrip-control"></a><span data-ttu-id="fe857-102">Procedura: Eseguire un disegno personalizzato di un controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="fe857-102">How to: Custom Draw a ToolStrip Control</span></span>
<span data-ttu-id="fe857-103">Ai controlli <xref:System.Windows.Forms.ToolStrip> sono associate le classi di rendering (disegno) seguenti:</span><span class="sxs-lookup"><span data-stu-id="fe857-103">The <xref:System.Windows.Forms.ToolStrip> controls have the following associated rendering (painting) classes:</span></span>  
  
- <span data-ttu-id="fe857-104"><xref:System.Windows.Forms.ToolStripSystemRenderer> fornisce l'aspetto e lo stile del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="fe857-104"><xref:System.Windows.Forms.ToolStripSystemRenderer> provides the appearance and style of your operating system.</span></span>  
  
- <span data-ttu-id="fe857-105"><xref:System.Windows.Forms.ToolStripProfessionalRenderer> fornisce l'aspetto e lo stile di Microsoft Office.</span><span class="sxs-lookup"><span data-stu-id="fe857-105"><xref:System.Windows.Forms.ToolStripProfessionalRenderer> provides the appearance and style of Microsoft Office.</span></span>  
  
- <span data-ttu-id="fe857-106"><xref:System.Windows.Forms.ToolStripRenderer> è la classe di base astratta per le altre due classi di rendering.</span><span class="sxs-lookup"><span data-stu-id="fe857-106"><xref:System.Windows.Forms.ToolStripRenderer> is the abstract base class for the other two rendering classes.</span></span>  
  
 <span data-ttu-id="fe857-107">Per disegnare un controllo <xref:System.Windows.Forms.ToolStrip> personalizzato (modalità nota anche come "Owner Draw"), è possibile eseguire l'override di una delle classi renderer e modificare un aspetto della logica di rendering.</span><span class="sxs-lookup"><span data-stu-id="fe857-107">To custom draw (also known as owner draw) a <xref:System.Windows.Forms.ToolStrip>, you can override one of the renderer classes and change an aspect of the rendering logic.</span></span>  
  
 <span data-ttu-id="fe857-108">Le procedure seguenti descrivono vari aspetti del disegno personalizzato.</span><span class="sxs-lookup"><span data-stu-id="fe857-108">The following procedures describe various aspects of custom drawing.</span></span>  
  
## <a name="switch-between-the-provided-renderers"></a><span data-ttu-id="fe857-109">Passa tra i renderer forniti</span><span class="sxs-lookup"><span data-stu-id="fe857-109">Switch between the provided renderers</span></span>
  
- <span data-ttu-id="fe857-110">Impostare la proprietà <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> sul valore <xref:System.Windows.Forms.ToolStripRenderMode> desiderato.</span><span class="sxs-lookup"><span data-stu-id="fe857-110">Set the <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> property to the <xref:System.Windows.Forms.ToolStripRenderMode> value you want.</span></span>  
  
     <span data-ttu-id="fe857-111">Con <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode> la proprietà statica <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> determina il renderer per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="fe857-111">With <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>, the static <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> determines the renderer for your application.</span></span> <span data-ttu-id="fe857-112">Gli altri valori di <xref:System.Windows.Forms.ToolStripRenderMode> sono <xref:System.Windows.Forms.ToolStripRenderMode.Custom>, <xref:System.Windows.Forms.ToolStripRenderMode.Professional> e <xref:System.Windows.Forms.ToolStripRenderMode.System>.</span><span class="sxs-lookup"><span data-stu-id="fe857-112">The other values of <xref:System.Windows.Forms.ToolStripRenderMode> are <xref:System.Windows.Forms.ToolStripRenderMode.Custom>, <xref:System.Windows.Forms.ToolStripRenderMode.Professional>, and <xref:System.Windows.Forms.ToolStripRenderMode.System>.</span></span>  
  
## <a name="change-the-officestyle-borders"></a><span data-ttu-id="fe857-113">Modificare i bordi di tipo Office</span><span class="sxs-lookup"><span data-stu-id="fe857-113">Change the Office–style borders</span></span>
  
- <span data-ttu-id="fe857-114">Eseguire l'override di <xref:System.Windows.Forms.ToolStripProfessionalRenderer.OnRenderToolStripBorder%2A?displayProperty=nameWithType>, ma senza chiamare la classe di base.</span><span class="sxs-lookup"><span data-stu-id="fe857-114">Override <xref:System.Windows.Forms.ToolStripProfessionalRenderer.OnRenderToolStripBorder%2A?displayProperty=nameWithType>, but do not call the base class.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fe857-115">Esiste una versione di questo metodo per <xref:System.Windows.Forms.ToolStripRenderer>, <xref:System.Windows.Forms.ToolStripSystemRenderer> e <xref:System.Windows.Forms.ToolStripProfessionalRenderer>.</span><span class="sxs-lookup"><span data-stu-id="fe857-115">There is a version of this method for <xref:System.Windows.Forms.ToolStripRenderer>, <xref:System.Windows.Forms.ToolStripSystemRenderer>, and <xref:System.Windows.Forms.ToolStripProfessionalRenderer>.</span></span>  
  
## <a name="change-the-professionalcolortable"></a><span data-ttu-id="fe857-116">Modificare il ProfessionalColorTable</span><span class="sxs-lookup"><span data-stu-id="fe857-116">Change the ProfessionalColorTable</span></span>
  
- <span data-ttu-id="fe857-117">Eseguire l'override di <xref:System.Windows.Forms.ProfessionalColorTable> e cambiare i colori desiderati.</span><span class="sxs-lookup"><span data-stu-id="fe857-117">Override <xref:System.Windows.Forms.ProfessionalColorTable> and change the colors you want.</span></span>  

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
  
## <a name="change-rendering-for-all-toolstrips"></a><span data-ttu-id="fe857-118">Modificare il rendering per tutti gli ToolStrip</span><span class="sxs-lookup"><span data-stu-id="fe857-118">Change rendering for all ToolStrips</span></span>
  
1. <span data-ttu-id="fe857-119">Usare la proprietà <xref:System.Windows.Forms.ToolStripManager.RenderMode%2A?displayProperty=nameWithType> per scegliere uno dei renderer forniti.</span><span class="sxs-lookup"><span data-stu-id="fe857-119">Use the <xref:System.Windows.Forms.ToolStripManager.RenderMode%2A?displayProperty=nameWithType> property to choose one of the provided renderers.</span></span>  
  
2. <span data-ttu-id="fe857-120">Usare <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> per assegnare un renderer personalizzato.</span><span class="sxs-lookup"><span data-stu-id="fe857-120">Use <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> to assign a custom renderer.</span></span>  
  
3. <span data-ttu-id="fe857-121">Accertarsi che <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> sia impostata sul valore predefinito di <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>.</span><span class="sxs-lookup"><span data-stu-id="fe857-121">Ensure that <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> is set to the default value of <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>.</span></span>  
  
## <a name="turn-off-the-office-colors"></a><span data-ttu-id="fe857-122">Disattiva colori Office</span><span class="sxs-lookup"><span data-stu-id="fe857-122">Turn off the Office colors</span></span>
  
- <span data-ttu-id="fe857-123">Impostare <xref:System.Windows.Forms.ToolStripManager.VisualStylesEnabled%2A?displayProperty=nameWithType> su `false`.</span><span class="sxs-lookup"><span data-stu-id="fe857-123">Set <xref:System.Windows.Forms.ToolStripManager.VisualStylesEnabled%2A?displayProperty=nameWithType> to `false`.</span></span>  
  
## <a name="turn-off-the-office-colors-for-one-toolstrip"></a><span data-ttu-id="fe857-124">Disattiva i colori dell'ufficio per un ToolStrip</span><span class="sxs-lookup"><span data-stu-id="fe857-124">Turn off the Office colors for one ToolStrip</span></span>
  
- <span data-ttu-id="fe857-125">Usare codice simile all'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="fe857-125">Use code similar to the following code example.</span></span>  

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
  
## <a name="see-also"></a><span data-ttu-id="fe857-126">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="fe857-126">See also</span></span>

- <xref:System.Windows.Forms.ToolStripSystemRenderer>
- <xref:System.Windows.Forms.ToolStripProfessionalRenderer>
- <xref:System.Windows.Forms.ToolStripRenderer>
- [<span data-ttu-id="fe857-127">Controlli con supporto incorporato per la creazione da parte del proprietario</span><span class="sxs-lookup"><span data-stu-id="fe857-127">Controls with Built-In Owner-Drawing Support</span></span>](controls-with-built-in-owner-drawing-support.md)
- [<span data-ttu-id="fe857-128">Procedura: creare e impostare un renderer personalizzato per il controllo ToolStrip in Windows Form</span><span class="sxs-lookup"><span data-stu-id="fe857-128">How to: Create and Set a Custom Renderer for the ToolStrip Control in Windows Forms</span></span>](create-and-set-a-custom-renderer-for-the-toolstrip-control-in-wf.md)
- [<span data-ttu-id="fe857-129">Panoramica del controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="fe857-129">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
