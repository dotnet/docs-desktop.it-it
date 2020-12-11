---
title: 'Procedura: recuperare dati in un formato dati particolare'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- drag-and-drop [WPF], retrieving data
- DataFormats class [WPF], retrieving data
- DataObject class [WPF], retrieving data
ms.assetid: a625acf3-1144-44cd-add7-456aefc3859f
ms.openlocfilehash: b3ec1b8fa873fd449956912e9e77e98b0362cb0e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962788"
---
# <a name="how-to-retrieve-data-in-a-particular-data-format"></a><span data-ttu-id="9ea04-102">Procedura: recuperare dati in un formato dati particolare</span><span class="sxs-lookup"><span data-stu-id="9ea04-102">How to: Retrieve Data in a Particular Data Format</span></span>
<span data-ttu-id="9ea04-103">Negli esempi seguenti viene illustrato come recuperare dati da un oggetto dati in un formato specificato.</span><span class="sxs-lookup"><span data-stu-id="9ea04-103">The following examples show how to retrieve data from a data object in a specified format.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ea04-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="9ea04-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="9ea04-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9ea04-105">Description</span></span>  
 <span data-ttu-id="9ea04-106">Nell'esempio di codice seguente viene utilizzato l' <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> Overload per verificare innanzitutto se è disponibile un formato dati specificato (in modalità nativa o mediante conversione automatica); se il formato specificato è disponibile, nell'esempio vengono recuperati i dati utilizzando il <xref:System.Windows.DataObject.GetData%28System.String%29> metodo.</span><span class="sxs-lookup"><span data-stu-id="9ea04-106">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%29> overload to first check if a specified data format is available (natively or by auto-convert); if the specified format is available, the example retrieves the data by using the <xref:System.Windows.DataObject.GetData%28System.String%29> method.</span></span>  
  
### <a name="code"></a><span data-ttu-id="9ea04-107">Codice</span><span class="sxs-lookup"><span data-stu-id="9ea04-107">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat)]  
  
## <a name="example"></a><span data-ttu-id="9ea04-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="9ea04-108">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="9ea04-109">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9ea04-109">Description</span></span>  
 <span data-ttu-id="9ea04-110">Il codice di esempio seguente usa l' <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> Overload per verificare innanzitutto se un formato di dati specificato è disponibile a livello nativo (i formati di dati convertibili automaticamente sono filtrati); se il formato specificato è disponibile, nell'esempio vengono recuperati i dati usando il <xref:System.Windows.DataObject.GetData%28System.String%29> metodo.</span><span class="sxs-lookup"><span data-stu-id="9ea04-110">The following example code uses the <xref:System.Windows.DataObject.GetDataPresent%28System.String%2CSystem.Boolean%29> overload to first check if a specified data format is available natively (auto-convertible data formats are filtered); if the specified format is available, the example retrieves the data by using the <xref:System.Windows.DataObject.GetData%28System.String%29> method.</span></span>  
  
### <a name="code"></a><span data-ttu-id="9ea04-111">Codice</span><span class="sxs-lookup"><span data-stu-id="9ea04-111">Code</span></span>  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat_Native](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_getspecificdataformat_native)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_GetSpecificDataFormat_Native](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_getspecificdataformat_native)]  
  
## <a name="see-also"></a><span data-ttu-id="9ea04-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ea04-112">See also</span></span>

- <xref:System.Windows.IDataObject>
- [<span data-ttu-id="9ea04-113">Cenni preliminari sul trascinamento della selezione</span><span class="sxs-lookup"><span data-stu-id="9ea04-113">Drag and Drop Overview</span></span>](drag-and-drop-overview.md)
