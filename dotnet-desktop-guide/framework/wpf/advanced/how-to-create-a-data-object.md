---
title: 'Procedura: creare un oggetto dati'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataObject class [WPF], creating
- data objects [WPF], creating
- drag-and-drop [WPF], creating data objects
ms.assetid: 022fa142-717d-4fea-a53c-3b52e9d91aff
ms.openlocfilehash: deae8751518d9322e8d924a1b1fcbc20e25b35ed
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967927"
---
# <a name="how-to-create-a-data-object"></a><span data-ttu-id="f89cc-102">Procedura: creare un oggetto dati</span><span class="sxs-lookup"><span data-stu-id="f89cc-102">How to: Create a Data Object</span></span>
<span data-ttu-id="f89cc-103">Negli esempi seguenti vengono illustrati vari modi per creare un oggetto dati utilizzando i costruttori forniti dalla <xref:System.Windows.DataObject> classe.</span><span class="sxs-lookup"><span data-stu-id="f89cc-103">The following examples show various ways to create a data object using the constructors provided by the <xref:System.Windows.DataObject> class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f89cc-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="f89cc-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="f89cc-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f89cc-105">Description</span></span>  
 <span data-ttu-id="f89cc-106">Nell'esempio di codice seguente viene creato un nuovo oggetto dati e viene utilizzato uno dei costruttori di overload ( <xref:System.Windows.DataObject.%23ctor%28System.Object%29> ) per inizializzare l'oggetto dati con una stringa.</span><span class="sxs-lookup"><span data-stu-id="f89cc-106">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%28System.Object%29>) to initialize the data object with a string.</span></span>  <span data-ttu-id="f89cc-107">In questo caso, un formato dati appropriato viene determinato automaticamente in base al tipo di dati archiviati e la conversione automatica dei dati archiviati è consentita per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f89cc-107">In this case, an appropriate data format is determined automatically according to the stored data's type, and auto-converting of the stored data is allowed by default.</span></span>  
  
### <a name="code"></a><span data-ttu-id="f89cc-108">Codice</span><span class="sxs-lookup"><span data-stu-id="f89cc-108">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_simple)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_simple)]  
  
### <a name="description"></a><span data-ttu-id="f89cc-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f89cc-109">Description</span></span>  
 <span data-ttu-id="f89cc-110">Il codice di esempio seguente è una versione ridotta del codice illustrato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="f89cc-110">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="f89cc-111">Codice</span><span class="sxs-lookup"><span data-stu-id="f89cc-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple_Condensed](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_simple_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Simple_Condensed](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_simple_condensed)]  
  
## <a name="example"></a><span data-ttu-id="f89cc-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="f89cc-112">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="f89cc-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f89cc-113">Description</span></span>  
 <span data-ttu-id="f89cc-114">Nell'esempio di codice seguente viene creato un nuovo oggetto dati e viene utilizzato uno dei costruttori di overload ( <xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%29> ) per inizializzare l'oggetto dati con una stringa e un formato dati specificato.</span><span class="sxs-lookup"><span data-stu-id="f89cc-114">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%29>) to initialize the data object with a string and a specified data format.</span></span>  <span data-ttu-id="f89cc-115">In questo caso il formato dati è specificato da una stringa. la <xref:System.Windows.DataFormats> classe fornisce un set di stringhe di tipo predefinite.</span><span class="sxs-lookup"><span data-stu-id="f89cc-115">In this case the data format is specified by a string; the <xref:System.Windows.DataFormats> class provides a set of pre-defined type strings.</span></span> <span data-ttu-id="f89cc-116">La conversione automatica dei dati archiviati è consentita per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f89cc-116">Auto-converting of the stored data is allowed by default.</span></span>  
  
### <a name="code"></a><span data-ttu-id="f89cc-117">Codice</span><span class="sxs-lookup"><span data-stu-id="f89cc-117">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring)]  
  
### <a name="description"></a><span data-ttu-id="f89cc-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f89cc-118">Description</span></span>  
 <span data-ttu-id="f89cc-119">Il codice di esempio seguente è una versione ridotta del codice illustrato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="f89cc-119">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="f89cc-120">Codice</span><span class="sxs-lookup"><span data-stu-id="f89cc-120">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString_Condensed](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_typestring_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_TypeString_Condensed](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_typestring_condensed)]  
  
## <a name="example"></a><span data-ttu-id="f89cc-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="f89cc-121">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="f89cc-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f89cc-122">Description</span></span>  
 <span data-ttu-id="f89cc-123">Nell'esempio di codice seguente viene creato un nuovo oggetto dati e viene utilizzato uno dei costruttori di overload ( <xref:System.Windows.DataObject.%23ctor%2A> ) per inizializzare l'oggetto dati con una stringa e un formato dati specificato.</span><span class="sxs-lookup"><span data-stu-id="f89cc-123">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%2A>) to initialize the data object with a string and a specified data format.</span></span>  <span data-ttu-id="f89cc-124">In questo caso il formato dati è specificato da un <xref:System.Type> parametro.</span><span class="sxs-lookup"><span data-stu-id="f89cc-124">In this case the data format is specified by a <xref:System.Type> parameter.</span></span>  <span data-ttu-id="f89cc-125">La conversione automatica dei dati archiviati è consentita per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f89cc-125">Auto-converting of the stored data is allowed by default.</span></span>  
  
### <a name="code"></a><span data-ttu-id="f89cc-126">Codice</span><span class="sxs-lookup"><span data-stu-id="f89cc-126">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_type)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_type)]  
  
### <a name="description"></a><span data-ttu-id="f89cc-127">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f89cc-127">Description</span></span>  
 <span data-ttu-id="f89cc-128">Il codice di esempio seguente è una versione ridotta del codice illustrato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="f89cc-128">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="f89cc-129">Codice</span><span class="sxs-lookup"><span data-stu-id="f89cc-129">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type_Condensed](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_type_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_Type_Condensed](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_type_condensed)]  
  
## <a name="example"></a><span data-ttu-id="f89cc-130">Esempio</span><span class="sxs-lookup"><span data-stu-id="f89cc-130">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="f89cc-131">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f89cc-131">Description</span></span>  
 <span data-ttu-id="f89cc-132">Nell'esempio di codice seguente viene creato un nuovo oggetto dati e viene utilizzato uno dei costruttori di overload ( <xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%2CSystem.Boolean%29> ) per inizializzare l'oggetto dati con una stringa e un formato dati specificato.</span><span class="sxs-lookup"><span data-stu-id="f89cc-132">The following example code creates a new data object and uses one of the overloaded constructors (<xref:System.Windows.DataObject.%23ctor%28System.String%2CSystem.Object%2CSystem.Boolean%29>) to initialize the data object with a string and a specified data format.</span></span>  <span data-ttu-id="f89cc-133">In questo caso il formato dati è specificato da una stringa. la <xref:System.Windows.DataFormats> classe fornisce un set di stringhe di tipo predefinite.</span><span class="sxs-lookup"><span data-stu-id="f89cc-133">In this case the data format is specified by a string; the <xref:System.Windows.DataFormats> class provides a set of pre-defined type strings.</span></span> <span data-ttu-id="f89cc-134">Questo particolare overload del costruttore consente al chiamante di specificare se è consentita la conversione automatica.</span><span class="sxs-lookup"><span data-stu-id="f89cc-134">This particular constructor overload enables the caller to specify whether auto-converting is allowed.</span></span>  
  
### <a name="code"></a><span data-ttu-id="f89cc-135">Codice</span><span class="sxs-lookup"><span data-stu-id="f89cc-135">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_autoconvert)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_autoconvert)]  
  
### <a name="description"></a><span data-ttu-id="f89cc-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f89cc-136">Description</span></span>  
 <span data-ttu-id="f89cc-137">Il codice di esempio seguente è una versione ridotta del codice illustrato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="f89cc-137">The following example code is a condensed version of the code shown above.</span></span>  
  
### <a name="code"></a><span data-ttu-id="f89cc-138">Codice</span><span class="sxs-lookup"><span data-stu-id="f89cc-138">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert_Condensed](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_createdataobject_autoconvert_condensed)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_CreateDataObject_AutoConvert_Condensed](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_createdataobject_autoconvert_condensed)]  
  
## <a name="see-also"></a><span data-ttu-id="f89cc-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f89cc-139">See also</span></span>

- <xref:System.Windows.IDataObject>
