---
title: 'Procedura: impostare notifiche relative ad aggiornamenti di associazioni'
ms.date: 03/30/2017
helpviewer_keywords:
- notifications [WPF], binding updates
- data binding [WPF], notification of binding updates
- binding [WPF], updates [WPF], notifications of
ms.assetid: 5673073e-dbe1-49da-980a-484a88f9595a
ms.openlocfilehash: d6a27d0226abe1b67a92f76219be3a563fc26216
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968491"
---
# <a name="how-to-set-up-notification-of-binding-updates"></a><span data-ttu-id="d05d0-102">Procedura: impostare notifiche relative ad aggiornamenti di associazioni</span><span class="sxs-lookup"><span data-stu-id="d05d0-102">How to: Set Up Notification of Binding Updates</span></span>
<span data-ttu-id="d05d0-103">Questo esempio spiega come impostare una notifica quando viene aggiornata la proprietà della destinazione di binding (destinazione) o dell'origine di binding (origine).</span><span class="sxs-lookup"><span data-stu-id="d05d0-103">This example shows how to set up to be notified when the binding target (target) or the binding source (source) property of a binding has been updated.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d05d0-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="d05d0-104">Example</span></span>  
 [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] <span data-ttu-id="d05d0-105">genera un evento di aggiornamento dati ogni volta che l'origine o la destinazione di binding viene aggiornata.</span><span class="sxs-lookup"><span data-stu-id="d05d0-105">raises a data update event each time that the binding source or target has been updated.</span></span> <span data-ttu-id="d05d0-106">Internamente, questo evento viene usato per indicare la necessità di un aggiornamento per [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)], poiché sono cambiati i dati associati.</span><span class="sxs-lookup"><span data-stu-id="d05d0-106">Internally, this event is used to inform the [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] that it should update, because the bound data has changed.</span></span> <span data-ttu-id="d05d0-107">Si noti che per il corretto funzionamento di questi eventi e anche per il corretto funzionamento dell'associazione unidirezionale o bidirezionale, è necessario implementare la classe di dati tramite l' <xref:System.ComponentModel.INotifyPropertyChanged> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="d05d0-107">Note that for these events to work, and also for one-way or two-way binding to work properly, you need to implement your data class using the <xref:System.ComponentModel.INotifyPropertyChanged> interface.</span></span> <span data-ttu-id="d05d0-108">Per altre informazioni, vedere [Implementare la notifica di modifiche alle proprietà](how-to-implement-property-change-notification.md).</span><span class="sxs-lookup"><span data-stu-id="d05d0-108">For more information, see [Implement Property Change Notification](how-to-implement-property-change-notification.md).</span></span>  
  
 <span data-ttu-id="d05d0-109">Impostare la <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A> <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A> proprietà o (o entrambe) su `true` nell'associazione.</span><span class="sxs-lookup"><span data-stu-id="d05d0-109">Set the <xref:System.Windows.Data.Binding.NotifyOnTargetUpdated%2A> or <xref:System.Windows.Data.Binding.NotifyOnSourceUpdated%2A> property (or both) to `true` in the binding.</span></span> <span data-ttu-id="d05d0-110">Il gestore fornito per l'ascolto di questo evento deve essere associato direttamente all'elemento in cui si desidera essere informati delle modifiche oppure al contesto dati complessivo se si desidera conoscere eventuali modifiche nel contesto.</span><span class="sxs-lookup"><span data-stu-id="d05d0-110">The handler you provide to listen for this event must be attached directly to the element where you want to be informed of changes, or to the overall data context if you want to be aware that anything in the context has changed.</span></span>  
  
 <span data-ttu-id="d05d0-111">Ecco un esempio che illustra come configurare le notifiche quando viene aggiornata una proprietà di destinazione.</span><span class="sxs-lookup"><span data-stu-id="d05d0-111">Here is an example that shows how to set up for notification when a target property has been updated.</span></span>  
  
 [!code-xaml[DirectionalBinding#2](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#2)]  
  
 <span data-ttu-id="d05d0-112">È quindi possibile assegnare un gestore basato sul delegato EventHandler \<T> , *OnTargetUpdated* in questo esempio, per gestire l'evento:</span><span class="sxs-lookup"><span data-stu-id="d05d0-112">You can then assign a handler based on the EventHandler\<T> delegate, *OnTargetUpdated* in this example, to handle the event:</span></span>  
  
 [!code-csharp[DirectionalBinding#3](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml.cs#3)]  
[!code-csharp[DirectionalBinding#EndEvent](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml.cs#endevent)]  
  
 <span data-ttu-id="d05d0-113">I parametri dell'evento possono essere usati per determinare i dettagli sulla proprietà modificata (ad esempio, il tipo o l'elemento specifico se lo stesso gestore è associato a più elementi). Questa condizione può risultare utile in presenza di più proprietà associate in un singolo elemento.</span><span class="sxs-lookup"><span data-stu-id="d05d0-113">Parameters of the event can be used to determine details about the property that changed (such as the type or the specific element if the same handler is attached to more than one element), which can be useful if there are multiple bound properties on a single element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d05d0-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d05d0-114">See also</span></span>

- [<span data-ttu-id="d05d0-115">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="d05d0-115">Data Binding Overview</span></span>](/dotnet/desktop-wpf/data/data-binding-overview)
- [<span data-ttu-id="d05d0-116">Procedure</span><span class="sxs-lookup"><span data-stu-id="d05d0-116">How-to Topics</span></span>](data-binding-how-to-topics.md)
