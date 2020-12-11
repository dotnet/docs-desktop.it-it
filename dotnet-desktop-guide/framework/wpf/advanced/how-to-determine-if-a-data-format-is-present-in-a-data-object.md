---
title: 'Procedura: determinare se un formato di dati è presente in un oggetto dati'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataFormats class [WPF]
- drag-and-drop [WPF], data formats present
- data formats [WPF], determining if present
ms.assetid: e487a454-c9fc-4e53-aeaa-c458d059ad4c
ms.openlocfilehash: 4cec733490e2a9dc5d54b3b253ac38a5090ac885
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965620"
---
# <a name="how-to-determine-if-a-data-format-is-present-in-a-data-object"></a><span data-ttu-id="7d7c3-102">Procedura: determinare se un formato di dati è presente in un oggetto dati</span><span class="sxs-lookup"><span data-stu-id="7d7c3-102">How to: Determine if a Data Format is Present in a Data Object</span></span>
<span data-ttu-id="7d7c3-103">Negli esempi seguenti viene illustrato come utilizzare i vari <xref:System.Windows.DataObject.GetDataPresent%2A> Overload del metodo per eseguire una query sull'eventuale presenza di un particolare formato di dati in un oggetto dati.</span><span class="sxs-lookup"><span data-stu-id="7d7c3-103">The following examples show how to use the various <xref:System.Windows.DataObject.GetDataPresent%2A> method overloads to query whether a particular data format is present in a data object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7d7c3-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="7d7c3-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="7d7c3-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7d7c3-105">Description</span></span>  
 <span data-ttu-id="7d7c3-106">Nell'esempio di codice seguente viene utilizzato l' <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> Overload per eseguire una query per la presenza di un particolare formato di dati in base alla stringa di descrittore.</span><span class="sxs-lookup"><span data-stu-id="7d7c3-106">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> overload to query for the presence of a particular data format by descriptor string.</span></span>  
  
### <a name="code"></a><span data-ttu-id="7d7c3-107">Codice</span><span class="sxs-lookup"><span data-stu-id="7d7c3-107">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_String](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_string)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_String](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_string)]  
  
## <a name="example"></a><span data-ttu-id="7d7c3-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="7d7c3-108">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="7d7c3-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7d7c3-109">Description</span></span>  
 <span data-ttu-id="7d7c3-110">Nell'esempio di codice seguente viene utilizzato l' <xref:System.Windows.DataObject.GetDataPresent%28System.Type%29> Overload per eseguire una query per la presenza di un particolare formato di dati in base al tipo.</span><span class="sxs-lookup"><span data-stu-id="7d7c3-110">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.Type%29> overload to query for the presence of a particular data format by type.</span></span>  
  
### <a name="code"></a><span data-ttu-id="7d7c3-111">Codice</span><span class="sxs-lookup"><span data-stu-id="7d7c3-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Type](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_type)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Type](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_type)]  
  
## <a name="example"></a><span data-ttu-id="7d7c3-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="7d7c3-112">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="7d7c3-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7d7c3-113">Description</span></span>  
 <span data-ttu-id="7d7c3-114">Nell'esempio di codice seguente viene utilizzato l' <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> Overload per eseguire una query per i dati in base alla stringa di descrittore e viene specificato come gestire i formati di dati convertibili automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7d7c3-114">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> overload to query for data by descriptor string, and specifying how to treat auto-convertible data formats.</span></span>  
  
### <a name="code"></a><span data-ttu-id="7d7c3-115">Codice</span><span class="sxs-lookup"><span data-stu-id="7d7c3-115">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Autoconvert](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_querydataformats_autoconvert)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_QueryDataFormats_Autoconvert](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_querydataformats_autoconvert)]  
  
## <a name="see-also"></a><span data-ttu-id="7d7c3-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7d7c3-116">See also</span></span>

- <xref:System.Windows.IDataObject>
