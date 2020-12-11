---
title: 'Procedura: creare un controllo dotato di un tasto di scelta e di una disposizione testo'
ms.date: 03/30/2017
helpviewer_keywords:
- access keys [WPF], control for
- controls [WPF], text wrapping
- wrapping text [WPF]
- keys [WPF], control for
- controls [WPF], access keys
- text wrapping [WPF]
ms.assetid: 205099d9-2551-4302-a25e-a15af9f67e04
ms.openlocfilehash: 86239374ca9cb3bd3d71415496e32d4a27fbae5a
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969475"
---
# <a name="how-to-create-a-control-that-has-an-access-key-and-text-wrapping"></a><span data-ttu-id="f8c4c-102">Procedura: creare un controllo dotato di un tasto di scelta e di una disposizione testo</span><span class="sxs-lookup"><span data-stu-id="f8c4c-102">How to: Create a Control That Has an Access Key and Text Wrapping</span></span>

<span data-ttu-id="f8c4c-103">Questo esempio illustra come creare un controllo dotato di un tasto di scelta e con un supporto di disposizione testo.</span><span class="sxs-lookup"><span data-stu-id="f8c4c-103">This example shows how to create a control that has an access key and supports text wrapping.</span></span> <span data-ttu-id="f8c4c-104">Nell'esempio viene usato un <xref:System.Windows.Controls.Label> controllo per illustrare questi concetti.</span><span class="sxs-lookup"><span data-stu-id="f8c4c-104">The example uses a <xref:System.Windows.Controls.Label> control to illustrate these concepts.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f8c4c-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="f8c4c-105">Example</span></span>  

 <span data-ttu-id="f8c4c-106">**Aggiungere la disposizione del testo all'etichetta**</span><span class="sxs-lookup"><span data-stu-id="f8c4c-106">**Add Text Wrapping to Your Label**</span></span>  
  
 <span data-ttu-id="f8c4c-107">Il <xref:System.Windows.Controls.Label> controllo non supporta il ritorno a capo del testo.</span><span class="sxs-lookup"><span data-stu-id="f8c4c-107">The <xref:System.Windows.Controls.Label> control does not support text wrapping.</span></span> <span data-ttu-id="f8c4c-108">Se è necessaria un'etichetta che esegue il wrapping su più righe, è possibile annidare un altro elemento che supporta la disposizione testo e inserirlo nell'etichetta.</span><span class="sxs-lookup"><span data-stu-id="f8c4c-108">If you need a label that wraps across multiple lines, you can nest another element that does support text wrapping and put the element inside the label.</span></span> <span data-ttu-id="f8c4c-109">Nell'esempio seguente viene illustrato come utilizzare un oggetto <xref:System.Windows.Controls.TextBlock> per creare un'etichetta che esegue il wrapping di più righe di testo.</span><span class="sxs-lookup"><span data-stu-id="f8c4c-109">The following example shows how to use a <xref:System.Windows.Controls.TextBlock> to make a label that wraps several lines of text.</span></span>  
  
 [!code-xaml[LabelSnippet#5](~/samples/snippets/csharp/VS_Snippets_Wpf/LabelSnippet/CS/Pane1.xaml#5)]  
  
 <span data-ttu-id="f8c4c-110">**Aggiungere un tasto di scelta e una disposizione testo all'etichetta**</span><span class="sxs-lookup"><span data-stu-id="f8c4c-110">**Add an Access Key and Text Wrapping to Your Label**</span></span>  
  
 <span data-ttu-id="f8c4c-111">Se è necessario un oggetto <xref:System.Windows.Controls.Label> con un tasto di scelta, usare l' <xref:System.Windows.Controls.AccessText> elemento all'interno di <xref:System.Windows.Controls.Label> .</span><span class="sxs-lookup"><span data-stu-id="f8c4c-111">If you need a <xref:System.Windows.Controls.Label> that has an access key (mnemonic), use the <xref:System.Windows.Controls.AccessText> element that is inside the <xref:System.Windows.Controls.Label>.</span></span>  
  
 <span data-ttu-id="f8c4c-112">Controlli quali <xref:System.Windows.Controls.Label> ,, <xref:System.Windows.Controls.Button> <xref:System.Windows.Controls.RadioButton> , <xref:System.Windows.Controls.CheckBox> , <xref:System.Windows.Controls.MenuItem> , <xref:System.Windows.Controls.TabItem> , <xref:System.Windows.Controls.Expander> e dispongono di <xref:System.Windows.Controls.GroupBox> modelli di controllo predefiniti.</span><span class="sxs-lookup"><span data-stu-id="f8c4c-112">Controls such as <xref:System.Windows.Controls.Label>, <xref:System.Windows.Controls.Button>, <xref:System.Windows.Controls.RadioButton>, <xref:System.Windows.Controls.CheckBox>, <xref:System.Windows.Controls.MenuItem>, <xref:System.Windows.Controls.TabItem>, <xref:System.Windows.Controls.Expander>, and <xref:System.Windows.Controls.GroupBox> have default control templates.</span></span> <span data-ttu-id="f8c4c-113">Questi modelli contengono un <xref:System.Windows.Controls.ContentPresenter> .</span><span class="sxs-lookup"><span data-stu-id="f8c4c-113">These templates contain a <xref:System.Windows.Controls.ContentPresenter>.</span></span> <span data-ttu-id="f8c4c-114">Una delle proprietà che è possibile impostare in <xref:System.Windows.Controls.ContentPresenter> è <xref:System.Windows.Controls.ContentPresenter.RecognizesAccessKey%2A> = "true", che è possibile usare per specificare una chiave di accesso per il controllo.</span><span class="sxs-lookup"><span data-stu-id="f8c4c-114">One of the properties that you can set on the <xref:System.Windows.Controls.ContentPresenter> is <xref:System.Windows.Controls.ContentPresenter.RecognizesAccessKey%2A>="true", which you can use to specify an access key for the control.</span></span>  
  
 <span data-ttu-id="f8c4c-115">Nell'esempio seguente viene illustrato come creare un oggetto <xref:System.Windows.Controls.Label> che dispone di un tasto di accesso e supporta il ritorno a capo del testo.</span><span class="sxs-lookup"><span data-stu-id="f8c4c-115">The following example shows how to create a <xref:System.Windows.Controls.Label> that has an access key and supports text wrapping.</span></span> <span data-ttu-id="f8c4c-116">Per abilitare il ritorno a capo del testo, nell'esempio viene impostata la <xref:System.Windows.Controls.AccessText.TextWrapping%2A> proprietà e viene utilizzato un carattere di sottolineatura per specificare la chiave di accesso.</span><span class="sxs-lookup"><span data-stu-id="f8c4c-116">To enable text wrapping, the example sets the <xref:System.Windows.Controls.AccessText.TextWrapping%2A> property and uses an underline character to specify the access key.</span></span> <span data-ttu-id="f8c4c-117">Il carattere immediatamente successivo al carattere di sottolineatura è il tasto di scelta.</span><span class="sxs-lookup"><span data-stu-id="f8c4c-117">(The character that immediately follows the underline character is the access key.)</span></span>  
  
 [!code-xaml[LabelSnippet#4](~/samples/snippets/csharp/VS_Snippets_Wpf/LabelSnippet/CS/Pane1.xaml#4)]  
  
## <a name="see-also"></a><span data-ttu-id="f8c4c-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8c4c-118">See also</span></span>

- <span data-ttu-id="f8c4c-119">[Procedura: impostare la proprietà di destinazione di un controllo Label](/previous-versions/dotnet/netframework-3.5/ms752101(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="f8c4c-119">[How to: Set the Target Property of a Label](/previous-versions/dotnet/netframework-3.5/ms752101(v=vs.90))</span></span>
