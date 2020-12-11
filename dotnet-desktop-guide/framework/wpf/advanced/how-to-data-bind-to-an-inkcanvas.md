---
title: 'Procedura: Data binding con un InkCanvas'
ms.date: 03/30/2017
helpviewer_keywords:
- InkCanvas [WPF], binding data to
- binding data [WPF], to InkCanvas
ms.assetid: 8d6b4d9e-ea7f-4412-ba83-3feccec5a515
ms.openlocfilehash: 5d3fc0ed7b6176d7bc68bf20af42c311b5563908
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967906"
---
# <a name="how-to-data-bind-to-an-inkcanvas"></a>Procedura: Data binding con un InkCanvas
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come associare la <xref:System.Windows.Controls.InkCanvas.Strokes%2A> proprietà di un oggetto <xref:System.Windows.Controls.InkCanvas> a un altro <xref:System.Windows.Controls.InkCanvas> .  
  
 [!code-xaml[InkCanvasBindingSnippet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#2)]  
  
 Nell'esempio seguente viene illustrato come associare la <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> proprietà a un'origine dati.  
  
 [!code-xaml[InkCanvasBindingSnippet#3](~/samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#3)]  
[!code-xaml[InkCanvasBindingSnippet#4](~/samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window2.xaml#4)]  
  
 Nell'esempio seguente vengono dichiarati due <xref:System.Windows.Controls.InkCanvas> oggetti in XAML e viene stabilito data binding tra di essi e altre origini dati.  Il primo <xref:System.Windows.Controls.InkCanvas> , denominato `ic` , è associato a due origini dati.  Le <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> proprietà e su `ic` sono associate a <xref:System.Windows.Controls.ListBox> oggetti, che a loro volta sono associate a matrici definite in XAML.  Le <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> <xref:System.Windows.Controls.InkCanvas.DefaultDrawingAttributes%2A> proprietà, e <xref:System.Windows.Controls.InkCanvas.Strokes%2A> della seconda <xref:System.Windows.Controls.InkCanvas> sono associate alla prima <xref:System.Windows.Controls.InkCanvas> `ic` .  
  
 [!code-xaml[InkCanvasBindingSnippet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/InkCanvasBindingSnippet/CS/Window1.xaml#1)]
