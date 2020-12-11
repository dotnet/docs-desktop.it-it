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
# <a name="constructing-and-drawing-curves"></a><span data-ttu-id="a5fcf-102">Costruzione e creazione di curve</span><span class="sxs-lookup"><span data-stu-id="a5fcf-102">Constructing and Drawing Curves</span></span>
<span data-ttu-id="a5fcf-103">GDI+ supporta diversi tipi di curve: ellissi, archi, spline cardinali e spline di Bézier.</span><span class="sxs-lookup"><span data-stu-id="a5fcf-103">GDI+ supports several types of curves: ellipses, arcs, cardinal splines, and Bézier splines.</span></span> <span data-ttu-id="a5fcf-104">Un'ellisse è definita dal relativo rettangolo di delimitazione; un arco è una parte di un'ellisse definita da un angolo iniziale e da un angolo di sweep.</span><span class="sxs-lookup"><span data-stu-id="a5fcf-104">An ellipse is defined by its bounding rectangle; an arc is a portion of an ellipse defined by a starting angle and a sweep angle.</span></span> <span data-ttu-id="a5fcf-105">Una spline di tipo Cardinal viene definita da una matrice di punti e da un parametro di tensionamento, ovvero la curva passa in modo graduale attraverso ogni punto della matrice e il parametro di tensione influenza la curva.</span><span class="sxs-lookup"><span data-stu-id="a5fcf-105">A cardinal spline is defined by an array of points and a tension parameter — the curve passes smoothly through each point in the array, and the tension parameter influences the way the curve bends.</span></span> <span data-ttu-id="a5fcf-106">Una spline di Bézier è definita da due endpoint e due punti di controllo la curva non passa attraverso i punti di controllo, ma i punti di controllo influenzano la direzione e la curva quando la curva passa da un endpoint all'altro.</span><span class="sxs-lookup"><span data-stu-id="a5fcf-106">A Bézier spline is defined by two endpoints and two control points  the curve does not pass through the control points, but the control points influence the direction and bend as the curve goes from one endpoint to the other.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a5fcf-107">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="a5fcf-107">In This Section</span></span>  
 [<span data-ttu-id="a5fcf-108">Procedura: Disegnare cardinal spline</span><span class="sxs-lookup"><span data-stu-id="a5fcf-108">How to: Draw Cardinal Splines</span></span>](how-to-draw-cardinal-splines.md)  
 <span data-ttu-id="a5fcf-109">Descrive le spline cardinali e come crearle.</span><span class="sxs-lookup"><span data-stu-id="a5fcf-109">Describes cardinal splines and how to draw them.</span></span>  
  
 [<span data-ttu-id="a5fcf-110">Procedura: Disegnare una singola spline di Bézier</span><span class="sxs-lookup"><span data-stu-id="a5fcf-110">How to: Draw a Single Bézier Spline</span></span>](how-to-draw-a-single-bezier-spline.md)  
 <span data-ttu-id="a5fcf-111">Descrive una spline di Bézier e come estrarne una.</span><span class="sxs-lookup"><span data-stu-id="a5fcf-111">Describes a Bézier spline and how to draw one.</span></span>  
  
 [<span data-ttu-id="a5fcf-112">Procedura: Disegnare una sequenza di spline di Bézier</span><span class="sxs-lookup"><span data-stu-id="a5fcf-112">How to: Draw a Sequence of Bézier Splines</span></span>](how-to-draw-a-sequence-of-bezier-splines.md)  
 <span data-ttu-id="a5fcf-113">Viene illustrato come creare diverse spline di Bézier in sequenza.</span><span class="sxs-lookup"><span data-stu-id="a5fcf-113">Explains how to draw several Bézier splines in sequence.</span></span>
