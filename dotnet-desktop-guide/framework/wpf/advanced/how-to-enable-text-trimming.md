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
# <a name="how-to-enable-text-trimming"></a><span data-ttu-id="06e78-102">Procedura: Attivare l'enumerazione TextTrimming</span><span class="sxs-lookup"><span data-stu-id="06e78-102">How to: Enable Text Trimming</span></span>

<span data-ttu-id="06e78-103">Questo esempio illustra l'utilizzo e gli effetti dei valori disponibili nell' <xref:System.Windows.TextTrimming> enumerazione.</span><span class="sxs-lookup"><span data-stu-id="06e78-103">This example demonstrates the usage and effects of the values available in the <xref:System.Windows.TextTrimming> enumeration.</span></span>

## <a name="example"></a><span data-ttu-id="06e78-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="06e78-104">Example</span></span>

<span data-ttu-id="06e78-105">Nell'esempio seguente viene definito un <xref:System.Windows.Controls.TextBlock> elemento con l' <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> attributo impostato.</span><span class="sxs-lookup"><span data-stu-id="06e78-105">The following example defines a <xref:System.Windows.Controls.TextBlock> element with the <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> attribute set.</span></span>

[!code-xaml[TextTrimmingSnippets#_TextTrimmingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml#_texttrimmingxaml)]

<span data-ttu-id="06e78-106">L'impostazione della <xref:System.Windows.TextTrimming> proprietà corrispondente nel codice è illustrata di seguito.</span><span class="sxs-lookup"><span data-stu-id="06e78-106">Setting the corresponding <xref:System.Windows.TextTrimming> property in code is demonstrated below.</span></span>

[!code-csharp[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](~/samples/snippets/csharp/VS_Snippets_Wpf/TextTrimmingSnippets/CSharp/Window1.xaml.cs#_texttrimmingsettexttrimming)]
[!code-vb[TextTrimmingSnippets#_TextTrimmingSetTextTrimming](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextTrimmingSnippets/VisualBasic/Window1.xaml.vb#_texttrimmingsettexttrimming)]

<span data-ttu-id="06e78-107">Sono attualmente disponibili tre opzioni per il taglio del testo: **CharacterEllipsis**, **WordEllipsis** e **None**.</span><span class="sxs-lookup"><span data-stu-id="06e78-107">There are currently three options for trimming text: **CharacterEllipsis**, **WordEllipsis**, and **None**.</span></span>

<span data-ttu-id="06e78-108">Quando <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> è impostato su **CharacterEllipsis**, il testo viene tagliato e continua con i puntini di sospensione in corrispondenza del carattere più vicino al bordo di taglio.</span><span class="sxs-lookup"><span data-stu-id="06e78-108">When <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> is set to **CharacterEllipsis**, text is trimmed and continued with an ellipsis at the character closest to the trimming edge.</span></span>  <span data-ttu-id="06e78-109">Questa impostazione consente di tagliare il testo in modo da adattarlo meglio al limite di taglio, ma potrebbe comportare la troncatura delle parole.</span><span class="sxs-lookup"><span data-stu-id="06e78-109">This setting tends to trim text to fit more closely to the trimming boundary, but may result in words being partially trimmed.</span></span>  <span data-ttu-id="06e78-110">La figura seguente mostra l'effetto di questa impostazione su un oggetto <xref:System.Windows.Controls.TextBlock> simile a quello definito sopra.</span><span class="sxs-lookup"><span data-stu-id="06e78-110">The following figure shows the effect of this setting on a <xref:System.Windows.Controls.TextBlock> similar to the one defined above.</span></span>

<span data-ttu-id="06e78-111">![Esempio: TextTrimming.CharacterEllipsis](./media/texttrimming-character.png "TextTrimming_Character")</span><span class="sxs-lookup"><span data-stu-id="06e78-111">![Example: TextTrimming.CharacterEllipsis](./media/texttrimming-character.png "TextTrimming_Character")</span></span>

<span data-ttu-id="06e78-112">Quando <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> è impostato su **WordEllipsis**, il testo viene tagliato e continua con i puntini di sospensione alla fine della prima parola completa più vicina al bordo di taglio.</span><span class="sxs-lookup"><span data-stu-id="06e78-112">When <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> is set to **WordEllipsis**, text is trimmed and continued with an ellipsis at the end of the first full word closest to the trimming edge.</span></span>  <span data-ttu-id="06e78-113">Questa impostazione non mostrerà parole parzialmente tagliate, ma tende a non tagliare il testo in modo analogo al bordo del taglio come impostazione di **CharacterEllipsis** .</span><span class="sxs-lookup"><span data-stu-id="06e78-113">This setting will not show partially trimmed words, but tends not to trim text as closely to the trimming edge as the **CharacterEllipsis** setting.</span></span>  <span data-ttu-id="06e78-114">Nella figura seguente viene illustrato l'effetto di questa impostazione sull'oggetto <xref:System.Windows.Controls.TextBlock> definito sopra.</span><span class="sxs-lookup"><span data-stu-id="06e78-114">The following figure shows the effect of this setting on the <xref:System.Windows.Controls.TextBlock> defined above.</span></span>

<span data-ttu-id="06e78-115">![Esempio: TextTrimming.WordEllipsis](./media/texttrimming-word.png "TextTrimming_Word")</span><span class="sxs-lookup"><span data-stu-id="06e78-115">![Example: TextTrimming.WordEllipsis](./media/texttrimming-word.png "TextTrimming_Word")</span></span>

<span data-ttu-id="06e78-116">Quando <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> è impostato su **None**, non viene eseguita alcuna operazione di taglio del testo.</span><span class="sxs-lookup"><span data-stu-id="06e78-116">When <xref:System.Windows.Controls.TextBlock.TextTrimming%2A> is set to **None**, no text trimming is performed.</span></span>  <span data-ttu-id="06e78-117">In questo caso viene eseguita una semplice operazione di ritaglio in corrispondenza del limite del contenitore di testo padre.</span><span class="sxs-lookup"><span data-stu-id="06e78-117">In this case, text is simply cropped to the boundary of the parent text container.</span></span>  <span data-ttu-id="06e78-118">La figura seguente mostra l'effetto di questa impostazione su un oggetto <xref:System.Windows.Controls.TextBlock> simile a quello definito sopra.</span><span class="sxs-lookup"><span data-stu-id="06e78-118">The following figure shows the effect of this setting on a <xref:System.Windows.Controls.TextBlock> similar to the one defined above.</span></span>

<span data-ttu-id="06e78-119">![Esempio: TextTrimming.None](./media/texttrimming-none.png "TextTrimming_None")</span><span class="sxs-lookup"><span data-stu-id="06e78-119">![Example: TextTrimming.None](./media/texttrimming-none.png "TextTrimming_None")</span></span>
