---
title: 'Procedura: Visualizzare la Guida rapida'
ms.date: 03/30/2017
helpviewer_keywords:
- pop-up Help
- Help [Windows Forms], pop-up Help
- Windows Forms, displaying Help
- forms [Windows Forms], displaying Help
- modal dialog boxes [Windows Forms], pop-up Help
- F1 Help [Windows Forms], in dialog boxes
- HelpProvider component [Windows Forms]
- Help [Windows Forms], adding to dialog boxes
ms.assetid: 218aa81e-e87e-4d67-af05-11627bbdce3b
ms.openlocfilehash: a3b40f49119fcf7900f1f0c8b77c5d83fe81144c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951454"
---
# <a name="how-to-display-pop-up-help"></a><span data-ttu-id="cf811-102">Procedura: visualizzare la Guida popup</span><span class="sxs-lookup"><span data-stu-id="cf811-102">How to: Display pop-up Help</span></span>

<span data-ttu-id="cf811-103">Un modo per visualizzare la Guida in Windows Forms è tramite **il pulsante** ?, situato sul lato destro della barra del titolo, accessibile tramite la <xref:System.Windows.Forms.Form.HelpButton%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="cf811-103">One way to display Help on Windows Forms is through the **Help** button, located on the right side of the title bar, accessible through the <xref:System.Windows.Forms.Form.HelpButton%2A> property.</span></span> <span data-ttu-id="cf811-104">Questo tipo di visualizzazione della Guida è ideale con le finestre di dialogo.</span><span class="sxs-lookup"><span data-stu-id="cf811-104">This type of Help display is well-suited for use with dialog boxes.</span></span> <span data-ttu-id="cf811-105">Con le finestre di dialogo visualizzate come modali (con il metodo <xref:System.Windows.Forms.Form.ShowDialog%2A>) risulta difficile accedere a sistemi di Guida esterni, perché le finestre di dialogo modali devono venire chiuse prima che lo stato attivo possa passare a un'altra finestra.</span><span class="sxs-lookup"><span data-stu-id="cf811-105">Dialog boxes shown modally (with the <xref:System.Windows.Forms.Form.ShowDialog%2A> method) have trouble bringing up external Help systems, because modal dialog boxes need to be closed before focus can shift to another window.</span></span> <span data-ttu-id="cf811-106">Inoltre, per usare **il pulsante** ? è necessario che nella barra del titolo non sia presente un pulsante di **riduzione a icona** o un pulsante **Ingrandisci** .</span><span class="sxs-lookup"><span data-stu-id="cf811-106">Additionally, using the **Help** button requires that there is no **Minimize** button or **Maximize** button shown in the title bar.</span></span> <span data-ttu-id="cf811-107">Si tratta di una convenzione della finestra di dialogo standard, mentre i moduli in genere dispongono di pulsanti **Riduci a icona** e **Ingrandisci** .</span><span class="sxs-lookup"><span data-stu-id="cf811-107">This is a standard dialog-box convention, whereas forms usually have **Minimize** and **Maximize** buttons.</span></span>

<span data-ttu-id="cf811-108">È anche possibile usare il <xref:System.Windows.Forms.HelpProvider> componente per collegare i controlli ai file in un sistema di guida, anche se è stata implementata la Guida popup.</span><span class="sxs-lookup"><span data-stu-id="cf811-108">You can also use the <xref:System.Windows.Forms.HelpProvider> component to link controls to files in a Help system, even if you have implemented pop-up Help.</span></span> <span data-ttu-id="cf811-109">Per ulteriori informazioni, vedere [la Guida in un'applicazione Windows](how-to-provide-help-in-a-windows-application.md).</span><span class="sxs-lookup"><span data-stu-id="cf811-109">For more information, see [Providing Help in a Windows Application](how-to-provide-help-in-a-windows-application.md).</span></span>

## <a name="display-pop-up-help"></a><span data-ttu-id="cf811-110">Visualizza la Guida popup</span><span class="sxs-lookup"><span data-stu-id="cf811-110">Display pop-up Help</span></span>

1. <span data-ttu-id="cf811-111">In Visual Studio trascinare un componente [HelpProvider](../controls/helpprovider-component-windows-forms.md) dalla casella degli strumenti al form.</span><span class="sxs-lookup"><span data-stu-id="cf811-111">In Visual Studio, drag a [HelpProvider](../controls/helpprovider-component-windows-forms.md) component from the Toolbox to your form.</span></span>

   <span data-ttu-id="cf811-112">Il componente verrà posizionato sulla barra delle applicazioni in basso in Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="cf811-112">It will sit in the tray at the bottom of the Windows Forms Designer.</span></span>

2. <span data-ttu-id="cf811-113">Nella finestra Proprietà impostare la proprietà <xref:System.Windows.Forms.Form.HelpButton%2A> su `true`.</span><span class="sxs-lookup"><span data-stu-id="cf811-113">In the Properties window, set the <xref:System.Windows.Forms.Form.HelpButton%2A> property to `true`.</span></span> <span data-ttu-id="cf811-114">Sulla destra della barra del titolo del form verrà visualizzato un pulsante con un punto interrogativo.</span><span class="sxs-lookup"><span data-stu-id="cf811-114">This will display a button with a question mark in it on the right side of the title bar of the form.</span></span>

3. <span data-ttu-id="cf811-115">Per visualizzare <xref:System.Windows.Forms.Form.HelpButton%2A>, è necessario impostare le proprietà <xref:System.Windows.Forms.Form.MinimizeBox%2A> e <xref:System.Windows.Forms.Form.MaximizeBox%2A> del form su `false`, la proprietà <xref:System.Windows.Forms.Form.ControlBox%2A> su `true` e la proprietà <xref:System.Windows.Forms.Form.FormBorderStyle%2A> su uno dei valori seguenti: <xref:System.Windows.Forms.FormBorderStyle.FixedSingle>, <xref:System.Windows.Forms.FormBorderStyle.Fixed3D>, <xref:System.Windows.Forms.FormBorderStyle.FixedDialog> o <xref:System.Windows.Forms.FormBorderStyle.Sizable>.</span><span class="sxs-lookup"><span data-stu-id="cf811-115">In order for the <xref:System.Windows.Forms.Form.HelpButton%2A> to display, the form's <xref:System.Windows.Forms.Form.MinimizeBox%2A> and <xref:System.Windows.Forms.Form.MaximizeBox%2A> properties must be set to `false`, the <xref:System.Windows.Forms.Form.ControlBox%2A> property set to `true`, and the <xref:System.Windows.Forms.Form.FormBorderStyle%2A> property to one of the following values: <xref:System.Windows.Forms.FormBorderStyle.FixedSingle>, <xref:System.Windows.Forms.FormBorderStyle.Fixed3D>, <xref:System.Windows.Forms.FormBorderStyle.FixedDialog> or <xref:System.Windows.Forms.FormBorderStyle.Sizable>.</span></span>

4. <span data-ttu-id="cf811-116">Selezionare il controllo per il quale si desidera visualizzare la Guida nel form e impostare la stringa della Guida nella finestra Proprietà.</span><span class="sxs-lookup"><span data-stu-id="cf811-116">Select the control for which you want to show help on your form and set the Help string in the Properties window.</span></span> <span data-ttu-id="cf811-117">Si tratta della stringa di testo che verrà visualizzata in una finestra simile a una [Descrizione comando](../controls/tooltip-component-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="cf811-117">This is the string of text that will be displayed in a window similar to a [ToolTip](../controls/tooltip-component-windows-forms.md).</span></span>

5. <span data-ttu-id="cf811-118">Premere **F5**.</span><span class="sxs-lookup"><span data-stu-id="cf811-118">Press **F5**.</span></span>

6. <span data-ttu-id="cf811-119">Premere il **pulsante? sulla barra del titolo** e fare clic sul controllo in cui è stata impostata la stringa della guida.</span><span class="sxs-lookup"><span data-stu-id="cf811-119">Press the **Help** button on the title bar and click the control on which you set the Help string.</span></span>

## <a name="see-also"></a><span data-ttu-id="cf811-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cf811-120">See also</span></span>

- [<span data-ttu-id="cf811-121">Visualizzazione della Guida relativa a un controllo tramite le descrizioni comandi</span><span class="sxs-lookup"><span data-stu-id="cf811-121">Control Help Using ToolTips</span></span>](control-help-using-tooltips.md)
- [<span data-ttu-id="cf811-122">Integrazione della Guida dell'utente in Windows Form</span><span class="sxs-lookup"><span data-stu-id="cf811-122">Integrating User Help in Windows Forms</span></span>](integrating-user-help-in-windows-forms.md)
- [<span data-ttu-id="cf811-123">WinForms</span><span class="sxs-lookup"><span data-stu-id="cf811-123">Windows Forms</span></span>](../index.yml)
