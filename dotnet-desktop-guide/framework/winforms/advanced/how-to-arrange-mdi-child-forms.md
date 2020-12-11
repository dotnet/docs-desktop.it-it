---
title: 'Procedura: Disporre form figlio MDI'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- child forms [Windows Forms], arranging
- MDI [Windows Forms], arranging child forms
ms.assetid: a0786378-3206-4ccc-898e-7d3b38cc5089
ms.openlocfilehash: 7e4d5a80961ae37951251dffa30cb8e75b20be27
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951502"
---
# <a name="how-to-arrange-mdi-child-forms"></a><span data-ttu-id="0c384-102">Procedura: Disporre form figlio MDI</span><span class="sxs-lookup"><span data-stu-id="0c384-102">How to: Arrange MDI Child Forms</span></span>
<span data-ttu-id="0c384-103">Le applicazioni hanno spesso dei comandi di menu per azioni quali Affianca, Sovrapponi e Disponi che controllano il layout dei form figlio MDI aperti.</span><span class="sxs-lookup"><span data-stu-id="0c384-103">Often, applications will have menu commands for actions such as Tile, Cascade, and Arrange, which control the layout of the open MDI child forms.</span></span> <span data-ttu-id="0c384-104">È possibile usare il metodo <xref:System.Windows.Forms.Form.LayoutMdi%2A> con uno dei valori di enumerazione <xref:System.Windows.Forms.MdiLayout> per ridisporre i form figlio in un form padre MDI.</span><span class="sxs-lookup"><span data-stu-id="0c384-104">You can use the <xref:System.Windows.Forms.Form.LayoutMdi%2A> method with one of the <xref:System.Windows.Forms.MdiLayout> enumeration values to rearrange the child forms in an MDI parent form.</span></span>  
  
 <span data-ttu-id="0c384-105">I valori di enumerazione <xref:System.Windows.Forms.MdiLayout> visualizzano i form figlio sovrapposti, affiancati orizzontalmente o verticalmente o sotto forma di icone disposte nella parte inferiore del form MDI.</span><span class="sxs-lookup"><span data-stu-id="0c384-105">The <xref:System.Windows.Forms.MdiLayout> enumeration values display child forms as cascading, as horizontally or vertically tiled, or as child form icons arranged along the lower portion of the MDI form.</span></span> <span data-ttu-id="0c384-106">Questi valori hanno lo stesso effetto dei comandi Windows **Cascade Windows**, **mostrano le finestre affiancate**, **mostrano Windows in pila** e **visualizzano il desktop**, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="0c384-106">These values have the same effect as the Windows commands **Cascade windows**, **Show windows side by side**, **Show windows stacked**, and **Show the desktop**, respectively.</span></span>  
  
 <span data-ttu-id="0c384-107">Spesso questi metodi vengono usati come gestori eventi chiamati da un evento della voce di menu <xref:System.Windows.Forms.Control.Click>.</span><span class="sxs-lookup"><span data-stu-id="0c384-107">Often, these methods are used as the event handlers called by a menu item's <xref:System.Windows.Forms.Control.Click> event.</span></span> <span data-ttu-id="0c384-108">In questo modo, una voce di menu con testo "Sovrapponi le finestre" può avere l'effetto desiderato sulle finestre figlio MDI.</span><span class="sxs-lookup"><span data-stu-id="0c384-108">In this way, a menu item with the text "Cascade Windows" can have the desired effect on the MDI child windows.</span></span>  
  
### <a name="to-arrange-child-forms"></a><span data-ttu-id="0c384-109">Per disporre i form figlio</span><span class="sxs-lookup"><span data-stu-id="0c384-109">To arrange child forms</span></span>  
  
1. <span data-ttu-id="0c384-110">In un metodo usare il metodo <xref:System.Windows.Forms.Form.LayoutMdi%2A> per impostare l'enumerazione <xref:System.Windows.Forms.MdiLayout> per il form padre MDI.</span><span class="sxs-lookup"><span data-stu-id="0c384-110">In a method, use the <xref:System.Windows.Forms.Form.LayoutMdi%2A> method to set the <xref:System.Windows.Forms.MdiLayout> enumeration for the MDI parent form.</span></span> <span data-ttu-id="0c384-111">Nel seguente esempio viene usato il valore di enumerazione <xref:System.Windows.Forms.MdiLayout.Cascade?displayProperty=nameWithType> per le finestre figlio del form padre MDI (`Form1`).</span><span class="sxs-lookup"><span data-stu-id="0c384-111">The following example uses the <xref:System.Windows.Forms.MdiLayout.Cascade?displayProperty=nameWithType> enumeration value for the child windows of the MDI parent form (`Form1`).</span></span> <span data-ttu-id="0c384-112">L'enumerazione viene utilizzata nel codice durante il gestore eventi per l' <xref:System.Windows.Forms.Control.Click> evento della voce di menu **Cascade Windows** .</span><span class="sxs-lookup"><span data-stu-id="0c384-112">The enumeration is used in code during the event handler for the <xref:System.Windows.Forms.Control.Click> event of the **Cascade Windows** menu item.</span></span>  
  
    ```vb  
    Protected Sub CascadeWindows_Click(ByVal sender As System.Object, ByVal e As System.EventArgs)  
       Me.LayoutMdi(System.Windows.Forms.MdiLayout.Cascade)  
    End Sub  
    ```  
  
    ```csharp  
    protected void CascadeWindows_Click(object sender, System.EventArgs e){  
       this.LayoutMdi(System.Windows.Forms.MdiLayout.Cascade);  
    }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="0c384-113">È anche possibile affiancare le finestre e disporle sotto forma di icona modificando i valori di enumerazione <xref:System.Windows.Forms.MdiLayout> usati.</span><span class="sxs-lookup"><span data-stu-id="0c384-113">You can also tile windows and arranging windows as icons by changing the <xref:System.Windows.Forms.MdiLayout> enumeration value used.</span></span>  
  
2. <span data-ttu-id="0c384-114">Se si usa Visual C#, inserire il codice seguente nel costruttore del form per registrare il gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="0c384-114">If you’re using Visual C#, place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0c384-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0c384-115">See also</span></span>

- [<span data-ttu-id="0c384-116">Applicazioni MDI (Interfaccia a documenti multipli, Multiple-Document Interface)</span><span class="sxs-lookup"><span data-stu-id="0c384-116">Multiple-Document Interface (MDI) Applications</span></span>](multiple-document-interface-mdi-applications.md)
- [<span data-ttu-id="0c384-117">Procedura: Creare form padre MDI</span><span class="sxs-lookup"><span data-stu-id="0c384-117">How to: Create MDI Parent Forms</span></span>](how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="0c384-118">Procedura: Creare form figlio MDI</span><span class="sxs-lookup"><span data-stu-id="0c384-118">How to: Create MDI Child Forms</span></span>](how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="0c384-119">Procedura: Determinare il figlio MDI attivo</span><span class="sxs-lookup"><span data-stu-id="0c384-119">How to: Determine the Active MDI Child</span></span>](how-to-determine-the-active-mdi-child.md)
- [<span data-ttu-id="0c384-120">Procedura: Inviare dati al figlio MDI attivo</span><span class="sxs-lookup"><span data-stu-id="0c384-120">How to: Send Data to the Active MDI Child</span></span>](how-to-send-data-to-the-active-mdi-child.md)
