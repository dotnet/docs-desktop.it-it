---
title: 'Procedura: specificare la direzione di associazione'
ms.date: 03/30/2017
helpviewer_keywords:
- direction of binding [WPF]
- binding direction [WPF]
- data binding [WPF], direction of binding
ms.assetid: 37334478-028b-4514-86c9-1420709f4818
ms.openlocfilehash: 6b3c6afde5e9fa1b778905b1a278bb295b6cbf11
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964561"
---
# <a name="how-to-specify-the-direction-of-the-binding"></a><span data-ttu-id="35d0f-102">Procedura: specificare la direzione dell'associazione</span><span class="sxs-lookup"><span data-stu-id="35d0f-102">How to: Specify the direction of the binding</span></span>

<span data-ttu-id="35d0f-103">Questo esempio spiega come specificare se il binding aggiorna solo la proprietà della destinazione del binding (destinazione), dell'origine del binding (origine) o entrambe.</span><span class="sxs-lookup"><span data-stu-id="35d0f-103">This example shows how to specify whether the binding updates only the binding target (target) property, the binding source (source) property, or both the target property and the source property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="35d0f-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="35d0f-104">Example</span></span>  
 <span data-ttu-id="35d0f-105">Utilizzare la <xref:System.Windows.Data.Binding.Mode%2A?displayProperty=nameWithType> proprietà per specificare la direzione del binding.</span><span class="sxs-lookup"><span data-stu-id="35d0f-105">You use the <xref:System.Windows.Data.Binding.Mode%2A?displayProperty=nameWithType> property to specify the direction of the binding.</span></span> <span data-ttu-id="35d0f-106">Di seguito sono riportate le opzioni disponibili per gli aggiornamenti di binding:</span><span class="sxs-lookup"><span data-stu-id="35d0f-106">The following are the available options for binding updates:</span></span>  
  
- <span data-ttu-id="35d0f-107"><xref:System.Windows.Data.BindingMode.TwoWay?displayProperty=nameWithType> Aggiorna la proprietà di destinazione o la proprietà ogni volta che la proprietà di destinazione o la proprietà di origine viene modificata.</span><span class="sxs-lookup"><span data-stu-id="35d0f-107"><xref:System.Windows.Data.BindingMode.TwoWay?displayProperty=nameWithType> updates the target property or the property whenever either the target property or the source property changes.</span></span>  
  
- <span data-ttu-id="35d0f-108"><xref:System.Windows.Data.BindingMode.OneWay?displayProperty=nameWithType> Aggiorna la proprietà di destinazione solo quando la proprietà di origine viene modificata.</span><span class="sxs-lookup"><span data-stu-id="35d0f-108"><xref:System.Windows.Data.BindingMode.OneWay?displayProperty=nameWithType> updates the target property only when the source property changes.</span></span>  
  
- <span data-ttu-id="35d0f-109"><xref:System.Windows.Data.BindingMode.OneTime?displayProperty=nameWithType> Aggiorna la proprietà di destinazione solo quando l'applicazione viene avviata o quando <xref:System.Windows.FrameworkElement.DataContext%2A> subisce una modifica.</span><span class="sxs-lookup"><span data-stu-id="35d0f-109"><xref:System.Windows.Data.BindingMode.OneTime?displayProperty=nameWithType> updates the target property only when the application starts or when the <xref:System.Windows.FrameworkElement.DataContext%2A> undergoes a change.</span></span>  
  
- <span data-ttu-id="35d0f-110"><xref:System.Windows.Data.BindingMode.OneWayToSource?displayProperty=nameWithType> Aggiorna la proprietà di origine quando viene modificata la proprietà di destinazione.</span><span class="sxs-lookup"><span data-stu-id="35d0f-110"><xref:System.Windows.Data.BindingMode.OneWayToSource?displayProperty=nameWithType> updates the source property when the target property changes.</span></span>  
  
- <span data-ttu-id="35d0f-111"><xref:System.Windows.Data.BindingMode.Default?displayProperty=nameWithType> determina l' <xref:System.Windows.Data.Binding.Mode%2A> utilizzo del valore predefinito della proprietà target.</span><span class="sxs-lookup"><span data-stu-id="35d0f-111"><xref:System.Windows.Data.BindingMode.Default?displayProperty=nameWithType> causes the default <xref:System.Windows.Data.Binding.Mode%2A> value of target property to be used.</span></span>  
  
 <span data-ttu-id="35d0f-112">Per altre informazioni, vedere l'enumerazione <xref:System.Windows.Data.BindingMode>.</span><span class="sxs-lookup"><span data-stu-id="35d0f-112">For more information, see the <xref:System.Windows.Data.BindingMode> enumeration.</span></span>  
  
 <span data-ttu-id="35d0f-113">Nell'esempio seguente viene illustrato come impostare la proprietà <xref:System.Windows.Data.Binding.Mode%2A>.</span><span class="sxs-lookup"><span data-stu-id="35d0f-113">The following example shows how to set the <xref:System.Windows.Data.Binding.Mode%2A> property.</span></span>  
  
 [!code-xaml[DirectionalBinding#4](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#4)]  
  
 <span data-ttu-id="35d0f-114">Per rilevare le modifiche apportate all'origine (applicabili alle <xref:System.Windows.Data.BindingMode.OneWay> <xref:System.Windows.Data.BindingMode.TwoWay> associazioni e), l'origine deve implementare un meccanismo appropriato di notifica delle modifiche alle proprietà, ad esempio <xref:System.ComponentModel.INotifyPropertyChanged> .</span><span class="sxs-lookup"><span data-stu-id="35d0f-114">To detect source changes (applicable to <xref:System.Windows.Data.BindingMode.OneWay> and <xref:System.Windows.Data.BindingMode.TwoWay> bindings), the source must implement a suitable property change notification mechanism such as <xref:System.ComponentModel.INotifyPropertyChanged>.</span></span> <span data-ttu-id="35d0f-115">Per un esempio di implementazione, vedere [implementare una notifica di modifica delle proprietà](how-to-implement-property-change-notification.md) <xref:System.ComponentModel.INotifyPropertyChanged> .</span><span class="sxs-lookup"><span data-stu-id="35d0f-115">See [Implement Property Change Notification](how-to-implement-property-change-notification.md) for an example of an <xref:System.ComponentModel.INotifyPropertyChanged> implementation.</span></span>  
  
 <span data-ttu-id="35d0f-116">Per <xref:System.Windows.Data.BindingMode.TwoWay> le <xref:System.Windows.Data.BindingMode.OneWayToSource> associazioni o, è possibile controllare l'intervallo degli aggiornamenti di origine impostando la <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="35d0f-116">For <xref:System.Windows.Data.BindingMode.TwoWay> or <xref:System.Windows.Data.BindingMode.OneWayToSource> bindings, you can control the timing of the source updates by setting the <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> property.</span></span> <span data-ttu-id="35d0f-117">Per altre informazioni, vedere <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.</span><span class="sxs-lookup"><span data-stu-id="35d0f-117">See <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> for more information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35d0f-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35d0f-118">See also</span></span>

- <xref:System.Windows.Data.Binding>
- [<span data-ttu-id="35d0f-119">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="35d0f-119">Data Binding Overview</span></span>](/dotnet/desktop-wpf/data/data-binding-overview)
- [<span data-ttu-id="35d0f-120">Procedure</span><span class="sxs-lookup"><span data-stu-id="35d0f-120">How-to Topics</span></span>](data-binding-how-to-topics.md)
