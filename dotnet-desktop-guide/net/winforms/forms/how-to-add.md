---
title: Aggiungere un modulo a un progetto
description: Aggiungere un nuovo modulo a un progetto di Windows Forms .NET in Visual Studio
ms.date: 10/26/2020
helpviewer_keywords:
- Windows Forms, create add form
ms.openlocfilehash: fb35c1b62ca0b7a21581c350ddca7f21f45ec27f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967300"
---
# <a name="how-to-add-a-form-to-a-project-windows-forms-net"></a>Come aggiungere un modulo a un progetto (Windows Forms .NET)

Aggiungere i moduli al progetto con Visual Studio. Quando l'app dispone di più moduli, è possibile scegliere quale sia il modulo di avvio per l'app ed è possibile visualizzare più forme nello stesso momento.

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="add-a-new-form"></a>Aggiungi un nuovo modulo

Aggiungere un nuovo modulo con Visual Studio.

01. In Visual Studio trovare il riquadro **Esplora progetti** . Fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi**  >  **modulo (Windows Forms)**.

    :::image type="content" source="media/how-to-add/right-click.png" alt-text="Fare clic con il pulsante destro del mouse su Esplora soluzioni per aggiungere nuovo modulo al progetto Windows Form":::

01. Nella casella **nome** Digitare un nome per il form, ad esempio *MyNewForm*. Visual Studio fornirà un nome predefinito e univoco che è possibile usare.

    :::image type="content" source="media/how-to-add/new-form-dialog.png" alt-text="Finestra di dialogo Aggiungi elemento in Visual Studio per Windows Form":::

Una volta aggiunto il modulo, Visual Studio apre la finestra di progettazione del form per il form.

## <a name="add-a-project-reference-to-a-form"></a>Aggiungere un riferimento di progetto a un modulo

Se si dispone dei file di origine in un modulo, è possibile aggiungere il modulo al progetto copiando i file nella stessa cartella del progetto. Il progetto fa automaticamente riferimento a tutti i file di codice presenti nella stessa cartella o nella stessa cartella figlio del progetto.

I moduli sono costituiti da due file che condividono lo stesso nome: _Form2.cs_ (_Form2_ è un esempio di nome di file) e _Form2. Designer.cs_. Talvolta è presente un file di risorse, che condivide lo stesso nome, _Form2. resx_. Nell'esempio precedente _Form2_ rappresenta il nome del file di base. È possibile copiare tutti i file correlati nella cartella del progetto.

In alternativa, è possibile usare Visual Studio per importare un file nel progetto. Quando si aggiunge un file esistente al progetto, il file viene copiato nella stessa cartella del progetto.

01. In Visual Studio trovare il riquadro **Esplora progetti** . Fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi**  >  **elemento esistente**.

    :::image type="content" source="media/how-to-add/existing-right-click.png" alt-text="Fare clic con il pulsante destro del mouse su Esplora soluzioni per aggiungere il modulo esistente al progetto":::

02. Passare alla cartella contenente i file del modulo.

03. Selezionare il file _Form2.cs_ , dove _Form2_ è il nome del file di base dei file del modulo correlati. Non selezionare gli altri file, ad esempio _Form2. Designer.cs_.

## <a name="see-also"></a>Vedere anche

- [Come posizionare e ridimensionare un form (Windows Forms .NET)](how-to-position-and-resize.md)
- [Cenni preliminari sugli eventi (Windows Forms .NET)](events.md)
- [Posizione e layout dei controlli (Windows Forms .NET)](../controls/layout.md)
