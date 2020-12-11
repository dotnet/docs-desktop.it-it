---
title: Cenni preliminari sulla classe Menu
ms.date: 03/30/2017
helpviewer_keywords:
- Menu control [WPF]
- controls [WPF], Menu
ms.assetid: 67df6de5-db96-4c71-b752-af90729a6537
ms.openlocfilehash: 53bc8f10e61b6e4e9e1f3b9a484340d9e2ec2a85
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969568"
---
# <a name="menu-overview"></a>Cenni preliminari sulla classe Menu
La <xref:System.Windows.Controls.Menu> classe consente di organizzare gli elementi associati a comandi e gestori eventi in ordine gerarchico. Ogni <xref:System.Windows.Controls.Menu> elemento contiene una raccolta di <xref:System.Windows.Controls.MenuItem> elementi.  

<a name="menu_control"></a>
## <a name="menu-control"></a>Controllo Menu  
 Il <xref:System.Windows.Controls.Menu> controllo presenta un elenco di elementi che specificano i comandi o le opzioni per un'applicazione. In genere, quando <xref:System.Windows.Controls.MenuItem> si fa clic su un sottomenu viene aperto un sottomenu o viene eseguita un'applicazione per eseguire un comando.  
  
<a name="creating_menus"></a>
## <a name="creating-menus"></a>Creazione di menu  
 Nell'esempio seguente viene creato un oggetto <xref:System.Windows.Controls.Menu> per modificare il testo in un oggetto <xref:System.Windows.Controls.TextBox> . <xref:System.Windows.Controls.Menu>Contiene <xref:System.Windows.Controls.MenuItem> gli oggetti che utilizzano le <xref:System.Windows.Controls.MenuItem.Command%2A> proprietà, e <xref:System.Windows.Controls.MenuItem.IsCheckable%2A> <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> e gli <xref:System.Windows.Controls.MenuItem.Checked> eventi, <xref:System.Windows.Controls.MenuItem.Unchecked> e <xref:System.Windows.Controls.MenuItem.Click> .  
  
 [!code-xaml[MenuItemCommandsAndEvents#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml#1)]  
  
 [!code-csharp[MenuItemCommandsAndEvents#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuItemCommandsAndEvents/CSharp/Window1.xaml.cs#2)]
 [!code-vb[MenuItemCommandsAndEvents#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MenuItemCommandsAndEvents/VisualBasic/Window1.xaml.vb#2)]  
  
<a name="menus_with_shortcutkeys"></a>
## <a name="menuitems-with-keyboard-shortcuts"></a>MenuItems con abbreviazioni da tastiera  
 Le scelte rapide da tastiera sono combinazioni di caratteri che è possibile immettere con la tastiera per richiamare i <xref:System.Windows.Controls.Menu> comandi. Il collegamento per **Copia** ad esempio è CTRL+C. Sono disponibili due proprietà da usare con i tasti di scelta rapida e le voci di menu, <xref:System.Windows.Controls.MenuItem.InputGestureText%2A> o <xref:System.Windows.Controls.MenuItem.Command%2A> .  
  
<a name="menus_inputgesturetext"></a>
### <a name="inputgesturetext"></a>InputGestureText  
 Nell'esempio seguente viene illustrato come utilizzare la <xref:System.Windows.Controls.MenuItem.InputGestureText%2A> proprietà per assegnare il testo del tasto di scelta rapida ai <xref:System.Windows.Controls.MenuItem> controlli. In questo modo nella voce di menu vengono inserite solo le abbreviazioni da tastiera.  Non associa il comando a <xref:System.Windows.Controls.MenuItem> . L'applicazione deve gestire l'input dell'utente per eseguire l'azione.  
  
 [!code-xaml[MenuEvent#6](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#6)]  
  
<a name="menus_commands"></a>
### <a name="command"></a>Comando  
 Nell'esempio seguente viene illustrato come utilizzare la <xref:System.Windows.Controls.MenuItem.Command%2A> proprietà per associare i comandi **Open** e **Save** ai <xref:System.Windows.Controls.MenuItem> controlli. Non solo la proprietà Command associa un comando a un oggetto <xref:System.Windows.Controls.MenuItem> , ma fornisce anche il testo del movimento di input da usare come collegamento.  
  
 [!code-xaml[MenuEvent#8](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuEvent/CSharp/Pane1.xaml#8)]  
  
 La <xref:System.Windows.Controls.MenuItem> classe dispone inoltre di una <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> proprietà che specifica l'elemento in cui si verifica il comando. Se <xref:System.Windows.Controls.MenuItem.CommandTarget%2A> non è impostato, l'elemento con lo stato attivo della tastiera riceve il comando. Per altre informazioni sui comandi vedere [Cenni preliminari sull'esecuzione di comandi](../advanced/commanding-overview.md).  
  
<a name="menu_styling"></a>
## <a name="menu-styling"></a>Applicazione di stili al testo  
 Con lo stile del controllo è possibile modificare in modo significativo l'aspetto e il comportamento dei <xref:System.Windows.Controls.Menu> controlli senza dover scrivere un controllo personalizzato. Oltre a impostare le proprietà visive, è anche possibile applicare un oggetto <xref:System.Windows.Style> a singole parti di un controllo, modificare il comportamento delle parti del controllo tramite proprietà o aggiungere altre parti o modificare il layout di un controllo. Negli esempi seguenti vengono illustrati diversi modi per aggiungere un oggetto <xref:System.Windows.Style> a un <xref:System.Windows.Controls.Menu> controllo.  
  
 Il primo esempio di codice definisce un oggetto <xref:System.Windows.Style> denominato `Simple` che Mostra come usare le impostazioni di sistema correnti nello stile. Il codice assegna il colore di `MenuHighlightBrush` come colore di sfondo del menu e `MenuTextBrush` come colore di primo piano del menu. Si noti l'uso delle chiavi di risorsa per assegnare i pennelli.  
  
 [!code-xaml[MenuStylesSnippet#1](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#1)]  
  
 Nell'esempio seguente vengono usati <xref:System.Windows.Trigger> elementi che consentono di modificare l'aspetto di un oggetto <xref:System.Windows.Controls.MenuItem> in risposta a eventi che si verificano in <xref:System.Windows.Controls.Menu> . Quando si sposta il puntatore del mouse su <xref:System.Windows.Controls.Menu> , il colore di primo piano e le caratteristiche del tipo di carattere delle voci di menu cambiano.  
  
 [!code-xaml[MenuStylesSnippet#2](~/samples/snippets/csharp/VS_Snippets_Wpf/MenuStylesSnippet/CS/app.xaml#2)]  
  
## <a name="see-also"></a>Vedere anche

- [Esempio di raccolta di controlli WPF](https://github.com/Microsoft/WPF-Samples/tree/master/Getting%20Started/ControlsAndLayout)
