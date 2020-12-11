---
title: 'Procedura: specificare la direzione di associazione'
ms.date: 03/30/2017
helpviewer_keywords:
- direction of binding [WPF]
- binding direction [WPF]
- data binding [WPF], direction of binding
ms.assetid: 37334478-028b-4514-86c9-1420709f4818
ms.openlocfilehash: 6b3c6afde5e9fa1b778905b1a278bb295b6cbf11
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964561"
---
# <a name="how-to-specify-the-direction-of-the-binding"></a>Procedura: specificare la direzione dell'associazione

Questo esempio spiega come specificare se il binding aggiorna solo la proprietà della destinazione del binding (destinazione), dell'origine del binding (origine) o entrambe.  
  
## <a name="example"></a>Esempio  
 Utilizzare la <xref:System.Windows.Data.Binding.Mode%2A?displayProperty=nameWithType> proprietà per specificare la direzione del binding. Di seguito sono riportate le opzioni disponibili per gli aggiornamenti di binding:  
  
- <xref:System.Windows.Data.BindingMode.TwoWay?displayProperty=nameWithType> Aggiorna la proprietà di destinazione o la proprietà ogni volta che la proprietà di destinazione o la proprietà di origine viene modificata.  
  
- <xref:System.Windows.Data.BindingMode.OneWay?displayProperty=nameWithType> Aggiorna la proprietà di destinazione solo quando la proprietà di origine viene modificata.  
  
- <xref:System.Windows.Data.BindingMode.OneTime?displayProperty=nameWithType> Aggiorna la proprietà di destinazione solo quando l'applicazione viene avviata o quando <xref:System.Windows.FrameworkElement.DataContext%2A> subisce una modifica.  
  
- <xref:System.Windows.Data.BindingMode.OneWayToSource?displayProperty=nameWithType> Aggiorna la proprietà di origine quando viene modificata la proprietà di destinazione.  
  
- <xref:System.Windows.Data.BindingMode.Default?displayProperty=nameWithType> determina l' <xref:System.Windows.Data.Binding.Mode%2A> utilizzo del valore predefinito della proprietà target.  
  
 Per altre informazioni, vedere l'enumerazione <xref:System.Windows.Data.BindingMode>.  
  
 Nell'esempio seguente viene illustrato come impostare la proprietà <xref:System.Windows.Data.Binding.Mode%2A>.  
  
 [!code-xaml[DirectionalBinding#4](~/samples/snippets/csharp/VS_Snippets_Wpf/DirectionalBinding/CSharp/Page1.xaml#4)]  
  
 Per rilevare le modifiche apportate all'origine (applicabili alle <xref:System.Windows.Data.BindingMode.OneWay> <xref:System.Windows.Data.BindingMode.TwoWay> associazioni e), l'origine deve implementare un meccanismo appropriato di notifica delle modifiche alle proprietà, ad esempio <xref:System.ComponentModel.INotifyPropertyChanged> . Per un esempio di implementazione, vedere [implementare una notifica di modifica delle proprietà](how-to-implement-property-change-notification.md) <xref:System.ComponentModel.INotifyPropertyChanged> .  
  
 Per <xref:System.Windows.Data.BindingMode.TwoWay> le <xref:System.Windows.Data.BindingMode.OneWayToSource> associazioni o, è possibile controllare l'intervallo degli aggiornamenti di origine impostando la <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A> Proprietà. Per altre informazioni, vedere <xref:System.Windows.Data.Binding.UpdateSourceTrigger%2A>.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Data.Binding>
- [Panoramica sul data binding](/dotnet/desktop-wpf/data/data-binding-overview)
- [Procedure](data-binding-how-to-topics.md)
