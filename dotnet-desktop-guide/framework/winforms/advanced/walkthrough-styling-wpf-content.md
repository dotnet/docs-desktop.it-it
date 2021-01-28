---
title: 'Procedura dettagliata: stile contenuto WPF'
ms.date: 03/30/2017
helpviewer_keywords:
- WPF Designer [Windows Forms], styling WPF content
- interoperability [WDF]
- styles [Windows Forms], WPF content
ms.assetid: e574aac7-7ea4-4cdb-8034-bab541f000df
ms.openlocfilehash: f7acec4edb31dba0aa014943dde7f758fe8e4575
ms.sourcegitcommit: 7f48b9ecf8a30db42c8ecea0dd4df577736631a2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2021
ms.locfileid: "98957396"
---
# <a name="walkthrough-style-wpf-content"></a>Procedura dettagliata: stile contenuto WPF

Questo articolo illustra come applicare lo stile a un controllo Windows Presentation Foundation (WPF) ospitato in un Windows Form.

## <a name="prerequisites"></a>Prerequisiti

Per completare la procedura dettagliata, è necessario Visual Studio.

## <a name="create-the-project"></a>Creare il progetto

Aprire Visual Studio e creare un nuovo progetto di applicazione Windows Form in Visual Basic o Visual C# denominato `StylingWpfContent` .

> [!NOTE]
> Con il contenuto WPF sono supportati solo progetti C# e Visual Basic.

## <a name="create-the-wpf-control-types"></a>Creare i tipi di controllo WPF

Dopo avere aggiunto un tipo di controllo WPF al progetto, è possibile inserirlo in un controllo <xref:System.Windows.Forms.Integration.ElementHost>.

1. Aggiungere un nuovo progetto WPF <xref:System.Windows.Controls.UserControl> alla soluzione. Usare il nome predefinito per il tipo di controllo, `UserControl1.xaml`. Per ulteriori informazioni, vedere [procedura dettagliata: creazione di nuovi contenuti WPF in Windows Form in fase di progettazione](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).

2. In visualizzazione Progettazione verificare che `UserControl1` sia selezionato.

3. Nella finestra **Proprietà** impostare il valore delle <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> proprietà e su **200**.

4. Aggiungere un <xref:System.Windows.Controls.Button?displayProperty=nameWithType> controllo a <xref:System.Windows.Controls.UserControl> e impostare il valore della <xref:System.Windows.Controls.ContentControl.Content%2A> proprietà su **Cancel**.

5. Aggiungere un secondo <xref:System.Windows.Controls.Button?displayProperty=nameWithType> controllo a <xref:System.Windows.Controls.UserControl> e impostare il valore della <xref:System.Windows.Controls.ContentControl.Content%2A> proprietà su **OK**.

6. Compilare il progetto.

## <a name="apply-a-style-to-a-wpf-control"></a>Applicare uno stile a un controllo WPF

È possibile applicare uno stile diverso a un controllo WPF per modificarne l'aspetto e il comportamento.

1. Aprire `Form1` in Progettazione Windows Form.

1. Nella **casella degli strumenti** fare doppio clic su `UserControl1` per creare un'istanza di `UserControl1` nel form.

   L'istanza di `UserControl1` viene inclusa in un nuovo controllo <xref:System.Windows.Forms.Integration.ElementHost> denominato `elementHost1`.

1. Nel pannello smart tag per `elementHost1` fare clic su **modifica contenuto ospitato** nell'elenco a discesa.

   `UserControl1` viene aperto in WPF Designer.

1. Nella visualizzazione XAML inserire il seguente codice XAML dopo il tag di apertura `<UserControl>`. Questo codice XAML crea una sfumatura con un bordo sfumato a contrasto. Quando si fa clic sul controllo, le sfumature vengono modificate per generare l'aspetto di un pulsante premuto. Per altre informazioni, vedere [Applicazione di stili e modelli](/dotnet/desktop-wpf/fundamentals/styles-templates-overview).

   ```xaml
   <UserControl.Resources>
    <LinearGradientBrush x:Key="NormalBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#FFF" Offset="0.0"/>
        <GradientStop Color="#CCC" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="PressedBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#BBB" Offset="0.0"/>
        <GradientStop Color="#EEE" Offset="0.1"/>
        <GradientStop Color="#EEE" Offset="0.9"/>
        <GradientStop Color="#FFF" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="NormalBorderBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#CCC" Offset="0.0"/>
        <GradientStop Color="#444" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="BorderBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#CCC" Offset="0.0"/>
        <GradientStop Color="#444" Offset="1.0"/>
    </LinearGradientBrush>
    <LinearGradientBrush x:Key="PressedBorderBrush" EndPoint="0,1" StartPoint="0,0">
        <GradientStop Color="#444" Offset="0.0"/>
        <GradientStop Color="#888" Offset="1.0"/>
    </LinearGradientBrush>

    <Style x:Key="SimpleButton" TargetType="{x:Type Button}" BasedOn="{x:Null}">
        <Setter Property="Background" Value="{StaticResource NormalBrush}"/>
        <Setter Property="BorderBrush" Value="{StaticResource NormalBorderBrush}"/>
        <Setter Property="Template">
            <Setter.Value>
                <ControlTemplate TargetType="{x:Type Button}">
                    <Grid x:Name="Grid">
                        <Border x:Name="Border" Background="{TemplateBinding Background}" BorderBrush="{TemplateBinding BorderBrush}" BorderThickness="{TemplateBinding BorderThickness}" Padding="{TemplateBinding Padding}"/>
                        <ContentPresenter HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}" Margin="{TemplateBinding Padding}" VerticalAlignment="{TemplateBinding VerticalContentAlignment}" RecognizesAccessKey="True"/>
                    </Grid>
                    <ControlTemplate.Triggers>
                        <Trigger Property="IsPressed" Value="true">
                            <Setter Property="Background" Value="{StaticResource PressedBrush}" TargetName="Border"/>
                            <Setter Property="BorderBrush" Value="{StaticResource PressedBorderBrush}" TargetName="Border"/>
                        </Trigger>
                    </ControlTemplate.Triggers>
                </ControlTemplate>
            </Setter.Value>
        </Setter>
    </Style>
   </UserControl.Resources>
   ```

1. Applicare lo `SimpleButton` stile definito nel passaggio precedente al pulsante Annulla inserendo il codice XAML seguente nel `<Button>` tag del pulsante **Annulla** .

   ```xaml
   Style="{StaticResource SimpleButton}
   ```

   La dichiarazione di un pulsante sarà simile al codice XAML seguente:

   ```xaml
   <Button Height="23" Margin="41,52,98,0" Name="button1" VerticalAlignment="Top"
                Style="{StaticResource SimpleButton}">Cancel</Button>
   ```

1. Compilare il progetto.

1. Aprire `Form1` in Progettazione Windows Form.

1. Il nuovo stile viene applicato al pulsante.

1. Scegliere **Avvia debug** dal menu **debug** per eseguire l'applicazione.

1. Fare clic sui pulsanti **OK** e **Annulla** e visualizzare le differenze.

## <a name="see-also"></a>Vedi anche

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Migrazione e interoperabilità](/dotnet/framework/wpf/advanced/migration-and-interoperability)
- [Utilizzo di controlli WPF](using-wpf-controls.md)
- [Progettare XAML in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
- [Panoramica di XAML (WPF)](/dotnet/desktop-wpf/fundamentals/xaml)
- [Applicazione di stili e modelli](/dotnet/desktop-wpf/fundamentals/styles-templates-overview)
