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
# <a name="how-to-raise-change-notifications-using-a-bindingsource-and-the-inotifypropertychanged-interface"></a><span data-ttu-id="0d2d5-102">Procedura: Generare notifiche di modifica usando BindingSource e l'interfaccia INotifyPropertyChanged</span><span class="sxs-lookup"><span data-stu-id="0d2d5-102">How to: Raise Change Notifications Using a BindingSource and the INotifyPropertyChanged Interface</span></span>

<span data-ttu-id="0d2d5-103">Il <xref:System.Windows.Forms.BindingSource> componente rileva automaticamente le modifiche in un'origine dati quando il tipo contenuto nell'origine dati implementa <xref:System.ComponentModel.INotifyPropertyChanged> e genera <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> eventi quando viene modificato un valore della proprietà.</span><span class="sxs-lookup"><span data-stu-id="0d2d5-103">The <xref:System.Windows.Forms.BindingSource> component automatically detects changes in a data source when the type contained in the data source implements <xref:System.ComponentModel.INotifyPropertyChanged> and raises <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> events when a property value is changed.</span></span> <span data-ttu-id="0d2d5-104">Questo rilevamento delle modifiche è utile perché i controlli associati all' <xref:System.Windows.Forms.BindingSource> aggiornamento automatico quando cambiano i valori dell'origine dati.</span><span class="sxs-lookup"><span data-stu-id="0d2d5-104">This change detection is useful because controls bound to the <xref:System.Windows.Forms.BindingSource> automatically update as the data source values change.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0d2d5-105">Se l'origine dati implementa <xref:System.ComponentModel.INotifyPropertyChanged> e devono essere eseguite operazioni asincrone, non devono essere apportate modifiche all'origine dati in un thread in background.</span><span class="sxs-lookup"><span data-stu-id="0d2d5-105">If your data source implements <xref:System.ComponentModel.INotifyPropertyChanged> and you are performing asynchronous operations, you should not make changes to the data source on a background thread.</span></span> <span data-ttu-id="0d2d5-106">In alternativa, è possibile leggere i dati in un thread in background e quindi unire i dati in un elenco nel thread dell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="0d2d5-106">Instead, you should read the data on a background thread and merge the data into a list on the UI thread.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d2d5-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="0d2d5-107">Example</span></span>  

 <span data-ttu-id="0d2d5-108">Nell'esempio di codice riportato di seguito viene illustrata una semplice implementazione dell'interfaccia <xref:System.ComponentModel.INotifyPropertyChanged>.</span><span class="sxs-lookup"><span data-stu-id="0d2d5-108">The following code example demonstrates a simple implementation of the <xref:System.ComponentModel.INotifyPropertyChanged> interface.</span></span> <span data-ttu-id="0d2d5-109">Viene inoltre descritto il modo in cui il componente <xref:System.Windows.Forms.BindingSource> passa automaticamente una modifica dell'origine dati a un controllo associato quando <xref:System.Windows.Forms.BindingSource> è associato a un elenco di tipo <xref:System.ComponentModel.INotifyPropertyChanged>.</span><span class="sxs-lookup"><span data-stu-id="0d2d5-109">It also shows how the <xref:System.Windows.Forms.BindingSource> automatically passes a data source change to a bound control when the <xref:System.Windows.Forms.BindingSource> is bound to a list of the <xref:System.ComponentModel.INotifyPropertyChanged> type.</span></span>  
  
 <span data-ttu-id="0d2d5-110">Se si utilizza l'attributo `CallerMemberName`, le chiamate al metodo `NotifyPropertyChanged` non devono specificare il nome della proprietà come argomento di tipo stringa.</span><span class="sxs-lookup"><span data-stu-id="0d2d5-110">If you use the `CallerMemberName` attribute, calls to the `NotifyPropertyChanged` method don't have to specify the property name as a string argument.</span></span> <span data-ttu-id="0d2d5-111">Per ulteriori informazioni, vedere [informazioni sul chiamante (C#)](/dotnet/csharp/language-reference/attributes/caller-information) o [informazioni sul chiamante (Visual Basic)](/dotnet/visual-basic/programming-guide/concepts/caller-information).</span><span class="sxs-lookup"><span data-stu-id="0d2d5-111">For more information, see [Caller Information (C#)](/dotnet/csharp/language-reference/attributes/caller-information) or [Caller Information (Visual Basic)](/dotnet/visual-basic/programming-guide/concepts/caller-information).</span></span>  
  
 [!code-csharp[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/CS/Form1.cs#1)]
 [!code-vb[System.ComponentModel.IPropertyChangeExample#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.ComponentModel.IPropertyChangeExample/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="0d2d5-112">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="0d2d5-112">Compiling the Code</span></span>  

 <span data-ttu-id="0d2d5-113">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="0d2d5-113">This example requires:</span></span>  
  
- <span data-ttu-id="0d2d5-114">Riferimenti agli assembly System, System. Data, System. Drawing e System. Windows. Forms.</span><span class="sxs-lookup"><span data-stu-id="0d2d5-114">References to the System, System.Data, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d2d5-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0d2d5-115">See also</span></span>

- <xref:System.ComponentModel.INotifyPropertyChanged>
- [<span data-ttu-id="0d2d5-116">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="0d2d5-116">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="0d2d5-117">Procedura: Generare notifiche di modifica usando il metodo ResetItem di BindingSource</span><span class="sxs-lookup"><span data-stu-id="0d2d5-117">How to: Raise Change Notifications Using the BindingSource ResetItem Method</span></span>](how-to-raise-change-notifications-using-the-bindingsource-resetitem-method.md)
