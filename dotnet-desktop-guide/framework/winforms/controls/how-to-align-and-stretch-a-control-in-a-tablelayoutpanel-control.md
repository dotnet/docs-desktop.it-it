---
title: 'Procedura: Allineare ed estendere un controllo in un controllo TableLayoutPanel'
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.AlignStretchCtrl
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms], stretching controls
- controls [Windows Forms], stretching
- controls [Windows Forms], aligning
ms.assetid: 7dc1a157-6fee-4995-8ebc-b65bdc0909a8
ms.openlocfilehash: fd32593bcad9e3f3ef93edee8aa2659d423f9feb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964006"
---
# <a name="how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control"></a>Procedura: Allineare ed estendere un controllo in un controllo TableLayoutPanel

È possibile allineare ed estendere i controlli in un oggetto <xref:System.Windows.Forms.TableLayoutPanel> con le <xref:System.Windows.Forms.Control.Anchor%2A> <xref:System.Windows.Forms.Control.Dock%2A> proprietà e.

## <a name="align-and-stretch-a-control"></a>Allineare ed estendere un controllo

1. In Visual Studio trascinare un <xref:System.Windows.Forms.TableLayoutPanel> controllo dalla **casella degli strumenti** nel form.

2. Trascinare un <xref:System.Windows.Forms.Button> controllo dalla **casella degli strumenti** nella cella superiore sinistra del <xref:System.Windows.Forms.TableLayoutPanel> controllo. Il <xref:System.Windows.Forms.Button> controllo viene centrato nella cella.

3. Impostare il valore della <xref:System.Windows.Forms.Button> proprietà del controllo <xref:System.Windows.Forms.Control.Anchor%2A> su `Left,Right` . Il <xref:System.Windows.Forms.Button> controllo si estende in base alla larghezza della cella.

4. Impostare il valore della <xref:System.Windows.Forms.Button> proprietà del controllo <xref:System.Windows.Forms.Control.Anchor%2A> su `Top,Bottom` . Il <xref:System.Windows.Forms.Button> controllo si estende in modo da corrispondere all'altezza della cella.

5. Impostare il valore della <xref:System.Windows.Forms.Button> proprietà del controllo <xref:System.Windows.Forms.Control.Dock%2A> su <xref:System.Windows.Forms.DockStyle.Fill> . Il <xref:System.Windows.Forms.Button> controllo si espande per riempire la cella.

6. Impostare il valore della <xref:System.Windows.Forms.Button> proprietà del controllo <xref:System.Windows.Forms.Control.Dock%2A> su <xref:System.Windows.Forms.DockStyle.None> . Il <xref:System.Windows.Forms.Button> controllo torna alle dimensioni originali e passa all'angolo superiore sinistro della cella. Il **Progettazione Windows Form** ha impostato la <xref:System.Windows.Forms.Control.Anchor%2A> proprietà su `Top, Left` .

7. Impostare il valore della <xref:System.Windows.Forms.Button> proprietà del controllo <xref:System.Windows.Forms.Control.Anchor%2A> su `Bottom,Right` . Il <xref:System.Windows.Forms.Button> controllo viene spostato nell'angolo inferiore destro della cella.

8. Impostare il valore della <xref:System.Windows.Forms.Button> proprietà del controllo <xref:System.Windows.Forms.Control.Anchor%2A> su <xref:System.Windows.Forms.AnchorStyles.None> . Il <xref:System.Windows.Forms.Button> controllo viene spostato al centro della cella.

## <a name="see-also"></a>Vedere anche

- [Controllo TableLayoutPanel](tablelayoutpanel-control-windows-forms.md)
