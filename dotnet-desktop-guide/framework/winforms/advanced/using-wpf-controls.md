---
title: Utilizzo di controlli WPF
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms Designer [Windows Forms], interoperability with WPF
- interoperability [WPF]
ms.assetid: 03c85dce-26ad-44cd-bc1d-8e0cb56de096
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: dfc086b4873c41bf1919b680d472807283e8a340
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952728"
---
# <a name="use-wpf-controls-in-windows-forms-apps"></a><span data-ttu-id="cec5b-102">Usare i controlli WPF nelle app Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cec5b-102">Use WPF controls in Windows Forms apps</span></span>

<span data-ttu-id="cec5b-103">È possibile utilizzare i controlli Windows Presentation Foundation (WPF) nelle applicazioni basate su Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="cec5b-103">You can use Windows Presentation Foundation (WPF) controls in Windows Forms-based applications.</span></span> <span data-ttu-id="cec5b-104">Sebbene si tratta di due tecnologie di visualizzazione diverse, interagiscono senza problemi.</span><span class="sxs-lookup"><span data-stu-id="cec5b-104">Although these are two different view technologies, they interoperate smoothly.</span></span>

<span data-ttu-id="cec5b-105">Il Progettazione Windows Form in Visual Studio fornisce un ambiente di progettazione visiva per l'hosting di controlli Windows Presentation Foundation.</span><span class="sxs-lookup"><span data-stu-id="cec5b-105">The Windows Forms Designer in Visual Studio provides a visual design environment for hosting Windows Presentation Foundation controls.</span></span> <span data-ttu-id="cec5b-106">Un controllo WPF è ospitato da un particolare controllo Windows Forms denominato <xref:System.Windows.Forms.Integration.ElementHost> .</span><span class="sxs-lookup"><span data-stu-id="cec5b-106">A WPF control is hosted by a special Windows Forms control that's named <xref:System.Windows.Forms.Integration.ElementHost>.</span></span> <span data-ttu-id="cec5b-107">Questo controllo consente al controllo WPF di partecipare al layout del form e di ricevere i messaggi della tastiera e del mouse.</span><span class="sxs-lookup"><span data-stu-id="cec5b-107">This control enables the WPF control to participate in the form's layout and to receive keyboard and mouse messages.</span></span> <span data-ttu-id="cec5b-108">In fase di progettazione, è possibile disporre il <xref:System.Windows.Forms.Integration.ElementHost> controllo come qualsiasi Windows Forms controllo.</span><span class="sxs-lookup"><span data-stu-id="cec5b-108">At design time, you can arrange the <xref:System.Windows.Forms.Integration.ElementHost> control just as you would any Windows Forms control.</span></span>

<span data-ttu-id="cec5b-109">È inoltre possibile utilizzare Windows Forms controlli nelle applicazioni basate su WPF.</span><span class="sxs-lookup"><span data-stu-id="cec5b-109">You can also use Windows Forms controls in WPF-based applications.</span></span> <span data-ttu-id="cec5b-110">Per altre informazioni, vedere [progettazione di XAML in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="cec5b-110">For more information, see [Design XAML in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio).</span></span>

## <a name="see-also"></a><span data-ttu-id="cec5b-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cec5b-111">See also</span></span>

- [<span data-ttu-id="cec5b-112">Interoperatività di WPF e Windows Forms</span><span class="sxs-lookup"><span data-stu-id="cec5b-112">WPF and Windows Forms interoperation</span></span>](/dotnet/framework/wpf/advanced/wpf-and-windows-forms-interoperation)
