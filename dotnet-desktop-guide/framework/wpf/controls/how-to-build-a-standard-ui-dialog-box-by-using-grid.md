---
title: "Procedura: compilare una finestra di dialogo standard dell'interfaccia utente utilizzando l'elemento Grid"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dialog boxes [WPF], creating
- Grid control [WPF], creating [WPF], dialog box
ms.assetid: d6ac3d51-844b-4d29-96d8-81a696a7b960
ms.openlocfilehash: 442d69f891d53365653c01ef4dca296398ae7195
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969523"
---
# <a name="how-to-build-a-standard-ui-dialog-box-by-using-grid"></a>Procedura: compilare una finestra di dialogo standard dell'interfaccia utente utilizzando l'elemento Grid
Questo esempio illustra come creare una finestra [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] di dialogo standard usando l' <xref:System.Windows.Controls.Grid> elemento.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene creata una finestra di dialogo come la finestra di dialogo **Esegui** nel sistema operativo Windows.  
  
 Nell'esempio viene creato un oggetto <xref:System.Windows.Controls.Grid> e vengono utilizzate le <xref:System.Windows.Controls.ColumnDefinition> <xref:System.Windows.Controls.RowDefinition> classi e per definire cinque colonne e quattro righe.  
  
 Nell'esempio viene quindi aggiunto e posizionato un oggetto <xref:System.Windows.Controls.Image> , `RunIcon.png` , per rappresentare l'immagine presente nella finestra di dialogo. L'immagine viene posizionata nella prima colonna e nella prima riga di <xref:System.Windows.Controls.Grid> (angolo superiore sinistro).  
  
 Successivamente, nell'esempio viene aggiunto un <xref:System.Windows.Controls.TextBlock> elemento alla prima colonna, che si estende sulle colonne rimanenti della prima riga. Aggiunge un altro <xref:System.Windows.Controls.TextBlock> elemento alla seconda riga della prima colonna, per rappresentare la casella di testo **aperta** . <xref:System.Windows.Controls.TextBlock>Segue, che rappresenta l'area di immissione dati.  
  
 Infine, nell'esempio vengono aggiunti tre <xref:System.Windows.Controls.Button> elementi alla riga finale, che rappresentano gli eventi **OK**, **Cancel** e **Browse** .  
  
 [!code-csharp[GridRunDialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.GridUnitType>
- [Cenni preliminari sugli elementi Panel](panels-overview.md)
- [Procedure](grid-how-to-topics.md)
