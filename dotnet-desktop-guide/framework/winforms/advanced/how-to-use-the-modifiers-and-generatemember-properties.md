---
title: 'Procedura: Usare modificatori e proprietà GenerateMember'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
f1_keywords:
- Designer_GenerateMember
- Designer_Modifiers
helpviewer_keywords:
- base forms
- inheritance [Windows Forms], forms
- inherited forms [Windows Forms], Windows Forms
- inherited forms
- form inheritance
- Windows Forms, inheritance
ms.assetid: 3381a5e4-e1a3-44e2-a765-a0b758937b85
ms.openlocfilehash: 3fbaaae53aa60f6356c3a8daa0513de86ef2dacb
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962443"
---
# <a name="how-to-use-the-modifiers-and-generatemember-properties"></a>Procedura: Usare modificatori e proprietà GenerateMember

Quando si inserisce un componente in un Windows Form, due proprietà vengono fornite dall'ambiente di progettazione: `GenerateMember` e `Modifiers` . La `GenerateMember` proprietà specifica quando il progettazione Windows Form genera una variabile membro per un componente. La `Modifiers` proprietà è il modificatore di accesso assegnato a tale variabile membro. Se il valore della `GenerateMember` proprietà è `false` , il valore della `Modifiers` proprietà non ha alcun effetto.

## <a name="specify-whether-a-component-is-a-member-of-the-form"></a>Specificare se un componente è un membro del form

1. In Visual Studio, nella Progettazione Windows Form aprire il modulo.

2. Aprire la **casella degli strumenti** e, nel form, inserire tre <xref:System.Windows.Forms.Button> controlli.

3. Impostare le `GenerateMember` `Modifiers` proprietà e per ogni <xref:System.Windows.Forms.Button> controllo in base alla tabella seguente.

    |Nome pulsante|Valore GenerateMember|Valore modificatori|
    |-----------------|--------------------------|---------------------|
    |`button1`|`true`|`private`|
    |`button2`|`true`|`protected`|
    |`button3`|`false`|Nessuna modifica|

4. Compilare la soluzione.

5. In **Esplora soluzioni** fare clic sul pulsante **Mostra tutti i file**.

6. Aprire il nodo **Form1** e nell'editor di **codice** aprire il file **Form1. designer. vb** o **Form1.designer.cs** . Questo file contiene il codice emesso dal Progettazione Windows Form.

7. Trovare le dichiarazioni per i tre pulsanti. Nell'esempio di codice riportato di seguito vengono illustrate le differenze specificate dalle `GenerateMember` `Modifiers` proprietà e.

     [!code-csharp[System.Windows.Forms.GenerateMember#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.GenerateMember#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#3)]

     [!code-csharp[System.Windows.Forms.GenerateMember#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.GenerateMember#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.GenerateMember/VB/Form1.vb#2)]

> [!NOTE]
> Per impostazione predefinita, il Progettazione Windows Form assegna il `private` `Friend` modificatore (in Visual Basic) ai controlli contenitore come <xref:System.Windows.Forms.Panel> . Se la base <xref:System.Windows.Forms.UserControl> o <xref:System.Windows.Forms.Form> un controllo contenitore non accetta nuovi elementi figlio nei controlli e nei form ereditati. La soluzione consiste nel modificare il modificatore del controllo contenitore di base in `protected` o `public` .

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Button>
- [Ereditarietà visiva di Windows Form](windows-forms-visual-inheritance.md)
- [Procedura dettagliata: Dimostrazione dell'ereditarietà visiva](walkthrough-demonstrating-visual-inheritance.md)
- [Procedura: Ereditare Windows Form](how-to-inherit-windows-forms.md)
