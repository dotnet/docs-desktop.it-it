---
title: 'Procedura: assicurarsi che GridSplitter sia visibile'
ms.date: 03/30/2017
helpviewer_keywords:
- GridSplitter control [WPF], ensuring visibility of
ms.assetid: 0a62a964-89c8-48f0-9023-5df721a8cf47
ms.openlocfilehash: 2085ac5cec206d8692a1267acf132688f0aa9082
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969790"
---
# <a name="how-to-make-sure-that-a-gridsplitter-is-visible"></a>Procedura: assicurarsi che GridSplitter sia visibile
Questo esempio illustra come verificare che un <xref:System.Windows.Controls.GridSplitter> controllo non sia nascosto dagli altri controlli di un oggetto <xref:System.Windows.Controls.Grid> .  
  
## <a name="example"></a>Esempio  
 <xref:System.Windows.Controls.Panel.Children%2A>Viene eseguito il rendering dell'oggetto di un <xref:System.Windows.Controls.Grid> controllo nell'ordine in cui sono definiti nel markup o nel codice. <xref:System.Windows.Controls.GridSplitter> i controlli possono essere nascosti da altri controlli se non vengono definiti come ultimi elementi della <xref:System.Windows.Controls.Panel.Children%2A> raccolta o se si assegnano altri controlli a un livello superiore <xref:System.Windows.Controls.Panel.ZIndexProperty> .  
  
 Per evitare <xref:System.Windows.Controls.GridSplitter> i controlli nascosti, effettuare una delle operazioni seguenti.  
  
- Verificare che <xref:System.Windows.Controls.GridSplitter> i controlli siano l'ultimo <xref:System.Windows.Controls.Panel.Children%2A> aggiunto a <xref:System.Windows.Controls.Grid> . Nell'esempio seguente viene illustrato <xref:System.Windows.Controls.GridSplitter> come l'ultimo elemento della <xref:System.Windows.Controls.Panel.Children%2A> raccolta di <xref:System.Windows.Controls.Grid> .  
  
 [!code-xaml[GridSplitterSnips#GridSplitterLastChild](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterlastchild)]  
  
- Impostare sull'oggetto in modo che <xref:System.Windows.Controls.Panel.ZIndexProperty> <xref:System.Windows.Controls.GridSplitter> sia maggiore di un controllo che altrimenti lo nasconderebbe. Nell'esempio seguente il controllo viene assegnato <xref:System.Windows.Controls.GridSplitter> a un livello superiore <xref:System.Windows.Controls.Panel.ZIndexProperty> rispetto al <xref:System.Windows.Controls.Button> controllo.  
  
 [!code-xaml[GridSplitterSnips#GridSplitterZIndex](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplitterzindex)]  
  
- Impostare i margini sul controllo che altrimenti nasconderebbe in <xref:System.Windows.Controls.GridSplitter> modo che l'oggetto <xref:System.Windows.Controls.GridSplitter> venga esposto. Nell'esempio seguente vengono impostati i margini su un controllo che altrimenti verrebbe sovrapposto e nascosto <xref:System.Windows.Controls.GridSplitter> .  
  
 [!code-xaml[GridSplitterSnips#GridSplitterMargin](~/samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterSnips/CSharp/Window1.xaml#gridsplittermargin)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.GridSplitter>
- [Procedure](gridsplitter-how-to-topics.md)
