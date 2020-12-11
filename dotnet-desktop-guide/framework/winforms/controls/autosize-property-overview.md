---
title: Cenni preliminari sulla proprietà AutoSize
ms.date: 03/30/2017
helpviewer_keywords:
- sizing [Windows Forms], automatic
- layout [Windows Forms], AutoSize
- automatic sizing
- AutoSizeMode property
ms.assetid: 62fd82a2-9565-4f65-925b-9d1e66dc4e7d
ms.openlocfilehash: eb87616c2ddcf9a4ab62245d365763ee57ffb964
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952644"
---
# <a name="autosize-property-overview"></a>Cenni preliminari sulla proprietà AutoSize
La <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà consente a un controllo di modificarne le dimensioni, se necessario, per ottenere il valore specificato dalla <xref:System.Windows.Forms.Control.PreferredSize%2A> Proprietà. Per modificare il comportamento di ridimensionamento per controlli specifici, impostare la `AutoSizeMode` Proprietà.

## <a name="autosize-behavior"></a>Comportamento di AutoSize
 Solo alcuni controlli supportano la <xref:System.Windows.Forms.Control.AutoSize%2A> Proprietà. Inoltre, alcuni controlli che supportano la <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà supportano anche la `AutoSizeMode` Proprietà.

 La <xref:System.Windows.Forms.Control.AutoSize%2A> Proprietà produce un comportamento leggermente diverso, a seconda del tipo di controllo specifico e del valore della `AutoSizeMode` proprietà, se la proprietà esiste. Nella tabella seguente vengono descritti i comportamenti sempre veri e viene fornita una breve descrizione di ognuno di essi:

|Comportamento sempre reale|Descrizione|
|--------------------------|-----------------|
|Il dimensionamento automatico è una funzionalità di run-time.|Ciò significa che non cresce né compatta un controllo e quindi non ha alcun effetto.|
|Se un controllo cambia dimensione, il valore della relativa <xref:System.Windows.Forms.Control.Location%2A> proprietà rimane sempre costante.|Quando il contenuto di un controllo ne determina la crescita, il controllo si estende verso destra e verso il basso. I controlli non crescono verso sinistra.|
|Le <xref:System.Windows.Forms.Control.Dock%2A> <xref:System.Windows.Forms.Control.Anchor%2A> proprietà e vengono rispettate quando <xref:System.Windows.Forms.Control.AutoSize%2A> è `true` .|Il valore della proprietà del controllo <xref:System.Windows.Forms.Control.Location%2A> viene regolato sul valore corretto.<br /><br /> **Nota** Il <xref:System.Windows.Forms.Label> controllo rappresenta l'eccezione a questa regola. Quando si imposta il valore della proprietà di un <xref:System.Windows.Forms.Label> controllo ancorato <xref:System.Windows.Forms.Control.AutoSize%2A> su `true` , il <xref:System.Windows.Forms.Label> controllo non viene esteso.|
|<xref:System.Windows.Forms.Control.MaximumSize%2A>Le proprietà e di un controllo <xref:System.Windows.Forms.Control.MinimumSize%2A> vengono sempre rispettate, indipendentemente dal valore della relativa <xref:System.Windows.Forms.Control.AutoSize%2A> Proprietà.|Le <xref:System.Windows.Forms.Control.MaximumSize%2A> <xref:System.Windows.Forms.Control.MinimumSize%2A> proprietà e non sono interessate dalla <xref:System.Windows.Forms.Control.AutoSize%2A> Proprietà.|
|Per impostazione predefinita, non sono impostate dimensioni minime.|Ciò significa che se un controllo è impostato su compatta in <xref:System.Windows.Forms.Control.AutoSize%2A> e non contiene contenuto, il valore della relativa <xref:System.Windows.Forms.Control.Size%2A> proprietà è 0, 0. In questo caso, il controllo ridurrà fino a un punto e non sarà immediatamente visibile.|
|Se un controllo non implementa il <xref:System.Windows.Forms.Control.GetPreferredSize%2A> metodo, il <xref:System.Windows.Forms.Control.GetPreferredSize%2A> metodo restituisce l'ultimo valore assegnato alla <xref:System.Windows.Forms.Control.Size%2A> Proprietà.|Ciò significa che l'impostazione <xref:System.Windows.Forms.Control.AutoSize%2A> di su `true` non avrà alcun effetto.|
|Un controllo in una <xref:System.Windows.Forms.TableLayoutPanel> cella viene sempre compattato per adattarsi alla cella fino a quando non viene raggiunto il relativo oggetto <xref:System.Windows.Forms.Control.MinimumSize%2A> .|Questa dimensione viene applicata come dimensione massima. Questa situazione non si verifica quando la cella fa parte di una <xref:System.Windows.Forms.SizeType.AutoSize> riga o di una colonna.|

## <a name="autosizemode-property"></a>Proprietà AutoSizeMode
 La `AutoSizeMode` proprietà fornisce un controllo più granulare sul <xref:System.Windows.Forms.Control.AutoSize%2A> comportamento predefinito. La `AutoSizeMode` proprietà specifica il modo in cui un controllo viene ridimensionato in base al relativo contenuto. Il contenuto, ad esempio, potrebbe essere il testo di un <xref:System.Windows.Forms.Button> controllo o i controlli figlio per un contenitore.

 Nella tabella seguente vengono illustrate le <xref:System.Windows.Forms.AutoSizeMode> Impostazioni e una descrizione del comportamento di ogni impostazione.

|Impostazione di AutoSizeMode|Comportamento|
|--------------------------|--------------|
|GrowAndShrink|Il controllo aumenta o diminuisce per comprenderne il contenuto.<br /><br /> I <xref:System.Windows.Forms.Control.MinimumSize%2A> <xref:System.Windows.Forms.Control.MaximumSize%2A> valori e vengono rispettati, ma il valore corrente della <xref:System.Windows.Forms.Control.Size%2A> proprietà viene ignorato.<br /><br /> Si tratta dello stesso comportamento dei controlli con la <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà e nessuna `AutoSizeMode` Proprietà.|
|GrowOnly|Il controllo aumenta quanto necessario per comprenderne il contenuto, ma non verrà compattato rispetto al valore specificato dalla relativa <xref:System.Windows.Forms.Control.Size%2A> Proprietà.<br /><br /> Questo è il valore predefinito per `AutoSizeMode`.|

## <a name="controls-that-support-the-autosize-property"></a>Controlli che supportano la proprietà AutoSize
 Nella tabella seguente sono elencati i controlli che supportano <xref:System.Windows.Forms.Control.AutoSize%2A> le `AutoSizeMode` proprietà e.

|Supporto per AutoSize|Tipo di controllo|
|----------------------|------------------|
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> Proprietà supportata.<br />-Nessuna `AutoSizeMode` Proprietà.|<xref:System.Windows.Forms.CheckBox><br /><br /> <xref:System.Windows.Forms.DomainUpDown><br /><br /> <xref:System.Windows.Forms.Label><br /><br /> <xref:System.Windows.Forms.LinkLabel><br /><br /> <xref:System.Windows.Forms.MaskedTextBox> ( <xref:System.Windows.Forms.TextBox> base)<br /><br /> <xref:System.Windows.Forms.NumericUpDown><br /><br /> <xref:System.Windows.Forms.RadioButton><br /><br /> <xref:System.Windows.Forms.TextBox><br /><br /> <xref:System.Windows.Forms.TrackBar>|
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> Proprietà supportata.<br />-   `AutoSizeMode` Proprietà supportata.|<xref:System.Windows.Forms.Button><br /><br /> <xref:System.Windows.Forms.CheckedListBox><br /><br /> <xref:System.Windows.Forms.FlowLayoutPanel><br /><br /> <xref:System.Windows.Forms.Form><br /><br /> <xref:System.Windows.Forms.GroupBox><br /><br /> <xref:System.Windows.Forms.Panel><br /><br /> <xref:System.Windows.Forms.TableLayoutPanel>|
|-Nessuna <xref:System.Windows.Forms.Control.AutoSize%2A> Proprietà.|<xref:System.Windows.Forms.CheckedListBox><br /><br /> <xref:System.Windows.Forms.ComboBox><br /><br /> <xref:System.Windows.Forms.DataGridView><br /><br /> <xref:System.Windows.Forms.DateTimePicker><br /><br /> <xref:System.Windows.Forms.ListBox><br /><br /> <xref:System.Windows.Forms.ListView><br /><br /> <xref:System.Windows.Forms.MaskedTextBox><br /><br /> <xref:System.Windows.Forms.MonthCalendar><br /><br /> <xref:System.Windows.Forms.ProgressBar><br /><br /> <xref:System.Windows.Forms.PropertyGrid><br /><br /> <xref:System.Windows.Forms.RichTextBox><br /><br /> <xref:System.Windows.Forms.SplitContainer><br /><br /> <xref:System.Windows.Forms.TabControl><br /><br /> <xref:System.Windows.Forms.TabPage><br /><br /> <xref:System.Windows.Forms.TreeView><br /><br /> <xref:System.Windows.Forms.WebBrowser><br /><br /> <xref:System.Windows.Forms.ScrollBar>|

## <a name="autosize-in-the-design-environment"></a>Ridimensiona automaticamente nell'ambiente di progettazione
 Nella tabella seguente viene descritto il comportamento di ridimensionamento di un controllo in fase di progettazione, in base al valore delle <xref:System.Windows.Forms.Control.AutoSize%2A> `AutoSizeMode` proprietà e.

 Eseguire l'override della <xref:System.Windows.Forms.Design.ControlDesigner.SelectionRules%2A> proprietà per determinare se un determinato controllo è in uno stato ridimensionabile dall'utente. Nella tabella seguente, "Can" significa <xref:System.Windows.Forms.Design.SelectionRules.Moveable> solo che "Can" significa <xref:System.Windows.Forms.Design.SelectionRules.AllSizeable> e <xref:System.Windows.Forms.Design.SelectionRules.Moveable> .

|Impostazioni AutoSize|Movimento di ridimensionamento in fase di progettazione|
|-----------------------|---------------------------------|
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> = `true`<br />-Nessuna `AutoSizeMode` Proprietà.|L'utente non può ridimensionare il controllo in fase di progettazione, ad eccezione dei controlli seguenti:<br /><br /> -   <xref:System.Windows.Forms.TextBox><br />-   <xref:System.Windows.Forms.MaskedTextBox><br />-   <xref:System.Windows.Forms.RichTextBox><br />-   <xref:System.Windows.Forms.TrackBar>|
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> = `true`<br />-   `AutoSizeMode` = <xref:System.Windows.Forms.AutoSizeMode.GrowAndShrink>|L'utente non può ridimensionare il controllo in fase di progettazione.|
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> = `true`<br />-   `AutoSizeMode` = <xref:System.Windows.Forms.AutoSizeMode.GrowOnly>|L'utente può ridimensionare il controllo in fase di progettazione. Quando la <xref:System.Windows.Forms.Control.Size%2A> proprietà è impostata, l'utente può solo aumentare le dimensioni del controllo.|
|-   <xref:System.Windows.Forms.Control.AutoSize%2A> = `false`, o <xref:System.Windows.Forms.Control.AutoSize%2A> la proprietà è nascosta.|L'utente può ridimensionare il controllo in fase di progettazione.|

> [!NOTE]
> Per ottimizzare la produttività, il Progettazione Windows Form in Visual Studio nasconde la <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà della <xref:System.Windows.Forms.Form> classe. In fase di progettazione, il form si comporta come se la <xref:System.Windows.Forms.Control.AutoSize%2A> Proprietà fosse impostata su `false` , indipendentemente dall'impostazione effettiva. In fase di esecuzione non viene eseguito alcun alloggio speciale e la <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà viene applicata come specificato dall'impostazione della proprietà.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.Control.AutoSize%2A>
- <xref:System.Windows.Forms.Control.PreferredSize%2A>
- <xref:System.Windows.Forms.Control.GetPreferredSize%2A>
