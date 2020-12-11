---
title: "Procedura: cancellare l'input penna da un controllo personalizzato"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [WPF], erasing ink on
- ink [WPF], erasing on custom control
ms.assetid: d88c50f9-b4d8-4962-a28b-67d6a15a5fe0
ms.openlocfilehash: 60e2af64cb0c5b313f4f1201cab70da6a88f61e7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967870"
---
# <a name="how-to-erase-ink-on-a-custom-control"></a><span data-ttu-id="b0b41-102">Procedura: cancellare l'input penna da un controllo personalizzato</span><span class="sxs-lookup"><span data-stu-id="b0b41-102">How to: Erase Ink on a Custom Control</span></span>
<span data-ttu-id="b0b41-103"><xref:System.Windows.Ink.IncrementalStrokeHitTester>Determina se il tratto attualmente disegnato interseca un altro tratto.</span><span class="sxs-lookup"><span data-stu-id="b0b41-103">The <xref:System.Windows.Ink.IncrementalStrokeHitTester> determines whether the currently drawn stroke intersects another stroke.</span></span>  <span data-ttu-id="b0b41-104">Questa operazione è utile per la creazione di un controllo che consente a un utente di cancellare parti di un tratto, il modo in cui un utente può su un oggetto <xref:System.Windows.Controls.InkCanvas> quando <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> è impostato su <xref:System.Windows.Controls.InkCanvasEditingMode.EraseByPoint> .</span><span class="sxs-lookup"><span data-stu-id="b0b41-104">This is useful for creating a control that enables a user to erase parts of a stroke, the way a user can on an <xref:System.Windows.Controls.InkCanvas> when the <xref:System.Windows.Controls.InkCanvas.EditingMode%2A> is set to <xref:System.Windows.Controls.InkCanvasEditingMode.EraseByPoint>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b0b41-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="b0b41-105">Example</span></span>  
 <span data-ttu-id="b0b41-106">Nell'esempio seguente viene creato un controllo personalizzato che consente all'utente di cancellare parti di tratti.</span><span class="sxs-lookup"><span data-stu-id="b0b41-106">The following example creates a custom control that enables the user to erase parts of strokes.</span></span>  <span data-ttu-id="b0b41-107">In questo esempio viene creato un controllo che contiene input penna quando viene inizializzato.</span><span class="sxs-lookup"><span data-stu-id="b0b41-107">This example creates a control that contains ink when it is initialized.</span></span>  <span data-ttu-id="b0b41-108">Per creare un controllo che raccolga l'input penna, vedere [creazione di un controllo input penna](creating-an-ink-input-control.md).</span><span class="sxs-lookup"><span data-stu-id="b0b41-108">To create a control that collects ink, see [Creating an Ink Input Control](creating-an-ink-input-control.md).</span></span>  
  
 [!code-csharp[HowToEraseInk#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToEraseInk/CSharp/InkEraser.cs#1)]
 [!code-vb[HowToEraseInk#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToEraseInk/VisualBasic/InkEraser.vb#1)]
