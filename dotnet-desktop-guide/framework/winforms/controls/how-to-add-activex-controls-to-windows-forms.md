---
title: Aggiungere controlli ActiveX ai form
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms controls, ActiveX controls
- forms [Windows Forms], adding ActiveX controls
- ActiveX controls [Windows Forms], adding
ms.assetid: 54a61e5b-555e-4887-b41e-6244fed271eb
ms.openlocfilehash: ebcaf984e3c64bae2988b5c2d1c94abac79ad36e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962128"
---
# <a name="how-to-add-activex-controls-to-windows-forms"></a>Procedura: aggiungere i controlli ActiveX a Windows Form

Sebbene il Progettazione Windows Form in Visual Studio sia ottimizzato per ospitare controlli Windows Forms, è anche possibile inserire controlli ActiveX in Windows Forms.

> [!CAUTION]
> Esistono limitazioni delle prestazioni per Windows Forms quando vengono aggiunti i controlli ActiveX.

Prima di aggiungere i controlli ActiveX al form, è necessario aggiungerli alla casella degli strumenti. Per ulteriori informazioni, vedere [componenti com, finestra di dialogo Personalizza casella degli strumenti](/previous-versions/visualstudio/visual-studio-2010/cby6tzh5(v=vs.100)).

## <a name="add-an-activex-control-to-your-windows-form"></a>Aggiungere un controllo ActiveX a Windows Form

Per aggiungere un controllo ActiveX a Windows Form, fare doppio clic sul controllo nella casella degli strumenti.

Visual Studio aggiunge tutti i riferimenti al controllo nel progetto. Per ulteriori informazioni sugli aspetti da tenere presenti quando si utilizzano i controlli ActiveX in Windows Forms, vedere [considerazioni sull'hosting di un controllo ActiveX in un Windows Form](considerations-when-hosting-an-activex-control-on-a-windows-form.md).

> [!NOTE]
> Il Windows Forms l'utilità di importazione del controllo ActiveX (AxImp.exe) crea argomenti di eventi di tipo diverso dal previsto durante l'importazione di librerie di collegamento dinamico ActiveX. Gli argomenti creati da AxImp.exe sono simili ai seguenti: `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEvent e)` , quando `Invoke(object sender, DWebBrowserEvents2_ProgressChangeEventArgs e)` è previsto. Tenere presente che questa irregolarità non impedisce il corretto funzionamento del codice. Per informazioni dettagliate, vedere [Windows Forms l'utilità di importazione del controllo ActiveX (Aximp.exe)](/dotnet/framework/tools/aximp-exe-windows-forms-activex-control-importer).

## <a name="see-also"></a>Vedere anche

- [Controlli di Windows Forms](index.md)
- [Confronto tra controlli e oggetti programmabili in diversi linguaggi e librerie](/previous-versions/visualstudio/visual-studio-2010/0061wezk(v=vs.100))
- [Procedura: aggiungere controlli a un Windows Form](how-to-add-controls-to-windows-forms.md)
- [Impostazione delle etichette di singoli controlli Windows Form e creazione dei relativi tasti di scelta rapida](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [Controlli da usare in Windows Form](controls-to-use-on-windows-forms.md)
- [Controlli Windows Form per funzione](windows-forms-controls-by-function.md)
