---
title: DatePicker
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], DatePicker
- DatePicker control [WPF]
ms.assetid: 619765c8-8d25-4315-aec2-79aea08fed9f
ms.openlocfilehash: 4e4b536aca768872a0729a9b34a5dc1cc17e04fb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967540"
---
# <a name="datepicker"></a>DatePicker
Il <xref:System.Windows.Controls.DatePicker> controllo consente all'utente di selezionare una data digitando l'oggetto in un campo di testo o utilizzando un controllo a discesa <xref:System.Windows.Controls.Calendar> .  
  
 La figura seguente mostra un <xref:System.Windows.Controls.DatePicker> .  
  
 ![Controllo DatePicker](./media/ndp-datepicker.png "NDP_DatePicker")  
Controllo DatePicker  
  
 Molte delle proprietà di un <xref:System.Windows.Controls.DatePicker> controllo sono per la gestione della relativa incorporata <xref:System.Windows.Controls.Calendar> e funzionano in modo identico alla proprietà equivalente in <xref:System.Windows.Controls.Calendar> . In particolare, le <xref:System.Windows.Controls.DatePicker.IsTodayHighlighted%2A?displayProperty=nameWithType> <xref:System.Windows.Controls.DatePicker.FirstDayOfWeek%2A?displayProperty=nameWithType> proprietà,, <xref:System.Windows.Controls.DatePicker.BlackoutDates%2A?displayProperty=nameWithType> , <xref:System.Windows.Controls.DatePicker.DisplayDateStart%2A?displayProperty=nameWithType> , <xref:System.Windows.Controls.DatePicker.DisplayDateEnd%2A?displayProperty=nameWithType> , <xref:System.Windows.Controls.DatePicker.DisplayDate%2A?displayProperty=nameWithType> e <xref:System.Windows.Controls.DatePicker.SelectedDate%2A?displayProperty=nameWithType> funzionano in modo identico alle rispettive <xref:System.Windows.Controls.Calendar> controparti. Per altre informazioni, vedere <xref:System.Windows.Controls.Calendar>.  
  
 Gli utenti possono digitare una data direttamente in un campo di testo, che imposta la <xref:System.Windows.Controls.DatePicker.Text%2A> Proprietà. Se <xref:System.Windows.Controls.DatePicker> non è in grado di convertire la stringa immessa in una data valida, <xref:System.Windows.Controls.DatePicker.DateValidationError> verrà generato l'evento. Per impostazione predefinita, questo genera un'eccezione, ma un gestore eventi per <xref:System.Windows.Controls.DatePicker.DateValidationError> può impostare la <xref:System.Windows.Controls.DatePickerDateValidationErrorEventArgs.ThrowException%2A> proprietà su `false` e impedire che venga generata un'eccezione.  
  
## <a name="see-also"></a>Vedere anche

- [Controlli](index.md)
- [Applicazione di stili e modelli](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
