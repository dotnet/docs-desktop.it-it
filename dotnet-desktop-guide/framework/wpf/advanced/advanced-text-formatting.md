---
title: Formattazione del testo avanzata
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- formatting [WPF]
- text [WPF]
- typography [WPF], text formatting
ms.assetid: f0a7986e-f5b2-485c-a27d-f8e922022212
ms.openlocfilehash: 662d01d892f6ee4ca8a9e19fca06e822cec00ff5
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96967453"
---
# <a name="advanced-text-formatting"></a>Formattazione del testo avanzata
Windows Presentation Foundation (WPF) fornisce un set di API affidabile per includere testo nell'applicazione. Il layout e [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] le API, ad esempio <xref:System.Windows.Controls.TextBlock> , forniscono gli elementi più comuni e di uso generale per la presentazione del testo. Il disegno di API, ad esempio <xref:System.Windows.Media.GlyphRunDrawing> e <xref:System.Windows.Media.FormattedText> , fornisce un mezzo per includere testo formattato nei disegni. Al livello più avanzato, WPF fornisce un motore di formattazione del testo estendibile per controllare ogni aspetto della presentazione del testo, ad esempio la gestione dell'archivio di testo, la gestione della formattazione delle esecuzioni del testo e la gestione di oggetti incorporati.  
  
 In questo argomento viene fornita un'introduzione alla formattazione del testo WPF. Si concentra sull'implementazione del client e sull'uso del motore di formattazione del testo WPF.  
  
> [!NOTE]
> Tutti gli esempi di codice all'interno di questo documento sono disponibili nell'esempio relativo alla [formattazione avanzata del testo](https://github.com/Microsoft/WPF-Samples/tree/master/PerMonitorDPI/TextFormatting).  

<a name="prereq"></a>
## <a name="prerequisites"></a>Prerequisiti  
 Questo argomento presuppone che l'utente abbia familiarità con le API di livello superiore usate per la presentazione del testo. La maggior parte degli scenari utente non richiede le API avanzate di formattazione del testo illustrate in questo argomento. Per un'introduzione alle diverse API di testo, vedere [documenti in WPF](documents-in-wpf.md).  
  
<a name="section1"></a>
## <a name="advanced-text-formatting"></a>Formattazione del testo avanzata  
 Il layout del testo e i [!INCLUDE[TLA2#tla_ui](../../../includes/tla2sharptla-ui-md.md)] controlli in WPF forniscono le proprietà di formattazione che consentono di includere facilmente testo formattato nell'applicazione. Questi controlli espongono numerose proprietà per la gestione della presentazione del testo, inclusi il carattere tipografico, le dimensioni e il colore. In circostanze normali, questi controlli sono in grado di gestire la maggior parte degli scenari di presentazione del testo nell'applicazione. Tuttavia, alcuni scenari avanzati richiedono il controllo dell'archiviazione del testo e della presentazione del testo. WPF fornisce un motore di formattazione del testo estendibile a questo scopo.  
  
 Le funzionalità avanzate di formattazione del testo disponibili in WPF sono costituite da un motore di formattazione del testo, da un archivio di testo, da sequenze di testo e da proprietà di formattazione. Il motore di formattazione del testo, <xref:System.Windows.Media.TextFormatting.TextFormatter> , crea righe di testo da utilizzare per la presentazione. Questa operazione viene eseguita avviando il processo di formattazione della riga e chiamando il formattatore di testo <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A> . Il formattatore di testo recupera le esecuzioni di testo dall'archivio di testo chiamando il metodo dell'archivio <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> . Gli <xref:System.Windows.Media.TextFormatting.TextRun> oggetti vengono quindi formati in <xref:System.Windows.Media.TextFormatting.TextLine> oggetti dal formattatore di testo e assegnati all'applicazione per l'ispezione o la visualizzazione.  
  
<a name="section2"></a>
## <a name="using-the-text-formatter"></a>Uso del formattatore di testo  
 <xref:System.Windows.Media.TextFormatting.TextFormatter> è il motore di formattazione del testo WPF e fornisce servizi per la formattazione e l'infrazione di righe di testo. Il formattatore di testo può gestire diversi formati di carattere del testo e stili di paragrafo e include il supporto per il layout di testo internazionale.  
  
 Diversamente da un'API di testo tradizionale, il <xref:System.Windows.Media.TextFormatting.TextFormatter> interagisce con un client di layout di testo tramite un set di metodi di callback. Richiede che il client fornisca questi metodi in un'implementazione della <xref:System.Windows.Media.TextFormatting.TextSource> classe. Nel diagramma seguente viene illustrata l'interazione del layout del testo tra l'applicazione client e <xref:System.Windows.Media.TextFormatting.TextFormatter> .  
  
 ![Diagramma del client del layout di testo e TextFormatter](./media/advanced-text-formatting/text-layout-textformatter-interaction.png)  
  
 Il formattatore di testo viene usato per recuperare le righe di testo formattato dall'archivio di testo, che è un'implementazione di <xref:System.Windows.Media.TextFormatting.TextSource> . Questa operazione viene eseguita creando prima un'istanza del formattatore di testo usando il <xref:System.Windows.Media.TextFormatting.TextFormatter.Create%2A> metodo. Questo metodo crea un'istanza del formattatore di testo e imposta i valori massimi di altezza e larghezza della riga. Non appena viene creata un'istanza del formattatore di testo, il processo di creazione della riga viene avviato chiamando il <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A> metodo. <xref:System.Windows.Media.TextFormatting.TextFormatter> richiama l'origine di testo per recuperare il testo e i parametri di formattazione per le esecuzioni del testo che formano una riga.  
  
 L'esempio seguente illustra il processo di formattazione di un archivio di testo. L' <xref:System.Windows.Media.TextFormatting.TextFormatter> oggetto viene utilizzato per recuperare righe di testo dall'archivio di testo e quindi formattare la riga di testo per il disegno in <xref:System.Windows.Media.DrawingContext> .  
  
 [!code-csharp[TextFormatterExample#100](~/samples/snippets/csharp/VS_Snippets_Wpf/TextFormatterExample/CSharp/Window1.xaml.cs#100)]
 [!code-vb[TextFormatterExample#100](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextFormatterExample/VisualBasic/Window1.xaml.vb#100)]  
  
<a name="section3"></a>
## <a name="implementing-the-client-text-store"></a>Implementazione dell'archivio di testo del client  
 Quando si estende il motore di formattazione del testo, è necessario implementare e gestire tutti gli aspetti dell'archivio di testo. Non si tratta di un'attività elementare. L'archivio di testo è responsabile del rilevamento delle proprietà delle sequenze di testo, delle proprietà dei paragrafi, degli oggetti incorporati e di altri contenuti simili. Fornisce anche il formattatore di testo con singoli <xref:System.Windows.Media.TextFormatting.TextRun> oggetti che il formattatore di testo usa per creare <xref:System.Windows.Media.TextFormatting.TextLine> oggetti.  
  
 Per gestire la virtualizzazione dell'archivio di testo, l'archivio di testo deve essere derivato da <xref:System.Windows.Media.TextFormatting.TextSource> . <xref:System.Windows.Media.TextFormatting.TextSource> definisce il metodo usato dal formattatore di testo per recuperare le sequenze di testo dall'archivio di testo. <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> Metodo utilizzato dal formattatore di testo per recuperare le esecuzioni di testo utilizzate nella formattazione della riga. La chiamata a <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> viene eseguita ripetutamente dal formattatore di testo fino a quando non si verifica una delle condizioni seguenti:  
  
- <xref:System.Windows.Media.TextFormatting.TextEndOfLine>Viene restituito un oggetto o una sottoclasse.  
  
- La larghezza accumulata delle esecuzioni di testo supera la lunghezza massima della riga specificata nella chiamata per creare il formattatore di testo o la chiamata al metodo del formattatore di testo <xref:System.Windows.Media.TextFormatting.TextFormatter.FormatLine%2A> .  
  
- Viene restituita una sequenza di nuova riga Unicode, ad esempio "CF", "LF" o "CRLF".  
  
<a name="section4"></a>
## <a name="providing-text-runs"></a>Inserimento delle sequenze di testo  
 Il fulcro del processo di formattazione del testo è rappresentato dall'interazione tra il formattatore di testo e l'archivio di testo. L'implementazione di <xref:System.Windows.Media.TextFormatting.TextSource> fornisce il formattatore di testo con gli <xref:System.Windows.Media.TextFormatting.TextRun> oggetti e le proprietà con cui formattare le esecuzioni di testo. Questa interazione viene gestita dal <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> metodo, che viene chiamato dal formattatore di testo.  
  
 Nella tabella seguente vengono illustrati alcuni degli <xref:System.Windows.Media.TextFormatting.TextRun> oggetti predefiniti.  
  
|Tipo di TextRun|Utilizzo|  
|------------------|-----------|  
|<xref:System.Windows.Media.TextFormatting.TextCharacters>|Sequenza di testo specializzata usata per passare nuovamente al formattatore di testo una rappresentazione dei glifi dei caratteri.|  
|<xref:System.Windows.Media.TextFormatting.TextEmbeddedObject>|Sequenza di testo specializzata usata per fornire contenuto nel quale la misurazione, l'hit testing e il disegno vengono eseguite come un'unica operazione, ad esempio un pulsante o un'immagine all'interno del testo.|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfLine>|Sequenza di testo specializzata usata per contrassegnare la fine di una riga.|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfParagraph>|Sequenza di testo specializzata usata per contrassegnare la fine di un paragrafo.|  
|<xref:System.Windows.Media.TextFormatting.TextEndOfSegment>|Sequenza di testo specializzata usata per contrassegnare la fine di un segmento, ad esempio per terminare l'ambito interessato da un' <xref:System.Windows.Media.TextFormatting.TextModifier> esecuzione precedente.|  
|<xref:System.Windows.Media.TextFormatting.TextHidden>|Sequenza di testo specializzata usata per contrassegnare un intervallo di caratteri nascosti.|  
|<xref:System.Windows.Media.TextFormatting.TextModifier>|Sequenza di testo specializzata usata per modificare le proprietà delle sequenze di testo nel relativo ambito. L'ambito si estende alla successiva <xref:System.Windows.Media.TextFormatting.TextEndOfSegment> sequenza di testo corrispondente o alla successiva <xref:System.Windows.Media.TextFormatting.TextEndOfParagraph> .|  
  
 Qualsiasi <xref:System.Windows.Media.TextFormatting.TextRun> oggetto predefinito può essere sottoclassato. Ciò consente all'origine del testo di fornire al formattatore di testo sequenze di testo che includono dati personalizzati.  
  
 Nell'esempio seguente viene illustrato un <xref:System.Windows.Media.TextFormatting.TextSource.GetTextRun%2A> metodo. Questo archivio di testo restituisce <xref:System.Windows.Media.TextFormatting.TextRun> gli oggetti al formattatore di testo per l'elaborazione.  
  
 [!code-csharp[TextFormatterExample#101](~/samples/snippets/csharp/VS_Snippets_Wpf/TextFormatterExample/CSharp/CustomTextSource.cs#101)]
 [!code-vb[TextFormatterExample#101](~/samples/snippets/visualbasic/VS_Snippets_Wpf/TextFormatterExample/VisualBasic/CustomTextSource.vb#101)]  
  
> [!NOTE]
> In questo esempio, l'archivio di testo fornisce a tutto il testo le stesse proprietà. Gli archivi di testo avanzati devono implementare una gestione personalizzata dell'estensione in modo da consentire ai singoli caratteri di avere proprietà diverse.  
  
<a name="section5"></a>
## <a name="specifying-formatting-properties"></a>Specifica delle proprietà di formattazione  
 <xref:System.Windows.Media.TextFormatting.TextRun> gli oggetti vengono formattati usando le proprietà fornite dall'archivio di testo. Queste proprietà sono disponibili in due tipi, <xref:System.Windows.Media.TextFormatting.TextParagraphProperties> e <xref:System.Windows.Media.TextFormatting.TextRunProperties> . <xref:System.Windows.Media.TextFormatting.TextParagraphProperties> gestire le proprietà inclusivi di paragrafo, ad esempio <xref:System.Windows.TextAlignment> e <xref:System.Windows.FlowDirection> . <xref:System.Windows.Media.TextFormatting.TextRunProperties> Proprietà che possono essere diverse per ogni sequenza di testo all'interno di un paragrafo, ad esempio il pennello in primo piano, <xref:System.Windows.Media.Typeface> e la dimensione del carattere. Per implementare il paragrafo personalizzato e i tipi di proprietà della sequenza di testo personalizzata, l'applicazione deve creare classi che derivano <xref:System.Windows.Media.TextFormatting.TextParagraphProperties> rispettivamente da e <xref:System.Windows.Media.TextFormatting.TextRunProperties> .  
  
## <a name="see-also"></a>Vedere anche

- [Funzionalità tipografiche di WPF](typography-in-wpf.md)
- [Documenti in WPF](documents-in-wpf.md)
