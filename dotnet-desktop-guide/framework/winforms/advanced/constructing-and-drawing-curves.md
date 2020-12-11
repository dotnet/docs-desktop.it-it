---
title: Costruzione e creazione di curve
ms.date: 03/30/2017
helpviewer_keywords:
- drawing [Windows Forms], curves
- examples [Windows Forms], drawing curves
- curves [Windows Forms], drawing
ms.assetid: 76e92623-4130-4644-b867-faca58bdb3a2
ms.openlocfilehash: 4c1b0cc6c6f878569fcf0c392f1b6f9683ec8afc
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952487"
---
# <a name="constructing-and-drawing-curves"></a>Costruzione e creazione di curve
GDI+ supporta diversi tipi di curve: ellissi, archi, spline cardinali e spline di Bézier. Un'ellisse è definita dal relativo rettangolo di delimitazione; un arco è una parte di un'ellisse definita da un angolo iniziale e da un angolo di sweep. Una spline di tipo Cardinal viene definita da una matrice di punti e da un parametro di tensionamento, ovvero la curva passa in modo graduale attraverso ogni punto della matrice e il parametro di tensione influenza la curva. Una spline di Bézier è definita da due endpoint e due punti di controllo la curva non passa attraverso i punti di controllo, ma i punti di controllo influenzano la direzione e la curva quando la curva passa da un endpoint all'altro.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Procedura: Disegnare cardinal spline](how-to-draw-cardinal-splines.md)  
 Descrive le spline cardinali e come crearle.  
  
 [Procedura: Disegnare una singola spline di Bézier](how-to-draw-a-single-bezier-spline.md)  
 Descrive una spline di Bézier e come estrarne una.  
  
 [Procedura: Disegnare una sequenza di spline di Bézier](how-to-draw-a-sequence-of-bezier-splines.md)  
 Viene illustrato come creare diverse spline di Bézier in sequenza.
