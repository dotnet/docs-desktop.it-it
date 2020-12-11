---
title: "Procedura: Implementare l'interfaccia ITypedList"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ITypedList interface
- BindingList(Of T) class
- data binding [Windows Forms], implementing
- IBindingList interface
ms.assetid: 834cc15c-50bc-4a8b-a610-313d6a217357
ms.openlocfilehash: 3f5a5032166087c7398d310071b3998c845e2780
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965422"
---
# <a name="how-to-implement-the-itypedlist-interface"></a><span data-ttu-id="a46e4-102">Procedura: Implementare l'interfaccia ITypedList</span><span class="sxs-lookup"><span data-stu-id="a46e4-102">How to: Implement the ITypedList Interface</span></span>
<span data-ttu-id="a46e4-103">Implementare l' <xref:System.ComponentModel.ITypedList> interfaccia per consentire l'individuazione dello schema per un elenco associabile.</span><span class="sxs-lookup"><span data-stu-id="a46e4-103">Implement the <xref:System.ComponentModel.ITypedList> interface to enable discovery of the schema for a bindable list.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a46e4-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="a46e4-104">Example</span></span>  
 <span data-ttu-id="a46e4-105">Nell'esempio di codice riportato di seguito viene illustrato come implementare l' <xref:System.ComponentModel.ITypedList> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="a46e4-105">The following code example demonstrates how to implement the <xref:System.ComponentModel.ITypedList> interface.</span></span> <span data-ttu-id="a46e4-106">Un tipo generico denominato `SortableBindingList` deriva dalla <xref:System.ComponentModel.BindingList%601> classe e implementa l' <xref:System.ComponentModel.ITypedList> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="a46e4-106">A generic type named `SortableBindingList` derives from the <xref:System.ComponentModel.BindingList%601> class and implements the <xref:System.ComponentModel.ITypedList> interface.</span></span> <span data-ttu-id="a46e4-107">Una classe semplice denominata `Customer` fornisce i dati associati all'intestazione di un <xref:System.Windows.Forms.DataGridView> controllo.</span><span class="sxs-lookup"><span data-stu-id="a46e4-107">A simple class named `Customer` provides data, which is bound to the header of a <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 [!code-csharp[System.ComponentModel.ITypedList#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.ITypedList/CS/SortableBindingList.cs#1)]
 [!code-vb[System.ComponentModel.ITypedList#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.ITypedList/VB/SortableBindingList.vb#1)]  
  
 [!code-csharp[System.ComponentModel.ITypedList#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.ITypedList/CS/Customer.cs#10)]
 [!code-vb[System.ComponentModel.ITypedList#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.ITypedList/VB/Customer.vb#10)]  
  
 [!code-csharp[System.ComponentModel.ITypedList#100](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.ITypedList/CS/Form1.cs#100)]
 [!code-vb[System.ComponentModel.ITypedList#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.ITypedList/VB/Form1.vb#100)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a46e4-108">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="a46e4-108">Compiling the Code</span></span>  
 <span data-ttu-id="a46e4-109">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="a46e4-109">This example requires:</span></span>  
  
- <span data-ttu-id="a46e4-110">Riferimenti agli assembly System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="a46e4-110">References to the System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a46e4-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a46e4-111">See also</span></span>

- <xref:System.ComponentModel.ITypedList>
- <xref:System.ComponentModel.BindingList%601>
- <xref:System.ComponentModel.IBindingList>
- [<span data-ttu-id="a46e4-112">Associazione dati e Windows Form</span><span class="sxs-lookup"><span data-stu-id="a46e4-112">Data Binding and Windows Forms</span></span>](data-binding-and-windows-forms.md)
