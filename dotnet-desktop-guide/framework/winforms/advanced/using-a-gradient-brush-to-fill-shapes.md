---
title: Utilizzo di un pennello a sfumatura per il riempimento di forme
ms.date: 03/30/2017
helpviewer_keywords:
- brushes [Windows Forms], gradient brushes
- gradient brushes
- examples [Windows Forms], gradient brushes
ms.assetid: 2c6037b9-05bd-44c0-a22a-19584b722524
ms.openlocfilehash: 7ff555ba4fd81e9123e5f9e9feed38a0ec9d0a08
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963031"
---
# <a name="using-a-gradient-brush-to-fill-shapes"></a>Utilizzo di un pennello a sfumatura per il riempimento di forme
È possibile utilizzare un pennello sfumatura per riempire una forma con un colore a modifica graduale. È ad esempio possibile utilizzare una sfumatura orizzontale per riempire una forma con un colore che cambia gradualmente man mano che si passa dal bordo sinistro della forma al bordo destro. Immaginate un rettangolo con un bordo sinistro nero (rappresentato da componenti rosso, verde e blu 0, 0, 0) e un bordo destro rosso (rappresentato da 255, 0, 0). Se il rettangolo è 256 pixel di larghezza, il componente rosso di un determinato pixel sarà maggiore di uno rispetto al componente rosso del pixel alla sua sinistra. Il pixel più a sinistra in una riga ha componenti di colore (0, 0, 0), il secondo pixel ha (1, 0, 0), il terzo pixel ha (2, 0, 0) e così via, fino a quando non si arriva al pixel più a destra, che include componenti colore (255, 0, 0). Questi valori di colore interpolati costituiscono la sfumatura di colore.  
  
 Una sfumatura lineare cambia colore mentre si sposta orizzontalmente, verticalmente o in parallelo in una linea inclinata specificata. Una sfumatura di tracciato cambia colore mentre si sposta sull'interno e sul limite di un tracciato. È possibile personalizzare le sfumature del tracciato per ottenere una vasta gamma di effetti.  
  
 Nella figura seguente viene illustrato un rettangolo riempito con un pennello sfumato lineare e un'ellisse riempita con un pennello sfumatura tracciato:  
  
 ![Rettangolo riempito con un pennello sfumato con un'ellisse.](./media/using-a-gradient-brush-to-fill-shapes/rectangle-ellipse-gradient-brush.png)  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Procedura: Creare una sfumatura lineare](how-to-create-a-linear-gradient.md)  
 Viene illustrato come creare una sfumatura lineare utilizzando la <xref:System.Drawing.Drawing2D.LinearGradientBrush> classe.  
  
 [Procedura: Creare una sfumatura percorso](how-to-create-a-path-gradient.md)  
 Viene descritto come creare una sfumatura del percorso utilizzando la <xref:System.Drawing.Drawing2D.PathGradientBrush> classe.  
  
 [Procedura: Applicare la correzione gamma a una sfumatura](how-to-apply-gamma-correction-to-a-gradient.md)  
 Viene illustrato come usare la correzione gamma con un pennello sfumatura.  
  
## <a name="reference"></a>Informazioni di riferimento  
 <xref:System.Drawing.Drawing2D.LinearGradientBrush?displayProperty=nameWithType>  
 Contiene una descrizione di questa classe e include collegamenti a tutti i relativi membri.  
  
 <xref:System.Drawing.Drawing2D.PathGradientBrush?displayProperty=nameWithType>  
 Contiene una descrizione di questa classe e include collegamenti a tutti i relativi membri.
