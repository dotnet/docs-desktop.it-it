---
title: 'Procedura: modificare il tipo di cursore'
description: Modificare il cursore del puntatore del mouse per un elemento e per un'applicazione in Windows Presentation Foundation. Questo esempio è costituito da XAML e da un file code-behind.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- mouse pointer [WPF], cursor type
- cursor (mouse pointer)
ms.assetid: 08c945a7-8ab0-4320-acf3-0b4955a344c2
ms.openlocfilehash: 54b4dcbed1b92164d3ed9b4c1c9f9a9f8c760ae7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965002"
---
# <a name="how-to-change-the-cursor-type"></a><span data-ttu-id="7bbf7-104">Procedura: modificare il tipo di cursore</span><span class="sxs-lookup"><span data-stu-id="7bbf7-104">How to: Change the Cursor Type</span></span>
<span data-ttu-id="7bbf7-105">Questo esempio illustra come modificare l'oggetto <xref:System.Windows.Input.Cursor> del puntatore del mouse per un elemento specifico e per l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7bbf7-105">This example shows how to change the <xref:System.Windows.Input.Cursor> of the mouse pointer for a specific element and for the application.</span></span>  
  
 <span data-ttu-id="7bbf7-106">Questo esempio è costituito da un file [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] e da un file code-behind.</span><span class="sxs-lookup"><span data-stu-id="7bbf7-106">This example consists of a [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] file and a code behind file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7bbf7-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="7bbf7-107">Example</span></span>  
 <span data-ttu-id="7bbf7-108">Viene creata l'interfaccia utente, costituita da un oggetto <xref:System.Windows.Controls.ComboBox> per selezionare l'oggetto desiderato <xref:System.Windows.Input.Cursor> , una coppia di <xref:System.Windows.Controls.RadioButton> oggetti per determinare se la modifica del cursore viene applicata solo a un singolo elemento o si applica all'intera applicazione e a un oggetto <xref:System.Windows.Controls.Border> che è l'elemento a cui viene applicato il nuovo cursore.</span><span class="sxs-lookup"><span data-stu-id="7bbf7-108">The user interface is created, which consists of a <xref:System.Windows.Controls.ComboBox> to select the desired <xref:System.Windows.Input.Cursor>, a pair of <xref:System.Windows.Controls.RadioButton> objects to determine if the cursor change applies to only a single element or applies to the entire application, and a <xref:System.Windows.Controls.Border> which is the element that the new cursor is applied to.</span></span>  
  
 [!code-xaml[cursors#ChangeCursorsXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml#changecursorsxaml)]  
  
 <span data-ttu-id="7bbf7-109">Il codice sottostante seguente crea un <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> gestore eventi che viene chiamato quando il tipo di cursore viene modificato in <xref:System.Windows.Controls.ComboBox> .</span><span class="sxs-lookup"><span data-stu-id="7bbf7-109">The following code behind creates a <xref:System.Windows.Controls.Primitives.Selector.SelectionChanged> event handler which is called when the cursor type is changed in the <xref:System.Windows.Controls.ComboBox>.</span></span>  <span data-ttu-id="7bbf7-110">Un'istruzione switch filtra sul nome del cursore e imposta la <xref:System.Windows.FrameworkElement.Cursor%2A> proprietà nell'oggetto, <xref:System.Windows.Controls.Border> denominato *DisplayArea*.</span><span class="sxs-lookup"><span data-stu-id="7bbf7-110">A switch statement filters on the cursor name and sets the <xref:System.Windows.FrameworkElement.Cursor%2A> property on the <xref:System.Windows.Controls.Border> which is named *DisplayArea*.</span></span>  
  
 <span data-ttu-id="7bbf7-111">Se la modifica del cursore è impostata su "intera applicazione", la <xref:System.Windows.Input.Mouse.OverrideCursor%2A> proprietà viene impostata sulla <xref:System.Windows.FrameworkElement.Cursor%2A> proprietà del <xref:System.Windows.Controls.Border> controllo.</span><span class="sxs-lookup"><span data-stu-id="7bbf7-111">If the cursor change is set to "Entire Application", the <xref:System.Windows.Input.Mouse.OverrideCursor%2A> property is set to the <xref:System.Windows.FrameworkElement.Cursor%2A> property of the <xref:System.Windows.Controls.Border> control.</span></span>  <span data-ttu-id="7bbf7-112">In questo modo si impone la modifica del cursore per l'intera applicazione.</span><span class="sxs-lookup"><span data-stu-id="7bbf7-112">This forces the cursor to change for the whole application.</span></span>  
  
 [!code-csharp[cursors#ChangeCursorsSample](~/samples/snippets/csharp/VS_Snippets_Wpf/cursors/CSharp/Window1.xaml.cs#changecursorssample)]
 [!code-vb[cursors#ChangeCursorsSample](~/samples/snippets/visualbasic/VS_Snippets_Wpf/cursors/VisualBasic/Window1.xaml.vb#changecursorssample)]  
  
## <a name="see-also"></a><span data-ttu-id="7bbf7-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7bbf7-113">See also</span></span>

- [<span data-ttu-id="7bbf7-114">Cenni preliminari sull'input</span><span class="sxs-lookup"><span data-stu-id="7bbf7-114">Input Overview</span></span>](input-overview.md)
