---
title: Utilizzo di controlli WPF
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms Designer [Windows Forms], interoperability with WPF
- interoperability [WPF]
ms.assetid: 03c85dce-26ad-44cd-bc1d-8e0cb56de096
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: dfc086b4873c41bf1919b680d472807283e8a340
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952728"
---
# <a name="use-wpf-controls-in-windows-forms-apps"></a>Usare i controlli WPF nelle app Windows Forms

È possibile utilizzare i controlli Windows Presentation Foundation (WPF) nelle applicazioni basate su Windows Forms. Sebbene si tratta di due tecnologie di visualizzazione diverse, interagiscono senza problemi.

Il Progettazione Windows Form in Visual Studio fornisce un ambiente di progettazione visiva per l'hosting di controlli Windows Presentation Foundation. Un controllo WPF è ospitato da un particolare controllo Windows Forms denominato <xref:System.Windows.Forms.Integration.ElementHost> . Questo controllo consente al controllo WPF di partecipare al layout del form e di ricevere i messaggi della tastiera e del mouse. In fase di progettazione, è possibile disporre il <xref:System.Windows.Forms.Integration.ElementHost> controllo come qualsiasi Windows Forms controllo.

È inoltre possibile utilizzare Windows Forms controlli nelle applicazioni basate su WPF. Per altre informazioni, vedere [progettazione di XAML in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio).

## <a name="see-also"></a>Vedere anche

- [Interoperatività di WPF e Windows Forms](/dotnet/framework/wpf/advanced/wpf-and-windows-forms-interoperation)
