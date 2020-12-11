---
title: Progettare un layout descrittivo per la localizzazione
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms]
- application design [Windows Forms], localization
- Windows Forms, localization
- localization [Windows Forms], Windows Forms layout
ms.assetid: d13eff2d-701c-4b6e-8838-3885cbfb7223
ms.openlocfilehash: ae52669d2547532fcdaabab9aeb2cf40a4a6fa2d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963853"
---
# <a name="how-to-design-a-windows-forms-layout-that-responds-well-to-localization"></a><span data-ttu-id="b7fd2-102">Procedura: progettare un layout di Windows Form che risponda correttamente alla localizzazione</span><span class="sxs-lookup"><span data-stu-id="b7fd2-102">How to: Design a Windows Forms Layout that Responds Well to Localization</span></span>

<span data-ttu-id="b7fd2-103">La creazione di form pronti per la localizzazione accelera notevolmente lo sviluppo per i mercati internazionali.</span><span class="sxs-lookup"><span data-stu-id="b7fd2-103">Creating forms that are ready to be localized greatly speeds development for international markets.</span></span> <span data-ttu-id="b7fd2-104">È possibile usare il controllo <xref:System.Windows.Forms.TableLayoutPanel> per implementare layout che rispondano correttamente man mano che i controlli vengono ridimensionati in seguito alle modifiche dei valori della proprietà <xref:System.Windows.Forms.Control.Text%2A>.</span><span class="sxs-lookup"><span data-stu-id="b7fd2-104">You can use the <xref:System.Windows.Forms.TableLayoutPanel> control to implement layouts that respond gracefully as controls resize due to changes in their <xref:System.Windows.Forms.Control.Text%2A> property values.</span></span>

## <a name="example"></a><span data-ttu-id="b7fd2-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="b7fd2-105">Example</span></span>

 <span data-ttu-id="b7fd2-106">In questo form viene illustrato come creare un layout che viene modificato proporzionalmente quando si traducono i valori stringa visualizzati in altre lingue.</span><span class="sxs-lookup"><span data-stu-id="b7fd2-106">This form demonstrates how to create a layout that proportionally adjusts when you translate displayed string values into other languages.</span></span> <span data-ttu-id="b7fd2-107">Questo processo di traduzione è denominato *localizzazione*.</span><span class="sxs-lookup"><span data-stu-id="b7fd2-107">This process of translation is called *localization*.</span></span> <span data-ttu-id="b7fd2-108">Per altre informazioni, vedere [Localizzazione](/dotnet/standard/globalization-localization/localization).</span><span class="sxs-lookup"><span data-stu-id="b7fd2-108">For more information, see [Localization](/dotnet/standard/globalization-localization/localization).</span></span>

 <span data-ttu-id="b7fd2-109">In Visual Studio è disponibile supporto completo per questa attività.</span><span class="sxs-lookup"><span data-stu-id="b7fd2-109">There is extensive support for this task in Visual Studio.</span></span>  <span data-ttu-id="b7fd2-110">Vedere anche [Procedura dettagliata: creazione di un layout dalle proporzioni adattabili per la localizzazione](/previous-versions/visualstudio/visual-studio-2010/7k9fa71y(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="b7fd2-110">See also [Walkthrough: Creating a Layout That Adjusts Proportion for Localization](/previous-versions/visualstudio/visual-studio-2010/7k9fa71y(v=vs.100)).</span></span>

 [!code-csharp[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/CS/localizableform.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/VB/localizableform.vb#1)]

## <a name="additional-resources"></a><span data-ttu-id="b7fd2-111">Risorse aggiuntive</span><span class="sxs-lookup"><span data-stu-id="b7fd2-111">Additional resources</span></span>

1. [<span data-ttu-id="b7fd2-112">Procedura: Allineare ed estendere un controllo in un controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="b7fd2-112">How to: Align and Stretch a Control in a TableLayoutPanel Control</span></span>](how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control.md)

2. [<span data-ttu-id="b7fd2-113">Procedura dettagliata: Disposizione dei controlli in Windows Forms usando FlowLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="b7fd2-113">Walkthrough: Arranging Controls on Windows Forms Using a FlowLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)

3. [<span data-ttu-id="b7fd2-114">Procedura: Inserire righe e colonne in un controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="b7fd2-114">How to: Span Rows and Columns in a TableLayoutPanel Control</span></span>](how-to-span-rows-and-columns-in-a-tablelayoutpanel-control.md)

4. [<span data-ttu-id="b7fd2-115">Procedura: Modificare colonne e righe in un controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="b7fd2-115">How to: Edit Columns and Rows in a TableLayoutPanel Control</span></span>](how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control.md)

5. [<span data-ttu-id="b7fd2-116">Procedura dettagliata: eseguire attività comuni utilizzando le azioni della finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="b7fd2-116">Walkthrough: Perform common tasks using designer actions</span></span>](perform-common-tasks-design-actions.md)

6. [<span data-ttu-id="b7fd2-117">Procedura dettagliata: disposizione di controlli in Windows Form usando TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="b7fd2-117">Walkthrough: Arranging Controls on Windows Forms Using a TableLayoutPanel</span></span>](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)

7. [<span data-ttu-id="b7fd2-118">Procedura dettagliata: Disposizione dei controlli Windows Forms con spaziatura interna, margini e la proprietà AutoSize</span><span class="sxs-lookup"><span data-stu-id="b7fd2-118">Walkthrough: Laying Out Windows Forms Controls with Padding, Margins, and the AutoSize Property</span></span>](windows-forms-controls-padding-autosize.md)

8. <span data-ttu-id="b7fd2-119">[Procedura: Supportare la localizzazione in Windows Form usando la proprietà AutoSize e il controllo TableLayoutPanel](/previous-versions/visualstudio/visual-studio-2010/1zkt8b33(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b7fd2-119">[How to: Support Localization on Windows Forms Using AutoSize and the TableLayoutPanel Control](/previous-versions/visualstudio/visual-studio-2010/1zkt8b33(v=vs.100))</span></span>

9. <span data-ttu-id="b7fd2-120">[Procedura dettagliata: creazione di un Windows Form ridimensionabile per l'inserimento di dati](/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b7fd2-120">[Walkthrough: Creating a Resizable Windows Form for Data Entry](/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100))</span></span>

## <a name="compiling-the-code"></a><span data-ttu-id="b7fd2-121">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="b7fd2-121">Compiling the Code</span></span>

 <span data-ttu-id="b7fd2-122">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="b7fd2-122">This example requires:</span></span>

- <span data-ttu-id="b7fd2-123">Riferimenti agli assembly System, System.Data, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="b7fd2-123">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>

## <a name="see-also"></a><span data-ttu-id="b7fd2-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b7fd2-124">See also</span></span>

- <xref:System.Windows.Forms.TableLayoutPanel>
- <xref:System.Windows.Forms.FlowLayoutPanel>
- [<span data-ttu-id="b7fd2-125">Localizzazione</span><span class="sxs-lookup"><span data-stu-id="b7fd2-125">Localization</span></span>](/dotnet/standard/globalization-localization/localization)
