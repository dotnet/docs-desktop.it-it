---
title: 'Procedura: implementare notifiche di modifiche alle proprietà'
description: Abilitare le proprietà per notificare automaticamente un'origine di binding quando il valore della proprietà viene modificato in Windows Presentation Foundation (WPF).
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- notifications of change [WPF]
- data binding [WPF], property change notifications
- change notifications [WPF]
- properties [WPF], change notifications
ms.assetid: 30b59d9e-8c3a-4349-aa82-4be837e841cf
ms.openlocfilehash: f3cf3fe211e852fccaa605623820ebbde7e62917
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968248"
---
# <a name="how-to-implement-property-change-notification"></a>Procedura: implementare notifiche di modifiche alle proprietà
Per supportare <xref:System.Windows.Data.BindingMode.OneWay> o <xref:System.Windows.Data.BindingMode.TwoWay> associare per consentire alle proprietà della destinazione del binding di riflettere automaticamente le modifiche dinamiche dell'origine del binding, ad esempio per fare in modo che il riquadro di anteprima venga aggiornato automaticamente quando l'utente modifica un modulo, la classe deve fornire le notifiche appropriate per la modifica delle proprietà. Questo esempio illustra come creare una classe che implementa <xref:System.ComponentModel.INotifyPropertyChanged> .  
  
## <a name="example"></a>Esempio  
 Per implementare <xref:System.ComponentModel.INotifyPropertyChanged> è necessario dichiarare l' <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> evento e creare il `OnPropertyChanged` metodo. Quindi, per ogni proprietà per cui si desidera ricevere notifiche per le modifiche, chiamare `OnPropertyChanged` ogni volta che la proprietà viene aggiornata.  
  
 [!code-csharp[SimpleBinding#PersonClass](~/samples/snippets/csharp/VS_Snippets_Wpf/SimpleBinding/CSharp/Person.cs#personclass)]
 [!code-vb[SimpleBinding#PersonClass](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SimpleBinding/VisualBasic/Person.vb#personclass)]  
  
 Per un esempio di come `Person` è possibile usare la classe per supportare l' <xref:System.Windows.Data.BindingMode.TwoWay> associazione, vedere [controllo quando il testo della casella di testo aggiorna l'origine](how-to-control-when-the-textbox-text-updates-the-source.md).  
  
## <a name="see-also"></a>Vedere anche

- [Cenni preliminari sulle origini del binding](binding-sources-overview.md)
- [Panoramica sul data binding](/dotnet/desktop-wpf/data/data-binding-overview)
- [Procedure](data-binding-how-to-topics.md)
