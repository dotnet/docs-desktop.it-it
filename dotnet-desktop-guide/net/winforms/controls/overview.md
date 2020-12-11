---
title: Cenni preliminari sull'uso dei controlli
description: Informazioni sul modo in cui i controlli vengono usati nei Windows Forms per .NET. I controlli sono componenti riutilizzabili che forniscono funzionalità all'utente. Sono disponibili molti controlli pronti per l'uso. È anche possibile creare nuovi controlli.
ms.date: 10/26/2020
ms.topic: overview
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, controls
- controls [Windows Forms]
- custom controls [Windows Forms]
ms.openlocfilehash: 7476ce47a1767a2ab13c25a7408f5861014e7de8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968794"
---
# <a name="overview-of-using-controls-windows-forms-net"></a><span data-ttu-id="8de64-106">Cenni preliminari sull'utilizzo di controlli (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="8de64-106">Overview of using controls (Windows Forms .NET)</span></span>

<span data-ttu-id="8de64-107">Windows Forms controlli sono componenti riutilizzabili che incapsulano le funzionalità dell'interfaccia utente e vengono usati nelle applicazioni basate su Windows sul lato client.</span><span class="sxs-lookup"><span data-stu-id="8de64-107">Windows Forms controls are reusable components that encapsulate user interface functionality and are used in client-side, Windows-based applications.</span></span> <span data-ttu-id="8de64-108">Windows Form fornisce numerosi controlli pronti per l'uso, nonché l'infrastruttura per lo sviluppo di controlli personalizzati.</span><span class="sxs-lookup"><span data-stu-id="8de64-108">Not only does Windows Forms provide many ready-to-use controls, it also provides the infrastructure for developing your own controls.</span></span> <span data-ttu-id="8de64-109">È possibile combinare ed estendere i controlli esistenti oppure creare controlli personalizzati.</span><span class="sxs-lookup"><span data-stu-id="8de64-109">You can combine existing controls, extend existing controls, or author your own custom controls.</span></span> <span data-ttu-id="8de64-110">Per altre informazioni, vedere [tipi di controlli personalizzati](custom.md).</span><span class="sxs-lookup"><span data-stu-id="8de64-110">For more information, see [Types of custom controls](custom.md).</span></span>

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="adding-controls"></a><span data-ttu-id="8de64-111">Aggiunta di controlli</span><span class="sxs-lookup"><span data-stu-id="8de64-111">Adding controls</span></span>

<span data-ttu-id="8de64-112">I controlli vengono aggiunti tramite la finestra di progettazione di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="8de64-112">Controls are added through the Visual Studio Designer.</span></span> <span data-ttu-id="8de64-113">Con la finestra di progettazione è possibile inserire, ridimensionare, allineare e spostare i controlli.</span><span class="sxs-lookup"><span data-stu-id="8de64-113">With the Designer, you can place, size, align, and move controls.</span></span> <span data-ttu-id="8de64-114">In alternativa, è possibile aggiungere i controlli tramite codice.</span><span class="sxs-lookup"><span data-stu-id="8de64-114">Alternatively, controls can be added through code.</span></span> <span data-ttu-id="8de64-115">Per ulteriori informazioni, vedere [aggiungere un controllo (Windows Forms)](how-to-add-to-a-form.md).</span><span class="sxs-lookup"><span data-stu-id="8de64-115">For more information, see [Add a control (Windows Forms)](how-to-add-to-a-form.md).</span></span>

## <a name="layout-options"></a><span data-ttu-id="8de64-116">Opzioni di layout</span><span class="sxs-lookup"><span data-stu-id="8de64-116">Layout options</span></span>

<span data-ttu-id="8de64-117">La posizione in cui un controllo viene visualizzato in un elemento padre è determinata dal valore della <xref:System.Windows.Forms.Control.Location> proprietà rispetto alla parte superiore sinistra della superficie padre.</span><span class="sxs-lookup"><span data-stu-id="8de64-117">The position a control appears on a parent is determined by the value of the <xref:System.Windows.Forms.Control.Location> property relative to the top-left of the parent surface.</span></span> <span data-ttu-id="8de64-118">La coordinata della posizione in alto a sinistra nell'elemento padre è `(x0,y0)` .</span><span class="sxs-lookup"><span data-stu-id="8de64-118">The top-left position coordinate in the parent is `(x0,y0)`.</span></span> <span data-ttu-id="8de64-119">La dimensione del controllo è determinata dalla <xref:System.Windows.Forms.Control.Size> proprietà e rappresenta la larghezza e l'altezza del controllo.</span><span class="sxs-lookup"><span data-stu-id="8de64-119">The size of the control is determined by the <xref:System.Windows.Forms.Control.Size> property and represents the width and height of the control.</span></span>

<span data-ttu-id="8de64-120">Oltre al posizionamento manuale e al ridimensionamento, vengono forniti diversi controlli contenitore che consentono di posizionare automaticamente i controlli.</span><span class="sxs-lookup"><span data-stu-id="8de64-120">Besides manual positioning and sizing, various container controls are provided that help with automatic placement of controls.</span></span>

<span data-ttu-id="8de64-121">Per altre informazioni, vedere [posizione e layout dei controlli](layout.md).</span><span class="sxs-lookup"><span data-stu-id="8de64-121">For more information, see [Position and layout of controls](layout.md).</span></span>
<!-- TODO

## Control events

-->

## <a name="see-also"></a><span data-ttu-id="8de64-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8de64-122">See also</span></span>

- [<span data-ttu-id="8de64-123">Posizione e layout dei controlli</span><span class="sxs-lookup"><span data-stu-id="8de64-123">Position and layout of controls</span></span>](layout.md)
- [<span data-ttu-id="8de64-124">Cenni preliminari sul controllo Label (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="8de64-124">Label control overview (Windows Forms .NET)</span></span>](labels.md)
- [<span data-ttu-id="8de64-125">Aggiungere un controllo (Windows Forms .NET)</span><span class="sxs-lookup"><span data-stu-id="8de64-125">Add a control (Windows Forms .NET)</span></span>](how-to-add-to-a-form.md)
