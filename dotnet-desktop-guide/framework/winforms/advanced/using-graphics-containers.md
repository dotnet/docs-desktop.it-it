---
title: Utilizzo dei contenitori di grafica
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], using containers
- graphics containers
- examples [Windows Forms], graphics containers
ms.assetid: 74632f91-cefa-4f51-ab7c-f9ac91942caf
ms.openlocfilehash: cfad7254057a31ea8268784cd4b6849850f3e2aa
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952763"
---
# <a name="using-graphics-containers"></a>Utilizzo dei contenitori di grafica
Un <xref:System.Drawing.Graphics> oggetto fornisce metodi come <xref:System.Drawing.Graphics.DrawLine%2A> , <xref:System.Drawing.Graphics.DrawImage%2A> e per la <xref:System.Drawing.Graphics.DrawString%2A> visualizzazione di immagini vettoriali, immagini raster e testo. Un <xref:System.Drawing.Graphics> oggetto dispone inoltre di diverse proprietà che influenzano la qualità e l'orientamento degli elementi disegnati. Ad esempio, la proprietà modalità di smussamento determina se l'anti-aliasing viene applicato a linee e curve e la proprietà trasformazione globale influisce sulla posizione e sulla rotazione degli elementi disegnati.  
  
 Un <xref:System.Drawing.Graphics> oggetto è associato a un dispositivo di visualizzazione specifico. Quando si utilizza un <xref:System.Drawing.Graphics> oggetto da creare in una finestra, l' <xref:System.Drawing.Graphics> oggetto viene anche associato a tale finestra specifica.  
  
 Un <xref:System.Drawing.Graphics> oggetto può essere considerato come un contenitore perché include un set di proprietà che influenzano il disegno ed è collegato a informazioni specifiche del dispositivo. È possibile creare un contenitore secondario all'interno di un oggetto esistente chiamando <xref:System.Drawing.Graphics> il <xref:System.Drawing.Graphics.BeginContainer%2A> metodo di tale <xref:System.Drawing.Graphics> oggetto.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Gestione dello stato di un oggetto Graphics](managing-the-state-of-a-graphics-object.md)  
 Viene descritto come gestire le impostazioni di qualità, l'area di ridimensionamento e le trasformazioni di un <xref:System.Drawing.Graphics> oggetto.  
  
 [Utilizzo di contenitori di grafica annidati](using-nested-graphics-containers.md)  
 Viene illustrato come utilizzare i contenitori per controllare lo stato dell' <xref:System.Drawing.Graphics> oggetto.
