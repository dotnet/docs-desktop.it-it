---
title: 'Procedura: Creare un controllo con associazione e formattare i dati visualizzati'
ms.date: 03/30/2017
helpviewer_keywords:
- data [Windows Forms], formatting
- bound controls [Windows Forms], creating
- bound controls [Windows Forms], formatting data
ms.assetid: d5a56228-899d-41d9-8af8-87b3f4ec2f94
ms.openlocfilehash: e1448e0dcb80a7ac7ab0199b14957bddec27c133
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951362"
---
# <a name="how-to-create-a-bound-control-and-format-the-displayed-data"></a><span data-ttu-id="17931-102">Procedura: Creare un controllo con associazione e formattare i dati visualizzati</span><span class="sxs-lookup"><span data-stu-id="17931-102">How to: Create a Bound Control and Format the Displayed Data</span></span>

<span data-ttu-id="17931-103">Con Windows Forms data binding, è possibile formattare i dati visualizzati in un controllo associato a dati utilizzando la finestra di dialogo **formattazione e associazione avanzata** .</span><span class="sxs-lookup"><span data-stu-id="17931-103">With Windows Forms data binding, you can format the data displayed in a data-bound control by using the **Formatting and Advanced Binding** dialog box.</span></span>

## <a name="to-bind-a-control-and-format-the-displayed-data"></a><span data-ttu-id="17931-104">Per associare un controllo e formattare i dati visualizzati</span><span class="sxs-lookup"><span data-stu-id="17931-104">To bind a control and format the displayed data</span></span>

1. <span data-ttu-id="17931-105">Effettuare una connessione a un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="17931-105">Connect to a data source.</span></span> <span data-ttu-id="17931-106">Per ulteriori informazioni, vedere [connessione a un'origine dati](/dotnet/framework/data/adonet/connecting-to-a-data-source).</span><span class="sxs-lookup"><span data-stu-id="17931-106">For more information, see [Connecting to a Data Source](/dotnet/framework/data/adonet/connecting-to-a-data-source).</span></span>

2. <span data-ttu-id="17931-107">In Visual Studio selezionare il controllo nel form, quindi aprire la finestra **Proprietà** .</span><span class="sxs-lookup"><span data-stu-id="17931-107">In Visual Studio, select the control on the form, and then open the **Properties** window.</span></span>

3. <span data-ttu-id="17931-108">Espandere la proprietà **(DataBindings)** , quindi nella casella **(avanzate)** fare clic sul pulsante con i puntini di sospensione ( ![ pulsante con i puntini di sospensione (...) nella finestra proprietà di Visual Studio ](./media/how-to-create-a-bound-control-and-format-the-displayed-data/visual-studio-ellipsis-button.png) ) per visualizzare la finestra di dialogo **formattazione e associazione avanzata** , che include un elenco completo delle proprietà per il controllo.</span><span class="sxs-lookup"><span data-stu-id="17931-108">Expand the **(DataBindings)** property, and then in the **(Advanced)** box, click the ellipsis button (![The Ellipsis button (...) in the Properties window of Visual Studio](./media/how-to-create-a-bound-control-and-format-the-displayed-data/visual-studio-ellipsis-button.png)) to display the **Formatting and Advanced Binding** dialog box, which has a complete list of properties for that control.</span></span>

4. <span data-ttu-id="17931-109">Selezionare la proprietà che si desidera associare, quindi selezionare la freccia del **Binding** .</span><span class="sxs-lookup"><span data-stu-id="17931-109">Select the property you want to bind, and then select the **Binding** arrow.</span></span>

     <span data-ttu-id="17931-110">Verrà visualizzato un elenco di origini dati disponibili.</span><span class="sxs-lookup"><span data-stu-id="17931-110">A list of available data sources is displayed.</span></span>

5. <span data-ttu-id="17931-111">Espandere l'origine dati da associare fino a quando non vengono visualizzati i dati desiderati.</span><span class="sxs-lookup"><span data-stu-id="17931-111">Expand the data source you want to bind to until you find the single data element you want.</span></span>

     <span data-ttu-id="17931-112">Se ad esempio si vuole associare il valore di una colonna in una tabella di set di dati, espandere il nome del set di dati, quindi espandere il nome della tabella per visualizzare i nomi delle colonne.</span><span class="sxs-lookup"><span data-stu-id="17931-112">For example, if you are binding to a column value in a dataset's table, expand the name of the dataset, and then expand the table name to display column names.</span></span>

6. <span data-ttu-id="17931-113">Consente di selezionare il nome di un elemento a cui eseguire l'associazione.</span><span class="sxs-lookup"><span data-stu-id="17931-113">Select the name of an element to bind to.</span></span>

7. <span data-ttu-id="17931-114">Nella casella **tipo formato** selezionare il formato che si desidera applicare ai dati visualizzati nel controllo.</span><span class="sxs-lookup"><span data-stu-id="17931-114">In the **Format type** box, select the format you want to apply to the data displayed in the control.</span></span>

     <span data-ttu-id="17931-115">In ogni caso, è possibile specificare il valore visualizzato nel controllo se l'origine dati contiene <xref:System.DBNull>.</span><span class="sxs-lookup"><span data-stu-id="17931-115">In every case, you can specify the value displayed in the control if the data source contains <xref:System.DBNull>.</span></span> <span data-ttu-id="17931-116">In caso contrario, le opzioni variano leggermente, a seconda del tipo di formato scelto.</span><span class="sxs-lookup"><span data-stu-id="17931-116">Otherwise, the options vary slightly, depending on the format type you choose.</span></span> <span data-ttu-id="17931-117">La tabella seguente illustra i tipi di formato e le opzioni.</span><span class="sxs-lookup"><span data-stu-id="17931-117">The following table shows the format types and options.</span></span>

    |<span data-ttu-id="17931-118">Tipo di formato</span><span class="sxs-lookup"><span data-stu-id="17931-118">Format type</span></span>|<span data-ttu-id="17931-119">Opzione di formattazione</span><span class="sxs-lookup"><span data-stu-id="17931-119">Formatting option</span></span>|
    |-----------------|-----------------------|
    |<span data-ttu-id="17931-120">Nessuna formattazione</span><span class="sxs-lookup"><span data-stu-id="17931-120">No Formatting</span></span>|<span data-ttu-id="17931-121">Nessuna opzione.</span><span class="sxs-lookup"><span data-stu-id="17931-121">No options.</span></span>|
    |<span data-ttu-id="17931-122">Numerico</span><span class="sxs-lookup"><span data-stu-id="17931-122">Numeric</span></span>|<span data-ttu-id="17931-123">Specificare il numero di posizioni decimali usando il controllo di scorrimento **posizioni decimali** .</span><span class="sxs-lookup"><span data-stu-id="17931-123">Specify number of decimal places by using **Decimal places** up-down control.</span></span>|
    |<span data-ttu-id="17931-124">Valuta</span><span class="sxs-lookup"><span data-stu-id="17931-124">Currency</span></span>|<span data-ttu-id="17931-125">Specificare il numero di posizioni decimali usando il controllo di scorrimento **posizioni decimali** .</span><span class="sxs-lookup"><span data-stu-id="17931-125">Specify number of decimal places by using **Decimal places** up-down control.</span></span>|
    |<span data-ttu-id="17931-126">Data/Ora</span><span class="sxs-lookup"><span data-stu-id="17931-126">Date Time</span></span>|<span data-ttu-id="17931-127">Selezionare la modalità di visualizzazione della data e dell'ora selezionando uno degli elementi nella casella di selezione **tipo** .</span><span class="sxs-lookup"><span data-stu-id="17931-127">Select how the date and time should be displayed by selecting one of the items in the **Type** selection box.</span></span>|
    |<span data-ttu-id="17931-128">Notazione scientifica</span><span class="sxs-lookup"><span data-stu-id="17931-128">Scientific</span></span>|<span data-ttu-id="17931-129">Specificare il numero di posizioni decimali usando il controllo di scorrimento **posizioni decimali** .</span><span class="sxs-lookup"><span data-stu-id="17931-129">Specify number of decimal places by using **Decimal places** up-down control.</span></span>|
    |<span data-ttu-id="17931-130">Personalizzato</span><span class="sxs-lookup"><span data-stu-id="17931-130">Custom</span></span>|<span data-ttu-id="17931-131">Specificare una stringa di formato personalizzata.</span><span class="sxs-lookup"><span data-stu-id="17931-131">Specify a custom format string using.</span></span><br /><br /> <span data-ttu-id="17931-132">Per altre informazioni, vedere [Formattazione di tipi](/dotnet/standard/base-types/formatting-types).</span><span class="sxs-lookup"><span data-stu-id="17931-132">For more information, see [Formatting Types](/dotnet/standard/base-types/formatting-types).</span></span> <span data-ttu-id="17931-133">**Nota:**  Non è garantito che le stringhe di formato personalizzate round trip tra l'origine dati e il controllo associato.</span><span class="sxs-lookup"><span data-stu-id="17931-133">**Note:**  Custom format strings are not guaranteed to successfully round trip between the data source and bound control.</span></span> <span data-ttu-id="17931-134">Gestire invece l'evento <xref:System.Windows.Forms.Binding.Parse> o <xref:System.Windows.Forms.Binding.Format> per l'associazione e applicare la formattazione personalizzata nel codice di gestione degli eventi.</span><span class="sxs-lookup"><span data-stu-id="17931-134">Instead handle the <xref:System.Windows.Forms.Binding.Parse> or <xref:System.Windows.Forms.Binding.Format> event for the binding and apply custom formatting in the event-handling code.</span></span>|

8. <span data-ttu-id="17931-135">Selezionare **OK** per chiudere la finestra di dialogo **formattazione e associazione avanzata** e tornare al finestra Proprietà.</span><span class="sxs-lookup"><span data-stu-id="17931-135">Select **OK** to close the **Formatting and Advanced Binding** dialog box and return to the Properties window.</span></span>

## <a name="see-also"></a><span data-ttu-id="17931-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="17931-136">See also</span></span>

- [<span data-ttu-id="17931-137">Procedura: Creare un controllo con associazione semplice in un Windows Form</span><span class="sxs-lookup"><span data-stu-id="17931-137">How to: Create a Simple-Bound Control on a Windows Form</span></span>](how-to-create-a-simple-bound-control-on-a-windows-form.md)
- [<span data-ttu-id="17931-138">Convalida dell'input utente in Windows Form</span><span class="sxs-lookup"><span data-stu-id="17931-138">User Input Validation in Windows Forms</span></span>](user-input-validation-in-windows-forms.md)
- [<span data-ttu-id="17931-139">Data binding di Windows Form</span><span class="sxs-lookup"><span data-stu-id="17931-139">Windows Forms Data Binding</span></span>](windows-forms-data-binding.md)
