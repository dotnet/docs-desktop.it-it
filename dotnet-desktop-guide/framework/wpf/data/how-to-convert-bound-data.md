---
title: 'Procedura: convertire i dati associati'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- converting [WPF], bound data
- data binding [WPF], converting bound data
- binding data [WPF], converting bound data
ms.assetid: b00aaa19-c6df-4c3b-a9fd-88a0b488df2b
ms.openlocfilehash: 981994426afd173fa8560d3ee24c6cf24c0c24aa
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966622"
---
# <a name="how-to-convert-bound-data"></a>Procedura: convertire i dati associati
In questo esempio viene illustrato come applicare la conversione ai dati utilizzati nelle associazioni.  
  
 Per convertire i dati durante l'associazione, è necessario creare una classe che implementi l' <xref:System.Windows.Data.IValueConverter> interfaccia, che include i <xref:System.Windows.Data.IValueConverter.Convert%2A> <xref:System.Windows.Data.IValueConverter.ConvertBack%2A> metodi e.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrata l'implementazione di un convertitore di data che converte il valore di data passato in modo da visualizzare solo l'anno, il mese e il giorno. Quando si implementa l' <xref:System.Windows.Data.IValueConverter> interfaccia, è consigliabile decorare l'implementazione con un <xref:System.Windows.Data.ValueConversionAttribute> attributo per indicare agli strumenti di sviluppo i tipi di dati implicati nella conversione, come nell'esempio seguente:  
  
 [!code-csharp[DataBindingLab#18](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DateConverter.cs#18)]
 [!code-vb[DataBindingLab#18](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/DateConverter.vb#18)]  
  
 Una volta creato un convertitore, è possibile aggiungerlo come risorsa nel [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] file. Nell'esempio seguente *src* esegue il mapping allo spazio dei nomi in cui è definito *DateConverter* .  
  
 [!code-xaml[DataBindingLab#15](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#15)]  
  
 Infine, è possibile usare il convertitore nell'associazione usando la sintassi seguente. Nell'esempio seguente il contenuto di testo di <xref:System.Windows.Controls.TextBlock> è associato a *StartDate*, che è una proprietà di un'origine dati esterna.  
  
 [!code-xaml[DataBindingLab#17](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/DataBindingLabApp.xaml#17)]  
  
 Le risorse di stile a cui viene fatto riferimento nell'esempio precedente sono definite in una sezione delle risorse non illustrata in questo argomento.  
  
## <a name="see-also"></a>Vedere anche

- [Implementare la convalida dell'associazione](how-to-implement-binding-validation.md)
- [Panoramica sul data binding](/dotnet/desktop-wpf/data/data-binding-overview)
- [Procedure](data-binding-how-to-topics.md)
