---
title: Integrazione della Guida dell'utente
ms.date: 03/30/2017
helpviewer_keywords:
- Help [Windows Forms], Windows Forms (using designer)
- Windows Forms, Help (using designer)
- HTML Help [Windows Forms], Windows Forms (using designer)
- Help [Windows Forms], Windows applications (using designer)
- forms. Help (using designer)
- Windows applications [Windows Forms], Help (using designer)
ms.assetid: a8563d25-8a75-4bc7-a024-f1870591b50f
ms.openlocfilehash: e1d9921b01c1fafe690a2727f2a45443d6f42728
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963166"
---
# <a name="integrating-user-help-in-windows-forms"></a><span data-ttu-id="35bee-102">Integrazione della Guida dell'utente in Windows Form</span><span class="sxs-lookup"><span data-stu-id="35bee-102">Integrating User Help in Windows Forms</span></span>
<span data-ttu-id="35bee-103">Un aspetto essenziale, ma spesso trascurato, della creazione di applicazioni basate su Windows è il sistema di guida, in quanto questo è il punto in cui gli utenti si attivano per ottenere assistenza in momenti di confusione.</span><span class="sxs-lookup"><span data-stu-id="35bee-103">An essential, but often overlooked, aspect of building Windows-based applications is the Help system, as this is where users turn for assistance in times of confusion.</span></span> <span data-ttu-id="35bee-104">Windows Forms supportano due tipi diversi di guida, ognuno fornito dal [componente HelpProvider](../controls/helpprovider-component-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="35bee-104">Windows Forms support two different types of Help, each provided by the [HelpProvider Component](../controls/helpprovider-component-windows-forms.md).</span></span> <span data-ttu-id="35bee-105">Il primo consiste nel puntare l'utente a un file della Guida HTML o HTML della guida 1. formato *x* o superiore.</span><span class="sxs-lookup"><span data-stu-id="35bee-105">The first involves pointing the user to a Help file of either HTML or HTML Help 1.*x* or greater format.</span></span> <span data-ttu-id="35bee-106">Il secondo può visualizzare Brief "What ' s this" (informazioni di questo tipo) sui singoli controlli. Questa operazione è particolarmente utile nelle finestre di dialogo.</span><span class="sxs-lookup"><span data-stu-id="35bee-106">The second can display brief "What's This"-type Help on individual controls; this is especially useful on dialog boxes.</span></span> <span data-ttu-id="35bee-107">Entrambi i tipi di guida possono essere usati nello stesso formato.</span><span class="sxs-lookup"><span data-stu-id="35bee-107">Both types of Help can be used on the same form.</span></span>  
  
 <span data-ttu-id="35bee-108">Inoltre, è possibile utilizzare il [componente descrizione comando](../controls/tooltip-component-windows-forms.md) per fornire la guida individuale per i controlli Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="35bee-108">Additionally, the [ToolTip Component](../controls/tooltip-component-windows-forms.md) can be used to provide individual Help for controls on Windows Forms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="35bee-109">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="35bee-109">In This Section</span></span>  
 [<span data-ttu-id="35bee-110">Procedura: Visualizzare la Guida in un'applicazione Windows</span><span class="sxs-lookup"><span data-stu-id="35bee-110">How to: Provide Help in a Windows Application</span></span>](how-to-provide-help-in-a-windows-application.md)  
 <span data-ttu-id="35bee-111">Viene illustrato come utilizzare il `HelpProvider` componente per collegare i controlli ai file in un sistema di guida.</span><span class="sxs-lookup"><span data-stu-id="35bee-111">Explains how to use the `HelpProvider` component to link controls to files in a Help system.</span></span>  
  
 [<span data-ttu-id="35bee-112">Procedura: Visualizzare la Guida rapida</span><span class="sxs-lookup"><span data-stu-id="35bee-112">How to: Display Pop-up Help</span></span>](how-to-display-pop-up-help.md)  
 <span data-ttu-id="35bee-113">Viene illustrato come utilizzare il `HelpProvider` componente per visualizzare la Guida popup in Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="35bee-113">Explains how to use the `HelpProvider` component to show pop-up Help on Windows Forms.</span></span>  
  
 [<span data-ttu-id="35bee-114">Visualizzazione della Guida relativa a un controllo tramite le descrizioni comandi</span><span class="sxs-lookup"><span data-stu-id="35bee-114">Control Help Using ToolTips</span></span>](control-help-using-tooltips.md)  
 <span data-ttu-id="35bee-115">Viene descritto l'utilizzo del `ToolTip` componente per visualizzare la guida specifica del controllo.</span><span class="sxs-lookup"><span data-stu-id="35bee-115">Describes using the `ToolTip` component to show control-specific Help.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="35bee-116">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="35bee-116">Related Sections</span></span>  
 [<span data-ttu-id="35bee-117">Componente HelpProvider</span><span class="sxs-lookup"><span data-stu-id="35bee-117">HelpProvider Component</span></span>](../controls/helpprovider-component-windows-forms.md)  
 <span data-ttu-id="35bee-118">Vengono illustrati i concetti di base del `HelpProvider` componente.</span><span class="sxs-lookup"><span data-stu-id="35bee-118">Explains the basics of the `HelpProvider` component.</span></span>  
  
 [<span data-ttu-id="35bee-119">Componente ToolTip</span><span class="sxs-lookup"><span data-stu-id="35bee-119">ToolTip Component</span></span>](../controls/tooltip-component-windows-forms.md)  
 <span data-ttu-id="35bee-120">Vengono illustrati i concetti di base del `ToolTip` componente.</span><span class="sxs-lookup"><span data-stu-id="35bee-120">Explains the basics of the `ToolTip` component.</span></span>  
  
 [<span data-ttu-id="35bee-121">Panoramica sui Windows Form</span><span class="sxs-lookup"><span data-stu-id="35bee-121">Windows Forms Overview</span></span>](../windows-forms-overview.md)  
 <span data-ttu-id="35bee-122">Vengono illustrati i concetti di base di Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="35bee-122">Explains the basics of Windows Forms.</span></span>  
  
 [<span data-ttu-id="35bee-123">WinForms</span><span class="sxs-lookup"><span data-stu-id="35bee-123">Windows Forms</span></span>](../index.yml)  
 <span data-ttu-id="35bee-124">Viene fornita una panoramica delle Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="35bee-124">Provides an overview of Windows Forms.</span></span>
