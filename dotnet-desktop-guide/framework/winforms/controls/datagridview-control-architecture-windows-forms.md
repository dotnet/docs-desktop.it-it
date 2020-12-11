---
title: Architettura del controllo DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], architecture
ms.assetid: 1c6cabf0-02ee-4bbc-9574-b54bb7f5b19e
ms.openlocfilehash: 2e1884383cca87f8d4ff84f486e2b29761a0c55d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951083"
---
# <a name="datagridview-control-architecture-windows-forms"></a><span data-ttu-id="61a37-102">Architettura del controllo DataGridView (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="61a37-102">DataGridView Control Architecture (Windows Forms)</span></span>
<span data-ttu-id="61a37-103">Il <xref:System.Windows.Forms.DataGridView> controllo e le classi correlate sono progettati per essere un sistema flessibile ed estendibile per la visualizzazione e la modifica dei dati tabulari.</span><span class="sxs-lookup"><span data-stu-id="61a37-103">The <xref:System.Windows.Forms.DataGridView> control and its related classes are designed to be a flexible, extensible system for displaying and editing tabular data.</span></span> <span data-ttu-id="61a37-104">Queste classi sono tutte contenute nello <xref:System.Windows.Forms?displayProperty=nameWithType> spazio dei nomi e sono tutte denominate con il prefisso "DataGridView".</span><span class="sxs-lookup"><span data-stu-id="61a37-104">These classes are all contained in the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace, and they are all named with the "DataGridView" prefix.</span></span>  
  
## <a name="architecture-elements"></a><span data-ttu-id="61a37-105">Elementi dell'architettura</span><span class="sxs-lookup"><span data-stu-id="61a37-105">Architecture Elements</span></span>  
 <span data-ttu-id="61a37-106">Le <xref:System.Windows.Forms.DataGridView> classi complementari primarie derivano da <xref:System.Windows.Forms.DataGridViewElement> .</span><span class="sxs-lookup"><span data-stu-id="61a37-106">The primary <xref:System.Windows.Forms.DataGridView> companion classes derive from <xref:System.Windows.Forms.DataGridViewElement>.</span></span> <span data-ttu-id="61a37-107">Nel modello a oggetti seguente viene illustrata la <xref:System.Windows.Forms.DataGridViewElement> gerarchia di ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="61a37-107">The following object model illustrates the <xref:System.Windows.Forms.DataGridViewElement> inheritance hierarchy.</span></span>  
  
 ![Diagramma che mostra la gerarchia del modello a oggetti DataGridViewElement.](./media/datagridview-control-architecture-windows-forms/datagridviewelement-object-model.gif)  
  
 <span data-ttu-id="61a37-109">La <xref:System.Windows.Forms.DataGridViewElement> classe fornisce un riferimento al controllo padre <xref:System.Windows.Forms.DataGridView> e ha una <xref:System.Windows.Forms.DataGridViewElement.State%2A> proprietà che contiene un valore che rappresenta una combinazione di valori dell' <xref:System.Windows.Forms.DataGridViewElementStates> enumerazione.</span><span class="sxs-lookup"><span data-stu-id="61a37-109">The <xref:System.Windows.Forms.DataGridViewElement> class provides a reference to the parent <xref:System.Windows.Forms.DataGridView> control and has a <xref:System.Windows.Forms.DataGridViewElement.State%2A> property, which holds a value that represents a combination of values from the <xref:System.Windows.Forms.DataGridViewElementStates> enumeration.</span></span>  
  
 <span data-ttu-id="61a37-110">Le sezioni seguenti descrivono <xref:System.Windows.Forms.DataGridView> in modo più dettagliato le classi complementari.</span><span class="sxs-lookup"><span data-stu-id="61a37-110">The following sections describe the <xref:System.Windows.Forms.DataGridView> companion classes in more detail.</span></span>  
  
### <a name="datagridviewelementstates"></a><span data-ttu-id="61a37-111">DataGridViewElementStates</span><span class="sxs-lookup"><span data-stu-id="61a37-111">DataGridViewElementStates</span></span>  
 <span data-ttu-id="61a37-112">L'enumerazione <xref:System.Windows.Forms.DataGridViewElementStates> contiene i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="61a37-112">The <xref:System.Windows.Forms.DataGridViewElementStates> enumeration contains the following values:</span></span>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.None>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.ReadOnly>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Resizable>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.ResizableSet>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Selected>  
  
- <xref:System.Windows.Forms.DataGridViewElementStates.Visible>  
  
 <span data-ttu-id="61a37-113">I valori di questa enumerazione possono essere combinati con gli operatori logici bit per bit, quindi la <xref:System.Windows.Forms.DataGridViewElement.State%2A> proprietà può esprimere più di uno stato in una sola volta.</span><span class="sxs-lookup"><span data-stu-id="61a37-113">The values of this enumeration can be combined with the bitwise logical operators, so the <xref:System.Windows.Forms.DataGridViewElement.State%2A> property can express more than one state at once.</span></span> <span data-ttu-id="61a37-114">Ad esempio, un oggetto <xref:System.Windows.Forms.DataGridViewElement> può essere simultaneamente <xref:System.Windows.Forms.DataGridViewElementStates.Frozen> , <xref:System.Windows.Forms.DataGridViewElementStates.Selected> e <xref:System.Windows.Forms.DataGridViewElementStates.Visible> .</span><span class="sxs-lookup"><span data-stu-id="61a37-114">For example, a <xref:System.Windows.Forms.DataGridViewElement> can be simultaneously <xref:System.Windows.Forms.DataGridViewElementStates.Frozen>, <xref:System.Windows.Forms.DataGridViewElementStates.Selected>, and <xref:System.Windows.Forms.DataGridViewElementStates.Visible>.</span></span>  
  
### <a name="cells-and-bands"></a><span data-ttu-id="61a37-115">Celle e bande</span><span class="sxs-lookup"><span data-stu-id="61a37-115">Cells and Bands</span></span>  
 <span data-ttu-id="61a37-116">Il <xref:System.Windows.Forms.DataGridView> controllo è costituito da due tipi fondamentali di oggetti, ovvero celle e bande.</span><span class="sxs-lookup"><span data-stu-id="61a37-116">The <xref:System.Windows.Forms.DataGridView> control comprises two fundamental kinds of objects: cells and bands.</span></span> <span data-ttu-id="61a37-117">Tutte le celle derivano dalla <xref:System.Windows.Forms.DataGridViewCell> classe di base.</span><span class="sxs-lookup"><span data-stu-id="61a37-117">All cells derive from the <xref:System.Windows.Forms.DataGridViewCell> base class.</span></span> <span data-ttu-id="61a37-118">I due tipi di bande, <xref:System.Windows.Forms.DataGridViewColumn> e <xref:System.Windows.Forms.DataGridViewRow> , derivano entrambi dalla <xref:System.Windows.Forms.DataGridViewBand> classe base.</span><span class="sxs-lookup"><span data-stu-id="61a37-118">The two kinds of bands, <xref:System.Windows.Forms.DataGridViewColumn> and <xref:System.Windows.Forms.DataGridViewRow>, both derive from the <xref:System.Windows.Forms.DataGridViewBand> base class.</span></span>  
  
 <span data-ttu-id="61a37-119">Il <xref:System.Windows.Forms.DataGridView> controllo interagisce con diverse classi, ma il più comunemente rilevato sono <xref:System.Windows.Forms.DataGridViewCell> , <xref:System.Windows.Forms.DataGridViewColumn> e <xref:System.Windows.Forms.DataGridViewRow> .</span><span class="sxs-lookup"><span data-stu-id="61a37-119">The <xref:System.Windows.Forms.DataGridView> control interoperates with several classes, but the most commonly encountered are <xref:System.Windows.Forms.DataGridViewCell>, <xref:System.Windows.Forms.DataGridViewColumn>, and <xref:System.Windows.Forms.DataGridViewRow>.</span></span>  
  
### <a name="datagridviewcell"></a><span data-ttu-id="61a37-120">DataGridViewCell</span><span class="sxs-lookup"><span data-stu-id="61a37-120">DataGridViewCell</span></span>  
 <span data-ttu-id="61a37-121">La cella è l'unità fondamentale di interazione per l'oggetto <xref:System.Windows.Forms.DataGridView> .</span><span class="sxs-lookup"><span data-stu-id="61a37-121">The cell is the fundamental unit of interaction for the <xref:System.Windows.Forms.DataGridView>.</span></span> <span data-ttu-id="61a37-122">La visualizzazione è centrata sulle celle e l'immissione dei dati viene spesso eseguita tramite le celle.</span><span class="sxs-lookup"><span data-stu-id="61a37-122">Display is centered on cells, and data entry is often performed through cells.</span></span> <span data-ttu-id="61a37-123">È possibile accedere alle celle usando la <xref:System.Windows.Forms.DataGridViewRow.Cells%2A> raccolta della <xref:System.Windows.Forms.DataGridViewRow> classe ed è possibile accedere alle celle selezionate usando la <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> raccolta del <xref:System.Windows.Forms.DataGridView> controllo.</span><span class="sxs-lookup"><span data-stu-id="61a37-123">You can access cells by using the <xref:System.Windows.Forms.DataGridViewRow.Cells%2A> collection of the <xref:System.Windows.Forms.DataGridViewRow> class, and you can access the selected cells by using the <xref:System.Windows.Forms.DataGridView.SelectedCells%2A> collection of the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="61a37-124">Nel modello a oggetti seguente viene illustrato questo utilizzo e viene illustrata la <xref:System.Windows.Forms.DataGridViewCell> gerarchia di ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="61a37-124">The following object model illustrates this usage and shows the <xref:System.Windows.Forms.DataGridViewCell> inheritance hierarchy.</span></span>  
  
 ![Diagramma che mostra la gerarchia del modello a oggetti DataGridViewCell.](./media/datagridview-control-architecture-windows-forms/datagridviewcell-object-model.gif)  
  
 <span data-ttu-id="61a37-126">Il <xref:System.Windows.Forms.DataGridViewCell> tipo è una classe di base astratta dalla quale derivano tutti i tipi di cella.</span><span class="sxs-lookup"><span data-stu-id="61a37-126">The <xref:System.Windows.Forms.DataGridViewCell> type is an abstract base class, from which all cell types derive.</span></span> <span data-ttu-id="61a37-127"><xref:System.Windows.Forms.DataGridViewCell> e i relativi tipi derivati non sono Windows Forms controlli, ma alcuni controlli Windows Forms host.</span><span class="sxs-lookup"><span data-stu-id="61a37-127"><xref:System.Windows.Forms.DataGridViewCell> and its derived types are not Windows Forms controls, but some host Windows Forms controls.</span></span> <span data-ttu-id="61a37-128">Qualsiasi funzionalità di modifica supportata da una cella viene in genere gestita da un controllo ospitato.</span><span class="sxs-lookup"><span data-stu-id="61a37-128">Any editing functionality supported by a cell is typically handled by a hosted control.</span></span>  
  
 <span data-ttu-id="61a37-129"><xref:System.Windows.Forms.DataGridViewCell> gli oggetti non controllano l'aspetto e le funzionalità di disegno in modo analogo ai controlli Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="61a37-129"><xref:System.Windows.Forms.DataGridViewCell> objects do not control their own appearance and painting features in the same way as Windows Forms controls.</span></span> <span data-ttu-id="61a37-130">Al contrario, <xref:System.Windows.Forms.DataGridView> è responsabile dell'aspetto degli <xref:System.Windows.Forms.DataGridViewCell> oggetti.</span><span class="sxs-lookup"><span data-stu-id="61a37-130">Instead, the <xref:System.Windows.Forms.DataGridView> is responsible for the appearance of its <xref:System.Windows.Forms.DataGridViewCell> objects.</span></span> <span data-ttu-id="61a37-131">È possibile influenzare in modo significativo l'aspetto e il comportamento delle celle interagendo con le <xref:System.Windows.Forms.DataGridView> proprietà e gli eventi del controllo.</span><span class="sxs-lookup"><span data-stu-id="61a37-131">You can significantly affect the appearance and behavior of cells by interacting with the <xref:System.Windows.Forms.DataGridView> control's properties and events.</span></span> <span data-ttu-id="61a37-132">Quando si dispone di requisiti speciali per le personalizzazioni che esulano dalle funzionalità del <xref:System.Windows.Forms.DataGridView> controllo, è possibile implementare una classe personalizzata che deriva da <xref:System.Windows.Forms.DataGridViewCell> o da una delle relative classi figlio.</span><span class="sxs-lookup"><span data-stu-id="61a37-132">When you have special requirements for customizations that are beyond the capabilities of the <xref:System.Windows.Forms.DataGridView> control, you can implement your own class that derives from <xref:System.Windows.Forms.DataGridViewCell> or one of its child classes.</span></span>  
  
 <span data-ttu-id="61a37-133">Nell'elenco seguente vengono illustrate le classi derivate da <xref:System.Windows.Forms.DataGridViewCell> :</span><span class="sxs-lookup"><span data-stu-id="61a37-133">The following list shows the classes derived from <xref:System.Windows.Forms.DataGridViewCell>:</span></span>  
  
- <xref:System.Windows.Forms.DataGridViewTextBoxCell>  
  
- <xref:System.Windows.Forms.DataGridViewButtonCell>  
  
- <xref:System.Windows.Forms.DataGridViewLinkCell>  
  
- <xref:System.Windows.Forms.DataGridViewCheckBoxCell>  
  
- <xref:System.Windows.Forms.DataGridViewComboBoxCell>  
  
- <xref:System.Windows.Forms.DataGridViewImageCell>  
  
- <xref:System.Windows.Forms.DataGridViewHeaderCell>  
  
- <xref:System.Windows.Forms.DataGridViewRowHeaderCell>  
  
- <xref:System.Windows.Forms.DataGridViewColumnHeaderCell>  
  
- <xref:System.Windows.Forms.DataGridViewTopLeftHeaderCell>  
  
- <span data-ttu-id="61a37-134">Tipi di cella personalizzati</span><span class="sxs-lookup"><span data-stu-id="61a37-134">Your custom cell types</span></span>  
  
### <a name="datagridviewcolumn"></a><span data-ttu-id="61a37-135">DataGridViewColumn</span><span class="sxs-lookup"><span data-stu-id="61a37-135">DataGridViewColumn</span></span>  
 <span data-ttu-id="61a37-136">Lo schema dell' <xref:System.Windows.Forms.DataGridView> archivio dati associato del controllo è espresso nelle colonne del <xref:System.Windows.Forms.DataGridView> controllo.</span><span class="sxs-lookup"><span data-stu-id="61a37-136">The schema of the <xref:System.Windows.Forms.DataGridView> control's attached data store is expressed in the <xref:System.Windows.Forms.DataGridView> control's columns.</span></span> <span data-ttu-id="61a37-137">È possibile accedere alle <xref:System.Windows.Forms.DataGridView> colonne del controllo tramite la <xref:System.Windows.Forms.DataGridView.Columns%2A> raccolta.</span><span class="sxs-lookup"><span data-stu-id="61a37-137">You can access the <xref:System.Windows.Forms.DataGridView> control's columns by using the <xref:System.Windows.Forms.DataGridView.Columns%2A> collection.</span></span> <span data-ttu-id="61a37-138">È possibile accedere alle colonne selezionate tramite la <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> raccolta.</span><span class="sxs-lookup"><span data-stu-id="61a37-138">You can access the selected columns by using the <xref:System.Windows.Forms.DataGridView.SelectedColumns%2A> collection.</span></span> <span data-ttu-id="61a37-139">Nel modello a oggetti seguente viene illustrato questo utilizzo e viene illustrata la <xref:System.Windows.Forms.DataGridViewColumn> gerarchia di ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="61a37-139">The following object model illustrates this usage and shows the <xref:System.Windows.Forms.DataGridViewColumn> inheritance hierarchy.</span></span>  
  
 ![Diagramma che mostra la gerarchia del modello a oggetti DataGridViewColumn.](./media/datagridview-control-architecture-windows-forms/datagridviewcolumn-object-model.gif)  
  
 <span data-ttu-id="61a37-141">Alcuni tipi di cella chiave hanno tipi di colonna corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="61a37-141">Some of the key cell types have corresponding column types.</span></span> <span data-ttu-id="61a37-142">Sono derivati dalla <xref:System.Windows.Forms.DataGridViewColumn> classe di base.</span><span class="sxs-lookup"><span data-stu-id="61a37-142">These are derived from the <xref:System.Windows.Forms.DataGridViewColumn> base class.</span></span>  
  
 <span data-ttu-id="61a37-143">Nell'elenco seguente vengono illustrate le classi derivate da <xref:System.Windows.Forms.DataGridViewColumn> :</span><span class="sxs-lookup"><span data-stu-id="61a37-143">The following list shows the classes derived from <xref:System.Windows.Forms.DataGridViewColumn>:</span></span>  
  
- <xref:System.Windows.Forms.DataGridViewButtonColumn>  
  
- <xref:System.Windows.Forms.DataGridViewCheckBoxColumn>  
  
- <xref:System.Windows.Forms.DataGridViewComboBoxColumn>  
  
- <xref:System.Windows.Forms.DataGridViewImageColumn>  
  
- <xref:System.Windows.Forms.DataGridViewTextBoxColumn>  
  
- <xref:System.Windows.Forms.DataGridViewLinkColumn>  
  
- <span data-ttu-id="61a37-144">Tipi di colonna personalizzati</span><span class="sxs-lookup"><span data-stu-id="61a37-144">Your custom column types</span></span>  
  
### <a name="datagridview-editing-controls"></a><span data-ttu-id="61a37-145">Controlli di modifica DataGridView</span><span class="sxs-lookup"><span data-stu-id="61a37-145">DataGridView Editing Controls</span></span>  
 <span data-ttu-id="61a37-146">Le celle che supportano la funzionalità di modifica avanzata utilizzano in genere un controllo ospitato derivato da un controllo Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="61a37-146">Cells that support advanced editing functionality typically use a hosted control that is derived from a Windows Forms control.</span></span> <span data-ttu-id="61a37-147">Questi controlli implementano anche l' <xref:System.Windows.Forms.IDataGridViewEditingControl> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="61a37-147">These controls also implement the <xref:System.Windows.Forms.IDataGridViewEditingControl> interface.</span></span> <span data-ttu-id="61a37-148">Nel modello a oggetti seguente viene illustrato l'utilizzo di questi controlli.</span><span class="sxs-lookup"><span data-stu-id="61a37-148">The following object model illustrates the usage of these controls.</span></span>  
  
 ![Diagramma che mostra la gerarchia del modello a oggetti del controllo di modifica DataGridView.](./media/datagridview-control-architecture-windows-forms/datagridviewediting-object-model.gif)  
  
 <span data-ttu-id="61a37-150">Con il controllo vengono forniti i controlli di modifica seguenti <xref:System.Windows.Forms.DataGridView> :</span><span class="sxs-lookup"><span data-stu-id="61a37-150">The following editing controls are provided with the <xref:System.Windows.Forms.DataGridView> control:</span></span>  
  
- <xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>  
  
- <xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>  
  
 <span data-ttu-id="61a37-151">Per informazioni sulla creazione di controlli di modifica personalizzati, vedere [How to: Host Controls in Windows Forms celle DataGridView](how-to-host-controls-in-windows-forms-datagridview-cells.md).</span><span class="sxs-lookup"><span data-stu-id="61a37-151">For information about creating your own editing controls, see [How to: Host Controls in Windows Forms DataGridView Cells](how-to-host-controls-in-windows-forms-datagridview-cells.md).</span></span>  
  
 <span data-ttu-id="61a37-152">Nella tabella seguente viene illustrata la relazione tra i tipi di cella, i tipi di colonna e i controlli di modifica.</span><span class="sxs-lookup"><span data-stu-id="61a37-152">The following table illustrates the relationship among cell types, column types, and editing controls.</span></span>  
  
|<span data-ttu-id="61a37-153">Tipo di cella</span><span class="sxs-lookup"><span data-stu-id="61a37-153">Cell type</span></span>|<span data-ttu-id="61a37-154">Controllo ospitato</span><span class="sxs-lookup"><span data-stu-id="61a37-154">Hosted control</span></span>|<span data-ttu-id="61a37-155">Tipo di colonna</span><span class="sxs-lookup"><span data-stu-id="61a37-155">Column type</span></span>|  
|---------------|--------------------|-----------------|  
|<xref:System.Windows.Forms.DataGridViewButtonCell>|<span data-ttu-id="61a37-156">n/d</span><span class="sxs-lookup"><span data-stu-id="61a37-156">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewButtonColumn>|  
|<xref:System.Windows.Forms.DataGridViewCheckBoxCell>|<span data-ttu-id="61a37-157">n/d</span><span class="sxs-lookup"><span data-stu-id="61a37-157">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewCheckBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewComboBoxCell>|<xref:System.Windows.Forms.DataGridViewComboBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewComboBoxColumn>|  
|<xref:System.Windows.Forms.DataGridViewImageCell>|<span data-ttu-id="61a37-158">n/d</span><span class="sxs-lookup"><span data-stu-id="61a37-158">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewImageColumn>|  
|<xref:System.Windows.Forms.DataGridViewLinkCell>|<span data-ttu-id="61a37-159">n/d</span><span class="sxs-lookup"><span data-stu-id="61a37-159">n/a</span></span>|<xref:System.Windows.Forms.DataGridViewLinkColumn>|  
|<xref:System.Windows.Forms.DataGridViewTextBoxCell>|<xref:System.Windows.Forms.DataGridViewTextBoxEditingControl>|<xref:System.Windows.Forms.DataGridViewTextBoxColumn>|  
  
### <a name="datagridviewrow"></a><span data-ttu-id="61a37-160">DataGridViewRow</span><span class="sxs-lookup"><span data-stu-id="61a37-160">DataGridViewRow</span></span>  
 <span data-ttu-id="61a37-161">La <xref:System.Windows.Forms.DataGridViewRow> classe Visualizza i campi dati di un record dall'archivio dati a cui <xref:System.Windows.Forms.DataGridView> è associato il controllo.</span><span class="sxs-lookup"><span data-stu-id="61a37-161">The <xref:System.Windows.Forms.DataGridViewRow> class displays a record's data fields from the data store to which the <xref:System.Windows.Forms.DataGridView> control is attached.</span></span> <span data-ttu-id="61a37-162">È possibile accedere alle <xref:System.Windows.Forms.DataGridView> righe del controllo tramite la <xref:System.Windows.Forms.DataGridView.Rows%2A> raccolta.</span><span class="sxs-lookup"><span data-stu-id="61a37-162">You can access the <xref:System.Windows.Forms.DataGridView> control's rows by using the <xref:System.Windows.Forms.DataGridView.Rows%2A> collection.</span></span> <span data-ttu-id="61a37-163">È possibile accedere alle righe selezionate tramite la <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> raccolta.</span><span class="sxs-lookup"><span data-stu-id="61a37-163">You can access the selected rows by using the <xref:System.Windows.Forms.DataGridView.SelectedRows%2A> collection.</span></span> <span data-ttu-id="61a37-164">Nel modello a oggetti seguente viene illustrato questo utilizzo e viene illustrata la <xref:System.Windows.Forms.DataGridViewRow> gerarchia di ereditarietà.</span><span class="sxs-lookup"><span data-stu-id="61a37-164">The following object model illustrates this usage and shows the <xref:System.Windows.Forms.DataGridViewRow> inheritance hierarchy.</span></span>  
  
 ![Diagramma che mostra la gerarchia del modello a oggetti DataGridViewRow.](./media/datagridview-control-architecture-windows-forms/datagridviewrow-object-model.gif)
  
 <span data-ttu-id="61a37-166">È possibile derivare i propri tipi dalla <xref:System.Windows.Forms.DataGridViewRow> classe, anche se in genere non è necessario.</span><span class="sxs-lookup"><span data-stu-id="61a37-166">You can derive your own types from the <xref:System.Windows.Forms.DataGridViewRow> class, although this will typically not be necessary.</span></span> <span data-ttu-id="61a37-167">Il <xref:System.Windows.Forms.DataGridView> controllo dispone di diversi eventi e proprietà correlati alle righe per la personalizzazione del comportamento dei <xref:System.Windows.Forms.DataGridViewRow> relativi oggetti.</span><span class="sxs-lookup"><span data-stu-id="61a37-167">The <xref:System.Windows.Forms.DataGridView> control has several row-related events and properties for customizing the behavior of its <xref:System.Windows.Forms.DataGridViewRow> objects.</span></span>  
  
 <span data-ttu-id="61a37-168">Se si Abilita la <xref:System.Windows.Forms.DataGridView> proprietà del controllo <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> , viene visualizzata una riga speciale per l'aggiunta di nuove righe come ultima riga.</span><span class="sxs-lookup"><span data-stu-id="61a37-168">If you enable the <xref:System.Windows.Forms.DataGridView> control's <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> property, a special row for adding new rows appears as the last row.</span></span> <span data-ttu-id="61a37-169">Questa riga fa parte della <xref:System.Windows.Forms.DataGridView.Rows%2A> raccolta, ma dispone di funzionalità speciali che potrebbero richiedere attenzione.</span><span class="sxs-lookup"><span data-stu-id="61a37-169">This row is part of the <xref:System.Windows.Forms.DataGridView.Rows%2A> collection, but it has special functionality that may require your attention.</span></span> <span data-ttu-id="61a37-170">Per ulteriori informazioni, vedere [utilizzo della riga per i nuovi record nel controllo DataGridView Windows Forms](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="61a37-170">For more information, see [Using the Row for New Records in the Windows Forms DataGridView Control](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61a37-171">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61a37-171">See also</span></span>

- [<span data-ttu-id="61a37-172">Panoramica del controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="61a37-172">DataGridView Control Overview</span></span>](datagridview-control-overview-windows-forms.md)
- [<span data-ttu-id="61a37-173">Personalizzazione del controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="61a37-173">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="61a37-174">Utilizzo della riga per i nuovi record del controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="61a37-174">Using the Row for New Records in the Windows Forms DataGridView Control</span></span>](using-the-row-for-new-records-in-the-windows-forms-datagridview-control.md)
