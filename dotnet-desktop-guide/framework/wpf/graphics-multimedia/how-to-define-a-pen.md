---
title: 'Procedura: definire una penna'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pens [WPF], defining
- creating [WPF], pens
ms.assetid: 7a4f2900-cdf9-49de-84e0-ba5d0ded4d33
ms.openlocfilehash: 1d69a40604dbf2f7a73c17279ae946faeb6c634a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963463"
---
# <a name="how-to-define-a-pen"></a>Procedura: definire una penna
Questo esempio illustra come usare un oggetto <xref:System.Windows.Media.Pen> per delineare una forma. Per creare un semplice <xref:System.Windows.Media.Pen> , è necessario specificare solo i relativi <xref:System.Windows.Media.Pen.Thickness%2A> e <xref:System.Windows.Media.Pen.Brush%2A> . È possibile creare penne più complesse specificando un,, <xref:System.Windows.Media.Pen.DashStyle%2A> <xref:System.Windows.Media.Pen.DashCap%2A> <xref:System.Windows.Media.Pen.LineJoin%2A> , <xref:System.Windows.Media.Pen.StartLineCap%2A> e <xref:System.Windows.Media.Pen.EndLineCap%2A> .  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato un oggetto <xref:System.Windows.Media.Pen> per delineare una forma definita da un oggetto <xref:System.Windows.Media.GeometryDrawing> .  
  
 [!code-csharp[PenExamples_snip#PenExampleWholePage](~/samples/snippets/csharp/VS_Snippets_Wpf/PenExamples_snip/CSharp/PenExample.cs#penexamplewholepage)]
 [!code-vb[PenExamples_snip#PenExampleWholePage](~/samples/snippets/visualbasic/VS_Snippets_Wpf/PenExamples_snip/VisualBasic/PenExample.vb#penexamplewholepage)]  
  
 ![Strutture prodotte da un oggetto Pen](./media/graphicsmm-simple-pen.jpg "graphicsmm_simple_pen")  
GeometryDrawing
