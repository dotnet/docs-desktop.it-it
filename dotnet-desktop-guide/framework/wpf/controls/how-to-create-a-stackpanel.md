---
title: 'Procedura: creare uno StackPanel'
ms.date: 03/30/2017
helpviewer_keywords:
- StackPanel control [WPF], creating
ms.assetid: e7ce65cb-720a-4bb6-95b6-286b74488a58
ms.openlocfilehash: bcf6decff2fbc012b5f8b62794f0d7b2cd9f29fc
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968137"
---
# <a name="how-to-create-a-stackpanel"></a>Procedura: creare uno StackPanel
Questo esempio illustra come creare un oggetto <xref:System.Windows.Controls.StackPanel> .  
  
## <a name="example"></a>Esempio  
 Un oggetto <xref:System.Windows.Controls.StackPanel> consente di impilare gli elementi in una direzione specificata. Utilizzando le proprietà definite in <xref:System.Windows.Controls.StackPanel> , il contenuto può essere propagato verticalmente, ovvero l'impostazione predefinita, o orizzontalmente.  
  
 Nell'esempio seguente vengono impilati verticalmente cinque <xref:System.Windows.Controls.TextBlock> controlli, ognuno con un oggetto diverso <xref:System.Windows.Controls.Border> <xref:System.Windows.Controls.Border.Background%2A> da e, tramite <xref:System.Windows.Controls.StackPanel> . Gli elementi figlio che non dispongono <xref:System.Windows.FrameworkElement.Width%2A> di un'estensione specificata per riempire la finestra padre. Tuttavia, gli elementi figlio con un oggetto specificato <xref:System.Windows.FrameworkElement.Width%2A> vengono centrati all'interno della finestra.  
  
 La direzione predefinita dello stack in un <xref:System.Windows.Controls.StackPanel> è verticale. Per controllare il flusso del contenuto in un oggetto <xref:System.Windows.Controls.StackPanel> , usare la <xref:System.Windows.Controls.StackPanel.Orientation%2A> Proprietà. È possibile controllare l'allineamento orizzontale usando la <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> Proprietà.  
  
```xaml  
<Page xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation" WindowTitle="StackPanel Sample">  
  <StackPanel>  
    <Border Background="SkyBlue" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="12">Stacked Item #1</TextBlock>  
    </Border>  
    <Border Width="400" Background="CadetBlue" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="14">Stacked Item #2</TextBlock>  
    </Border>  
    <Border Background="LightGoldenRodYellow" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="16">Stacked Item #3</TextBlock>  
    </Border>  
    <Border Width="200" Background="PaleGreen" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="18">Stacked Item #4</TextBlock>  
    </Border>  
    <Border Background="White" BorderBrush="Black" BorderThickness="1">  
      <TextBlock Foreground="Black" FontSize="20">Stacked Item #5</TextBlock>  
    </Border>  
  </StackPanel>  
</Page>  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.StackPanel>
- [Cenni preliminari sugli elementi Panel](panels-overview.md)
- [Procedure](stackpanel-how-to-topics.md)
