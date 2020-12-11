---
title: "Procedura: Attivare l'enumerazione TextTrimming"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- text [WPF], trimming
- documents [WPF], trimming text
- trimming text [WPF]
ms.assetid: dd8c9191-d2be-45fd-9fb4-3c75b65578c5
ms.openlocfilehash: 25fff566868e792004a915fee195485c4a1f385f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967777"
---
# <a name="how-to-enable-text-trimming"></a>Procedura: Attivare l'enumerazione TextTrimming

Questo esempio illustra l'utilizzo e gli effetti dei valori disponibili nell' <xref:System.Windows.TextTrimming> enumerazione.

## <a name="example"></a>Esempio

Nell'esempio seguente viene definito un <xref:System.Windows.Controls.TextBlock> elemento con l' <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> attributo impostato.

[!code-xaml[TextTrimmingSnippets#_TextTrimmingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml#_texttrimmingxaml)]

L'impostazione della <xref:System.Windows.TextTrimming> proprietà corrispondente nel codice è illustrata di seguito.

[!code-csharp[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml.cs#_texttrimmingsettexttrimming)]
[!code-vb[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextTrimmingSnippets/VisualBasic/Window1.xaml.vb#_texttrimmingsettexttrimming)]

Sono attualmente disponibili tre opzioni per il taglio del testo: **CharacterEllipsis**, **WordEllipsis** e **None**.

Quando <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> è impostato su **CharacterEllipsis**, il testo viene tagliato e continua con i puntini di sospensione in corrispondenza del carattere più vicino al bordo di taglio.  Questa impostazione consente di tagliare il testo in modo da adattarlo meglio al limite di taglio, ma potrebbe comportare la troncatura delle parole.  La figura seguente mostra l'effetto di questa impostazione su un oggetto <xref:System.Windows.Controls.TextBlock> simile a quello definito sopra.

![Esempio: TextTrimming.CharacterEllipsis](./media/texttrimming-character.png "TextTrimming_Character")

Quando <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> è impostato su **WordEllipsis**, il testo viene tagliato e continua con i puntini di sospensione alla fine della prima parola completa più vicina al bordo di taglio.  Questa impostazione non mostrerà parole parzialmente tagliate, ma tende a non tagliare il testo in modo analogo al bordo del taglio come impostazione di **CharacterEllipsis** .  Nella figura seguente viene illustrato l'effetto di questa impostazione sull'oggetto <xref:System.Windows.Controls.TextBlock> definito sopra.

![Esempio: TextTrimming.WordEllipsis](./media/texttrimming-word.png "TextTrimming_Word")

Quando <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> è impostato su **None**, non viene eseguita alcuna operazione di taglio del testo.  In questo caso viene eseguita una semplice operazione di ritaglio in corrispondenza del limite del contenitore di testo padre.  La figura seguente mostra l'effetto di questa impostazione su un oggetto <xref:System.Windows.Controls.TextBlock> simile a quello definito sopra.

![Esempio: TextTrimming.None](./media/texttrimming-none.png "TextTrimming_None")
