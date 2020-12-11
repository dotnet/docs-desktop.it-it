---
title: 'Procedura: Estendere un controllo su righe e colonne in un controllo TableLayoutPanel'
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.StyleCollectionEditor.TLP.SpanRowsColumns
helpviewer_keywords:
- columns [Windows Forms], spanning
- merging cells
- TableLayoutPanel control [Windows Forms], spanning rows and columns
- rows [Windows Forms], spanning
- cells [Windows Forms], merging
ms.assetid: a8a2fdd3-a848-48b0-a4cd-4e85ebded87e
ms.openlocfilehash: a215b2b4e05bab5c81d2779d4b67d5b9d57b6ba5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965164"
---
# <a name="how-to-span-rows-and-columns-in-a-tablelayoutpanel-control"></a>Procedura: Estendere un controllo su righe e colonne in un controllo TableLayoutPanel
I controlli in un controllo possono estendersi su <xref:System.Windows.Forms.TableLayoutPanel> righe e colonne adiacenti.

## <a name="to-span-columns-and-rows"></a>Per estendere le colonne e le righe

1. Trascinare un controllo <xref:System.Windows.Forms.TableLayoutPanel> dalla **Casella degli strumenti** al form.

2. Trascinare un <xref:System.Windows.Forms.Button> controllo dalla **casella degli strumenti** nella cella superiore sinistra del <xref:System.Windows.Forms.TableLayoutPanel> controllo.

3. Impostare la <xref:System.Windows.Forms.Button> proprietà **ColumnSpan** del controllo su **2**. Si noti che il <xref:System.Windows.Forms.Button> controllo si estende sulla prima e sulla seconda colonna.

4. Impostare la <xref:System.Windows.Forms.Button> proprietà **RowSpan** del controllo su **2**. Si noti che il <xref:System.Windows.Forms.Button> controllo si estende sulla prima e sulla seconda riga.

5. Impostare la <xref:System.Windows.Forms.Button> proprietà **ColumnSpan** del controllo su **1**. Si noti che il <xref:System.Windows.Forms.Button> controllo viene spostato nella prima colonna e si estende alla prima e alla seconda riga.

## <a name="see-also"></a>Vedere anche

- [Controllo TableLayoutPanel](tablelayoutpanel-control-windows-forms.md)
