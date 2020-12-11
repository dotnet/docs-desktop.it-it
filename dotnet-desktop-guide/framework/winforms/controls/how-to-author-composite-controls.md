---
title: 'Procedura: Creare controlli compositi'
ms.date: 03/30/2017
helpviewer_keywords:
- UserControl class [Windows Forms], creating composite controls
- user controls [Windows Forms], creating
- user controls [Windows Forms], inheriting from
- composite controls [Windows Forms], creating
ms.assetid: 79c9cf05-5ab6-4a18-886d-88a64748b098
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: 42ea424507b89576df8099fd4849dd2665135a55
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964510"
---
# <a name="how-to-author-composite-controls"></a>Procedura: creare controlli compositi

I controlli compositi possono essere usati in molti modi. È possibile crearli come parte di un progetto applicazione desktop di Windows e usarli solo sui form del progetto. Oppure è possibile crearli in un progetto libreria di controlli Windows, compilare il progetto in un assembly e usare i controlli in altri progetti. È anche possibile ereditare da essi e usare l'ereditarietà visiva per personalizzarli rapidamente per scopi specifici.

## <a name="to-author-a-composite-control"></a>Per creare un controllo composito

1. In Visual Studio creare un nuovo progetto di **applicazione Windows** e denominarlo **DemoControlHost**.

2. Nel menu **Progetto** fare clic su **Aggiungi controllo utente**.

3. Nella finestra di dialogo **Aggiungi nuovo elemento** assegnare al file di classe (file con estensione .vb o .cs) il nome che si desidera assegnare al controllo composito.

4. Selezionare il pulsante **Aggiungi** per creare il file di classe per il controllo composito.

5. Aggiungere controlli dalla **Casella degli strumenti** alla superficie del controllo composito.

6. Inserire codice nella routine evento per gestire gli eventi generati dal controllo composito o dai relativi controlli costitutivi.

7. Chiudere la finestra di progettazione per il controllo composito e salvare il file quando viene richiesto.

8. Nel menu **Compila** scegliere **Compila soluzione**.

     Il progetto deve essere compilato affinché i controlli personalizzati siano visualizzati nella **Casella degli strumenti**.

9. Usare la scheda **DemoControlHost** della **Casella degli strumenti** per aggiungere istanze del controllo a `Form1`.

## <a name="to-author-a-control-class-library"></a>Per creare una libreria di classi del controllo

1. Aprire un nuovo progetto **Libreria di controlli Windows**.

     Per impostazione predefinita, il progetto contiene un controllo composito.

2. Aggiungere controlli e codice, come descritto nella procedura precedente.

3. Scegliere un controllo che non si desidera venga modificato dalle classi che ereditano e impostare la proprietà **Modifiers** del controllo su **Private**.

4. Compilare la DLL.

## <a name="to-inherit-from-a-composite-control-in-a-control-class-library"></a>Per ereditare da un controllo composito in una libreria di classi del controllo

1. Nel menu **File** puntare su **Aggiungi** e selezionare **Nuovo progetto** per aggiungere un nuovo progetto **Windows Application** alla soluzione.

2. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sulla cartella **Riferimenti** del nuovo progetto e scegliere **Aggiungi riferimento** per aprire la finestra di dialogo **Aggiungi riferimento**.

3. Selezionare la scheda **Progetti** e fare doppio clic sul progetto libreria di controlli.

4. Nel menu **Compila** scegliere **Compila soluzione**.

5. In **Esplora soluzioni** fare clic con il pulsante destro del mouse sul progetto libreria di controlli e selezionare **Aggiungi nuovo elemento** nel menu di scelta rapida.

6. Selezionare il modello **Controllo utente ereditato** dalla finestra di dialogo **Aggiungi nuovo elemento**.

7. Nella finestra di dialogo **Selezione ereditarietà** fare doppio clic sul controllo da cui si desidera ereditare.

     Un nuovo controllo viene aggiunto al progetto.

8. Aprire la finestra di progettazione visiva per il nuovo controllo e aggiungere altri controlli costitutivi.

     È possibile visualizzare i controlli costitutivi ereditati dal controllo composito nella DLL ed è possibile modificare le proprietà dei controlli la cui proprietà **Modifiers** è **Public**. Non è possibile modificare le proprietà del controllo la cui proprietà **Modifiers** è **Private**.

## <a name="see-also"></a>Vedere anche

- [Procedura dettagliata: modifica di un controllo composito](walkthrough-authoring-a-composite-control-with-visual-csharp.md)
- [Procedura dettagliata: eredità da un controllo Windows Forms](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
- [Consigli sui tipi di controlli](control-type-recommendations.md)
- [Procedura: Creare controlli per Windows Form](how-to-author-controls-for-windows-forms.md)
- [Tipi di controlli personalizzati](varieties-of-custom-controls.md)
