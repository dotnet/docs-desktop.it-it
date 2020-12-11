---
title: 'Procedura: Usare elementi di contenuto dinamico'
ms.date: 03/30/2017
helpviewer_keywords:
- flow content elements [WPF]
- documents [WPF], flow content elements
ms.assetid: 70fa11cd-5fa7-4872-a1cc-04d80f1132be
ms.openlocfilehash: f61116c0bf52ac726238d9e21c2422cedbb4716f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963712"
---
# <a name="how-to-use-flow-content-elements"></a><span data-ttu-id="fbe79-102">Procedura: Usare elementi di contenuto dinamico</span><span class="sxs-lookup"><span data-stu-id="fbe79-102">How to: Use Flow Content Elements</span></span>
<span data-ttu-id="fbe79-103">L'esempio seguente illustra l'uso dichiarativo di vari elementi di contenuto dinamico degli attributi associati.</span><span class="sxs-lookup"><span data-stu-id="fbe79-103">The following example demonstrates declarative usage for various flow content elements and associated attributes.</span></span>  <span data-ttu-id="fbe79-104">Gli elementi e gli attributi illustrati includono:</span><span class="sxs-lookup"><span data-stu-id="fbe79-104">Elements and attributes demonstrated include:</span></span>  
  
- <span data-ttu-id="fbe79-105">Elemento <xref:System.Windows.Documents.Bold></span><span class="sxs-lookup"><span data-stu-id="fbe79-105"><xref:System.Windows.Documents.Bold> element</span></span>  
  
- <span data-ttu-id="fbe79-106">Attributo <xref:System.Windows.Documents.Block.BreakPageBefore%2A></span><span class="sxs-lookup"><span data-stu-id="fbe79-106"><xref:System.Windows.Documents.Block.BreakPageBefore%2A> attribute</span></span>  
  
- <span data-ttu-id="fbe79-107">Attributo <xref:System.Windows.Documents.TextElement.FontSize%2A></span><span class="sxs-lookup"><span data-stu-id="fbe79-107"><xref:System.Windows.Documents.TextElement.FontSize%2A> attribute</span></span>  
  
- <span data-ttu-id="fbe79-108">Elemento <xref:System.Windows.Documents.Italic></span><span class="sxs-lookup"><span data-stu-id="fbe79-108"><xref:System.Windows.Documents.Italic> element</span></span>  
  
- <span data-ttu-id="fbe79-109">Elemento <xref:System.Windows.Documents.LineBreak></span><span class="sxs-lookup"><span data-stu-id="fbe79-109"><xref:System.Windows.Documents.LineBreak> element</span></span>  
  
- <span data-ttu-id="fbe79-110">Elemento <xref:System.Windows.Documents.List></span><span class="sxs-lookup"><span data-stu-id="fbe79-110"><xref:System.Windows.Documents.List> element</span></span>  
  
- <span data-ttu-id="fbe79-111">Elemento <xref:System.Windows.Documents.ListItem></span><span class="sxs-lookup"><span data-stu-id="fbe79-111"><xref:System.Windows.Documents.ListItem> element</span></span>  
  
- <span data-ttu-id="fbe79-112">Elemento <xref:System.Windows.Documents.Paragraph></span><span class="sxs-lookup"><span data-stu-id="fbe79-112"><xref:System.Windows.Documents.Paragraph> element</span></span>  
  
- <span data-ttu-id="fbe79-113">Elemento <xref:System.Windows.Documents.Run></span><span class="sxs-lookup"><span data-stu-id="fbe79-113"><xref:System.Windows.Documents.Run> element</span></span>  
  
- <span data-ttu-id="fbe79-114">Elemento <xref:System.Windows.Documents.Section></span><span class="sxs-lookup"><span data-stu-id="fbe79-114"><xref:System.Windows.Documents.Section> element</span></span>  
  
- <span data-ttu-id="fbe79-115">Elemento <xref:System.Windows.Documents.Span></span><span class="sxs-lookup"><span data-stu-id="fbe79-115"><xref:System.Windows.Documents.Span> element</span></span>  
  
- <span data-ttu-id="fbe79-116"><xref:System.Windows.Documents.Typography.Variants%2A> attributo (apice e pedice)</span><span class="sxs-lookup"><span data-stu-id="fbe79-116"><xref:System.Windows.Documents.Typography.Variants%2A> attribute (superscript and subscript)</span></span>  
  
- <span data-ttu-id="fbe79-117">Elemento <xref:System.Windows.Documents.Underline></span><span class="sxs-lookup"><span data-stu-id="fbe79-117"><xref:System.Windows.Documents.Underline> element</span></span>  
  
## <a name="example"></a><span data-ttu-id="fbe79-118">Esempio</span><span class="sxs-lookup"><span data-stu-id="fbe79-118">Example</span></span>  
 [!code-xaml[FlowDocInlineSnippets#_InlineElementsXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocInlineSnippets/CS/document.xaml#_inlineelementsxaml)]
