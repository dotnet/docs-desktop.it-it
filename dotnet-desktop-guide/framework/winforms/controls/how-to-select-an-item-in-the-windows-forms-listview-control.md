---
title: Seleziona un elemento nel controllo ListView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- lists [Windows Forms], selecting items
- ListView control [Windows Forms], selecting items
- selection [Windows Forms], in list views
- list views [Windows Forms], selecting items
ms.assetid: ddea918e-1ddf-47f4-bd09-1e9b4c9d0c39
ms.openlocfilehash: 57e985af9d0347510d7d7782f68d5b414d36e077
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952008"
---
# <a name="how-to-select-an-item-in-the-windows-forms-listview-control"></a><span data-ttu-id="0a69f-102">Procedura: Selezionare un elemento nel controllo ListView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0a69f-102">How to: Select an Item in the Windows Forms ListView Control</span></span>
<span data-ttu-id="0a69f-103">In questo esempio viene illustrato come selezionare a livello di codice un elemento in un <xref:System.Windows.Forms.ListView> controllo Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="0a69f-103">This example demonstrates how to programmatically select an item in a Windows Forms <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="0a69f-104">La selezione di un elemento a livello di codice non comporta automaticamente la modifica dello stato attivo sul <xref:System.Windows.Forms.ListView> controllo.</span><span class="sxs-lookup"><span data-stu-id="0a69f-104">Selecting an item programmatically does not automatically change the focus to the <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="0a69f-105">Per questo motivo, in genere è necessario impostare l'elemento come attivo quando si seleziona un elemento.</span><span class="sxs-lookup"><span data-stu-id="0a69f-105">For this reason, you will typically also want to set the item as focused when selecting an item.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0a69f-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="0a69f-106">Example</span></span>  
 [!code-csharp[System.Windows.Forms.ListView.Misc#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.ListView.Misc#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListView.Misc/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0a69f-107">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="0a69f-107">Compiling the Code</span></span>  
 <span data-ttu-id="0a69f-108">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="0a69f-108">This example requires:</span></span>  
  
- <span data-ttu-id="0a69f-109"><xref:System.Windows.Forms.ListView>Controllo denominato `listView1` che contiene almeno un elemento.</span><span class="sxs-lookup"><span data-stu-id="0a69f-109">A <xref:System.Windows.Forms.ListView> control named `listView1` that contains at least one item.</span></span>  
  
- <span data-ttu-id="0a69f-110">Riferimenti agli spazi dei nomi <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0a69f-110">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a69f-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0a69f-111">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListViewItem.Selected%2A?displayProperty=nameWithType>
