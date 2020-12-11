---
title: Selezionare i controlli WPF per Windows Forms
titleSuffix: ''
ms.date: 03/30/2017
helpviewer_keywords:
- WPF content [Windows Forms], assigning at design time
- ElementHost control [Windows Forms], assigning WPF content at design time
- interoperability [WPF]
- Windows Forms, content assignments
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: b3e9ef93-7e0f-4a2f-8f1e-3437609a1eb7
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: c1532206b467c523ffd8e4cf4f85c168a4aad80b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962353"
---
# <a name="walkthrough-assign-wpf-content-on-windows-forms-at-design-time"></a>Procedura dettagliata: assegnare contenuto WPF in Windows Forms in fase di progettazione

Questo articolo illustra come selezionare i tipi di controllo Windows Presentation Foundation (WPF) che si desidera visualizzare nel form. È possibile selezionare qualsiasi tipo di controllo WPF incluso nel progetto.

## <a name="prerequisites"></a>Prerequisiti

Per completare la procedura dettagliata, è necessario Visual Studio.

## <a name="create-the-project"></a>Creare il progetto

Aprire Visual Studio e creare un nuovo progetto di applicazione Windows Forms in Visual Basic o Visual C# denominato `SelectingWpfContent` .

> [!NOTE]
> Con il contenuto WPF sono supportati solo progetti C# e Visual Basic.

## <a name="create-the-wpf-control-types"></a>Creare i tipi di controllo WPF

Dopo avere aggiunto i tipi di controllo WPF al progetto, è possibile includerli in controlli <xref:System.Windows.Forms.Integration.ElementHost> diversi.

1. Aggiungere un nuovo progetto WPF <xref:System.Windows.Controls.UserControl> alla soluzione. Usare il nome predefinito per il tipo di controllo, `UserControl1.xaml`. Per ulteriori informazioni, vedere [procedura dettagliata: creazione di nuovi contenuti WPF in Windows Forms in fase di progettazione](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).

2. In visualizzazione Progettazione verificare che `UserControl1` sia selezionato.

3. Nella finestra **Proprietà** impostare il valore delle <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> proprietà e su **200**.

4. Aggiungere un <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> controllo a <xref:System.Windows.Controls.UserControl> e impostare il valore della <xref:System.Windows.Controls.TextBox.Text%2A> proprietà su **contenuto ospitato**.

5. Aggiungere un secondo controllo WPF <xref:System.Windows.Controls.UserControl> al progetto. Usare il nome predefinito per il tipo di controllo, `UserControl2.xaml`.

6. Nella finestra **Proprietà** impostare il valore delle <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> proprietà e su **200**.

7. Aggiungere un <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> controllo a <xref:System.Windows.Controls.UserControl> e impostare il valore della <xref:System.Windows.Controls.TextBox.Text%2A> proprietà su **Hosted Content 2**.

   > [!NOTE]
   > In generale, è opportuno ospitare contenuto WPF più sofisticato. Il controllo <xref:System.Windows.Controls.TextBox?displayProperty=nameWithType> è qui usato a solo a titolo esemplificativo.

8. Compilare il progetto.

## <a name="select-wpf-controls"></a>Selezionare i controlli WPF

È possibile assegnare contenuto WPF diverso a un controllo <xref:System.Windows.Forms.Integration.ElementHost> che include già contenuto.

1. Aprire `Form1` in Progettazione Windows Form.

2. Nella **casella degli strumenti** fare doppio clic su `UserControl1` per creare un'istanza di `UserControl1` nel form.

   L'istanza di `UserControl1` viene inclusa in un nuovo controllo <xref:System.Windows.Forms.Integration.ElementHost> denominato `elementHost1`.

3. Nel pannello smart tag per `elementHost1` aprire l'elenco a discesa **selezione contenuto ospitato** .

4. Nella casella di riepilogo a discesa selezionare **UserControl2** .

   Il controllo `elementHost1` include ora un'istanza del tipo `UserControl2`.

5. Nella finestra **Proprietà** verificare che la <xref:System.Windows.Forms.Integration.ElementHost.Child%2A> proprietà sia impostata su **UserControl2**.

6. Dalla **casella degli strumenti**, nel gruppo **interoperabilità WPF** trascinare un <xref:System.Windows.Forms.Integration.ElementHost> controllo nel form.

   Il nome predefinito del nuovo controllo è `elementHost2`.

7. Nel pannello smart tag per `elementHost2` aprire l'elenco a discesa **selezione contenuto ospitato** .

8. Selezionare **UserControl1** nell'elenco a discesa.

9. Il controllo `elementHost2` include ora un'istanza del tipo `UserControl1`.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Migrazione e interoperabilità](/dotnet/framework/wpf/advanced/migration-and-interoperability)
- [Utilizzo di controlli WPF](using-wpf-controls.md)
- [Progettare XAML in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
