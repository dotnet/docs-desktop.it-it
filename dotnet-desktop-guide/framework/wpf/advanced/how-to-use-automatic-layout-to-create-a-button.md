---
title: 'Procedura: Usare un layout automatico per creare un pulsante'
ms.date: 03/30/2017
helpviewer_keywords:
- Button controls [WPF], creating with automatic layout
- automatic layout [WPF], creating buttons
ms.assetid: 96c206d0-9e77-4784-9d2d-5045aed2021c
ms.openlocfilehash: 05b874f9894841d3c318ee131d15165111fd596a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963718"
---
# <a name="how-to-use-automatic-layout-to-create-a-button"></a>Procedura: Usare un layout automatico per creare un pulsante
Questo esempio descrive come usare un approccio basato sul layout automatico per la creazione di un pulsante in un'applicazione localizzabile.  
  
 La localizzazione di un [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] può essere un processo che richiede molto tempo. Spesso sono necessari il ridimensionamento e il riposizionamento degli elementi, oltre alla traduzione del testo. In passato ogni lingua [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] era adatta per la regolazione richiesta. Ora con le funzionalità di [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)] è possibile progettare elementi che riducono la necessità di regolazione. Viene chiamato l'approccio alla scrittura di applicazioni che possono essere ridimensionate e riposizionate più facilmente `automatic layout` .  
  
## <a name="example"></a>Esempio  

Nei due esempi seguenti vengono [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] create applicazioni che creano un'istanza di un pulsante, una con testo in lingua inglese e una con testo in spagnolo. Il codice è lo stesso ad eccezione del testo. Il pulsante si regola per adattarsi al testo.

[!code-xaml[LocalizationBtn_snip#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn_snip/CS/Pane1.xaml#1)]  
  
[!code-xaml[LocalizationBtn#1](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationBtn/CS/Pane1.xaml#1)]  
  
 Il grafico seguente mostra l'output degli esempi di codice con i pulsanti di ridimensionamento automatico:
  
 ![Lo stesso pulsante con testo in lingue diverse](./media/use-automatic-layout-overview/auto-resizable-button.png)  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sull'utilizzo del layout automatico](use-automatic-layout-overview.md)
- [Utilizzare una griglia per il layout automatico](how-to-use-a-grid-for-automatic-layout.md)
