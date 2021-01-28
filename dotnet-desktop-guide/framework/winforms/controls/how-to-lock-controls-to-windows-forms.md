---
title: Bloccare i controlli
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, locking
- controls [Windows Forms], locking
ms.assetid: 94efe0d2-c14e-4d14-b903-63ea9b07e290
ms.openlocfilehash: 2bd9c3c7c1109375a850a8bf65481931b475ada6
ms.sourcegitcommit: 7f48b9ecf8a30db42c8ecea0dd4df577736631a2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2021
ms.locfileid: "98957071"
---
# <a name="how-to-lock-controls-to-windows-forms"></a><span data-ttu-id="66469-102">Procedura: bloccare i controlli per Windows Form</span><span class="sxs-lookup"><span data-stu-id="66469-102">How to: Lock controls to Windows Forms</span></span>

<span data-ttu-id="66469-103">Quando si progetta l'interfaccia utente dell'applicazione Windows, è possibile bloccare i controlli una volta posizionati correttamente, in modo che non vengano spostati o ridimensionati inavvertitamente durante l'impostazione di altre proprietà.</span><span class="sxs-lookup"><span data-stu-id="66469-103">When you design the user interface (UI) of your Windows application, you can lock the controls once they are positioned correctly, so that you do not inadvertently move or resize them when setting other properties.</span></span>

<span data-ttu-id="66469-104">Inoltre, è possibile bloccare e sbloccare tutti i controlli del form contemporaneamente, che risulta utile per i moduli con molti controlli oppure è possibile sbloccare singoli controlli.</span><span class="sxs-lookup"><span data-stu-id="66469-104">Additionally, you can lock and unlock all the controls on the form at once, which is helpful for forms with many controls, or you can unlock individual controls.</span></span> <span data-ttu-id="66469-105">Dopo aver inserito tutti i controlli in cui si desidera nel form, bloccarli tutti sul posto per evitare un movimento errato.</span><span class="sxs-lookup"><span data-stu-id="66469-105">Once you have placed all the controls where you want them on the form, lock them all in place to prevent erroneous movement.</span></span>

## <a name="to-lock-a-control"></a><span data-ttu-id="66469-106">Per bloccare un controllo</span><span class="sxs-lookup"><span data-stu-id="66469-106">To lock a control</span></span>

<span data-ttu-id="66469-107">Nella finestra **Proprietà** di Visual Studio selezionare la proprietà **Locked** , quindi selezionare **true**.</span><span class="sxs-lookup"><span data-stu-id="66469-107">In the **Properties** window of Visual Studio, select the **Locked** property and then select **true**.</span></span> <span data-ttu-id="66469-108">Facendo doppio clic sul nome, l'impostazione della proprietà viene attivata o disattivata.</span><span class="sxs-lookup"><span data-stu-id="66469-108">(Double-clicking the name toggles the property setting.)</span></span>

<span data-ttu-id="66469-109">In alternativa, fare clic con il pulsante destro del mouse sul controllo e scegliere **Blocca controlli**.</span><span class="sxs-lookup"><span data-stu-id="66469-109">Alternatively, right-click the control and choose **Lock Controls**.</span></span>

> [!NOTE]
> <span data-ttu-id="66469-110">I controlli di blocco ne impediscono il trascinamento in una nuova dimensione o posizione nell'area di progettazione.</span><span class="sxs-lookup"><span data-stu-id="66469-110">Locking controls prevents them from being dragged to a new size or location on the design surface.</span></span> <span data-ttu-id="66469-111">Tuttavia, è comunque possibile modificare la dimensione o la posizione dei controlli per mezzo della finestra **Proprietà** o nel codice.</span><span class="sxs-lookup"><span data-stu-id="66469-111">However, you can still change the size or location of controls by means of the **Properties** window or in code.</span></span>

## <a name="to-lock-all-the-controls-on-a-form"></a><span data-ttu-id="66469-112">Per bloccare tutti i controlli in un form</span><span class="sxs-lookup"><span data-stu-id="66469-112">To lock all the controls on a form</span></span>

<span data-ttu-id="66469-113">Scegliere **Blocca controlli** dal menu **formato** .</span><span class="sxs-lookup"><span data-stu-id="66469-113">From the **Format** menu, choose **Lock Controls**.</span></span>

> [!NOTE]
> <span data-ttu-id="66469-114">Questo comando blocca anche le dimensioni del form, perché un modulo è un controllo.</span><span class="sxs-lookup"><span data-stu-id="66469-114">This command locks the form's size as well, because a form is a control.</span></span>

## <a name="to-unlock-all-locked-controls-on-a-form"></a><span data-ttu-id="66469-115">Per sbloccare tutti i controlli bloccati in un form</span><span class="sxs-lookup"><span data-stu-id="66469-115">To unlock all locked controls on a form</span></span>

<span data-ttu-id="66469-116">Scegliere **Blocca controlli** dal menu **formato** .</span><span class="sxs-lookup"><span data-stu-id="66469-116">From the **Format** menu, choose **Lock Controls**.</span></span>

<span data-ttu-id="66469-117">Tutti i controlli bloccati in precedenza nel modulo sono ora sbloccati.</span><span class="sxs-lookup"><span data-stu-id="66469-117">All previously locked controls on the form are now unlocked.</span></span>

## <a name="to-unlock-locked-controls-individually"></a><span data-ttu-id="66469-118">Per sbloccare singolarmente i controlli bloccati</span><span class="sxs-lookup"><span data-stu-id="66469-118">To unlock locked controls individually</span></span>

<span data-ttu-id="66469-119">Nella finestra **Proprietà** selezionare la proprietà **Locked** , quindi selezionare **false**.</span><span class="sxs-lookup"><span data-stu-id="66469-119">In the **Properties** window, select the **Locked** property and then select **false**.</span></span> <span data-ttu-id="66469-120">Facendo doppio clic sul nome, l'impostazione della proprietà viene attivata o disattivata.</span><span class="sxs-lookup"><span data-stu-id="66469-120">(Double-clicking the name toggles the property setting.)</span></span>

## <a name="see-also"></a><span data-ttu-id="66469-121">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="66469-121">See also</span></span>

- [<span data-ttu-id="66469-122">Controlli di Windows Form</span><span class="sxs-lookup"><span data-stu-id="66469-122">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="66469-123">Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida</span><span class="sxs-lookup"><span data-stu-id="66469-123">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="66469-124">Controlli da usare in Windows Form</span><span class="sxs-lookup"><span data-stu-id="66469-124">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="66469-125">Controlli Windows Form per funzione</span><span class="sxs-lookup"><span data-stu-id="66469-125">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
