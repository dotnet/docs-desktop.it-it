---
title: 'Procedura: Copiare e incollare un controllo ElementHost in fase di progettazione'
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, content copying and pasting
- interoperability [WPF]
- ElementHost control [Windows Forms], copying and pasting at design time
- WPF user control [Windows Forms], hosting in Windows Forms
ms.assetid: e570375d-2a68-44ba-b4f7-c781af2d20e8
ms.openlocfilehash: 82312cdc2d5bf8d81b0eb53e3e8a3fdb3319a72f
ms.sourcegitcommit: 7f48b9ecf8a30db42c8ecea0dd4df577736631a2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2021
ms.locfileid: "98956915"
---
# <a name="how-to-copy-and-paste-an-elementhost-control"></a>Procedura: copiare e incollare un controllo ElementHost

Questa procedura illustra come copiare un controllo Windows Presentation Foundation (WPF) in un Windows Form in Visual Studio.

1. In Visual Studio aggiungere un nuovo WPF <xref:System.Windows.Controls.UserControl> a un progetto Windows Form. Usare il nome predefinito per il tipo di controllo, `UserControl1.xaml`. Per ulteriori informazioni, vedere [procedura dettagliata: creazione di nuovi contenuti WPF in Windows Form in fase di progettazione](walkthrough-creating-new-wpf-content-on-windows-forms-at-design-time.md).

2. Nella finestra **Proprietà** impostare il valore delle <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> proprietà e di `UserControl1` su **200**.

3. Impostare il valore della <xref:System.Windows.Controls.Control.Background%2A> proprietà su **blu**.

4. Compilare il progetto.

5. Aprire `Form1` in Progettazione Windows Form.

6. Dalla **casella degli strumenti** trascinare un'istanza di `UserControl1` nel form.

   L'istanza di `UserControl1` viene inclusa in un nuovo controllo <xref:System.Windows.Forms.Integration.ElementHost> denominato `elementHost1`.

7. Con `elementHost1` selezionata, premere **CTRL** + **C** per copiarlo negli Appunti.

8. Premere **CTRL** + **V** per incollare il controllo copiato nel form.

   <xref:System.Windows.Forms.Integration.ElementHost> `elementHost2` Nel form viene creato un nuovo controllo denominato.

## <a name="see-also"></a>Vedi anche

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [Migrazione e interoperabilità](/dotnet/framework/wpf/advanced/migration-and-interoperability)
- [Utilizzo di controlli WPF](using-wpf-controls.md)
- [Progettare XAML in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
