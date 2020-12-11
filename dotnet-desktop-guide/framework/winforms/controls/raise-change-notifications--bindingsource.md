---
title: "Procedura: Generare notifiche di modifica usando BindingSource e l'interfaccia INotifyPropertyChanged"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- change notifications [Windows Forms], raising
- BindingSource component [Windows Forms], and IPropertyChange
- data sources [Windows Forms], detecting changes
- examples [Windows Forms], BindingSource component
- change notifications
- INotifyPropertyChanged interface [Windows Forms], using with BindingSource
- BindingSource component [Windows Forms], examples
ms.assetid: 7fa2cf51-c09f-4375-adf0-e36c5617f099
ms.openlocfilehash: cd8c3fba87fd5ab9acf9159fc1130ee28ed38497
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965899"
---
# <a name="how-to-raise-change-notifications-using-a-bindingsource-and-the-inotifypropertychanged-interface"></a>Procedura: Generare notifiche di modifica usando BindingSource e l'interfaccia INotifyPropertyChanged

Il <xref:System.Windows.Forms.BindingSource> componente rileva automaticamente le modifiche in un'origine dati quando il tipo contenuto nell'origine dati implementa <xref:System.ComponentModel.INotifyPropertyChanged> e genera <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> eventi quando viene modificato un valore della proprietà. Questo rilevamento delle modifiche è utile perché i controlli associati all' <xref:System.Windows.Forms.BindingSource> aggiornamento automatico quando cambiano i valori dell'origine dati.  
  
> [!NOTE]
> Se l'origine dati implementa <xref:System.ComponentModel.INotifyPropertyChanged> e devono essere eseguite operazioni asincrone, non devono essere apportate modifiche all'origine dati in un thread in background. In alternativa, è possibile leggere i dati in un thread in background e quindi unire i dati in un elenco nel thread dell'interfaccia utente.  
  
## <a name="example"></a>Esempio  

 Nell'esempio di codice riportato di seguito viene illustrata una semplice implementazione dell'interfaccia <xref:System.ComponentModel.INotifyPropertyChanged>. Viene inoltre descritto il modo in cui il componente <xref:System.Windows.Forms.BindingSource> passa automaticamente una modifica dell'origine dati a un controllo associato quando <xref:System.Windows.Forms.BindingSource> è associato a un elenco di tipo <xref:System.ComponentModel.INotifyPropertyChanged>.  
  
 Se si utilizza l'attributo `CallerMemberName`, le chiamate al metodo `NotifyPropertyChanged` non devono specificare il nome della proprietà come argomento di tipo stringa. Per ulteriori informazioni, vedere [informazioni sul chiamante (C#)](/dotnet/csharp/language-reference/attributes/caller-information) o [informazioni sul chiamante (Visual Basic)](/dotnet/visual-basic/programming-guide/concepts/caller-information).  
  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  

 L'esempio presenta i requisiti seguenti:  
  
- Riferimenti agli assembly System, System. Data, System. Drawing e System. Windows. Forms.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ComponentModel.INotifyPropertyChanged>
- [Componente BindingSource](bindingsource-component.md)
- [Procedura: Generare notifiche di modifica usando il metodo ResetItem di BindingSource](how-to-raise-change-notifications-using-the-bindingsource-resetitem-method.md)
