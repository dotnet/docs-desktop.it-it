---
title: Cenni preliminari sulle annotazioni
ms.date: 03/30/2017
ms.topic: overview
dev_langs:
- csharp
- vb
helpviewer_keywords:
- highlights [WPF]
- documents [WPF], annotations
- sticky notes [WPF]
ms.assetid: 716bf474-29bd-4c74-84a4-8e0744bdad62
ms.openlocfilehash: 8cfd5ddd1d90e9995081cd47211e1d9b0462b100
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967642"
---
# <a name="annotations-overview"></a><span data-ttu-id="0bf72-102">Cenni preliminari sulle annotazioni</span><span class="sxs-lookup"><span data-stu-id="0bf72-102">Annotations Overview</span></span>

<span data-ttu-id="0bf72-103">La scrittura di note o commenti su documenti cartacei è un'attività comune che diamo quasi per scontata.</span><span class="sxs-lookup"><span data-stu-id="0bf72-103">Writing notes or comments on paper documents is such a commonplace activity that we almost take it for granted.</span></span> <span data-ttu-id="0bf72-104">Queste note o commenti sono "annotazioni" aggiunte a un documento per contrassegnare informazioni o evidenziare elementi di interesse a cui fare riferimento in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="0bf72-104">These notes or comments are "annotations" that we add to a document to flag information or to highlight items of interest for later reference.</span></span> <span data-ttu-id="0bf72-105">Sebbene la scrittura di note su documenti stampati sia un'operazione semplice e comune, la capacità di aggiungere commenti personali ai documenti elettronici, se disponibile, è in genere molto limitata.</span><span class="sxs-lookup"><span data-stu-id="0bf72-105">Although writing notes on printed documents is easy and commonplace, the ability to add personal comments to electronic documents is typically very limited, if available at all.</span></span>  
  
 <span data-ttu-id="0bf72-106">In questo argomento vengono esaminati diversi tipi comuni di annotazioni, in particolare note e evidenziazioni e viene illustrato il modo in cui il framework delle annotazioni Microsoft semplifica questi tipi di annotazioni nelle applicazioni tramite i controlli di visualizzazione dei documenti Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="0bf72-106">This topic reviews several common types of annotations, specifically sticky notes and highlights, and illustrates how the Microsoft Annotations Framework facilitates these types of annotations in applications through the Windows Presentation Foundation (WPF) document viewing controls.</span></span>  <span data-ttu-id="0bf72-107">I controlli di visualizzazione dei documenti WPF che supportano le annotazioni includono <xref:System.Windows.Controls.FlowDocumentReader> e, nonché i <xref:System.Windows.Controls.FlowDocumentScrollViewer> controlli derivati da, <xref:System.Windows.Controls.Primitives.DocumentViewerBase> ad esempio <xref:System.Windows.Controls.DocumentViewer> e <xref:System.Windows.Controls.FlowDocumentPageViewer> .</span><span class="sxs-lookup"><span data-stu-id="0bf72-107">WPF document viewing controls that support annotations include <xref:System.Windows.Controls.FlowDocumentReader> and <xref:System.Windows.Controls.FlowDocumentScrollViewer>, as well as controls derived from <xref:System.Windows.Controls.Primitives.DocumentViewerBase> such as <xref:System.Windows.Controls.DocumentViewer> and <xref:System.Windows.Controls.FlowDocumentPageViewer>.</span></span>  

<a name="caf1_type_stickynotes"></a>

## <a name="sticky-notes"></a><span data-ttu-id="0bf72-108">Memo</span><span class="sxs-lookup"><span data-stu-id="0bf72-108">Sticky Notes</span></span>  

 <span data-ttu-id="0bf72-109">Normalmente una nota adesiva contiene informazioni scritte su un pezzetto di carta colorata che viene successivamente "attaccato" su un documento.</span><span class="sxs-lookup"><span data-stu-id="0bf72-109">A typical sticky note contains information written on a small piece of colored paper that is then "stuck" to a document.</span></span> <span data-ttu-id="0bf72-110">Le note adesive digitali forniscono funzionalità simili per i documenti elettronici, ma con la flessibilità aggiuntiva per includere molti altri tipi di contenuto, ad esempio il testo tipizzato, le note scritte a mano (ad esempio, i tratti di "input penna" di Tablet PC) o i collegamenti Web.</span><span class="sxs-lookup"><span data-stu-id="0bf72-110">Digital sticky notes provide similar functionality for electronic documents, but with the added flexibility to include many other types of content such as typed text, handwritten notes (for example, Tablet PC "ink" strokes), or Web links.</span></span>  
  
 <span data-ttu-id="0bf72-111">La figura seguente mostra alcuni esempi di annotazioni con evidenziatore, annotazioni di testo con Memo e annotazioni a penna di Memo.</span><span class="sxs-lookup"><span data-stu-id="0bf72-111">The following illustration shows some examples of highlight, text sticky note, and ink sticky note annotations.</span></span>  
  
 <span data-ttu-id="0bf72-112">![Annotazioni con evidenziatore, testo e a penna Sticky Notes](./media/caf-stickynote.jpg "CAF_StickyNote")</span><span class="sxs-lookup"><span data-stu-id="0bf72-112">![Highlight, text and ink sticky note annotations.](./media/caf-stickynote.jpg "CAF_StickyNote")</span></span>  
  
 <span data-ttu-id="0bf72-113">L'esempio seguente illustra il metodo che è possibile usare per abilitare il supporto delle annotazioni nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0bf72-113">The following example shows the method that you can use to enable annotation support in your application.</span></span>  
  
 [!code-csharp[DocViewerAnnotationsXml#DocViewXmlStartAnnotations](~/samples/snippets/csharp/VS_Snippets_Wpf/DocViewerAnnotationsXml/CSharp/Window1.xaml.cs#docviewxmlstartannotations)]
 [!code-vb[DocViewerAnnotationsXml#DocViewXmlStartAnnotations](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DocViewerAnnotationsXml/visualbasic/window1.xaml.vb#docviewxmlstartannotations)]  
  
<a name="caf1_type_callouts"></a>

## <a name="highlights"></a><span data-ttu-id="0bf72-114">Elementi di rilievo</span><span class="sxs-lookup"><span data-stu-id="0bf72-114">Highlights</span></span>  

 <span data-ttu-id="0bf72-115">Quando si eseguono annotazioni su un documento cartaceo, per attirare l'attenzione su elementi di interesse si usano metodi creativi, ad esempio sottolineando, evidenziando, cerchiando parole in una frase o tracciando segni o notazioni sul margine.</span><span class="sxs-lookup"><span data-stu-id="0bf72-115">People use creative methods to draw attention to items of interest when they mark up a paper document, such as underlining, highlighting, circling words in a sentence, or drawing marks or notations in the margin.</span></span>  <span data-ttu-id="0bf72-116">Le annotazioni evidenziate in Microsoft Annotations Framework forniscono una funzionalità simile per contrassegnare le informazioni visualizzate nei controlli di visualizzazione dei documenti WPF.</span><span class="sxs-lookup"><span data-stu-id="0bf72-116">Highlight annotations in Microsoft Annotations Framework provide a similar feature for marking up information displayed in WPF document viewing controls.</span></span>  
  
 <span data-ttu-id="0bf72-117">La figura seguente mostra un esempio di annotazione con evidenziatore.</span><span class="sxs-lookup"><span data-stu-id="0bf72-117">The following illustration shows an example of a highlight annotation.</span></span>  
  
 <span data-ttu-id="0bf72-118">![Annotazione con evidenziatore](./media/caf-callouts.png "CAF_Callouts")</span><span class="sxs-lookup"><span data-stu-id="0bf72-118">![Highlight Annotation](./media/caf-callouts.png "CAF_Callouts")</span></span>  
  
 <span data-ttu-id="0bf72-119">Gli utenti in genere creano annotazioni selezionando prima di tutto un testo o un elemento di interesse, quindi facendo clic con il pulsante destro del mouse per visualizzare una <xref:System.Windows.Controls.ContextMenu> delle opzioni di annotazione.</span><span class="sxs-lookup"><span data-stu-id="0bf72-119">Users typically create annotations by first selecting some text or an item of interest, and then right-clicking to display a <xref:System.Windows.Controls.ContextMenu> of annotation options.</span></span>  <span data-ttu-id="0bf72-120">Nell'esempio seguente viene illustrato l'oggetto che [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] è possibile utilizzare per dichiarare un <xref:System.Windows.Controls.ContextMenu> con i comandi indirizzati a cui gli utenti possono accedere per creare e gestire le annotazioni.</span><span class="sxs-lookup"><span data-stu-id="0bf72-120">The following example shows the [!INCLUDE[TLA#tla_xaml](../../../includes/tlasharptla-xaml-md.md)] you can use to declare a <xref:System.Windows.Controls.ContextMenu> with routed commands that users can access to create and manage annotations.</span></span>  
  
 [!code-xaml[DocViewerAnnotationsXps#CreateDeleteAnnotations](~/samples/snippets/csharp/VS_Snippets_Wpf/DocViewerAnnotationsXps/CSharp/Window1.xaml#createdeleteannotations)]  
  
<a name="caf1_framework_data_anchoring"></a>

## <a name="data-anchoring"></a><span data-ttu-id="0bf72-121">Ancoraggio dei dati</span><span class="sxs-lookup"><span data-stu-id="0bf72-121">Data Anchoring</span></span>  

 <span data-ttu-id="0bf72-122">Il framework delle annotazioni associa le annotazioni ai dati selezionati dall'utente, non solo a una posizione nella visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="0bf72-122">The Annotations Framework binds annotations to the data that the user selects, not just to a position on the display view.</span></span> <span data-ttu-id="0bf72-123">Pertanto, se la visualizzazione del documento cambia, ad esempio quando l'utente scorre o ridimensiona la finestra di visualizzazione, l'annotazione rimane nella selezione dati alla quale è associata.</span><span class="sxs-lookup"><span data-stu-id="0bf72-123">Therefore, if the document view changes, such as when the user scrolls or resizes the display window, the annotation stays with the data selection to which it is bound.</span></span> <span data-ttu-id="0bf72-124">Ad esempio, l'immagine seguente mostra un'annotazione effettuata dall'utente su una selezione di testo.</span><span class="sxs-lookup"><span data-stu-id="0bf72-124">For example, the following graphic illustrates an annotation that the user has made on a text selection.</span></span> <span data-ttu-id="0bf72-125">Quando la visualizzazione del documento cambia (scorre, viene ridimensionata o si sposta), l'annotazione con evidenziatore si sposta insieme alla selezione dati originale.</span><span class="sxs-lookup"><span data-stu-id="0bf72-125">When the document view changes (scrolls, resizes, scales, or otherwise moves), the highlight annotation moves with the original data selection.</span></span>  
  
 <span data-ttu-id="0bf72-126">![Ancoraggio dei dati dell'annotazione](./media/caf-dataanchoring.png "CAF_DataAnchoring")</span><span class="sxs-lookup"><span data-stu-id="0bf72-126">![Annotation Data Anchoring](./media/caf-dataanchoring.png "CAF_DataAnchoring")</span></span>  
  
<a name="matching_annotations_with_annotated_objects"></a>

## <a name="matching-annotations-with-annotated-objects"></a><span data-ttu-id="0bf72-127">Abbinamento delle annotazioni agli oggetti con annotazioni</span><span class="sxs-lookup"><span data-stu-id="0bf72-127">Matching Annotations with Annotated Objects</span></span>  

 <span data-ttu-id="0bf72-128">È possibile abbinare le annotazioni agli oggetti con annotazioni corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="0bf72-128">You can match annotations with the corresponding annotated objects.</span></span> <span data-ttu-id="0bf72-129">Si consideri, ad esempio, una semplice applicazione per la lettura di documenti con un riquadro dei commenti.</span><span class="sxs-lookup"><span data-stu-id="0bf72-129">For example, consider a simple document reader application that has a comments pane.</span></span> <span data-ttu-id="0bf72-130">Il riquadro dei commenti potrebbe essere una casella di riepilogo in cui viene visualizzato il testo di un elenco di annotazioni ancorate a un documento.</span><span class="sxs-lookup"><span data-stu-id="0bf72-130">The comments pane might be a list box that displays the text from a list of annotations that are anchored to a document.</span></span> <span data-ttu-id="0bf72-131">Se l'utente seleziona un elemento della casella di riepilogo, nell'applicazione viene visualizzato il paragrafo del documento a cui è ancorato l'oggetto di annotazione corrispondente.</span><span class="sxs-lookup"><span data-stu-id="0bf72-131">If the user selects an item in the list box, then the application brings into view the paragraph in the document that the corresponding annotation object is anchored to.</span></span>  
  
 <span data-ttu-id="0bf72-132">L'esempio seguente dimostra come implementare il gestore eventi di una casella di riepilogo di questo tipo che funge da riquadro dei commenti.</span><span class="sxs-lookup"><span data-stu-id="0bf72-132">The following example demonstrates how to implement the event handler of such a list box that serves as the comments pane.</span></span>  
  
 [!code-csharp[FlowDocumentAnnotatedViewer#Handler](~/samples/snippets/csharp/VS_Snippets_Wpf/FlowDocumentAnnotatedViewer/CSharp/Window1.xaml.cs#handler)]
 [!code-vb[FlowDocumentAnnotatedViewer#Handler](~/samples/snippets/visualbasic/VS_Snippets_Wpf/FlowDocumentAnnotatedViewer/visualbasic/window1.xaml.vb#handler)]  
  
 <span data-ttu-id="0bf72-133">Un altro scenario di esempio riguarda le applicazioni che consentono lo scambio di annotazioni e note permanenti tra i lettori di documenti tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="0bf72-133">Another example scenario involves applications that enable the exchange of annotations and sticky notes between document readers through email.</span></span> <span data-ttu-id="0bf72-134">Questa funzionalità consente a tali applicazioni di far spostare il lettore alla pagina contenente l'annotazione che viene scambiata.</span><span class="sxs-lookup"><span data-stu-id="0bf72-134">This feature enables these applications to navigate the reader to the page that contains the annotation that is being exchanged.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0bf72-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0bf72-135">See also</span></span>

- <xref:System.Windows.Controls.Primitives.DocumentViewerBase>
- <xref:System.Windows.Controls.DocumentViewer>
- <xref:System.Windows.Controls.FlowDocumentPageViewer>
- <xref:System.Windows.Controls.FlowDocumentScrollViewer>
- <xref:System.Windows.Controls.FlowDocumentReader>
- <xref:System.Windows.Annotations.IAnchorInfo>
- [<span data-ttu-id="0bf72-136">Schema annotazioni</span><span class="sxs-lookup"><span data-stu-id="0bf72-136">Annotations Schema</span></span>](annotations-schema.md)
- [<span data-ttu-id="0bf72-137">Cenni preliminari sull'oggetto ContextMenu</span><span class="sxs-lookup"><span data-stu-id="0bf72-137">ContextMenu Overview</span></span>](../controls/contextmenu-overview.md)
- [<span data-ttu-id="0bf72-138">Cenni preliminari sull'esecuzione di comandi</span><span class="sxs-lookup"><span data-stu-id="0bf72-138">Commanding Overview</span></span>](commanding-overview.md)
- [<span data-ttu-id="0bf72-139">Cenni preliminari sui documenti dinamici</span><span class="sxs-lookup"><span data-stu-id="0bf72-139">Flow Document Overview</span></span>](flow-document-overview.md)
- <span data-ttu-id="0bf72-140">[How to: Add a Command to a MenuItem (Procedura: Aggiungere un comando a un MenuItem)](/previous-versions/dotnet/netframework-3.5/ms741839(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="0bf72-140">[How to: Add a Command to a MenuItem](/previous-versions/dotnet/netframework-3.5/ms741839(v=vs.90))</span></span>
