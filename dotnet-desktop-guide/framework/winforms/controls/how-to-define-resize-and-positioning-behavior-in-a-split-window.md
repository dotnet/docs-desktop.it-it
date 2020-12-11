---
title: 'Procedura: Definire il ridimensionamento e il posizionamento in una finestra divisa'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- split windows [Windows Forms], resizing
- splitter windows [Windows Forms], resizing
- SplitContainer control [Windows Forms], resizing
ms.assetid: 9bf73f36-ed2d-4a02-b15a-0770eff4fdfa
ms.openlocfilehash: 8cdcfdfaa135a92ed6a6e96d4a72de2c97f2493d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96961915"
---
# <a name="how-to-define-resize-and-positioning-behavior-in-a-split-window"></a><span data-ttu-id="ed092-102">Procedura: Definire il ridimensionamento e il posizionamento in una finestra divisa</span><span class="sxs-lookup"><span data-stu-id="ed092-102">How to: Define Resize and Positioning Behavior in a Split Window</span></span>
<span data-ttu-id="ed092-103">I pannelli del <xref:System.Windows.Forms.SplitContainer> controllo si prestano bene a essere ridimensionati e modificati dagli utenti.</span><span class="sxs-lookup"><span data-stu-id="ed092-103">The panels of the <xref:System.Windows.Forms.SplitContainer> control lend themselves well to being resized and manipulated by users.</span></span> <span data-ttu-id="ed092-104">Tuttavia, in alcuni casi sarà necessario controllare a livello di codice la barra di divisione, ovvero la posizione in cui è posizionata e il grado di spostamento.</span><span class="sxs-lookup"><span data-stu-id="ed092-104">However, there will be times when you will want to programmatically control the splitter—where it is positioned and to what degree it can be moved.</span></span>  
  
 <span data-ttu-id="ed092-105">La <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> proprietà e le altre proprietà del <xref:System.Windows.Forms.SplitContainer> controllo consentono di controllare in modo preciso il comportamento dell'interfaccia utente in base alle esigenze.</span><span class="sxs-lookup"><span data-stu-id="ed092-105">The <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property and the other properties on the <xref:System.Windows.Forms.SplitContainer> control give you precise control over the behavior of your user interface to suit your needs.</span></span> <span data-ttu-id="ed092-106">Queste proprietà sono elencate nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="ed092-106">These properties are listed in the following table.</span></span>  
  
|<span data-ttu-id="ed092-107">Name</span><span class="sxs-lookup"><span data-stu-id="ed092-107">Name</span></span>|<span data-ttu-id="ed092-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ed092-108">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="ed092-109">Proprietà<xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A></span><span class="sxs-lookup"><span data-stu-id="ed092-109"><xref:System.Windows.Forms.SplitContainer.IsSplitterFixed%2A> property</span></span>|<span data-ttu-id="ed092-110">Determina se la barra di divisione è mobile per mezzo della tastiera o del mouse.</span><span class="sxs-lookup"><span data-stu-id="ed092-110">Determines if the splitter is movable by means of the keyboard or mouse.</span></span>|  
|<span data-ttu-id="ed092-111">Proprietà<xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A></span><span class="sxs-lookup"><span data-stu-id="ed092-111"><xref:System.Windows.Forms.SplitContainer.SplitterDistance%2A> property</span></span>|<span data-ttu-id="ed092-112">Determina la distanza in pixel dal bordo sinistro o superiore alla barra di divisione mobile.</span><span class="sxs-lookup"><span data-stu-id="ed092-112">Determines the distance in pixels from the left or upper edge to the movable splitter bar.</span></span>|  
|<span data-ttu-id="ed092-113">Proprietà<xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A></span><span class="sxs-lookup"><span data-stu-id="ed092-113"><xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property</span></span>|<span data-ttu-id="ed092-114">Determina la distanza minima, in pixel, che la barra di divisione può spostare dall'utente.</span><span class="sxs-lookup"><span data-stu-id="ed092-114">Determines the minimum distance, in pixels, that the splitter can be moved by the user.</span></span>|  
  
 <span data-ttu-id="ed092-115">Nell'esempio seguente la proprietà viene modificata in <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> modo da creare un effetto barra di divisione "blocco". quando l'utente trascina il separatore, viene incrementato in unità di 10 pixel invece che nel valore predefinito 1.</span><span class="sxs-lookup"><span data-stu-id="ed092-115">The example below modifies the <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property to create a "snapping splitter" effect; when the user drags the splitter, it increments in units of 10 pixels rather than the default 1.</span></span>  
  
### <a name="to-define-splitcontainer-resize-behavior"></a><span data-ttu-id="ed092-116">Per definire il comportamento di ridimensionamento di SplitContainer</span><span class="sxs-lookup"><span data-stu-id="ed092-116">To define SplitContainer resize behavior</span></span>  
  
1. <span data-ttu-id="ed092-117">In una routine, impostare la <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> proprietà sulla dimensione desiderata, in modo da ottenere il comportamento "blocco" della barra di divisione.</span><span class="sxs-lookup"><span data-stu-id="ed092-117">In a procedure, set the <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A> property to the desired size, so that the 'snapping' behavior of the splitter is achieved.</span></span>  
  
     <span data-ttu-id="ed092-118">Nell'esempio di codice seguente, nell'evento del form <xref:System.Windows.Forms.Form.Load> , la barra di divisione all'interno del <xref:System.Windows.Forms.SplitContainer> controllo viene impostata in modo da saltare 10 pixel quando viene trascinata.</span><span class="sxs-lookup"><span data-stu-id="ed092-118">In the following code example, within the form's <xref:System.Windows.Forms.Form.Load> event, the splitter within the <xref:System.Windows.Forms.SplitContainer> control is set to jump 10 pixels when dragged.</span></span>  
  
    ```vb  
    Private Sub Form1_Load(ByVal sender As System.Object, _  
        ByVal e As System.EventArgs) Handles MyBase.Load  
        Dim splitSnapper as new SplitContainer()  
        splitSnapper.SplitterIncrement = 10  
        splitSnapper.Dock = DockStyle.Fill  
        splitSnapper.Parent = me  
    End Sub  
    ```  
  
    ```csharp  
    private void Form1_Load(System.Object sender, System.EventArgs e)  
    {  
        SplitContainer splitSnapper = new SplitContainer();  
        splitSnapper.SplitterIncrement = 10;  
        splitSnapper.Dock = DockStyle.Fill;  
        splitSnapper.Parent = this;  
    }  
    ```  
  
     <span data-ttu-id="ed092-119">(Visual C#) Inserire il codice seguente nel costruttore del form per registrare il gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="ed092-119">(Visual C#) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.Load += new System.EventHandler(this.Form1_Load);  
    ```  
  
     <span data-ttu-id="ed092-120">Il passaggio di un separatore leggermente a sinistra o a destra non avrà alcun effetto visibile; Tuttavia, quando il puntatore del mouse passa 10 pixel in entrambe le direzioni, la barra di divisione si blocca sulla nuova posizione.</span><span class="sxs-lookup"><span data-stu-id="ed092-120">Moving the splitter slightly to the left or right will have no discernible effect; however, when the mouse pointer goes 10 pixels in either direction, the splitter will snap to the new position.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed092-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ed092-121">See also</span></span>

- <xref:System.Windows.Forms.SplitContainer>
- <xref:System.Windows.Forms.SplitContainer.SplitterIncrement%2A>
