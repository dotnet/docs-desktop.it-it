---
title: Panoramica del controllo MonthCalendar
ms.date: 03/30/2017
f1_keywords:
- MonthCalendar
helpviewer_keywords:
- calendars [Windows Forms], Windows Forms controls
- calendar controls [Windows Forms], Windows Forms
- MonthCalendar control [Windows Forms], setting the first day of the week
ms.assetid: 788c5325-b721-44ec-95bf-9b680ba0f6a2
ms.openlocfilehash: a9b56164339d03b380a564b21855f6d94ec06af5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965038"
---
# <a name="monthcalendar-control-overview-windows-forms"></a>Cenni preliminari sul controllo MonthCalendar (Windows Form)
Il <xref:System.Windows.Forms.MonthCalendar> controllo Windows Forms presenta un'interfaccia grafica intuitiva che consente agli utenti di visualizzare e impostare le informazioni sulla data. Il controllo Visualizza un calendario: una griglia contenente i giorni del mese numerati, disposti in colonne sotto i giorni della settimana, con l'intervallo di date selezionato evidenziato. È possibile selezionare un mese diverso facendo clic sui pulsanti freccia su entrambi i lati della didascalia del mese. A differenza del <xref:System.Windows.Forms.DateTimePicker> controllo simile, è possibile selezionare più di una data con il controllo. Per ulteriori informazioni sul <xref:System.Windows.Forms.DateTimePicker> controllo, vedere [controllo DateTimePicker](datetimepicker-control-windows-forms.md).  
  
## <a name="configuring-the-monthcalendar-control"></a>Configurazione del controllo MonthCalendar  
 L' <xref:System.Windows.Forms.MonthCalendar> aspetto del controllo è altamente configurabile. Per impostazione predefinita, la data odierna viene visualizzata come cerchio ed è nota anche nella parte inferiore della griglia. È possibile modificare questa funzionalità impostando le <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> <xref:System.Windows.Forms.MonthCalendar.ShowTodayCircle%2A> proprietà e su `false` . È inoltre possibile aggiungere numeri settimanali al calendario impostando la <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> proprietà su `true` . Impostando la <xref:System.Windows.Forms.MonthCalendar.CalendarDimensions%2A> proprietà, è possibile visualizzare più mesi orizzontalmente e verticalmente. Per impostazione predefinita, la domenica viene visualizzata come primo giorno della settimana, ma è possibile designare qualsiasi giorno utilizzando la <xref:System.Windows.Forms.MonthCalendar.FirstDayOfWeek%2A> Proprietà.  
  
 È inoltre possibile impostare determinate date da visualizzare in grassetto in base a una sola volta, annualmente o mensilmente, aggiungendo <xref:System.DateTime> oggetti alle <xref:System.Windows.Forms.MonthCalendar.BoldedDates%2A> <xref:System.Windows.Forms.MonthCalendar.AnnuallyBoldedDates%2A> proprietà, e <xref:System.Windows.Forms.MonthCalendar.MonthlyBoldedDates%2A> . Per altre informazioni, vedere [procedura: visualizzare giorni specifici in grassetto con il Windows Forms controllo MonthCalendar](display-specific-days-in-bold-with-wf-monthcalendar-control.md).  
  
 La proprietà chiave del <xref:System.Windows.Forms.MonthCalendar> controllo è <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A> , l'intervallo di date selezionato nel controllo. Il <xref:System.Windows.Forms.MonthCalendar.SelectionRange%2A> valore non può superare il numero massimo di giorni che è possibile selezionare, impostare nella <xref:System.Windows.Forms.MonthCalendar.MaxSelectionCount%2A> Proprietà. Le date meno recenti e più recenti che l'utente può selezionare sono determinate <xref:System.Windows.Forms.MonthCalendar.MaxDate%2A> dalle <xref:System.Windows.Forms.MonthCalendar.MinDate%2A> proprietà e.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.MonthCalendar>
- [Controllo MonthCalendar](monthcalendar-control-windows-forms.md)
