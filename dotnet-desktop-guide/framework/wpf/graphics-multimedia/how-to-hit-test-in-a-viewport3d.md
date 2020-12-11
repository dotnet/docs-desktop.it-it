---
title: 'Procedura: eseguire un hit test in un oggetto Viewport3D'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- 3D visuals [WPF], hit-testing for
- hit tests [WPF], for 3D visuals
- Viewport3D [WPF]
ms.assetid: 42bfbd99-c7c6-43f1-940b-90448faa412e
ms.openlocfilehash: 34bc86349332293e40aca5743cbabb2a48634da6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965266"
---
# <a name="how-to-hit-test-in-a-viewport3d"></a>Procedura: eseguire un hit test in un oggetto Viewport3D

Questo esempio illustra come eseguire un hit test per gli oggetti visivi 3D in un oggetto <xref:System.Windows.Controls.Viewport3D> .

Poiché <xref:System.Windows.Media.VisualTreeHelper.HitTest%2A> restituisce informazioni 2D e 3D, è possibile scorrere i risultati dei test per leggere solo i risultati 3D.

[!code-csharp[HitTest3D#HitTest3D3DN4](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml.cs#hittest3d3dn4)]
[!code-vb[HitTest3D#HitTest3D3DN4](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTest3D/visualbasic/window1.xaml.vb#hittest3d3dn4)]

Nell' <xref:System.Windows.Media.HitTestResultBehavior> esempio di codice seguente viene determinata la modalità di elaborazione dei risultati dell'hit test. `UpdateResultInfo` e `UpdateMaterial` sono metodi definiti localmente.

[!code-csharp[HitTest3D#HitTest3D3DN5](~/samples/snippets/csharp/VS_Snippets_Wpf/HitTest3D/CSharp/Window1.xaml.cs#hittest3d3dn5)]
[!code-vb[HitTest3D#HitTest3D3DN5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HitTest3D/visualbasic/window1.xaml.vb#hittest3d3dn5)]
