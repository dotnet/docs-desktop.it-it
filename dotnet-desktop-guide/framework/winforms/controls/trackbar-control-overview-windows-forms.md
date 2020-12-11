---
title: Panoramica del controllo TrackBar
ms.date: 03/30/2017
f1_keywords:
- TrackBar
helpviewer_keywords:
- sliders [Windows Forms], about sliders
- TrackBar control [Windows Forms], about TrackBar control
- slider controls [Windows Forms], about slider controls
ms.assetid: 95910ecb-8a4c-4776-89fa-206c89ed6973
ms.openlocfilehash: 6901405100df4633c84850757f55b756bc9a0199
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966502"
---
# <a name="trackbar-control-overview-windows-forms"></a>Cenni preliminari sul controllo TrackBar (Windows Form)
Il <xref:System.Windows.Forms.TrackBar> controllo Windows Forms (anche noto anche come controllo "slider") viene usato per spostarsi tra una grande quantità di informazioni o per modificare visivamente un'impostazione numerica. Il <xref:System.Windows.Forms.TrackBar> controllo è costituito da due parti: il cursore, noto anche come dispositivo di scorrimento, e i segni di graduazione. Il pollice è la parte che può essere regolata. La posizione corrisponde alla <xref:System.Windows.Forms.TrackBar.Value%2A> Proprietà. I segni di graduazione sono indicatori visivi spaziati a intervalli regolari. Il controllo TrackBar si sposta in incrementi specificati e può essere allineato orizzontalmente o verticalmente. Ad esempio, è possibile usare l'indicatore di avanzamento per controllare la velocità del cursore o la velocità del mouse per un sistema.  
  
## <a name="key-properties"></a>Proprietà chiave  
 Le proprietà chiave del <xref:System.Windows.Forms.TrackBar> controllo sono <xref:System.Windows.Forms.TrackBar.Value%2A> ,, <xref:System.Windows.Forms.TrackBar.TickFrequency%2A> <xref:System.Windows.Forms.TrackBar.Minimum%2A> e <xref:System.Windows.Forms.TrackBar.Maximum%2A> . <xref:System.Windows.Forms.TrackBar.TickFrequency%2A> spaziatura dei cicli. <xref:System.Windows.Forms.TrackBar.Minimum%2A> e <xref:System.Windows.Forms.TrackBar.Maximum%2A> sono i valori più piccoli e più grandi che possono essere rappresentati sull'indicatore di avanzamento.  
  
 Altre due proprietà importanti sono <xref:System.Windows.Forms.TrackBar.SmallChange%2A> e <xref:System.Windows.Forms.TrackBar.LargeChange%2A> . Il valore della <xref:System.Windows.Forms.TrackBar.SmallChange%2A> proprietà è il numero di posizioni in cui il cursore si sposta in risposta alla pressione del tasto freccia sinistra o destra. Il valore della <xref:System.Windows.Forms.TrackBar.LargeChange%2A> proprietà è il numero di posizioni in cui il cursore si sposta in risposta alla pressione del tasto PGSU o PGGIÙ o in risposta ai clic del mouse sulla barra di avanzamento su entrambi i lati del cursore.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.TrackBar>
- [Controllo TrackBar](trackbar-control-windows-forms.md)
