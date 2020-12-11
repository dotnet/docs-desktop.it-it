---
title: 'Procedura: Usare una griglia per il layout automatico'
ms.date: 03/30/2017
helpviewer_keywords:
- grids [WPF], automatic layout
- automatic layout [WPF], grid use
ms.assetid: ab9de407-e0c1-4047-bdf0-24951bf73879
ms.openlocfilehash: 5389d8d6130367d36a5c81b3bdc316c989474ce2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963739"
---
# <a name="how-to-use-a-grid-for-automatic-layout"></a><span data-ttu-id="b4ae5-102">Procedura: Usare una griglia per il layout automatico</span><span class="sxs-lookup"><span data-stu-id="b4ae5-102">How to: Use a Grid for Automatic Layout</span></span>
<span data-ttu-id="b4ae5-103">Questo esempio descrive come usare una griglia nell'approccio basato sul layout automatico per la creazione di un'applicazione localizzabile.</span><span class="sxs-lookup"><span data-stu-id="b4ae5-103">This example describes how to use a grid in the automatic layout approach to creating a localizable application.</span></span>  
  
 <span data-ttu-id="b4ae5-104">La localizzazione di un [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] può essere un processo che richiede molto tempo.</span><span class="sxs-lookup"><span data-stu-id="b4ae5-104">Localization of a [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] can be a time consuming process.</span></span> <span data-ttu-id="b4ae5-105">Spesso sono necessari il ridimensionamento e il riposizionamento degli elementi, oltre alla traduzione del testo.</span><span class="sxs-lookup"><span data-stu-id="b4ae5-105">Often localizers need to re-size and reposition elements in addition to translating text.</span></span> <span data-ttu-id="b4ae5-106">In passato ogni lingua [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] era adatta per la regolazione richiesta.</span><span class="sxs-lookup"><span data-stu-id="b4ae5-106">In the past each language that a [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] was adapted for required adjustment.</span></span> <span data-ttu-id="b4ae5-107">Ora con le funzionalità di [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] è possibile progettare elementi che riducono la necessità di regolazione.</span><span class="sxs-lookup"><span data-stu-id="b4ae5-107">Now with the capabilities of [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] you can design elements that reduce the need for adjustment.</span></span> <span data-ttu-id="b4ae5-108">Viene chiamato l'approccio alla scrittura di applicazioni che possono essere ridimensionate e riposizionate più facilmente `auto layout` .</span><span class="sxs-lookup"><span data-stu-id="b4ae5-108">The approach to writing applications that can be more easily re-sized and repositioned is called `auto layout`.</span></span>  
  
 <span data-ttu-id="b4ae5-109">Nell' [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] esempio seguente viene illustrato l'utilizzo di una griglia per posizionare alcuni pulsanti e testo.</span><span class="sxs-lookup"><span data-stu-id="b4ae5-109">The following [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] example demonstrates using a grid to position some buttons and text.</span></span> <span data-ttu-id="b4ae5-110">Si noti che l'altezza e la larghezza delle celle sono impostate su `Auto` ; pertanto, la cella che contiene il pulsante con un'immagine viene modificata in modo da adattarsi all'immagine.</span><span class="sxs-lookup"><span data-stu-id="b4ae5-110">Notice that the height and width of the cells are set to `Auto`; therefore the cell that contains the button with an image adjusts to fit the image.</span></span> <span data-ttu-id="b4ae5-111">Poiché l' <xref:System.Windows.Controls.Grid> elemento può adattarsi al contenuto, può essere utile quando si adotta l'approccio di layout automatico per la progettazione di applicazioni che possono essere localizzate.</span><span class="sxs-lookup"><span data-stu-id="b4ae5-111">Because the <xref:System.Windows.Controls.Grid> element can adjust to its content it can be useful when taking the automatic layout approach to designing applications that can be localized.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4ae5-112">Esempio</span><span class="sxs-lookup"><span data-stu-id="b4ae5-112">Example</span></span>  
 <span data-ttu-id="b4ae5-113">Nell'esempio riportato di seguito viene illustrato come usare una griglia.</span><span class="sxs-lookup"><span data-stu-id="b4ae5-113">The following example shows how to use a grid.</span></span>  
  
 [!code-xaml[LocalizationGrid#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]  
  
 <span data-ttu-id="b4ae5-114">La figura seguente mostra l'output dell'esempio di codice.</span><span class="sxs-lookup"><span data-stu-id="b4ae5-114">The following graphic shows the output of the code sample.</span></span>  
  
 <span data-ttu-id="b4ae5-115">![Esempio di Grid](./media/glob-grid.png "glob_grid")</span><span class="sxs-lookup"><span data-stu-id="b4ae5-115">![Grid example](./media/glob-grid.png "glob_grid")</span></span>  
<span data-ttu-id="b4ae5-116">Pannello Grid</span><span class="sxs-lookup"><span data-stu-id="b4ae5-116">Grid</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4ae5-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b4ae5-117">See also</span></span>

- [<span data-ttu-id="b4ae5-118">Cenni preliminari sull'utilizzo del layout automatico</span><span class="sxs-lookup"><span data-stu-id="b4ae5-118">Use Automatic Layout Overview</span></span>](use-automatic-layout-overview.md)
- [<span data-ttu-id="b4ae5-119">Usare il layout automatico per creare un pulsante</span><span class="sxs-lookup"><span data-stu-id="b4ae5-119">Use Automatic Layout to Create a Button</span></span>](how-to-use-automatic-layout-to-create-a-button.md)
