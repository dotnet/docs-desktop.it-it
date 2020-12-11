---
title: 'Procedura dettagliata: Compilare automaticamente la casella degli strumenti con componenti personalizzati'
ms.date: 03/30/2017
helpviewer_keywords:
- IToolboxService interface
- Toolbox [Windows Forms], populating
- custom components [Windows Forms], adding to Toolbox
ms.assetid: 2fa1e3e8-6b9f-42b2-97c0-2be57444dba4
ms.openlocfilehash: 3ceebbf07c0241996479a6f7f72ab19f4cd9aa05
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964981"
---
# <a name="walkthrough-automatically-populating-the-toolbox-with-custom-components"></a>Procedura dettagliata: Compilare automaticamente la casella degli strumenti con componenti personalizzati

Se i componenti sono definiti da un progetto nella soluzione attualmente aperta, verranno visualizzati automaticamente nella **casella degli strumenti**, senza alcuna azione richiesta dall'utente. È anche possibile popolare manualmente la **casella degli strumenti** con i componenti personalizzati usando la finestra di [dialogo Scegli elementi della casella degli strumenti (Visual Studio)](/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100)), ma la **casella degli strumenti** prende in considerazione gli elementi degli output di compilazione della soluzione con tutte le caratteristiche seguenti:

- Implementa <xref:System.ComponentModel.IComponent> ;

- Non ha <xref:System.ComponentModel.ToolboxItemAttribute> impostato su `false` ;

- Non è <xref:System.ComponentModel.DesignTimeVisibleAttribute> impostato su `false` .

> [!NOTE]
> La **casella degli strumenti** non segue le catene di riferimento, quindi non Visualizza gli elementi che non sono compilati da un progetto nella soluzione.

In questa procedura dettagliata viene illustrato come un componente personalizzato viene visualizzato automaticamente nella **casella degli strumenti** dopo che il componente è stato compilato. Le attività illustrate nella procedura dettagliata sono le seguenti:

- Creazione di un progetto Windows Forms.

- Creazione di un componente personalizzato.

- Creazione di un'istanza di un componente personalizzato.

- Scaricamento e ricaricamento di un componente personalizzato.

Al termine, si noterà che la **casella degli strumenti** viene popolata con un componente creato.

## <a name="create-the-project"></a>Creare il progetto

1. In Visual Studio creare un progetto di applicazione basato su Windows denominato `ToolboxExample` (**file**  >  **nuovo**  >  **progetto**  >  **Visual C#** o **Visual Basic**  >  **desktop classico**  >  **Windows Forms applicazione**).

2. Aggiungere un nuovo componente al progetto. nominarla `DemoComponent`.

     Per altre informazioni, vedere [procedura: aggiungere nuovi elementi di progetto](/previous-versions/visualstudio/visual-studio-2010/w0572c5b(v=vs.100)).

3. Compilare il progetto.

4. Scegliere la voce **Opzioni** dal menu **strumenti** . Fare clic su **generale** sotto l'elemento **Progettazione Windows Form** e verificare che l'opzione **AutoToolboxPopulate** sia impostata su **true**.

## <a name="create-an-instance-of-a-custom-component"></a>Creare un'istanza di un componente personalizzato

Il passaggio successivo consiste nel creare un'istanza del componente personalizzato nel form. Poiché la **casella degli strumenti** rappresenta automaticamente il nuovo componente, questa operazione è semplice come la creazione di qualsiasi altro componente o controllo.

1. Aprire il modulo del progetto nella **finestra di progettazione dei form**.

2. Nella **casella degli strumenti** fare clic sulla nuova scheda denominata **ToolboxExample Components**.

     Quando si fa clic sulla scheda, viene visualizzato **DemoComponent**.

    > [!NOTE]
    > Per motivi di prestazioni, i componenti nell'area popolata automaticamente della **casella degli strumenti** non visualizzano bitmap personalizzate e l'oggetto <xref:System.Drawing.ToolboxBitmapAttribute> non è supportato. Per visualizzare un'icona per un componente personalizzato nella **casella degli strumenti**, utilizzare la finestra di dialogo **Scegli elementi della casella degli strumenti** per caricare il componente.

3. Trascinare il componente nel form.

     Viene creata un'istanza del componente che viene aggiunta alla **barra dei componenti**.

## <a name="unload-and-reload-a-custom-component"></a>Scaricare e ricaricare un componente personalizzato

La **casella degli strumenti** prende in considerazione i componenti di ogni progetto caricato e, quando un progetto viene scaricato, rimuove i riferimenti ai componenti del progetto.

1. Scaricare il progetto dalla soluzione.

     Per altre informazioni sullo scaricamento dei progetti, vedere [procedura: scaricare e ricaricare i progetti](/previous-versions/visualstudio/visual-studio-2010/tt479x1t(v=vs.100)). Se viene richiesto di salvare, scegliere **Sì**.

2. Aggiungere un nuovo progetto di **applicazione Windows** alla soluzione. Aprire il modulo nella **finestra di progettazione**.

     La scheda **Componenti ToolboxExample** del progetto precedente non è più disponibile.

3. Ricaricare il `ToolboxExample` progetto.

     Viene nuovamente visualizzata la scheda **componenti di ToolboxExample** .

## <a name="next-steps"></a>Passaggi successivi

In questa procedura dettagliata viene illustrato che la **casella degli strumenti** prende in considerazione i componenti di un progetto, ma anche la **casella degli strumenti** prende in considerazione i controlli. Provare a usare i controlli personalizzati aggiungendo e rimuovendo i progetti di controllo dalla soluzione.

## <a name="see-also"></a>Vedere anche

- [Generale, Progettazione Windows Form, finestra di dialogo Opzioni](/previous-versions/visualstudio/visual-studio-2010/5aazxs78(v=vs.100))
- [Procedura: modificare le schede della Casella degli strumenti](/previous-versions/visualstudio/visual-studio-2010/66kwe227(v=vs.100))
- [Finestra di dialogo Scegli elementi della Casella degli strumenti (Visual Studio)](/previous-versions/visualstudio/visual-studio-2010/dyca0t6t(v=vs.100))
- [Inserimento di controlli in Windows Form](putting-controls-on-windows-forms.md)
