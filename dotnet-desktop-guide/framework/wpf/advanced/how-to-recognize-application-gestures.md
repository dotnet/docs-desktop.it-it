---
title: "Procedura: riconoscere i movimenti dell'applicazione"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application gestures [WPF], recognizing
- gestures [WPF], recognizing
ms.assetid: d58b740f-5192-4a3e-af59-7aa162e6ca15
ms.openlocfilehash: 647e7c9c1d785cebfdc362dc48511d865f3945dc
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968386"
---
# <a name="how-to-recognize-application-gestures"></a><span data-ttu-id="6d8ce-102">Procedura: riconoscere i movimenti dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="6d8ce-102">How To: Recognize Application Gestures</span></span>
<span data-ttu-id="6d8ce-103">Nell'esempio seguente viene illustrato come cancellare l'input penna quando un utente esegue un <xref:System.Windows.Ink.ApplicationGesture.ScratchOut> movimento su un oggetto <xref:System.Windows.Controls.InkCanvas> .</span><span class="sxs-lookup"><span data-stu-id="6d8ce-103">The following example demonstrates how to erase ink when a user makes a <xref:System.Windows.Ink.ApplicationGesture.ScratchOut> gesture on an <xref:System.Windows.Controls.InkCanvas>.</span></span> <span data-ttu-id="6d8ce-104">In questo esempio si presuppone che un oggetto <xref:System.Windows.Controls.InkCanvas> , denominato `inkCanvas1` , sia dichiarato nel file XAML.</span><span class="sxs-lookup"><span data-stu-id="6d8ce-104">This example assumes an <xref:System.Windows.Controls.InkCanvas>, called `inkCanvas1`, is declared in the XAML file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6d8ce-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="6d8ce-105">Example</span></span>  
 [!code-csharp[HowToRecognizeGestures#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToRecognizeGestures/CSharp/Window1.xaml.cs#1)]
 [!code-vb[HowToRecognizeGestures#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToRecognizeGestures/VisualBasic/Window1.xaml.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="6d8ce-106">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d8ce-106">See also</span></span>

- <xref:System.Windows.Ink.ApplicationGesture>
- <xref:System.Windows.Controls.InkCanvas>
- <xref:System.Windows.Controls.InkCanvas.Gesture>
