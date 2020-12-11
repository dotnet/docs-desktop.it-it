---
title: "Procedura: gestire l'evento MouseDoubleClick per ciascun elemento di ListView"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ListView controls [WPF], MouseDoubleClick event
ms.assetid: 81b39369-655a-4585-ac58-4640e5bb8fed
ms.openlocfilehash: 58c17697c5053be267893834e8364c531c1db4de
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968518"
---
# <a name="how-to-handle-the-mousedoubleclick-event-for-each-item-in-a-listview"></a>Procedura: gestire l'evento MouseDoubleClick per ciascun elemento di ListView
Per gestire un evento per un elemento in un oggetto <xref:System.Windows.Controls.ListView> , è necessario aggiungere un gestore eventi a ognuno di essi <xref:System.Windows.Controls.ListViewItem> . Quando un oggetto <xref:System.Windows.Controls.ListView> è associato a un'origine dati, non si crea in modo esplicito un oggetto <xref:System.Windows.Controls.ListViewItem> , ma è possibile gestire l'evento per ogni elemento aggiungendo un oggetto <xref:System.Windows.EventSetter> a uno stile di un oggetto <xref:System.Windows.Controls.ListViewItem> .  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene creato un oggetto con associazione <xref:System.Windows.Controls.ListView> a dati e viene creato un oggetto <xref:System.Windows.Style> per aggiungere un gestore eventi a ognuno di essi <xref:System.Windows.Controls.ListViewItem> .  
  
 [!code-xaml[ListViewHowTos#1](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#1)]  
[!code-xaml[ListViewHowTos#5](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#5)]  
[!code-xaml[ListViewHowTos#2](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml#2)]  
  
 Nell'esempio seguente viene gestito l' <xref:System.Windows.Controls.Control.MouseDoubleClick> evento.  
  
 [!code-csharp[ListViewHowTos#6](~/samples/snippets/csharp/VS_Snippets_Wpf/ListViewHowTos/CSharp/Window1.xaml.cs#6)]
 [!code-vb[ListViewHowTos#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ListViewHowTos/VisualBasic/Window1.xaml.vb#6)]  
  
> [!NOTE]
> Sebbene sia più comune associare un oggetto <xref:System.Windows.Controls.ListView> a un'origine dati, è possibile utilizzare uno stile per aggiungere un gestore eventi a ogni oggetto <xref:System.Windows.Controls.ListViewItem> in un non associato a dati <xref:System.Windows.Controls.ListView> indipendentemente dal fatto che si crei in modo esplicito un oggetto <xref:System.Windows.Controls.ListViewItem> .  Per ulteriori informazioni sui controlli creati in modo esplicito e implicito <xref:System.Windows.Controls.ListViewItem> , vedere <xref:System.Windows.Controls.ItemsControl> .  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Xml.XmlElement>
- [Panoramica sul data binding](/dotnet/desktop-wpf/data/data-binding-overview)
- [Applicazione di stili e modelli](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
- [Eseguire l'associazione a dati XML tramite un oggetto XMLDataProvider e query XPath](../data/how-to-bind-to-xml-data-using-an-xmldataprovider-and-xpath-queries.md)
- [Panoramica sul controllo ListView](listview-overview.md)
