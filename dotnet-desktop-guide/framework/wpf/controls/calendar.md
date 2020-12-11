---
title: Calendario
ms.date: 03/30/2017
helpviewer_keywords:
- controls [WPF], Calendar
- Calendar control [WPF]
ms.assetid: ee844e4a-eefe-48e2-bd0d-1d82cc5e960b
ms.openlocfilehash: c06cd34739dd25f717a5ea2cbc9803453558a400
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967159"
---
# <a name="calendar"></a>Calendario
Un calendario consente a un utente di selezionare una data tramite la visualizzazione di un calendario visivo.  
  
 Un <xref:System.Windows.Controls.Calendar> controllo può essere utilizzato autonomamente o come parte a discesa di un <xref:System.Windows.Controls.DatePicker> controllo. Per altre informazioni, vedere <xref:System.Windows.Controls.DatePicker>.  
  
 Nella figura seguente sono illustrati due <xref:System.Windows.Controls.Calendar> controlli, uno con selezioni e date di blackout e uno senza.  
  
 ![Controlli del calendario](./media/ndp-calendarcontrols.png "NDP_CalendarControls")  
Controlli del calendario  
  
 Nella tabella seguente vengono fornite informazioni sulle attività generalmente associate a <xref:System.Windows.Controls.Calendar> .  
  
|Attività|Implementazione|  
|----------|--------------------|  
|Specificare le date che non possono essere selezionate.|Usare la proprietà <xref:System.Windows.Controls.Calendar.BlackoutDates%2A>.|  
|<xref:System.Windows.Controls.Calendar>Visualizza un mese, un anno intero o un decennio.|Impostare la <xref:System.Windows.Controls.Calendar.DisplayMode%2A> proprietà su month, year o decade.|  
|Specificare se l'utente può selezionare una data, un intervallo di date o più intervalli di date.|Utilizzare la <xref:System.Windows.Controls.Calendar.SelectionMode%2A>.|  
|Specificare l'intervallo di date visualizzato dall'oggetto <xref:System.Windows.Controls.Calendar> .|Usare le <xref:System.Windows.Controls.Calendar.DisplayDateStart%2A> <xref:System.Windows.Controls.Calendar.DisplayDateEnd%2A> proprietà e.|  
|Consente di specificare se la data corrente è evidenziata.|Usare la proprietà <xref:System.Windows.Controls.Calendar.IsTodayHighlighted%2A>. Per impostazione predefinita, <xref:System.Windows.Controls.Calendar.IsTodayHighlighted%2A> è `true` .|  
|Modificare le dimensioni di <xref:System.Windows.Controls.Calendar> .|Usare <xref:System.Windows.Controls.Viewbox> o impostare la <xref:System.Windows.FrameworkElement.LayoutTransform%2A> proprietà su un oggetto <xref:System.Windows.Media.ScaleTransform> . Si noti che se si impostano le <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> proprietà e di un oggetto <xref:System.Windows.Controls.Calendar> , il calendario effettivo non ne modifica le dimensioni.|  
  
 Il <xref:System.Windows.Controls.Calendar> controllo fornisce la navigazione di base utilizzando il mouse o la tastiera. Nella tabella seguente viene riepilogata la navigazione da tastiera.  
  
|Combinazione di tasti|<xref:System.Windows.Controls.Calendar.DisplayMode%2A>|Azione|  
|---------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|------------|  
|FRECCIA|<xref:System.Windows.Controls.CalendarMode.Month>|Modifica la <xref:System.Windows.Controls.Calendar.SelectedDate%2A> proprietà se la <xref:System.Windows.Controls.Calendar.SelectionMode%2A> proprietà non è impostata su <xref:System.Windows.Controls.CalendarSelectionMode.None> .|  
|FRECCIA|<xref:System.Windows.Controls.CalendarMode.Year>|Modifica il mese della <xref:System.Windows.Controls.Calendar.DisplayDate%2A> Proprietà. Si noti che non <xref:System.Windows.Controls.Calendar.SelectedDate%2A> Cambia.|  
|FRECCIA|<xref:System.Windows.Controls.CalendarMode.Decade>|Modifica l'anno dell'oggetto <xref:System.Windows.Controls.Calendar.DisplayDate%2A> . Si noti che non <xref:System.Windows.Controls.Calendar.SelectedDate%2A> Cambia.|  
|MAIUSC + freccia|<xref:System.Windows.Controls.CalendarMode.Month>|Se <xref:System.Windows.Controls.Calendar.SelectionMode%2A> non è impostato su <xref:System.Windows.Controls.CalendarSelectionMode.SingleDate> o <xref:System.Windows.Controls.CalendarSelectionMode.None> , estende l'intervallo di date selezionate.|  
|HOME|<xref:System.Windows.Controls.CalendarMode.Month>|Imposta il <xref:System.Windows.Controls.Calendar.SelectedDate%2A> primo giorno del mese corrente.|  
|HOME|<xref:System.Windows.Controls.CalendarMode.Year>|Imposta il mese di sul <xref:System.Windows.Controls.Calendar.DisplayDate%2A> primo mese dell'anno. Non <xref:System.Windows.Controls.Calendar.SelectedDate%2A> Cambia.|  
|HOME|<xref:System.Windows.Controls.CalendarMode.Decade>|Modifica l'anno del nel <xref:System.Windows.Controls.Calendar.DisplayDate%2A> primo anno del decennio. Non <xref:System.Windows.Controls.Calendar.SelectedDate%2A> Cambia.|  
|FINE|<xref:System.Windows.Controls.CalendarMode.Month>|Modifica l'oggetto nell' <xref:System.Windows.Controls.Calendar.SelectedDate%2A> ultimo giorno del mese corrente.|  
|FINE|<xref:System.Windows.Controls.CalendarMode.Year>|Modifica il mese di nell' <xref:System.Windows.Controls.Calendar.DisplayDate%2A> ultimo mese dell'anno. Non <xref:System.Windows.Controls.Calendar.SelectedDate%2A> Cambia.|  
|FINE|<xref:System.Windows.Controls.CalendarMode.Decade>|Modifica l'anno di nell' <xref:System.Windows.Controls.Calendar.DisplayDate%2A> ultimo anno del decennio. Non <xref:System.Windows.Controls.Calendar.SelectedDate%2A> Cambia.|  
|CTRL+freccia SU|Qualsiasi|Passa al più grande successivo <xref:System.Windows.Controls.Calendar.DisplayMode%2A> . Se <xref:System.Windows.Controls.Calendar.DisplayMode%2A> è già <xref:System.Windows.Controls.CalendarMode.Decade> , non viene eseguita alcuna azione.|  
|CTRL+freccia GIÙ|Qualsiasi|Passa al più piccolo successivo <xref:System.Windows.Controls.Calendar.DisplayMode%2A> . Se <xref:System.Windows.Controls.Calendar.DisplayMode%2A> è già <xref:System.Windows.Controls.CalendarMode.Month> , non viene eseguita alcuna azione.|  
|BARRA SPAZIAtrice o invio|<xref:System.Windows.Controls.CalendarMode.Year> o <xref:System.Windows.Controls.CalendarMode.Decade>|Passa <xref:System.Windows.Controls.Calendar.DisplayMode%2A> alla <xref:System.Windows.Controls.CalendarMode.Month> o <xref:System.Windows.Controls.CalendarMode.Year> rappresentata dall'elemento con lo stato attivo.|  
  
## <a name="see-also"></a>Vedere anche

- [Controlli](index.md)
- [Applicazione di stili e modelli](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
