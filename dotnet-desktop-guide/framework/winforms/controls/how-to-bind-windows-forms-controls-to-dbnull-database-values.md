---
title: Associare i controlli ai valori del database DBNull
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- BindingSource component [Windows Forms], binding to DBNull values
- examples [Windows Forms], BindingSource component
- controls [Windows Forms], binding to DBNull values
ms.assetid: 96494e6f-5f40-4f83-af97-bbd7192c2af8
ms.openlocfilehash: 175d7f5aee2540916480e2c55a485af1f9d16653
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964480"
---
# <a name="how-to-bind-windows-forms-controls-to-dbnull-database-values"></a><span data-ttu-id="49534-102">Procedura: Associare i controlli di Windows Forms a valori di database DBNull</span><span class="sxs-lookup"><span data-stu-id="49534-102">How to: Bind Windows Forms Controls to DBNull Database Values</span></span>
<span data-ttu-id="49534-103">Quando si associano controlli Windows Form a un'origine dati e questa restituisce un valore <xref:System.DBNull>, è possibile sostituire un valore appropriato senza gestire, formattare o analizzare eventi.</span><span class="sxs-lookup"><span data-stu-id="49534-103">When you bind Windows Forms controls to a data source and the data source returns a <xref:System.DBNull> value, you can substitute an appropriate value without handling, formatting, or parsing events.</span></span> <span data-ttu-id="49534-104">La proprietà <xref:System.Windows.Forms.Binding.NullValue%2A> eseguirà la conversione del valore <xref:System.DBNull> in un oggetto specificato durante la formattazione o l'analisi dei valori dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="49534-104">The <xref:System.Windows.Forms.Binding.NullValue%2A> property will convert <xref:System.DBNull> to a specified object when formatting or parsing the data source values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="49534-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="49534-105">Example</span></span>  
 <span data-ttu-id="49534-106">Nell'esempio riportato di seguito viene illustrato come associare un valore <xref:System.DBNull> in due situazioni diverse.</span><span class="sxs-lookup"><span data-stu-id="49534-106">The following example demonstrates how to bind a <xref:System.DBNull> value in two different situations.</span></span> <span data-ttu-id="49534-107">Nel primo caso viene dimostrato come impostare il valore <xref:System.Windows.Forms.Binding.NullValue%2A> per una proprietà di stringa e nel secondo viene dimostrato come impostare il valore <xref:System.Windows.Forms.Binding.NullValue%2A> per una proprietà di immagine.</span><span class="sxs-lookup"><span data-stu-id="49534-107">The first demonstrates how to set the <xref:System.Windows.Forms.Binding.NullValue%2A> for a string property; the second demonstrates how to set the <xref:System.Windows.Forms.Binding.NullValue%2A> for an image property.</span></span>  
  
 [!code-csharp[System.Windows.Forms.BindingDBNull#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingDBNull/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingDBNull#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingDBNull/VB/form1.vb#1)]  
  
 <span data-ttu-id="49534-108">I tipi della proprietà associata e la proprietà <xref:System.Windows.Forms.Binding.NullValue%2A> devono corrispondere, in caso contrario viene generato un errore e non vengono elaborati altri valori <xref:System.Windows.Forms.Binding.NullValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="49534-108">The types of the bound property and the <xref:System.Windows.Forms.Binding.NullValue%2A> property must be the same or an error will result, and no further <xref:System.Windows.Forms.Binding.NullValue%2A> values will be processed.</span></span> <span data-ttu-id="49534-109">In questo caso, non viene generata alcuna eccezione.</span><span class="sxs-lookup"><span data-stu-id="49534-109">In this situation, an exception will not be thrown.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="49534-110">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="49534-110">Compiling the Code</span></span>  
 <span data-ttu-id="49534-111">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="49534-111">This example requires:</span></span>  
  
- <span data-ttu-id="49534-112">Riferimenti agli assembly System, System.Data, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="49534-112">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49534-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49534-113">See also</span></span>

- [<span data-ttu-id="49534-114">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="49534-114">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="49534-115">Procedura: Gestire errori ed eccezioni relativi al data binding</span><span class="sxs-lookup"><span data-stu-id="49534-115">How to: Handle Errors and Exceptions that Occur with Databinding</span></span>](how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)
- [<span data-ttu-id="49534-116">Procedura: Associare un controllo di Windows Forms a un tipo</span><span class="sxs-lookup"><span data-stu-id="49534-116">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)
