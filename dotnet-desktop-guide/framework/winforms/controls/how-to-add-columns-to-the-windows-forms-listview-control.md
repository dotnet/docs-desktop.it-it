---
title: Aggiunta di colonne al controllo ListView
description: Informazioni su come aggiungere colonne al controllo Windows Forms ListView per visualizzare diversi tipi di informazioni su ogni elemento dell'elenco.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
- list views [Windows Forms], adding columns
ms.assetid: 79174274-12ee-4a5d-80db-6ec02976d010
ms.openlocfilehash: 7ca4e86ca3a9679876f2525c49596534f175096a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962836"
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control"></a><span data-ttu-id="0a2f0-103">Procedura: Aggiungere colonne al controllo ListView di Windows Forms</span><span class="sxs-lookup"><span data-stu-id="0a2f0-103">How to: Add Columns to the Windows Forms ListView Control</span></span>
<span data-ttu-id="0a2f0-104">Nella visualizzazione dettagli, il <xref:System.Windows.Forms.ListView> controllo può visualizzare più colonne per ogni elemento dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="0a2f0-104">In the Details view, the <xref:System.Windows.Forms.ListView> control can display multiple columns for each list item.</span></span> <span data-ttu-id="0a2f0-105">È possibile utilizzare le colonne per visualizzare all'utente diversi tipi di informazioni su ogni elemento dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="0a2f0-105">You can use the columns to display to the user several types of information about each list item.</span></span> <span data-ttu-id="0a2f0-106">Ad esempio, un elenco di file potrebbe visualizzare il nome del file, il tipo di file, le dimensioni e la data dell'Ultima modifica del file.</span><span class="sxs-lookup"><span data-stu-id="0a2f0-106">For example, a list of files could display the file name, file type, size, and date the file was last modified.</span></span> <span data-ttu-id="0a2f0-107">Per informazioni sul popolamento delle colonne dopo la creazione, vedere [procedura: visualizzare elementi secondari nelle colonne con il controllo ListView Windows Forms](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).</span><span class="sxs-lookup"><span data-stu-id="0a2f0-107">For information about populating the columns after they are created, see [How to: Display Subitems in Columns with the Windows Forms ListView Control](how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).</span></span>  
  
### <a name="to-add-columns-programmatically"></a><span data-ttu-id="0a2f0-108">Per aggiungere colonne a livello di codice</span><span class="sxs-lookup"><span data-stu-id="0a2f0-108">To add columns programmatically</span></span>  
  
1. <span data-ttu-id="0a2f0-109">Impostare la proprietà del controllo <xref:System.Windows.Forms.ListView.View%2A> su <xref:System.Windows.Forms.View.Details> .</span><span class="sxs-lookup"><span data-stu-id="0a2f0-109">Set the control's <xref:System.Windows.Forms.ListView.View%2A> property to <xref:System.Windows.Forms.View.Details>.</span></span>  
  
2. <span data-ttu-id="0a2f0-110">Usare il <xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A> metodo della proprietà della visualizzazione elenco <xref:System.Windows.Forms.ListView.Columns%2A> .</span><span class="sxs-lookup"><span data-stu-id="0a2f0-110">Use the <xref:System.Windows.Forms.ListView.ColumnHeaderCollection.Add%2A> method of the list view's <xref:System.Windows.Forms.ListView.Columns%2A> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ListViewLegacyTopics#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/CS/Class1.cs#31)]
     [!code-vb[System.Windows.Forms.ListViewLegacyTopics#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ListViewLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="see-also"></a><span data-ttu-id="0a2f0-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0a2f0-111">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- [<span data-ttu-id="0a2f0-112">Controllo ListView</span><span class="sxs-lookup"><span data-stu-id="0a2f0-112">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="0a2f0-113">Panoramica del controllo ListView</span><span class="sxs-lookup"><span data-stu-id="0a2f0-113">ListView Control Overview</span></span>](listview-control-overview-windows-forms.md)
