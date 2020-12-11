---
title: 'Procedura: archiviare più formati di dati in un oggetto dati'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataObject class [WPF], storing multiple formats
- DataFormats class [WPF], storing multiple formats
- drag-and-drop [WPF], storing multiple formats
ms.assetid: 941ace29-29c4-4c26-b75b-ea7d06aa0d69
ms.openlocfilehash: 3f8e7233e1d28fec1f7dac114b04287aa3aff49f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952199"
---
# <a name="how-to-store-multiple-data-formats-in-a-data-object"></a>Procedura: archiviare più formati di dati in un oggetto dati
Nell'esempio seguente viene illustrato come utilizzare il <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%29> metodo per aggiungere dati a un oggetto dati in più formati.  
  
## <a name="example"></a>Esempio  
  
### <a name="description"></a>Descrizione  
  
### <a name="code"></a>Codice  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_storemultipleformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_storemultipleformats)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.IDataObject>
- [Cenni preliminari sul trascinamento della selezione](drag-and-drop-overview.md)
