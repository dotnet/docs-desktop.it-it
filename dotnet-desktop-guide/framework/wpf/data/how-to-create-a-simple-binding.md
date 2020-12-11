---
title: 'Procedura: creare associazioni semplici'
description: Consente di creare un binding semplice per le applicazioni tramite questo esempio di procedura in Windows Presentation Foundation (WPF).
ms.date: 03/30/2017
helpviewer_keywords:
- simple binding [WPF], creating
- data binding [WPF], creating simple bindings
- binding data [WPF], creating
ms.assetid: 69b80f72-6259-44cb-8294-5bdcebca1e08
ms.openlocfilehash: 9649116427c7da805323270fe3a23e6b23d330a5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966616"
---
# <a name="how-to-create-a-simple-binding"></a>Procedura: creare associazioni semplici
Questo esempio illustra come creare un semplice <xref:System.Windows.Data.Binding> .  
  
## <a name="example"></a>Esempio  
 In questo esempio è presente un `Person` oggetto con una proprietà stringa denominata `PersonName` . L' `Person` oggetto è definito nello spazio dei nomi denominato `SDKSample` .  
  
 La riga evidenziata che contiene l' `<src>` elemento nell'esempio seguente crea un'istanza dell' `Person` oggetto con un `PersonName` valore della proprietà `Joe` . Questa operazione viene eseguita nella `Resources` sezione ed è stata assegnata una `x:Key` .  
  
 [!code-xaml[SimpleBinding](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Page1.xaml?highlight=9,37)]  
  
 La riga evidenziata che contiene l' `<TextBlock>` elemento associa quindi il <xref:System.Windows.Controls.TextBlock> controllo alla `PersonName` Proprietà. Di conseguenza, <xref:System.Windows.Controls.TextBlock> viene visualizzato con il valore "Joe".  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica sul data binding](/dotnet/desktop-wpf/data/data-binding-overview)
- [Procedure](data-binding-how-to-topics.md)
