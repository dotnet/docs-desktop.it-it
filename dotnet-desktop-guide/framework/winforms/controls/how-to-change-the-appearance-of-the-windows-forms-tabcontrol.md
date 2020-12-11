---
title: Modificare l'aspetto di TabControl
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- icons [Windows Forms], displaying on tabs
- TabControl control [Windows Forms], changing page appearance
- tabs [Windows Forms], controlling appearance
- buttons [Windows Forms], displaying tabs as
ms.assetid: 7c6cc443-ed62-4d26-b94d-b8913b44f773
ms.openlocfilehash: 056070177e6bbaba0c93c7b94f5adfd7887be6a8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963961"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-tabcontrol"></a><span data-ttu-id="49452-102">Procedura: Modificare l'aspetto di TabControl di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="49452-102">How to: Change the Appearance of the Windows Forms TabControl</span></span>
<span data-ttu-id="49452-103">È possibile modificare l'aspetto delle schede in Windows Forms usando le proprietà dell'oggetto <xref:System.Windows.Forms.TabControl> e gli <xref:System.Windows.Forms.TabPage> oggetti che costituiscono le singole schede del controllo.</span><span class="sxs-lookup"><span data-stu-id="49452-103">You can change the appearance of tabs in Windows Forms by using properties of the <xref:System.Windows.Forms.TabControl> and the <xref:System.Windows.Forms.TabPage> objects that make up the individual tabs on the control.</span></span> <span data-ttu-id="49452-104">Impostando queste proprietà, è possibile visualizzare le immagini sulle schede, visualizzare le schede verticalmente anziché orizzontalmente, visualizzare più righe di schede e abilitare o disabilitare le schede a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="49452-104">By setting these properties, you can display images on tabs, display tabs vertically instead of horizontally, display multiple rows of tabs, and enable or disable tabs programmatically.</span></span>  
  
### <a name="to-display-an-icon-on-the-label-part-of-a-tab"></a><span data-ttu-id="49452-105">Per visualizzare un'icona nella parte etichetta di una scheda</span><span class="sxs-lookup"><span data-stu-id="49452-105">To display an icon on the label part of a tab</span></span>  
  
1. <span data-ttu-id="49452-106">Aggiungere un <xref:System.Windows.Forms.ImageList> controllo al form.</span><span class="sxs-lookup"><span data-stu-id="49452-106">Add an <xref:System.Windows.Forms.ImageList> control to the form.</span></span>  
  
2. <span data-ttu-id="49452-107">Aggiungere immagini all'elenco di immagini.</span><span class="sxs-lookup"><span data-stu-id="49452-107">Add images to the image list.</span></span>  
  
     <span data-ttu-id="49452-108">Per altre informazioni sugli elenchi di immagini, vedere [componente ImageList](imagelist-component-windows-forms.md) e [procedura: aggiungere o rimuovere immagini con il componente Windows Forms ImageList](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span><span class="sxs-lookup"><span data-stu-id="49452-108">For more information about image lists, see [ImageList Component](imagelist-component-windows-forms.md) and [How to: Add or Remove Images with the Windows Forms ImageList Component](how-to-add-or-remove-images-with-the-windows-forms-imagelist-component.md).</span></span>  
  
3. <span data-ttu-id="49452-109">Impostare la <xref:System.Windows.Forms.TabControl.ImageList%2A> proprietà dell'oggetto sul <xref:System.Windows.Forms.TabControl> <xref:System.Windows.Forms.ImageList> controllo.</span><span class="sxs-lookup"><span data-stu-id="49452-109">Set the <xref:System.Windows.Forms.TabControl.ImageList%2A> property of the <xref:System.Windows.Forms.TabControl> to the <xref:System.Windows.Forms.ImageList> control.</span></span>  
  
4. <span data-ttu-id="49452-110">Impostare la <xref:System.Windows.Forms.TabPage.ImageIndex%2A> proprietà dell'oggetto sull' <xref:System.Windows.Forms.TabPage> indice di un'immagine appropriata nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="49452-110">Set the <xref:System.Windows.Forms.TabPage.ImageIndex%2A> property of the <xref:System.Windows.Forms.TabPage> to the index of an appropriate image in the list.</span></span>  
  
### <a name="to-create-multiple-rows-of-tabs"></a><span data-ttu-id="49452-111">Per creare più righe di schede</span><span class="sxs-lookup"><span data-stu-id="49452-111">To create multiple rows of tabs</span></span>  
  
1. <span data-ttu-id="49452-112">Aggiungere il numero di schede desiderate.</span><span class="sxs-lookup"><span data-stu-id="49452-112">Add the number of tab pages you want.</span></span>  
  
2. <span data-ttu-id="49452-113">Impostare la proprietà <xref:System.Windows.Forms.TabControl.Multiline%2A> di <xref:System.Windows.Forms.TabControl> su `true`.</span><span class="sxs-lookup"><span data-stu-id="49452-113">Set the <xref:System.Windows.Forms.TabControl.Multiline%2A> property of the <xref:System.Windows.Forms.TabControl> to `true`.</span></span>  
  
3. <span data-ttu-id="49452-114">Se le schede non sono già presenti in più righe, impostare la <xref:System.Windows.Forms.Control.Width%2A> proprietà di <xref:System.Windows.Forms.TabControl> in modo che sia più stretta di tutte le schede.</span><span class="sxs-lookup"><span data-stu-id="49452-114">If the tabs do not already appear in multiple rows, set the <xref:System.Windows.Forms.Control.Width%2A> property of the <xref:System.Windows.Forms.TabControl> to be narrower than all the tabs.</span></span>  
  
### <a name="to-arrange-tabs-on-the-side-of-the-control"></a><span data-ttu-id="49452-115">Per disporre le schede sul lato del controllo</span><span class="sxs-lookup"><span data-stu-id="49452-115">To arrange tabs on the side of the control</span></span>  
  
- <span data-ttu-id="49452-116">Impostare la <xref:System.Windows.Forms.TabControl.Alignment%2A> proprietà di <xref:System.Windows.Forms.TabControl> su <xref:System.Windows.Forms.TabAlignment.Left> o su <xref:System.Windows.Forms.TabAlignment.Right> .</span><span class="sxs-lookup"><span data-stu-id="49452-116">Set the <xref:System.Windows.Forms.TabControl.Alignment%2A> property of the <xref:System.Windows.Forms.TabControl> to <xref:System.Windows.Forms.TabAlignment.Left> or <xref:System.Windows.Forms.TabAlignment.Right>.</span></span>  
  
### <a name="to-programmatically-enable-or-disable-all-controls-on-a-tab"></a><span data-ttu-id="49452-117">Per abilitare o disabilitare a livello di codice tutti i controlli in una scheda</span><span class="sxs-lookup"><span data-stu-id="49452-117">To programmatically enable or disable all controls on a tab</span></span>  
  
1. <span data-ttu-id="49452-118">Impostare la <xref:System.Windows.Forms.TabPage.Enabled%2A> proprietà di <xref:System.Windows.Forms.TabPage> su `true` o su `false` .</span><span class="sxs-lookup"><span data-stu-id="49452-118">Set the <xref:System.Windows.Forms.TabPage.Enabled%2A> property of the <xref:System.Windows.Forms.TabPage> to `true` or `false`.</span></span>  
  
    ```vb  
    TabPage1.Enabled = False  
    ```  
  
    ```csharp  
    tabPage1.Enabled = false;  
    ```  
  
    ```cpp  
    tabPage1->Enabled = false;  
    ```  
  
### <a name="to-display-tabs-as-buttons"></a><span data-ttu-id="49452-119">Per visualizzare le tabulazioni come pulsanti</span><span class="sxs-lookup"><span data-stu-id="49452-119">To display tabs as buttons</span></span>  
  
- <span data-ttu-id="49452-120">Impostare la <xref:System.Windows.Forms.TabControl.Appearance%2A> proprietà di <xref:System.Windows.Forms.TabControl> su <xref:System.Windows.Forms.TabAppearance.Buttons> o su <xref:System.Windows.Forms.TabAppearance.FlatButtons> .</span><span class="sxs-lookup"><span data-stu-id="49452-120">Set the <xref:System.Windows.Forms.TabControl.Appearance%2A> property of the <xref:System.Windows.Forms.TabControl> to <xref:System.Windows.Forms.TabAppearance.Buttons> or <xref:System.Windows.Forms.TabAppearance.FlatButtons>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49452-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49452-121">See also</span></span>

- [<span data-ttu-id="49452-122">Controllo TabControl</span><span class="sxs-lookup"><span data-stu-id="49452-122">TabControl Control</span></span>](tabcontrol-control-windows-forms.md)
- [<span data-ttu-id="49452-123">Panoramica del controllo TabControl</span><span class="sxs-lookup"><span data-stu-id="49452-123">TabControl Control Overview</span></span>](tabcontrol-control-overview-windows-forms.md)
- [<span data-ttu-id="49452-124">Procedura: Aggiungere un controllo a una scheda</span><span class="sxs-lookup"><span data-stu-id="49452-124">How to: Add a Control to a Tab Page</span></span>](how-to-add-a-control-to-a-tab-page.md)
- [<span data-ttu-id="49452-125">Procedura: Disabilitare le schede</span><span class="sxs-lookup"><span data-stu-id="49452-125">How to: Disable Tab Pages</span></span>](how-to-disable-tab-pages.md)
- [<span data-ttu-id="49452-126">Procedura: Aggiungere e rimuovere schede con TabControl di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="49452-126">How to: Add and Remove Tabs with the Windows Forms TabControl</span></span>](how-to-add-and-remove-tabs-with-the-windows-forms-tabcontrol.md)
