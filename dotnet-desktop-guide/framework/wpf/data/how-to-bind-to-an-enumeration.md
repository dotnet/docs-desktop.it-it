---
title: "Procedura: eseguire l'associazione a un'enumerazione"
ms.date: 03/30/2017
helpviewer_keywords:
- binding data [WPF], enumeration
- data binding [WPF], enumeration
- enumeration [WPF]
ms.assetid: b9091eba-1119-424e-868b-d1a4168b3732
ms.openlocfilehash: c92f1f00aa3feb37b70aa9a3647265236a1625b2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96951619"
---
# <a name="how-to-bind-to-an-enumeration"></a><span data-ttu-id="20215-102">Procedura: eseguire l'associazione a un'enumerazione</span><span class="sxs-lookup"><span data-stu-id="20215-102">How to: Bind to an Enumeration</span></span>
<span data-ttu-id="20215-103">In questo esempio viene illustrato come eseguire l'associazione a un'enumerazione mediante l'associazione al metodo GetValues dell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="20215-103">This example shows how to bind to an enumeration by binding to the enumeration's GetValues method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="20215-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="20215-104">Example</span></span>  
 <span data-ttu-id="20215-105">Nell'esempio seguente <xref:System.Windows.Controls.ListBox> viene visualizzato l'elenco dei valori di <xref:System.Windows.HorizontalAlignment> enumerazione tramite Data Binding.</span><span class="sxs-lookup"><span data-stu-id="20215-105">In the following example, the <xref:System.Windows.Controls.ListBox> displays the list of <xref:System.Windows.HorizontalAlignment> enumeration values through data binding.</span></span> <span data-ttu-id="20215-106"><xref:System.Windows.Controls.ListBox>E <xref:System.Windows.Controls.Button> sono associati in modo che sia possibile modificare il <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> valore della proprietà dell'oggetto <xref:System.Windows.Controls.Button> selezionando un valore in <xref:System.Windows.Controls.ListBox> .</span><span class="sxs-lookup"><span data-stu-id="20215-106">The <xref:System.Windows.Controls.ListBox> and the <xref:System.Windows.Controls.Button> are bound such that you can change the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property value of the <xref:System.Windows.Controls.Button> by selecting a value in the <xref:System.Windows.Controls.ListBox>.</span></span>  
  
 [!code-xaml[BindToEnum#BindToEnum](~/samples/snippets/csharp/VS_Snippets_Wpf/BindToEnum/CS/Window1.xaml#bindtoenum)]  
  
## <a name="see-also"></a><span data-ttu-id="20215-107">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="20215-107">See also</span></span>

- [<span data-ttu-id="20215-108">Eseguire l'associazione a un metodo</span><span class="sxs-lookup"><span data-stu-id="20215-108">Bind to a Method</span></span>](how-to-bind-to-a-method.md)
- [<span data-ttu-id="20215-109">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="20215-109">Data Binding Overview</span></span>](/dotnet/desktop-wpf/data/data-binding-overview)
- [<span data-ttu-id="20215-110">Procedure</span><span class="sxs-lookup"><span data-stu-id="20215-110">How-to Topics</span></span>](data-binding-how-to-topics.md)
