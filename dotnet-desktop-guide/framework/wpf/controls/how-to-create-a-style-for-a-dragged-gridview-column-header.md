---
title: "Procedura: creare uno stile per un'intestazione di colonna GridView trascinata"
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], styling
ms.assetid: 0b999645-0313-4b33-80b9-19ece08b5459
ms.openlocfilehash: dbcdd38e0397b8e637aff962420a2959f33203df
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968128"
---
# <a name="how-to-create-a-style-for-a-dragged-gridview-column-header"></a>Procedura: creare uno stile per un'intestazione di colonna GridView trascinata
In questo esempio viene illustrato come modificare l'aspetto di un oggetto trascinato <xref:System.Windows.Controls.GridViewColumnHeader> quando l'utente modifica la posizione di una colonna.  
  
## <a name="example"></a>Esempio  
 Quando si trascina un'intestazione di colonna in un'altra posizione in un oggetto <xref:System.Windows.Controls.ListView> che utilizza <xref:System.Windows.Controls.GridView> per la modalità di visualizzazione, la colonna viene spostata nella nuova posizione. Quando si trascina l'intestazione di colonna, viene visualizzata una copia mobile dell'intestazione, oltre all'intestazione originale. Un'intestazione di colonna in un <xref:System.Windows.Controls.GridView> è rappresentata da un <xref:System.Windows.Controls.GridViewColumnHeader> oggetto.  
  
 Per personalizzare l'aspetto delle intestazioni mobili e originali, è possibile impostare <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> per modificare l'oggetto <xref:System.Windows.Controls.GridViewColumnHeader> <xref:System.Windows.Style> . Queste <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> vengono applicate quando il <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> valore della proprietà è `true` e il <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> valore della proprietà è <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating> .  
  
 Quando l'utente preme il pulsante del mouse e lo tiene premuto mentre il mouse si posiziona su <xref:System.Windows.Controls.GridViewColumnHeader> , il <xref:System.Windows.Controls.Primitives.ButtonBase.IsPressed%2A> valore della proprietà viene modificato in `true` . Analogamente, quando l'utente inizia l'operazione di trascinamento, la <xref:System.Windows.Controls.GridViewColumnHeader.Role%2A> proprietà viene modificata in <xref:System.Windows.Controls.GridViewColumnHeaderRole.Floating> .  
  
 Nell'esempio seguente viene illustrato come impostare <xref:System.Windows.Controls.ControlTemplate.Triggers%2A> per modificare i <xref:System.Windows.Controls.Control.Foreground%2A> <xref:System.Windows.Controls.Control.Background%2A> colori e delle intestazioni originali e mobili quando l'utente trascina una colonna in una nuova posizione.  
  
 [!code-xaml[ListViewHeaderRoleStyle#GVCHControlTemplateStart](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#gvchcontroltemplatestart)]  
[!code-xaml[ListViewHeaderRoleStyle#ControlTemplateTriggersStart](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#controltemplatetriggersstart)]  
[!code-xaml[ListViewHeaderRoleStyle#IsPressed](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#ispressed)]  
[!code-xaml[ListViewHeaderRoleStyle#Floating](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#floating)]  
[!code-xaml[ListViewHeaderRoleStyle#ControlTemplateTriggersEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#controltemplatetriggersend)]  
[!code-xaml[ListViewHeaderRoleStyle#GVCHControlTemplateEnd](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHeaderRoleStyle/CS/Window1.xaml#gvchcontroltemplateend)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.GridViewColumnHeader>
- <xref:System.Windows.Controls.GridViewColumnHeaderRole>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [Procedure](listview-how-to-topics.md)
- [Panoramica sul controllo ListView](listview-overview.md)
- [Cenni preliminari su GridView](gridview-overview.md)
