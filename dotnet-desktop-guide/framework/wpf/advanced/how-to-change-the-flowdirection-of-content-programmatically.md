---
title: 'Procedura: Cambiare la proprietà FlowDirection del contenuto a livello di codice'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- FlowDirection property [WPF], changing programmatically
- documents [WPF], changing FlowDirection property programmatically
ms.assetid: 02f5a8ba-f8c0-4e5a-84b9-4c5bf12922a2
ms.openlocfilehash: ec159ed0efce8b5514788331e8715a55e7a8a638
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965797"
---
# <a name="how-to-change-the-flowdirection-of-content-programmatically"></a><span data-ttu-id="37668-102">Procedura: Cambiare la proprietà FlowDirection del contenuto a livello di codice</span><span class="sxs-lookup"><span data-stu-id="37668-102">How to: Change the FlowDirection of Content Programmatically</span></span>
<span data-ttu-id="37668-103">In questo esempio viene illustrato come modificare a livello <xref:System.Windows.FrameworkElement.FlowDirection%2A> di codice la proprietà di un oggetto <xref:System.Windows.Controls.FlowDocumentReader> .</span><span class="sxs-lookup"><span data-stu-id="37668-103">This example shows how to programmatically change the <xref:System.Windows.FrameworkElement.FlowDirection%2A> property of a <xref:System.Windows.Controls.FlowDocumentReader>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="37668-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="37668-104">Example</span></span>  
 <span data-ttu-id="37668-105"><xref:System.Windows.Controls.Button>Vengono creati due elementi, ognuno dei quali rappresenta uno dei valori possibili di <xref:System.Windows.FlowDirection> .</span><span class="sxs-lookup"><span data-stu-id="37668-105">Two <xref:System.Windows.Controls.Button> elements are created, each representing one of the possible values of <xref:System.Windows.FlowDirection>.</span></span> <span data-ttu-id="37668-106">Quando si fa clic su un pulsante, il valore della proprietà associata viene applicato al contenuto di un oggetto <xref:System.Windows.Controls.FlowDocumentReader> denominato `tf1` .</span><span class="sxs-lookup"><span data-stu-id="37668-106">When a button is clicked, the associated property value is applied to the contents of a <xref:System.Windows.Controls.FlowDocumentReader> named `tf1`.</span></span>  <span data-ttu-id="37668-107">Il valore della proprietà viene scritto anche in un oggetto <xref:System.Windows.Controls.TextBlock> denominato `txt1` .</span><span class="sxs-lookup"><span data-stu-id="37668-107">The property value is also written to a <xref:System.Windows.Controls.TextBlock> named `txt1`.</span></span>  
  
 [!code-xaml[FlowDirectionSnippets#_FlowDirectionXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDirectionSnippets/CSharp/Window1.xaml#_flowdirectionxaml)]  
  
## <a name="example"></a><span data-ttu-id="37668-108">Esempio</span><span class="sxs-lookup"><span data-stu-id="37668-108">Example</span></span>  
 <span data-ttu-id="37668-109">Gli eventi associati ai clic sui pulsanti definiti in precedenza vengono gestiti in un file code-behind C#.</span><span class="sxs-lookup"><span data-stu-id="37668-109">The events associated with the button clicks defined above are handled in a C# code-behind file.</span></span>  
  
 [!code-csharp[FlowDirectionSnippets#_FlowDirection](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDirectionSnippets/CSharp/Window1.xaml.cs#_flowdirection)]
 [!code-vb[FlowDirectionSnippets#_FlowDirection](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDirectionSnippets/VisualBasic/Window1.xaml.vb#_flowdirection)]
