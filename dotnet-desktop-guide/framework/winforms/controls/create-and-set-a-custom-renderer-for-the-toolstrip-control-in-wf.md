---
title: 'Procedura: creare e impostare un renderer personalizzato per il controllo ToolStrip'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ToolStrip control [Windows Forms], custom rendering
- toolbars [Windows Forms], rendering
- examples [Windows Forms], toolbars
- ToolStrip control [Windows Forms], rendering
ms.assetid: 88a804ba-679f-4ba3-938a-0dc396199c5b
ms.openlocfilehash: 49db0d785155f19b7220ac64011eaf4253aaa7e9
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951155"
---
# <a name="how-to-create-and-set-a-custom-renderer-for-the-toolstrip-control-in-windows-forms"></a><span data-ttu-id="7631a-102">Procedura: Creare e impostare un renderer personalizzato per il controllo ToolStrip in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="7631a-102">How to: Create and Set a Custom Renderer for the ToolStrip Control in Windows Forms</span></span>
<span data-ttu-id="7631a-103"><xref:System.Windows.Forms.ToolStrip> i controlli offrono un supporto semplice per temi e stili.</span><span class="sxs-lookup"><span data-stu-id="7631a-103"><xref:System.Windows.Forms.ToolStrip> controls give easy support to themes and styles.</span></span> <span data-ttu-id="7631a-104">È possibile ottenere un aspetto e un comportamento completamente personalizzati impostando la <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> proprietà o la <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> proprietà su un renderer personalizzato.</span><span class="sxs-lookup"><span data-stu-id="7631a-104">You can achieve completely custom appearance and behavior (look and feel) by setting either the <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> property or the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property to a custom renderer.</span></span>  
  
 <span data-ttu-id="7631a-105">È possibile assegnare i renderer a ogni singolo <xref:System.Windows.Forms.ToolStrip> controllo,, <xref:System.Windows.Forms.MenuStrip> o oppure <xref:System.Windows.Forms.ContextMenuStrip> <xref:System.Windows.Forms.StatusStrip> è possibile usare la <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> proprietà per influire su tutti gli oggetti impostando la <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> proprietà su <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="7631a-105">You can assign renderers to each individual <xref:System.Windows.Forms.ToolStrip>, <xref:System.Windows.Forms.MenuStrip>, <xref:System.Windows.Forms.ContextMenuStrip>, or <xref:System.Windows.Forms.StatusStrip> control, or you can use the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A> property to affect all objects by setting the <xref:System.Windows.Forms.ToolStrip.RenderMode%2A?displayProperty=nameWithType> property to <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode?displayProperty=nameWithType>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7631a-106"><xref:System.Windows.Forms.ToolStrip.RenderMode%2A> restituisce <xref:System.Windows.Forms.ToolStripRenderMode.Custom> solo se il valore di <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> non è `null` .</span><span class="sxs-lookup"><span data-stu-id="7631a-106"><xref:System.Windows.Forms.ToolStrip.RenderMode%2A> returns <xref:System.Windows.Forms.ToolStripRenderMode.Custom> only if the value of <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> is not `null`.</span></span>  
  
### <a name="to-create-a-custom-renderer"></a><span data-ttu-id="7631a-107">Per creare un renderer personalizzato</span><span class="sxs-lookup"><span data-stu-id="7631a-107">To create a custom renderer</span></span>  
  
1. <span data-ttu-id="7631a-108">Estendere la <xref:System.Windows.Forms.ToolStripRenderer> classe.</span><span class="sxs-lookup"><span data-stu-id="7631a-108">Extend the <xref:System.Windows.Forms.ToolStripRenderer> class.</span></span>  
  
2. <span data-ttu-id="7631a-109">Implementare il rendering personalizzato desiderato eseguendo l'override dell'appropriato *...*</span><span class="sxs-lookup"><span data-stu-id="7631a-109">Implement desired custom rendering by overriding appropriate *On…*</span></span> <span data-ttu-id="7631a-110">Membri di</span><span class="sxs-lookup"><span data-stu-id="7631a-110">members</span></span>  
  
    ```vb  
    Public Class RedTextRenderer  
        Inherits System.Windows.Forms.ToolStripRenderer  
        Protected Overrides Sub OnRenderItemText(ByVal e As _  
            ToolStripItemTextRenderEventArgs)
            e.TextColor = Color.Red  
            e.TextFont = New Font("Helvetica", 7, FontStyle.Bold)  
            MyBase.OnRenderItemText(e)  
        End Sub  
    End Class  
    ```  
  
    ```csharp  
    public class RedTextRenderer : _  
        System.Windows.Forms.ToolStripRenderer  
    {  
        protected override void _  
            OnRenderItemText(ToolStripItemTextRenderEventArgs e)  
        {  
            e.TextColor = Color.Red;  
            e.TextFont = new Font("Helvetica", 7, FontStyle.Bold);  
           base.OnRenderItemText(e);  
        }  
    }  
    ```  
  
### <a name="to-set-the-custom-renderer-to-be-the-current-renderer"></a><span data-ttu-id="7631a-111">Per impostare il renderer personalizzato come renderer corrente</span><span class="sxs-lookup"><span data-stu-id="7631a-111">To set the custom renderer to be the current renderer</span></span>  
  
1. <span data-ttu-id="7631a-112">Per impostare il renderer personalizzato per uno <xref:System.Windows.Forms.ToolStrip> , impostare la <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> proprietà sul renderer personalizzato.</span><span class="sxs-lookup"><span data-stu-id="7631a-112">To set the custom renderer for one <xref:System.Windows.Forms.ToolStrip>, set the <xref:System.Windows.Forms.ToolStrip.Renderer%2A?displayProperty=nameWithType> property to the custom renderer.</span></span>  
  
    ```vb  
    toolStrip1.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.Renderer = new RedTextRenderer();  
    ```  
  
2. <span data-ttu-id="7631a-113">In alternativa, per impostare il renderer personalizzato per tutte le <xref:System.Windows.Forms.ToolStrip> classi contenute nell'applicazione: impostare la <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> proprietà sul renderer personalizzato e impostare la <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> proprietà su <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode> .</span><span class="sxs-lookup"><span data-stu-id="7631a-113">Or to set the custom renderer for all <xref:System.Windows.Forms.ToolStrip> classes contained in your application: Set the <xref:System.Windows.Forms.ToolStripManager.Renderer%2A?displayProperty=nameWithType> property to the custom renderer and set the <xref:System.Windows.Forms.ToolStrip.RenderMode%2A> property to <xref:System.Windows.Forms.ToolStripRenderMode.ManagerRenderMode>.</span></span>  
  
    ```vb  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode  
    ToolStripManager.Renderer = New RedTextRenderer()  
    ```  
  
    ```csharp  
    toolStrip1.RenderMode = ToolStripRenderMode.ManagerRenderMode;  
    ToolStripManager.Renderer = new RedTextRenderer();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="7631a-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7631a-114">See also</span></span>

- <xref:System.Windows.Forms.ToolStripManager.Renderer%2A>
- <xref:System.Windows.Forms.ToolStripRenderer>
- <xref:System.Windows.Forms.ToolStrip.RenderMode%2A>
- [<span data-ttu-id="7631a-115">Panoramica del controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="7631a-115">ToolStrip Control Overview</span></span>](toolstrip-control-overview-windows-forms.md)
- [<span data-ttu-id="7631a-116">Architettura del controllo ToolStrip</span><span class="sxs-lookup"><span data-stu-id="7631a-116">ToolStrip Control Architecture</span></span>](toolstrip-control-architecture.md)
- [<span data-ttu-id="7631a-117">Riepilogo della tecnologia ToolStrip</span><span class="sxs-lookup"><span data-stu-id="7631a-117">ToolStrip Technology Summary</span></span>](toolstrip-technology-summary.md)
