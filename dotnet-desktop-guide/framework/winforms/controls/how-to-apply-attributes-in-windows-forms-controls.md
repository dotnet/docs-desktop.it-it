---
title: Applicare gli attributi nei controlli
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms], applying attributes
- attributes [Windows Forms], applying
- Windows Forms controls, applying attributes
ms.assetid: af0a3f7f-155b-4ba1-83c4-9cf721331a06
ms.openlocfilehash: f12b430d787b4b974e12902b2c17d3a35a09e468
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962059"
---
# <a name="how-to-apply-attributes-in-windows-forms-controls"></a><span data-ttu-id="d1dae-102">Procedura: Applicare attributi nei controlli Windows Forms</span><span class="sxs-lookup"><span data-stu-id="d1dae-102">How to: Apply Attributes in Windows Forms Controls</span></span>

<span data-ttu-id="d1dae-103">Per sviluppare componenti e controlli che interagiscono correttamente con l'ambiente di progettazione e vengono eseguiti correttamente in fase di esecuzione, è necessario applicare correttamente gli attributi a classi e membri.</span><span class="sxs-lookup"><span data-stu-id="d1dae-103">To develop components and controls that interact correctly with the design environment and execute correctly at run time, you need to apply attributes correctly to classes and members.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d1dae-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="d1dae-104">Example</span></span>  

 <span data-ttu-id="d1dae-105">Nell'esempio di codice riportato di seguito viene illustrato come utilizzare diversi attributi in un controllo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="d1dae-105">The following code example demonstrates how to use several attributes on a custom control.</span></span> <span data-ttu-id="d1dae-106">Il controllo illustra una semplice funzionalità di registrazione.</span><span class="sxs-lookup"><span data-stu-id="d1dae-106">The control demonstrates a simple logging capability.</span></span> <span data-ttu-id="d1dae-107">Quando il controllo è associato a un'origine dati, Visualizza i valori inviati dall'origine dati in un <xref:System.Windows.Forms.DataGridView> controllo.</span><span class="sxs-lookup"><span data-stu-id="d1dae-107">When the control is bound to a data source, it displays the values sent by the data source in a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="d1dae-108">Se un valore supera il valore specificato dalla `Threshold` proprietà, `ThresholdExceeded` viene generato un evento.</span><span class="sxs-lookup"><span data-stu-id="d1dae-108">If a value exceeds the value specified by the `Threshold` property, a `ThresholdExceeded` event is raised.</span></span>  
  
 <span data-ttu-id="d1dae-109">`AttributesDemoControl`Registra i valori con una `LogEntry` classe.</span><span class="sxs-lookup"><span data-stu-id="d1dae-109">The `AttributesDemoControl` logs values with a `LogEntry` class.</span></span> <span data-ttu-id="d1dae-110">La `LogEntry` classe è una classe modello, che significa che è parametrizzata sul tipo che registra.</span><span class="sxs-lookup"><span data-stu-id="d1dae-110">The `LogEntry` class is a template class, which means it is parameterized on the type that it logs.</span></span> <span data-ttu-id="d1dae-111">Se, ad esempio, l'oggetto `AttributesDemoControl` sta registrando valori di tipo `float` , ogni `LogEntry` istanza viene dichiarata e utilizzata come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="d1dae-111">For example, if the `AttributesDemoControl` is logging values of type `float`, each `LogEntry` instance is declared and used as follows.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#110)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#110](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#110)]  
  
> [!NOTE]
> <span data-ttu-id="d1dae-112">Poiché `LogEntry` è parametrizzato da un tipo arbitrario, deve utilizzare la reflection per operare sul tipo di parametro.</span><span class="sxs-lookup"><span data-stu-id="d1dae-112">Because `LogEntry` is parameterized by an arbitrary type, it must use reflection to operate on the parameter type.</span></span> <span data-ttu-id="d1dae-113">Per il funzionamento della funzionalità di soglia, il tipo di parametro `T` deve implementare l' <xref:System.IComparable> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="d1dae-113">For the threshold feature to work, the parameter type `T` must implement the <xref:System.IComparable> interface.</span></span>  
  
 <span data-ttu-id="d1dae-114">Il form che ospita le `AttributesDemoControl` query di un contatore delle prestazioni periodicamente.</span><span class="sxs-lookup"><span data-stu-id="d1dae-114">The form that hosts the `AttributesDemoControl` queries a performance counter periodically.</span></span> <span data-ttu-id="d1dae-115">Ogni valore è incluso in un oggetto `LogEntry` del tipo appropriato e viene aggiunto al form <xref:System.Windows.Forms.BindingSource> .</span><span class="sxs-lookup"><span data-stu-id="d1dae-115">Each value is packaged in a `LogEntry` of the appropriate type and added to the form's <xref:System.Windows.Forms.BindingSource>.</span></span> <span data-ttu-id="d1dae-116">`AttributesDemoControl`Riceve il valore tramite la relativa data binding e visualizza il valore in un <xref:System.Windows.Forms.DataGridView> controllo.</span><span class="sxs-lookup"><span data-stu-id="d1dae-116">The `AttributesDemoControl` receives the value through its data binding and displays the value in a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#1)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#1)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/form1.cs#100)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/form1.vb#100)]  
  
 <span data-ttu-id="d1dae-117">Il primo esempio di codice è l' `AttributesDemoControl` implementazione di.</span><span class="sxs-lookup"><span data-stu-id="d1dae-117">The first code example is the `AttributesDemoControl` implementation.</span></span> <span data-ttu-id="d1dae-118">Nel secondo esempio di codice viene illustrato un form che utilizza `AttributesDemoControl` .</span><span class="sxs-lookup"><span data-stu-id="d1dae-118">The second code example demonstrates a form that uses the `AttributesDemoControl`.</span></span>  
  
## <a name="class-level-attributes"></a><span data-ttu-id="d1dae-119">Attributi a livello di classe</span><span class="sxs-lookup"><span data-stu-id="d1dae-119">Class-level Attributes</span></span>  

 <span data-ttu-id="d1dae-120">Alcuni attributi vengono applicati a livello di classe.</span><span class="sxs-lookup"><span data-stu-id="d1dae-120">Some attributes are applied at the class level.</span></span> <span data-ttu-id="d1dae-121">Nell'esempio di codice riportato di seguito vengono illustrati gli attributi comunemente applicati a un controllo Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="d1dae-121">The following code example shows the attributes that are commonly applied to a Windows Forms control.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#20)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#20](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#20)]  
  
### <a name="typeconverter-attribute"></a><span data-ttu-id="d1dae-122">TypeConverter (attributo)</span><span class="sxs-lookup"><span data-stu-id="d1dae-122">TypeConverter Attribute</span></span>  

 <span data-ttu-id="d1dae-123"><xref:System.ComponentModel.TypeConverterAttribute> è un altro attributo a livello di classe comunemente utilizzato.</span><span class="sxs-lookup"><span data-stu-id="d1dae-123"><xref:System.ComponentModel.TypeConverterAttribute> is another commonly used class-level attribute.</span></span> <span data-ttu-id="d1dae-124">Nell'esempio di codice riportato di seguito viene illustrato l'utilizzo della `LogEntry` classe.</span><span class="sxs-lookup"><span data-stu-id="d1dae-124">The following code example shows its use for the `LogEntry` class.</span></span> <span data-ttu-id="d1dae-125">In questo esempio viene inoltre illustrata un'implementazione di <xref:System.ComponentModel.TypeConverter> per il `LogEntry` tipo, denominato `LogEntryTypeConverter` .</span><span class="sxs-lookup"><span data-stu-id="d1dae-125">This example also shows an implementation of a <xref:System.ComponentModel.TypeConverter> for the `LogEntry` type, called `LogEntryTypeConverter`.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#5)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#5)]  
  
## <a name="member-level-attributes"></a><span data-ttu-id="d1dae-126">Attributi a livello di membro</span><span class="sxs-lookup"><span data-stu-id="d1dae-126">Member-level Attributes</span></span>  

 <span data-ttu-id="d1dae-127">Alcuni attributi vengono applicati a livello di membro.</span><span class="sxs-lookup"><span data-stu-id="d1dae-127">Some attributes are applied at the member level.</span></span> <span data-ttu-id="d1dae-128">Negli esempi di codice riportati di seguito vengono illustrati alcuni attributi che vengono comunemente applicati alle proprietà dei controlli Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="d1dae-128">The following code examples show some attributes that are commonly applied to properties of Windows Forms controls.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#21)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#21)]  
  
### <a name="ambientvalue-attribute"></a><span data-ttu-id="d1dae-129">Attributo AmbientValue</span><span class="sxs-lookup"><span data-stu-id="d1dae-129">AmbientValue Attribute</span></span>  

 <span data-ttu-id="d1dae-130">Nell'esempio seguente viene illustrato il <xref:System.ComponentModel.AmbientValueAttribute> e viene mostrato il codice che supporta l'interazione con l'ambiente di progettazione.</span><span class="sxs-lookup"><span data-stu-id="d1dae-130">The following example demonstrates the <xref:System.ComponentModel.AmbientValueAttribute> and shows code that supports its interaction with the design environment.</span></span> <span data-ttu-id="d1dae-131">Questa interazione è detta *ambiente*.</span><span class="sxs-lookup"><span data-stu-id="d1dae-131">This interaction is called *ambience*.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#23)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#23](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#23)]  
  
### <a name="databinding-attributes"></a><span data-ttu-id="d1dae-132">Attributi DataBinding</span><span class="sxs-lookup"><span data-stu-id="d1dae-132">Databinding Attributes</span></span>  

 <span data-ttu-id="d1dae-133">Negli esempi seguenti viene illustrata un'implementazione di data binding complesse.</span><span class="sxs-lookup"><span data-stu-id="d1dae-133">The following examples demonstrate an implementation of complex data binding.</span></span> <span data-ttu-id="d1dae-134">Il livello di classe <xref:System.ComponentModel.ComplexBindingPropertiesAttribute> , illustrato in precedenza, specifica `DataSource` le `DataMember` proprietà e da utilizzare per data binding.</span><span class="sxs-lookup"><span data-stu-id="d1dae-134">The class-level <xref:System.ComponentModel.ComplexBindingPropertiesAttribute>, shown previously, specifies the `DataSource` and `DataMember` properties to use for data binding.</span></span> <span data-ttu-id="d1dae-135"><xref:System.ComponentModel.AttributeProviderAttribute>Specifica il tipo a cui la `DataSource` proprietà eseguirà l'associazione.</span><span class="sxs-lookup"><span data-stu-id="d1dae-135">The <xref:System.ComponentModel.AttributeProviderAttribute> specifies the type to which the `DataSource` property will bind.</span></span>  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#25)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#25](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#25)]  
  
 [!code-csharp[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/CS/attributesdemocontrol.cs#26)]
 [!code-vb[System.ComponentModel.AttributesDemoControl#26](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.AttributesDemoControl/VB/attributesdemocontrol.vb#26)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d1dae-136">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="d1dae-136">Compiling the Code</span></span>  
  
- <span data-ttu-id="d1dae-137">Il form che ospita l'oggetto `AttributesDemoControl` richiede un riferimento all' `AttributesDemoControl` assembly per la compilazione.</span><span class="sxs-lookup"><span data-stu-id="d1dae-137">The form that hosts the `AttributesDemoControl` requires a reference to the `AttributesDemoControl` assembly in order to build.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1dae-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d1dae-138">See also</span></span>

- <xref:System.IComparable>
- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="d1dae-139">Sviluppo di controlli Windows Form personalizzati con .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d1dae-139">Developing Custom Windows Forms Controls with the .NET Framework</span></span>](developing-custom-windows-forms-controls.md)
- [<span data-ttu-id="d1dae-140">Attributi nei controlli Windows Form</span><span class="sxs-lookup"><span data-stu-id="d1dae-140">Attributes in Windows Forms Controls</span></span>](attributes-in-windows-forms-controls.md)
- <span data-ttu-id="d1dae-141">[Procedura: serializzare raccolte di tipi standard mediante DesignerSerializationVisibilityAttribute](/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="d1dae-141">[How to: Serialize Collections of Standard Types with the DesignerSerializationVisibilityAttribute](/previous-versions/visualstudio/visual-studio-2013/ms171833(v=vs.120))</span></span>
