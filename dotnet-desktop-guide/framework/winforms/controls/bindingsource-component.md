---
title: Componente BindingSource
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [Windows Forms], Windows Forms
- Windows Forms, data binding control
- BindingSource component [Windows Forms]
ms.assetid: 3e2faf4c-f5b8-4fa6-9fbc-f59c37ec2fb9
ms.openlocfilehash: 54639edb512a8bc6c5909282d5e4c210439e2a6e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952596"
---
# <a name="bindingsource-component"></a><span data-ttu-id="aab9d-102">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="aab9d-102">BindingSource Component</span></span>
<span data-ttu-id="aab9d-103">Incapsula un'origine dati per l'associazione ai controlli.</span><span class="sxs-lookup"><span data-stu-id="aab9d-103">Encapsulates a data source for binding to controls.</span></span>  
  
 <span data-ttu-id="aab9d-104">Il componente <xref:System.Windows.Forms.BindingSource> ha due scopi.</span><span class="sxs-lookup"><span data-stu-id="aab9d-104">The <xref:System.Windows.Forms.BindingSource> component serves two purposes.</span></span> <span data-ttu-id="aab9d-105">Innanzitutto fornisce un livello di riferimento indiretto durante l'associazione dei controlli di un form ai dati.</span><span class="sxs-lookup"><span data-stu-id="aab9d-105">First, it provides a layer of indirection when binding the controls on a form to data.</span></span> <span data-ttu-id="aab9d-106">Questo si ottiene associando il componente <xref:System.Windows.Forms.BindingSource> all'origine dati e quindi associando i controlli del form al componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="aab9d-106">This is accomplished by binding the <xref:System.Windows.Forms.BindingSource> component to your data source, and then binding the controls on your form to the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="aab9d-107">Tutte le altre interazioni con i dati, tra cui l'esplorazione, l'ordinamento, il filtro e l'aggiornamento, vengono eseguite mediante chiamate al componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="aab9d-107">All further interaction with the data, including navigating, sorting, filtering, and updating, is accomplished with calls to the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 <span data-ttu-id="aab9d-108">In secondo luogo, il componente <xref:System.Windows.Forms.BindingSource> può fungere da origine dati fortemente tipizzata.</span><span class="sxs-lookup"><span data-stu-id="aab9d-108">Second, the <xref:System.Windows.Forms.BindingSource> component can act as a strongly typed data source.</span></span> <span data-ttu-id="aab9d-109">Aggiungendo un tipo al componente <xref:System.Windows.Forms.BindingSource> con il metodo <xref:System.Windows.Forms.BindingSource.Add%2A>, viene creato un elenco di tale tipo.</span><span class="sxs-lookup"><span data-stu-id="aab9d-109">Adding a type to the <xref:System.Windows.Forms.BindingSource> component with the <xref:System.Windows.Forms.BindingSource.Add%2A> method creates a list of that type.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="aab9d-110">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="aab9d-110">In This Section</span></span>  
 [<span data-ttu-id="aab9d-111">Cenni preliminari sul componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="aab9d-111">BindingSource Component Overview</span></span>](bindingsource-component-overview.md)  
 <span data-ttu-id="aab9d-112">Introduce i concetti generali del componente <xref:System.Windows.Forms.BindingSource>, che consente di associare un'origine dati a un controllo.</span><span class="sxs-lookup"><span data-stu-id="aab9d-112">Introduces the general concepts of the <xref:System.Windows.Forms.BindingSource> component, which allows you to bind a data source to a control.</span></span>  
  
 [<span data-ttu-id="aab9d-113">Procedura: Associare i controlli di Windows Forms a valori di database DBNull</span><span class="sxs-lookup"><span data-stu-id="aab9d-113">How to: Bind Windows Forms Controls to DBNull Database Values</span></span>](how-to-bind-windows-forms-controls-to-dbnull-database-values.md)  
 <span data-ttu-id="aab9d-114">Mostra come gestire un valore <xref:System.DBNull> dell'origine dati con il componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="aab9d-114">Shows how to handle a <xref:System.DBNull> value from the data source using the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 [<span data-ttu-id="aab9d-115">Procedura: Ordinare e filtrare i dati ADO.NET con il componente BindingSource di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="aab9d-115">How to: Sort and Filter ADO.NET Data with the Windows Forms BindingSource Component</span></span>](sort-and-filter-ado-net-data-with-wf-bindingsource-component.md)  
 <span data-ttu-id="aab9d-116">Illustra l'uso del componente <xref:System.Windows.Forms.BindingSource> per applicare criteri di ordinamento e filtri ai dati visualizzati.</span><span class="sxs-lookup"><span data-stu-id="aab9d-116">Demonstrates using the <xref:System.Windows.Forms.BindingSource> component to apply sorts and filters to displayed data.</span></span>  
  
 [<span data-ttu-id="aab9d-117">Procedura: Binding a un servizio Web tramite BindingSource di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="aab9d-117">How to: Bind to a Web Service Using the Windows Forms BindingSource</span></span>](how-to-bind-to-a-web-service-using-the-windows-forms-bindingsource.md)  
 <span data-ttu-id="aab9d-118">Mostra come usare il componente <xref:System.Windows.Forms.BindingSource> per eseguire il binding a un servizio Web.</span><span class="sxs-lookup"><span data-stu-id="aab9d-118">Shows how to use the <xref:System.Windows.Forms.BindingSource> component to bind to a Web service.</span></span>  
  
 [<span data-ttu-id="aab9d-119">Procedura: Gestire errori ed eccezioni relativi al data binding</span><span class="sxs-lookup"><span data-stu-id="aab9d-119">How to: Handle Errors and Exceptions that Occur with Databinding</span></span>](how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)  
 <span data-ttu-id="aab9d-120">Illustra l'uso del componente <xref:System.Windows.Forms.BindingSource> per gestire normalmente gli errori che si verificano in un'operazione di data binding.</span><span class="sxs-lookup"><span data-stu-id="aab9d-120">Demonstrates using the <xref:System.Windows.Forms.BindingSource> component to gracefully handle errors that occur in a data binding operation.</span></span>  
  
 [<span data-ttu-id="aab9d-121">Procedura: Associare un controllo di Windows Forms a un tipo</span><span class="sxs-lookup"><span data-stu-id="aab9d-121">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)  
 <span data-ttu-id="aab9d-122">Illustra l'uso di un componente <xref:System.Windows.Forms.BindingSource> per eseguire il binding a un tipo.</span><span class="sxs-lookup"><span data-stu-id="aab9d-122">Demonstrates using a <xref:System.Windows.Forms.BindingSource> component to bind to a type.</span></span>  
  
 [<span data-ttu-id="aab9d-123">Procedura: Associare un controllo di Windows Forms a un oggetto Factory</span><span class="sxs-lookup"><span data-stu-id="aab9d-123">How to: Bind a Windows Forms Control to a Factory Object</span></span>](how-to-bind-a-windows-forms-control-to-a-factory-object.md)  
 <span data-ttu-id="aab9d-124">Illustra l'uso di un componente <xref:System.Windows.Forms.BindingSource> per eseguire il binding a un oggetto o metodo factory.</span><span class="sxs-lookup"><span data-stu-id="aab9d-124">Demonstrates using a <xref:System.Windows.Forms.BindingSource> component to bind to a factory object or method.</span></span>  
  
 [<span data-ttu-id="aab9d-125">Procedura: Personalizzare l'aggiunta di elementi con BindingSource di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="aab9d-125">How to: Customize Item Addition with the Windows Forms BindingSource</span></span>](how-to-customize-item-addition-with-the-windows-forms-bindingsource.md)  
 <span data-ttu-id="aab9d-126">Illustra l'uso di un componente <xref:System.Windows.Forms.BindingSource> per creare nuovi elementi e aggiungerli a un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="aab9d-126">Demonstrates using a <xref:System.Windows.Forms.BindingSource> component to create new items and add them to a data source.</span></span>  
  
 [<span data-ttu-id="aab9d-127">Procedura: Generare notifiche di modifica usando il metodo ResetItem di BindingSource</span><span class="sxs-lookup"><span data-stu-id="aab9d-127">How to: Raise Change Notifications Using the BindingSource ResetItem Method</span></span>](how-to-raise-change-notifications-using-the-bindingsource-resetitem-method.md)  
 <span data-ttu-id="aab9d-128">Illustra l'uso di un componente <xref:System.Windows.Forms.BindingSource> per generare eventi di notifica di modifica per le origini dati che non supportano la notifica di modifica.</span><span class="sxs-lookup"><span data-stu-id="aab9d-128">Demonstrates using a <xref:System.Windows.Forms.BindingSource> component to raise change-notification events for data sources that do not support change notification.</span></span>  
  
 [<span data-ttu-id="aab9d-129">Procedura: Generare notifiche di modifica usando BindingSource e l'interfaccia INotifyPropertyChanged</span><span class="sxs-lookup"><span data-stu-id="aab9d-129">How to: Raise Change Notifications Using a BindingSource and the INotifyPropertyChanged Interface</span></span>](raise-change-notifications--bindingsource.md)  
 <span data-ttu-id="aab9d-130">Illustra come usare un tipo che eredita da <xref:System.ComponentModel.INotifyPropertyChanged> con un controllo <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="aab9d-130">Demonstrates how to use a type that inherits from the <xref:System.ComponentModel.INotifyPropertyChanged> with a <xref:System.Windows.Forms.BindingSource> control.</span></span>  
  
 [<span data-ttu-id="aab9d-131">Procedura: Riflettere gli aggiornamenti dell'origine dati in un controllo di Windows Forms con BindingSource</span><span class="sxs-lookup"><span data-stu-id="aab9d-131">How to: Reflect Data Source Updates in a Windows Forms Control with the BindingSource</span></span>](reflect-data-source-updates-in-a-wf-control-with-the-bindingsource.md)  
 <span data-ttu-id="aab9d-132">Illustra come rispondere alle modifiche nell'origine dati con il componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="aab9d-132">Demonstrates how to respond to changes in the data source using the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 [<span data-ttu-id="aab9d-133">Procedura: Condividere i dati associati tra moduli usando il componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="aab9d-133">How to: Share Bound Data Across Forms Using the BindingSource Component</span></span>](how-to-share-bound-data-across-forms-using-the-bindingsource-component.md)  
 <span data-ttu-id="aab9d-134">Mostra come usare <xref:System.Windows.Forms.BindingSource> per associare più form alla stessa origine dati.</span><span class="sxs-lookup"><span data-stu-id="aab9d-134">Shows how to use the <xref:System.Windows.Forms.BindingSource> to bind multiple forms to the same data source.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="aab9d-135">Informazioni di riferimento</span><span class="sxs-lookup"><span data-stu-id="aab9d-135">Reference</span></span>  
 <xref:System.Windows.Forms.BindingSource>  
 <span data-ttu-id="aab9d-136">Fornisce la documentazione di riferimento per il componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="aab9d-136">Provides reference documentation for the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
 <xref:System.Windows.Forms.BindingNavigator>  
 <span data-ttu-id="aab9d-137">Fornisce la documentazione di riferimento per il controllo <xref:System.Windows.Forms.BindingNavigator>.</span><span class="sxs-lookup"><span data-stu-id="aab9d-137">Provides reference documentation for the <xref:System.Windows.Forms.BindingNavigator> control.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="aab9d-138">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="aab9d-138">Related Sections</span></span>  
 [<span data-ttu-id="aab9d-139">Data binding di Windows Form</span><span class="sxs-lookup"><span data-stu-id="aab9d-139">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)  
 <span data-ttu-id="aab9d-140">Contiene i collegamenti agli argomenti che descrivono l'architettura di data binding di Windows Form.</span><span class="sxs-lookup"><span data-stu-id="aab9d-140">Contains links to topics describing the Windows Forms data binding architecture.</span></span>  
  
 <span data-ttu-id="aab9d-141">Vedere anche [Associazione di controlli ai dati in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="aab9d-141">Also see [Bind controls to data in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).</span></span>
