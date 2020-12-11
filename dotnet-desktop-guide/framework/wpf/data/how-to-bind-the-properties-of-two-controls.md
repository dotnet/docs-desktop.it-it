---
title: "Procedura: eseguire l'associazione delle proprietà di due controlli"
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], binding properties of two controls
- binding properties of two controls [WPF]
- controls [WPF], binding properties of
ms.assetid: 06318fac-6afd-4c7d-a277-6d7ef50f47bc
ms.openlocfilehash: 28b5f65a57fc210f3d405020daa0d75c28b934c8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951639"
---
# <a name="how-to-bind-the-properties-of-two-controls"></a><span data-ttu-id="85752-102">Procedura: eseguire l'associazione delle proprietà di due controlli</span><span class="sxs-lookup"><span data-stu-id="85752-102">How to: Bind the Properties of Two Controls</span></span>

<span data-ttu-id="85752-103">Questo esempio illustra come associare la proprietà di un controllo di cui è stata creata un'istanza a quella di un altro usando la <xref:System.Windows.Data.Binding.ElementName%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="85752-103">This example shows how to bind the property of one instantiated control to that of another using the <xref:System.Windows.Data.Binding.ElementName%2A> property.</span></span>

## <a name="example"></a><span data-ttu-id="85752-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="85752-104">Example</span></span>

<span data-ttu-id="85752-105">Nell'esempio seguente viene illustrato come associare la <xref:System.Windows.Controls.Panel.Background%2A> proprietà di un oggetto <xref:System.Windows.Controls.Canvas> alla proprietà [SelectedItem. Content](xref:System.Windows.Controls.ContentControl.Content%2A) di un oggetto <xref:System.Windows.Controls.ComboBox> :</span><span class="sxs-lookup"><span data-stu-id="85752-105">The following example shows how to bind the <xref:System.Windows.Controls.Panel.Background%2A> property of a <xref:System.Windows.Controls.Canvas> to the [SelectedItem.Content](xref:System.Windows.Controls.ContentControl.Content%2A) property of a <xref:System.Windows.Controls.ComboBox>:</span></span>

[!code-xaml[BindDptoDp#1](~/samples/snippets/csharp/VS_Snippets_Wpf/BindDPtoDP/CS/Window1.xaml#1)]

<span data-ttu-id="85752-106">Dopo il rendering questo esempio avrà l'aspetto seguente:</span><span class="sxs-lookup"><span data-stu-id="85752-106">When this example is rendered it looks like the following:</span></span>

![Screenshot che mostra una casella combinata con il valore verde selezionato e un quadrato verde.](./media/how-to-bind-the-properties-of-two-controls/data-binding-bind-background-canvas.png)

> [!NOTE]
> <span data-ttu-id="85752-108">La proprietà di destinazione del binding, in questo esempio la <xref:System.Windows.Controls.Panel.Background%2A> proprietà, deve essere una proprietà di dipendenza.</span><span class="sxs-lookup"><span data-stu-id="85752-108">The binding target property (in this example, the <xref:System.Windows.Controls.Panel.Background%2A> property) must be a dependency property.</span></span> <span data-ttu-id="85752-109">Per altre informazioni, vedere [Cenni preliminari sul data binding](/dotnet/desktop-wpf/data/data-binding-overview).</span><span class="sxs-lookup"><span data-stu-id="85752-109">For more information, see [Data Binding Overview](/dotnet/desktop-wpf/data/data-binding-overview).</span></span>

## <a name="see-also"></a><span data-ttu-id="85752-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85752-110">See also</span></span>

- [<span data-ttu-id="85752-111">Specificare l'origine del binding</span><span class="sxs-lookup"><span data-stu-id="85752-111">Specify the Binding Source</span></span>](how-to-specify-the-binding-source.md)
- [<span data-ttu-id="85752-112">Procedure</span><span class="sxs-lookup"><span data-stu-id="85752-112">How-to Topics</span></span>](data-binding-how-to-topics.md)
