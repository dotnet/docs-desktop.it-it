---
title: 'Procedura: regolare la spaziatura tra paragrafi'
ms.date: 03/30/2017
helpviewer_keywords:
- spacing between paragraphs [WPF]
- paragraphs [WPF], spacing between
- documents [WPF], adjusting spacing between paragraphs
ms.assetid: 7cd2f2ac-0e19-4587-bfb6-7f5b18c9536e
ms.openlocfilehash: e2a6ba34e3ab15eb316671fef7c11bea03d53c73
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964612"
---
# <a name="how-to-adjust-spacing-between-paragraphs"></a>Procedura: regolare la spaziatura tra paragrafi
Questo esempio illustra come regolare o eliminare la spaziatura tra i paragrafi nel contenuto del flusso.  
  
 In contenuto dinamico, lo spazio aggiuntivo visualizzato tra i paragrafi è il risultato dei margini impostati su questi paragrafi; la spaziatura tra i paragrafi può quindi essere controllata regolando i margini dei paragrafi.  Per eliminare completamente la spaziatura aggiuntiva tra due paragrafi, impostare i margini per i paragrafi su **0**.  Per ottenere una spaziatura uniforme tra i paragrafi nell'intero oggetto <xref:System.Windows.Documents.FlowDocument> , utilizzare lo stile per impostare un valore di margine uniforme per tutti i paragrafi in <xref:System.Windows.Documents.FlowDocument> .  
  
 È importante notare che i margini per due paragrafi adiacenti comporteranno il "collasso" al più grande dei due margini, anziché raddoppiare. Quindi, se due paragrafi adiacenti hanno rispettivamente margini di 20 pixel e 40 pixel, lo spazio risultante tra i paragrafi è 40 pixel, maggiore è il numero di valori dei due margini.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene utilizzato lo stile per impostare il margine di tutti <xref:System.Windows.Documents.Paragraph> gli elementi in un oggetto <xref:System.Windows.Documents.FlowDocument> su **0**, eliminando in tal modo la spaziatura aggiuntiva tra i paragrafi in <xref:System.Windows.Documents.FlowDocument> .  
  
 [!code-xaml[BlockSnippets#_ParagraphSpacingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/BlockSnippets/CSharp/Window1.xaml#_paragraphspacingxaml)]
