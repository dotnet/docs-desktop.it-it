---
title: 'Procedura: produrre un valore in base a un elenco di elementi associati'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], MultiBinding
- Multibinding [WPF]
ms.assetid: b3d06378-b511-4181-95aa-316d60c9229b
ms.openlocfilehash: ab030fbf4335a5bfd12834cb7b19c280487dc2f7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951869"
---
# <a name="how-to-produce-a-value-based-on-a-list-of-bound-items"></a><span data-ttu-id="7162a-102">Procedura: produrre un valore in base a un elenco di elementi associati</span><span class="sxs-lookup"><span data-stu-id="7162a-102">How to: Produce a Value Based on a List of Bound Items</span></span>
<span data-ttu-id="7162a-103"><xref:System.Windows.Data.MultiBinding> consente di associare una proprietà di destinazione dell'associazione a un elenco di proprietà di origine e quindi di applicare la logica per produrre un valore con gli input specificati.</span><span class="sxs-lookup"><span data-stu-id="7162a-103"><xref:System.Windows.Data.MultiBinding> allows you to bind a binding target property to a list of source properties and then apply logic to produce a value with the given inputs.</span></span> <span data-ttu-id="7162a-104">Questo esempio illustra come usare <xref:System.Windows.Data.MultiBinding> .</span><span class="sxs-lookup"><span data-stu-id="7162a-104">This example demonstrates how to use <xref:System.Windows.Data.MultiBinding>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7162a-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="7162a-105">Example</span></span>  
 <span data-ttu-id="7162a-106">Nell'esempio seguente, `NameListData` fa riferimento a una raccolta di oggetti `PersonName`, che contengono due proprietà: `firstName` e `lastName`.</span><span class="sxs-lookup"><span data-stu-id="7162a-106">In the following example, `NameListData` refers to a collection of `PersonName` objects, which are objects that contain two properties, `firstName` and `lastName`.</span></span> <span data-ttu-id="7162a-107">Nell'esempio seguente viene generato un oggetto <xref:System.Windows.Controls.TextBlock> che mostra il nome e il cognome di una persona con il cognome per primo.</span><span class="sxs-lookup"><span data-stu-id="7162a-107">The following example produces a <xref:System.Windows.Controls.TextBlock> that shows the first and last names of a person with the last name first.</span></span>  
  
 [!code-xaml[MultiBinding#Resources1](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources1)]  
[!code-xaml[MultiBinding#Resources2](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#resources2)]  
[!code-xaml[MultiBinding#MultiBindingTextBox2](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#multibindingtextbox2)]  
[!code-xaml[MultiBinding#Window](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/Window1.xaml#window)]  
  
 <span data-ttu-id="7162a-108">Per comprendere come viene generato il formato con il cognome prima del nome, osservare l'implementazione di `NameConverter`:</span><span class="sxs-lookup"><span data-stu-id="7162a-108">To understand how the last-name-first format is produced, let's take a look at the implementation of the `NameConverter`:</span></span>  
  
 [!code-csharp[MultiBinding#3](~/samples/snippets/csharp/VS_Snippets_Wpf/MultiBinding/CSharp/NameConverter.cs#3)]
 [!code-vb[MultiBinding#3](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MultiBinding/VisualBasic/NameConverter.vb#3)]  
  
 <span data-ttu-id="7162a-109">L'oggetto `NameConverter` implementa l'interfaccia <xref:System.Windows.Data.IMultiValueConverter>.</span><span class="sxs-lookup"><span data-stu-id="7162a-109">`NameConverter` implements the <xref:System.Windows.Data.IMultiValueConverter> interface.</span></span> <span data-ttu-id="7162a-110">`NameConverter` accetta i valori dei singoli binding e li archivia nella matrice di oggetti valore.</span><span class="sxs-lookup"><span data-stu-id="7162a-110">`NameConverter` takes the values from the individual bindings and stores them in the values object array.</span></span> <span data-ttu-id="7162a-111">L'ordine in cui gli <xref:System.Windows.Data.Binding> elementi vengono visualizzati sotto l' <xref:System.Windows.Data.MultiBinding> elemento è l'ordine in cui tali valori vengono archiviati nella matrice.</span><span class="sxs-lookup"><span data-stu-id="7162a-111">The order in which the <xref:System.Windows.Data.Binding> elements appear under the <xref:System.Windows.Data.MultiBinding> element is the order in which those values are stored in the array.</span></span> <span data-ttu-id="7162a-112">Al valore dell' <xref:System.Windows.Data.MultiBinding.ConverterParameter%2A> attributo viene fatto riferimento dall'argomento del parametro del <xref:System.Windows.Data.MultiBinding.Converter%2A> metodo, che esegue un'opzione sul parametro per determinare come formattare il nome.</span><span class="sxs-lookup"><span data-stu-id="7162a-112">The value of the <xref:System.Windows.Data.MultiBinding.ConverterParameter%2A> attribute is referenced by the parameter argument of the <xref:System.Windows.Data.MultiBinding.Converter%2A> method, which performs a switch on the parameter to determine how to format the name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7162a-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7162a-113">See also</span></span>

- [<span data-ttu-id="7162a-114">Converti dati associati</span><span class="sxs-lookup"><span data-stu-id="7162a-114">Convert Bound Data</span></span>](how-to-convert-bound-data.md)
- [<span data-ttu-id="7162a-115">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="7162a-115">Data Binding Overview</span></span>](/dotnet/desktop-wpf/data/data-binding-overview)
- [<span data-ttu-id="7162a-116">Procedure</span><span class="sxs-lookup"><span data-stu-id="7162a-116">How-to Topics</span></span>](data-binding-how-to-topics.md)
