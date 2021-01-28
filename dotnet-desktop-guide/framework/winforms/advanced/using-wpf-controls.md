---
title: Utilizzo di controlli WPF
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms Designer [Windows Forms], interoperability with WPF
- interoperability [WPF]
ms.assetid: 03c85dce-26ad-44cd-bc1d-8e0cb56de096
ms.openlocfilehash: e2e9fd6f0828d76494ed3d602b00b5d67770fc47
ms.sourcegitcommit: 7f48b9ecf8a30db42c8ecea0dd4df577736631a2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2021
ms.locfileid: "98957539"
---
# <a name="use-wpf-controls-in-windows-forms-apps"></a>Usare i controlli WPF nelle app Windows Form

È possibile utilizzare i controlli Windows Presentation Foundation (WPF) nelle applicazioni basate su Windows Form. Sebbene si tratta di due tecnologie di visualizzazione diverse, interagiscono senza problemi.

Il Progettazione Windows Form in Visual Studio fornisce un ambiente di progettazione visiva per l'hosting di controlli Windows Presentation Foundation. Un controllo WPF è ospitato da un particolare controllo Windows Form denominato <xref:System.Windows.Forms.Integration.ElementHost> . Questo controllo consente al controllo WPF di partecipare al layout del form e di ricevere i messaggi della tastiera e del mouse. In fase di progettazione, è possibile disporre il <xref:System.Windows.Forms.Integration.ElementHost> controllo come qualsiasi Windows Form controllo.

È inoltre possibile utilizzare Windows Form controlli nelle applicazioni basate su WPF. Per altre informazioni, vedere [progettazione di XAML in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio).

## <a name="see-also"></a>Vedi anche

- [Interoperatività di WPF e Windows Form](/dotnet/framework/wpf/advanced/wpf-and-windows-forms-interoperation)
