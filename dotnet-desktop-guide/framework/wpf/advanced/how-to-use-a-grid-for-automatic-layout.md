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
# <a name="how-to-use-a-grid-for-automatic-layout"></a>Procedura: Usare una griglia per il layout automatico
Questo esempio descrive come usare una griglia nell'approccio basato sul layout automatico per la creazione di un'applicazione localizzabile.  
  
 La localizzazione di un [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] può essere un processo che richiede molto tempo. Spesso sono necessari il ridimensionamento e il riposizionamento degli elementi, oltre alla traduzione del testo. In passato ogni lingua [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] era adatta per la regolazione richiesta. Ora con le funzionalità di [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] è possibile progettare elementi che riducono la necessità di regolazione. Viene chiamato l'approccio alla scrittura di applicazioni che possono essere ridimensionate e riposizionate più facilmente `auto layout` .  
  
 Nell' [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] esempio seguente viene illustrato l'utilizzo di una griglia per posizionare alcuni pulsanti e testo. Si noti che l'altezza e la larghezza delle celle sono impostate su `Auto` ; pertanto, la cella che contiene il pulsante con un'immagine viene modificata in modo da adattarsi all'immagine. Poiché l' <xref:System.Windows.Controls.Grid> elemento può adattarsi al contenuto, può essere utile quando si adotta l'approccio di layout automatico per la progettazione di applicazioni che possono essere localizzate.  
  
## <a name="example"></a>Esempio  
 Nell'esempio riportato di seguito viene illustrato come usare una griglia.  
  
 [!code-xaml[LocalizationGrid#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationGrid/CS/Pane1.xaml#1)]  
  
 La figura seguente mostra l'output dell'esempio di codice.  
  
 ![Esempio di Grid](./media/glob-grid.png "glob_grid")  
Pannello Grid  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'utilizzo del layout automatico](use-automatic-layout-overview.md)
- [Usare il layout automatico per creare un pulsante](how-to-use-automatic-layout-to-create-a-button.md)
