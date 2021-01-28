---
title: 'Procedura: visualizzare un controllo nella finestra di dialogo Scegli elementi della Casella degli strumenti'
ms.date: 08/23/2019
helpviewer_keywords:
- global assembly cache [Windows Forms], Choose Toolbox Items dialog box
- AssemblyFoldersEx [Windows Forms], Choose Toolbox Items dialog box
- controls [Windows Forms], display in Choose Toolbox Items dialog box
- assembly folder registration [Windows Forms], Choose Toolbox Items dialog box
- Choose Toolbox Items dialog box [Windows Forms], display control
ms.assetid: 01ef6eba-d044-40f0-951d-78eff7ebd9a9
ms.openlocfilehash: 501fd1054a0c7cc1accec6c7a3f8257da1a94417
ms.sourcegitcommit: 7f48b9ecf8a30db42c8ecea0dd4df577736631a2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2021
ms.locfileid: "98957526"
---
# <a name="how-to-display-a-control-in-the-choose-toolbox-items-dialog-box"></a>Procedura: visualizzare un controllo nella finestra di dialogo Scegli elementi della Casella degli strumenti

Quando si sviluppano e si distribuiscono i controlli, è possibile che tali controlli siano visualizzati nella finestra di dialogo **Scegli elementi della casella degli strumenti** di Visual Studio, che viene visualizzato quando si fa clic con il pulsante destro del mouse sulla **casella degli strumenti** e si seleziona **Scegli elementi**. È possibile abilitare il controllo per la visualizzazione in questa finestra di dialogo tramite la procedura di registrazione AssemblyFoldersEx.

Per visualizzare il controllo nella finestra di dialogo Scegli elementi della casella degli strumenti:

- Installare l'assembly di controllo nel Global Assembly Cache. Per altre informazioni, vedere [Procedura: installare un assembly nella Global Assembly Cache](/dotnet/framework/app-domains/install-assembly-into-gac).

  -oppure-

- Registrare il controllo e gli assembly in fase di progettazione associati tramite la procedura di registrazione AssemblyFoldersEx. AssemblyFoldersEx è un percorso del registro di sistema in cui i fornitori di terze parti archiviano percorsi per ogni versione del Framework supportata. La risoluzione in fase di progettazione può essere esaminata nel percorso del registro di sistema per trovare gli assembly di riferimento. Lo script del registro di sistema può specificare i controlli che si desidera visualizzare nella casella degli strumenti.

## <a name="see-also"></a>Vedi anche

- [Sviluppo di controlli Windows Form in fase di progettazione](developing-windows-forms-controls-at-design-time.md)
- [Procedura: installare un assembly nella global assembly cache](/dotnet/framework/app-domains/install-assembly-into-gac)
- [Procedura dettagliata: Compilare automaticamente la casella degli strumenti con componenti personalizzati](walkthrough-automatically-populating-the-toolbox-with-custom-components.md)
