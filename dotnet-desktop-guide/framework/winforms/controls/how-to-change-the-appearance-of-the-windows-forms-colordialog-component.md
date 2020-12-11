---
title: Modificare l'aspetto del componente ColorDialog
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- ColorDialog component [Windows Forms], examples
- ColorDialog component [Windows Forms], formatting appearance
- color dialog box [Windows Forms], configuring appearance
ms.assetid: bba4e262-1cd7-4f63-89cf-330a36f7b539
ms.openlocfilehash: 0402d7f3c03a0771512a03ac54e1b093c9fe6e9b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963964"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-colordialog-component"></a><span data-ttu-id="acef3-102">Procedura: Modificare l'aspetto del componente ColorDialog di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="acef3-102">How to: Change the Appearance of the Windows Forms ColorDialog Component</span></span>
<span data-ttu-id="acef3-103">È possibile configurare l'aspetto del componente Windows Forms <xref:System.Windows.Forms.ColorDialog> con una serie di proprietà.</span><span class="sxs-lookup"><span data-stu-id="acef3-103">You can configure the appearance of the Windows Forms <xref:System.Windows.Forms.ColorDialog> component with a number of its properties.</span></span> <span data-ttu-id="acef3-104">La finestra di dialogo include due sezioni, una che mostra i colori di base e l'altra che consente all'utente di definire colori personalizzati.</span><span class="sxs-lookup"><span data-stu-id="acef3-104">The dialog box has two sections — one that shows basic colors and one that allows the user to define custom colors.</span></span>  
  
 <span data-ttu-id="acef3-105">La maggior parte delle proprietà consente di limitare i colori selezionabili dall'utente dalla finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="acef3-105">Most of the properties restrict what colors the user can select from the dialog box.</span></span> <span data-ttu-id="acef3-106">Se la <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> proprietà è impostata su `true` , l'utente può definire colori personalizzati.</span><span class="sxs-lookup"><span data-stu-id="acef3-106">If the <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> property is set to `true`, the user is allowed to define custom colors.</span></span> <span data-ttu-id="acef3-107">La <xref:System.Windows.Forms.ColorDialog.FullOpen%2A> proprietà è `true` se la finestra di dialogo viene espansa per definire colori personalizzati; in caso contrario, l'utente deve fare clic su un pulsante "Definisci colori personalizzati".</span><span class="sxs-lookup"><span data-stu-id="acef3-107">The <xref:System.Windows.Forms.ColorDialog.FullOpen%2A> property is `true` if the dialog box is expanded to define custom colors; otherwise the user must click a "Define Custom Colors" button.</span></span> <span data-ttu-id="acef3-108">Quando la <xref:System.Windows.Forms.ColorDialog.AnyColor%2A> proprietà è impostata su `true` , nella finestra di dialogo vengono visualizzati tutti i colori disponibili nel set di colori di base.</span><span class="sxs-lookup"><span data-stu-id="acef3-108">When the <xref:System.Windows.Forms.ColorDialog.AnyColor%2A> property is set to `true`, the dialog box displays all available colors in the set of basic colors.</span></span> <span data-ttu-id="acef3-109">Se la <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> proprietà è impostata su `true` , l'utente non è in grado di selezionare i colori dimessi. solo i colori a tinta unita sono disponibili per la selezione.</span><span class="sxs-lookup"><span data-stu-id="acef3-109">If the <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> property is set to `true`, the user cannot select dithered colors; only solid colors are available to select.</span></span>  
  
 <span data-ttu-id="acef3-110">Se la <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> proprietà è impostata su `true` , nella finestra di dialogo viene visualizzato un pulsante?.</span><span class="sxs-lookup"><span data-stu-id="acef3-110">If the <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> property is set to `true`, a Help button appears on the dialog box.</span></span> <span data-ttu-id="acef3-111">Quando l'utente fa clic sul pulsante?, <xref:System.Windows.Forms.ColorDialog> <xref:System.Windows.Forms.CommonDialog.HelpRequest> viene generato l'evento del componente.</span><span class="sxs-lookup"><span data-stu-id="acef3-111">When the user clicks the Help button, the <xref:System.Windows.Forms.ColorDialog> component's <xref:System.Windows.Forms.CommonDialog.HelpRequest> event is raised.</span></span>  
  
### <a name="to-configure-the-appearance-of-the-color-dialog-box"></a><span data-ttu-id="acef3-112">Per configurare l'aspetto della finestra di dialogo colore</span><span class="sxs-lookup"><span data-stu-id="acef3-112">To configure the appearance of the color dialog box</span></span>  
  
1. <span data-ttu-id="acef3-113">Impostare le <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> proprietà,, <xref:System.Windows.Forms.ColorDialog.AnyColor%2A> <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> e sui <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> valori desiderati.</span><span class="sxs-lookup"><span data-stu-id="acef3-113">Set the <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A>, <xref:System.Windows.Forms.ColorDialog.AnyColor%2A>, <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A>, and <xref:System.Windows.Forms.ColorDialog.ShowHelp%2A> properties to the desired values.</span></span>  
  
    ```vb  
    ColorDialog1.AllowFullOpen = True  
    ColorDialog1.AnyColor = True  
    ColorDialog1.SolidColorOnly = False  
    ColorDialog1.ShowHelp = True  
    ```  
  
    ```csharp  
    colorDialog1.AllowFullOpen = true;  
    colorDialog1.AnyColor = true;  
    colorDialog1.SolidColorOnly = false;  
    colorDialog1.ShowHelp = true;  
    ```  
  
    ```cpp  
    colorDialog1->AllowFullOpen = true;  
    colorDialog1->AnyColor = true;  
    colorDialog1->SolidColorOnly = false;  
    colorDialog1->ShowHelp = true;  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="acef3-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="acef3-114">See also</span></span>

- <xref:System.Windows.Forms.ColorDialog>
- [<span data-ttu-id="acef3-115">Componente ColorDialog</span><span class="sxs-lookup"><span data-stu-id="acef3-115">ColorDialog Component</span></span>](colordialog-component-windows-forms.md)
- [<span data-ttu-id="acef3-116">Panoramica del componente ColorDialog</span><span class="sxs-lookup"><span data-stu-id="acef3-116">ColorDialog Component Overview</span></span>](colordialog-component-overview-windows-forms.md)
