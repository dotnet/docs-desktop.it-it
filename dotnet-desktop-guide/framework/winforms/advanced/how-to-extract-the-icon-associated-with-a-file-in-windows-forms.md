---
title: "Procedura: estrarre l'icona associata a un file"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- displaying a file name and its file type icon in a ListView control [Windows Forms]
- file name extension icons [Windows Forms], displaying in a ListView
- extracting icons associated with a file type [Windows Forms]
ms.assetid: 88e2ad8b-c34f-415a-84f2-dad756b5c928
ms.openlocfilehash: 28769144b0e1c631a31c3c541747a6215f861d0e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962623"
---
# <a name="how-to-extract-the-icon-associated-with-a-file-in-windows-forms"></a><span data-ttu-id="3fa74-102">Procedura: Estrarre l'icona associata a un file in Windows Form</span><span class="sxs-lookup"><span data-stu-id="3fa74-102">How to: Extract the Icon Associated with a File in Windows Forms</span></span>
<span data-ttu-id="3fa74-103">Molti file hanno icone incorporate che forniscono una rappresentazione visiva del tipo di file associato.</span><span class="sxs-lookup"><span data-stu-id="3fa74-103">Many files have embedded icons that provide a visual representation of the associated file type.</span></span> <span data-ttu-id="3fa74-104">Ad esempio, i documenti di Microsoft Word contengono un'icona che li identifica come documenti di Word.</span><span class="sxs-lookup"><span data-stu-id="3fa74-104">For example, Microsoft Word documents contain an icon that identifies them as Word documents.</span></span> <span data-ttu-id="3fa74-105">Quando si visualizzano i file in un controllo elenco o in un controllo tabella, potrebbe essere necessario visualizzare l'icona che rappresenta il tipo di file accanto a ogni nome file.</span><span class="sxs-lookup"><span data-stu-id="3fa74-105">When displaying files in a list control or table control, you may want to display the icon representing the file type next to each file name.</span></span> <span data-ttu-id="3fa74-106">Questa operazione può essere eseguita facilmente usando il <xref:System.Drawing.Icon.ExtractAssociatedIcon%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="3fa74-106">You can do this easily by using the <xref:System.Drawing.Icon.ExtractAssociatedIcon%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3fa74-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="3fa74-107">Example</span></span>  
 <span data-ttu-id="3fa74-108">Nell'esempio di codice riportato di seguito viene illustrato come estrarre l'icona associata a un file e visualizzare il nome del file e l'icona associata in un <xref:System.Windows.Forms.ListView> controllo.</span><span class="sxs-lookup"><span data-stu-id="3fa74-108">The following code example demonstrates how to extract the icon associated with a file and display the file name and its associated icon in a <xref:System.Windows.Forms.ListView> control.</span></span>  
  
 [!code-csharp[System.Drawing.Icon.ExtractAssociatedIconEx#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Icon.ExtractAssociatedIconEx#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Icon.ExtractAssociatedIconEx/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3fa74-109">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="3fa74-109">Compiling the Code</span></span>  
 <span data-ttu-id="3fa74-110">Per compilare l'esempio:</span><span class="sxs-lookup"><span data-stu-id="3fa74-110">To compile the example:</span></span>  
  
- <span data-ttu-id="3fa74-111">Incollare il codice precedente in un Windows Form e chiamare il `ExtractAssociatedIconExample` metodo dal costruttore del form o dal <xref:System.Windows.Forms.Form.Load> metodo di gestione degli eventi.</span><span class="sxs-lookup"><span data-stu-id="3fa74-111">Paste the preceding code into a Windows Form, and call the `ExtractAssociatedIconExample` method from the form's constructor or <xref:System.Windows.Forms.Form.Load> event-handling method.</span></span>  
  
     <span data-ttu-id="3fa74-112">Sarà necessario assicurarsi che il form importi lo <xref:System.IO> spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="3fa74-112">You will need to make sure that your form imports the <xref:System.IO> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fa74-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3fa74-113">See also</span></span>

- [<span data-ttu-id="3fa74-114">Immagini, bitmap e metafile</span><span class="sxs-lookup"><span data-stu-id="3fa74-114">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="3fa74-115">Controllo ListView</span><span class="sxs-lookup"><span data-stu-id="3fa74-115">ListView Control</span></span>](../controls/listview-control-windows-forms.md)
