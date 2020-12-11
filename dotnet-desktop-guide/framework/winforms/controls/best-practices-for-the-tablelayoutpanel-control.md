---
title: Suggerimenti per il controllo TableLayoutPanel
ms.date: 03/30/2017
helpviewer_keywords:
- layout [Windows Forms]
- TableLayoutPanel control [Windows Forms], best practices
- forms [Windows Forms], best practices
- AutoSize property [Windows Forms], tableLayoutPanel control
- controls [Windows Forms], sizing
- TableLayoutPanel control [Windows Forms], AutoSize behavior
- layout [Windows Forms], AutoSize
- layout [Windows Forms], best practices
- best practices [Windows Forms], tableLayoutPanel control
- sizing [Windows Forms], automatic
- automatic sizing
ms.assetid: b6706efb-d7a4-45ec-8cf4-08fa993e3afb
ms.openlocfilehash: e46d0fe6913bec61bd56199b7cb56a9b24d15bd0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962242"
---
# <a name="best-practices-for-the-tablelayoutpanel-control"></a><span data-ttu-id="697d1-102">Suggerimenti per il controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="697d1-102">Best Practices for the TableLayoutPanel Control</span></span>
<span data-ttu-id="697d1-103">Il <xref:System.Windows.Forms.TableLayoutPanel> controllo fornisce potenti funzionalità di layout che è opportuno prendere in considerazione prima di utilizzare nel Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="697d1-103">The <xref:System.Windows.Forms.TableLayoutPanel> control provides powerful layout features that you should consider carefully before using on your Windows Forms.</span></span>

## <a name="recommendations"></a><span data-ttu-id="697d1-104">Consigli</span><span class="sxs-lookup"><span data-stu-id="697d1-104">Recommendations</span></span>
 <span data-ttu-id="697d1-105">I suggerimenti seguenti consentono di usare il <xref:System.Windows.Forms.TableLayoutPanel> controllo per il migliore vantaggio.</span><span class="sxs-lookup"><span data-stu-id="697d1-105">The following recommendations will help you use the <xref:System.Windows.Forms.TableLayoutPanel> control to its best advantage.</span></span>

### <a name="targeted-use"></a><span data-ttu-id="697d1-106">Utilizzo mirato</span><span class="sxs-lookup"><span data-stu-id="697d1-106">Targeted Use</span></span>
 <span data-ttu-id="697d1-107">Utilizzare il <xref:System.Windows.Forms.TableLayoutPanel> controllo con moderazione.</span><span class="sxs-lookup"><span data-stu-id="697d1-107">Use the <xref:System.Windows.Forms.TableLayoutPanel> control sparingly.</span></span> <span data-ttu-id="697d1-108">Non è consigliabile usarlo in tutte le situazioni che richiedono un layout ridimensionabile.</span><span class="sxs-lookup"><span data-stu-id="697d1-108">You should not use it in all situations that require a resizable layout.</span></span> <span data-ttu-id="697d1-109">Nell'elenco seguente vengono descritti i layout che traggono vantaggio dalla maggior parte dell'utilizzo del <xref:System.Windows.Forms.TableLayoutPanel> controllo:</span><span class="sxs-lookup"><span data-stu-id="697d1-109">The following list describes layouts that benefit most from the use of the <xref:System.Windows.Forms.TableLayoutPanel> control:</span></span>

- <span data-ttu-id="697d1-110">Layout in cui sono presenti più parti del modulo che si ridimensionano in modo proporzionale.</span><span class="sxs-lookup"><span data-stu-id="697d1-110">Layouts in which there are multiple parts of the form that resize proportionally to each other.</span></span>

- <span data-ttu-id="697d1-111">Layout che verranno modificati o generati dinamicamente in fase di esecuzione, ad esempio moduli di immissione dati con campi personalizzabili dall'utente aggiunti o sottratti in base alle preferenze.</span><span class="sxs-lookup"><span data-stu-id="697d1-111">Layouts that will be modified or generated dynamically at run time, such as data entry forms that have user-customizable fields added or subtracted based on preferences.</span></span>

- <span data-ttu-id="697d1-112">Layout che devono rimanere a una dimensione complessiva fissa.</span><span class="sxs-lookup"><span data-stu-id="697d1-112">Layouts that should remain at an overall fixed size.</span></span> <span data-ttu-id="697d1-113">Ad esempio, è possibile disporre di una finestra di dialogo che deve rimanere inferiore a 800 x 600, ma è necessario supportare le stringhe localizzate.</span><span class="sxs-lookup"><span data-stu-id="697d1-113">For example, you may have a dialog box that should remain smaller than 800 x 600, but you need to support localized strings.</span></span>

 <span data-ttu-id="697d1-114">Nell'elenco seguente vengono descritti i layout che non traggono un vantaggio notevole dall'utilizzo del <xref:System.Windows.Forms.TableLayoutPanel> controllo:</span><span class="sxs-lookup"><span data-stu-id="697d1-114">The following list describes layouts that do not benefit greatly from using the <xref:System.Windows.Forms.TableLayoutPanel> control:</span></span>

- <span data-ttu-id="697d1-115">Moduli di immissione dati semplici con una singola colonna di etichette e una singola colonna di aree di immissione di testo.</span><span class="sxs-lookup"><span data-stu-id="697d1-115">Simple data entry forms with a single column of labels and a single column of text-entry areas.</span></span>

- <span data-ttu-id="697d1-116">Moduli con un'unica area di visualizzazione di grandi dimensioni che riempie tutto lo spazio disponibile quando si verifica un ridimensionamento.</span><span class="sxs-lookup"><span data-stu-id="697d1-116">Forms with a single large display area that should fill all the available space when a resize occurs.</span></span> <span data-ttu-id="697d1-117">Un esempio è un modulo che visualizza un singolo <xref:System.Windows.Forms.PropertyGrid> controllo.</span><span class="sxs-lookup"><span data-stu-id="697d1-117">An example of this is a form that displays a single <xref:System.Windows.Forms.PropertyGrid> control.</span></span> <span data-ttu-id="697d1-118">In questo caso, usare l'ancoraggio, perché non è necessario espandere nient'altro quando il form viene ridimensionato.</span><span class="sxs-lookup"><span data-stu-id="697d1-118">In this case, use anchoring, because nothing else should expand when the form is resized.</span></span>

 <span data-ttu-id="697d1-119">Scegliere con attenzione quali controlli devono trovarsi in un <xref:System.Windows.Forms.TableLayoutPanel> controllo.</span><span class="sxs-lookup"><span data-stu-id="697d1-119">Choose carefully which controls need to be in a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="697d1-120">Se è possibile aumentare il 30% del testo usando l'ancoraggio, provare a usare <xref:System.Windows.Forms.Control.Anchor%2A> solo la proprietà.</span><span class="sxs-lookup"><span data-stu-id="697d1-120">If you have room for your text to grow by 30% using anchoring, consider using the <xref:System.Windows.Forms.Control.Anchor%2A> property only.</span></span> <span data-ttu-id="697d1-121">Se è possibile stimare lo spazio richiesto dal layout, l'utilizzo di <xref:System.Windows.Forms.Control.Dock%2A> e <xref:System.Windows.Forms.Control.Anchor%2A> risulta più semplice rispetto alla stima dei dettagli dello spazio e del comportamento rimanenti <xref:System.Windows.Forms.Control.AutoSize%2A> .</span><span class="sxs-lookup"><span data-stu-id="697d1-121">If you can estimate the space required by your layout, use of <xref:System.Windows.Forms.Control.Dock%2A> and <xref:System.Windows.Forms.Control.Anchor%2A> is easier than estimating the details of remaining space and <xref:System.Windows.Forms.Control.AutoSize%2A> behavior.</span></span>

 <span data-ttu-id="697d1-122">In generale, quando si progetta il layout con il <xref:System.Windows.Forms.TableLayoutPanel> controllo, è possibile semplificare la progettazione.</span><span class="sxs-lookup"><span data-stu-id="697d1-122">In general, when designing your layout with the <xref:System.Windows.Forms.TableLayoutPanel> control, keep the design as simple as possible.</span></span>

### <a name="use-the-document-outline-window"></a><span data-ttu-id="697d1-123">Utilizzare la finestra Struttura documento</span><span class="sxs-lookup"><span data-stu-id="697d1-123">Use the Document Outline Window</span></span>
 <span data-ttu-id="697d1-124">La finestra Struttura documento fornisce una visualizzazione albero del layout, che è possibile utilizzare per modificare le relazioni tra l'ordine z e l'elemento padre-figlio dei controlli.</span><span class="sxs-lookup"><span data-stu-id="697d1-124">The Document Outline window gives you a tree view of your layout, which you can use to manipulate the z-order and parent-child relationships of your controls.</span></span> <span data-ttu-id="697d1-125">Scegliere **altre finestre** dal **menu Visualizza**, quindi **struttura documento**.</span><span class="sxs-lookup"><span data-stu-id="697d1-125">From the **View menu**, select **Other Windows**, then select **Document Outline**.</span></span>

### <a name="avoid-nesting"></a><span data-ttu-id="697d1-126">Evitare l'annidamento</span><span class="sxs-lookup"><span data-stu-id="697d1-126">Avoid Nesting</span></span>
 <span data-ttu-id="697d1-127">Evitare di annidare altri <xref:System.Windows.Forms.TableLayoutPanel> controlli all'interno di un <xref:System.Windows.Forms.TableLayoutPanel> controllo.</span><span class="sxs-lookup"><span data-stu-id="697d1-127">Avoid nesting other <xref:System.Windows.Forms.TableLayoutPanel> controls within a <xref:System.Windows.Forms.TableLayoutPanel> control.</span></span> <span data-ttu-id="697d1-128">Il debug di layout annidati può essere difficile.</span><span class="sxs-lookup"><span data-stu-id="697d1-128">Debugging nested layouts can be difficult.</span></span>

### <a name="avoid-visual-inheritance"></a><span data-ttu-id="697d1-129">Evitare l'ereditarietà visiva</span><span class="sxs-lookup"><span data-stu-id="697d1-129">Avoid Visual Inheritance</span></span>
 <span data-ttu-id="697d1-130">Il <xref:System.Windows.Forms.TableLayoutPanel> controllo non supporta l'ereditarietà visiva nell'progettazione Windows Form in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="697d1-130">The <xref:System.Windows.Forms.TableLayoutPanel> control does not support visual inheritance in the Windows Forms Designer in Visual Studio.</span></span> <span data-ttu-id="697d1-131">Un <xref:System.Windows.Forms.TableLayoutPanel> controllo in una classe derivata viene visualizzato come "bloccato" in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="697d1-131">A <xref:System.Windows.Forms.TableLayoutPanel> control in a derived class appears as "locked" at design time.</span></span>

## <a name="see-also"></a><span data-ttu-id="697d1-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="697d1-132">See also</span></span>

- <xref:System.Windows.Forms.TableLayoutPanel>
- <xref:System.Windows.Forms.FlowLayoutPanel>
