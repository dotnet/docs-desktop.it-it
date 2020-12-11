---
title: Architettura del componente BindingSource
ms.date: 03/30/2017
helpviewer_keywords:
- BindingSource component [Windows Forms], architecture
- Windows Forms, data binding
- BindingSource component [Windows Forms], about BindingSource component
- data binding [Windows Forms], BindingSource component
ms.assetid: 7bc69c90-8a11-48b1-9336-3adab5b41591
ms.openlocfilehash: 54a23ba899ceb05701fe3580aefbb723c6b3f0fd
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952602"
---
# <a name="bindingsource-component-architecture"></a>Architettura del componente BindingSource
Con il <xref:System.Windows.Forms.BindingSource> componente è possibile associare in modo universale tutti i controlli Windows Forms alle origini dati.  
  
 Il <xref:System.Windows.Forms.BindingSource> componente semplifica il processo di associazione dei controlli a un'origine dati e offre i vantaggi seguenti rispetto ai data binding tradizionali:  
  
- Abilita l'associazione in fase di progettazione a oggetti business.  
  
- Incapsula <xref:System.Windows.Forms.CurrencyManager> la funzionalità ed espone <xref:System.Windows.Forms.CurrencyManager> gli eventi in fase di progettazione.  
  
- Semplifica la creazione di un elenco che supporta l' <xref:System.ComponentModel.IBindingList> interfaccia fornendo una notifica di modifica dell'elenco per le origini dati che non supportano in modo nativo la notifica di modifica dell'elenco.  
  
- Fornisce un punto di estendibilità per il <xref:System.ComponentModel.IBindingList.AddNew%2A?displayProperty=nameWithType> metodo.  
  
- Fornisce un livello di riferimento indiretto tra l'origine dati e il controllo. Questo riferimento indiretto è importante quando l'origine dati può cambiare in fase di esecuzione.  
  
- Interagisce con altri controlli Windows Forms correlati ai dati, in particolare i <xref:System.Windows.Forms.BindingNavigator> controlli e <xref:System.Windows.Forms.DataGridView> .  
  
 Per questi motivi, il <xref:System.Windows.Forms.BindingSource> componente è il modo migliore per associare i controlli Windows Forms alle origini dati.  
  
## <a name="bindingsource-features"></a>Funzionalità BindingSource  
 Il <xref:System.Windows.Forms.BindingSource> componente fornisce diverse funzionalità per l'associazione dei controlli ai dati. Grazie a queste funzionalità, è possibile implementare la maggior parte degli scenari di data binding con quasi nessuna codifica.  
  
 <xref:System.Windows.Forms.BindingSource>Questa operazione viene eseguita dal componente fornendo un'interfaccia coerente per l'accesso a molti tipi diversi di origini dati. Ciò significa che si utilizza la stessa procedura per l'associazione a qualsiasi tipo. Ad esempio, è possibile aggiungere la <xref:System.Windows.Forms.BindingSource.DataSource%2A> proprietà a un <xref:System.Data.DataSet> oggetto o a un oggetto business e in entrambi i casi si utilizza lo stesso set di proprietà, metodi ed eventi per modificare l'origine dati.  
  
 L'interfaccia coerente fornita dal <xref:System.Windows.Forms.BindingSource> componente semplifica notevolmente il processo di associazione dei dati ai controlli. Per i tipi di origine dati che forniscono notifiche di modifica, il <xref:System.Windows.Forms.BindingSource> componente comunica automaticamente le modifiche tra il controllo e l'origine dati. Per i tipi di origine dati che non forniscono notifiche di modifica, vengono forniti gli eventi che consentono di generare notifiche di modifica. Nell'elenco seguente vengono illustrate le funzionalità supportate dal <xref:System.Windows.Forms.BindingSource> componente:  
  
- Indirezione.  
  
- Gestione della valuta.  
  
- Origine dati sotto forma di elenco.  
  
- <xref:System.Windows.Forms.BindingSource> come <xref:System.ComponentModel.IBindingList> .  
  
- Creazione di elementi personalizzati.  
  
- Creazione di elementi transazionali.  
  
- <xref:System.Collections.IEnumerable> supporto.  
  
- Supporto in fase di progettazione.  
  
- <xref:System.Windows.Forms.ListBindingHelper>Metodi statici.  
  
- Ordinamento e filtro con l' <xref:System.ComponentModel.IBindingListView> interfaccia.  
  
- Integrazione con <xref:System.Windows.Forms.BindingNavigator> .  
  
### <a name="indirection"></a>Riferimento indiretto  
 Il <xref:System.Windows.Forms.BindingSource> componente fornisce un livello di riferimento indiretto tra un controllo e un'origine dati. Anziché associare un controllo direttamente a un'origine dati, è necessario associare il controllo a un oggetto <xref:System.Windows.Forms.BindingSource> e associare l'origine dati alla proprietà del <xref:System.Windows.Forms.BindingSource> componente <xref:System.Windows.Forms.BindingSource.DataSource%2A> .  
  
 Con questo livello di riferimento indiretto è possibile modificare l'origine dati senza reimpostare l'associazione del controllo. Ciò offre le funzionalità seguenti:  
  
- È possibile associare l'oggetto <xref:System.Windows.Forms.BindingSource> a origini dati diverse mantenendo le associazioni di controllo correnti.  
  
- È possibile modificare gli elementi nell'origine dati e inviare notifiche ai controlli associati. Per altre informazioni, vedere [procedura: riflettere gli aggiornamenti dell'origine dati in un controllo Windows Forms con BindingSource](reflect-data-source-updates-in-a-wf-control-with-the-bindingsource.md).  
  
- È possibile eseguire l'associazione a un <xref:System.Type> anziché a un oggetto in memoria. Per altre informazioni, vedere [procedura: associare un controllo Windows Forms a un tipo](how-to-bind-a-windows-forms-control-to-a-type.md). È quindi possibile eseguire l'associazione a un oggetto in fase di esecuzione.  
  
### <a name="currency-management"></a>Gestione della valuta  
 Il <xref:System.Windows.Forms.BindingSource> componente implementa l' <xref:System.Windows.Forms.ICurrencyManagerProvider> interfaccia per gestire la gestione della valuta. Con l' <xref:System.Windows.Forms.ICurrencyManagerProvider> interfaccia, è anche possibile accedere al gestore della valuta per un <xref:System.Windows.Forms.BindingSource> , oltre al gestore della valuta per un altro <xref:System.Windows.Forms.BindingSource> associato allo stesso <xref:System.Windows.Forms.BindingSource.DataMember%2A> .  
  
 Il <xref:System.Windows.Forms.BindingSource> componente incapsula la <xref:System.Windows.Forms.CurrencyManager> funzionalità ed espone le <xref:System.Windows.Forms.CurrencyManager> proprietà e gli eventi più comuni. Nella tabella seguente vengono descritti alcuni dei membri correlati alla gestione della valuta.  
  
 Proprietà<xref:System.Windows.Forms.ICurrencyManagerProvider.CurrencyManager%2A>  
 Ottiene il gestore valute associato a <xref:System.Windows.Forms.BindingSource> .  
  
 Metodo <xref:System.Windows.Forms.ICurrencyManagerProvider.GetRelatedCurrencyManager%2A>  
 Se è presente un altro <xref:System.Windows.Forms.BindingSource> associato al membro dati specificato, ottiene il gestore della valuta.  
  
 Proprietà<xref:System.Windows.Forms.BindingSource.Current%2A>  
 Ottiene l'elemento corrente dell'origine dati.  
  
 Proprietà<xref:System.Windows.Forms.BindingSource.Position%2A>  
 Ottiene o imposta la posizione corrente nell'elenco sottostante.  
  
 Metodo <xref:System.Windows.Forms.BindingSource.EndEdit%2A>  
 Applica le modifiche in sospeso all'origine dati sottostante.  
  
 Metodo <xref:System.Windows.Forms.BindingSource.CancelEdit%2A>  
 Annulla l'operazione di modifica corrente.  
  
### <a name="data-source-as-a-list"></a>Origine dati sotto forma di elenco  
 Il <xref:System.Windows.Forms.BindingSource> componente implementa le <xref:System.ComponentModel.IBindingListView> <xref:System.ComponentModel.ITypedList> interfacce e. Con questa implementazione, è possibile usare il <xref:System.Windows.Forms.BindingSource> componente stesso come origine dati, senza alcuna archiviazione esterna.  
  
 Quando il <xref:System.Windows.Forms.BindingSource> componente è associato a un'origine dati, espone l'origine dati come elenco.  
  
 La <xref:System.Windows.Forms.BindingSource.DataSource%2A> proprietà può essere impostata su diverse origini dati. Sono inclusi tipi, oggetti ed elenchi di tipi. L'origine dati risultante verrà esposta come elenco. Nella tabella seguente vengono illustrate alcune delle origini dati comuni e la valutazione dell'elenco risultante.  
  
|Proprietà DataSource|Elencare i risultati|  
|-------------------------|------------------|  
|Riferimento null (`Nothing` in Visual Basic)|Oggetto vuoto <xref:System.ComponentModel.IBindingList> di oggetti. L'aggiunta di un elemento consente di impostare l'elenco sul tipo dell'elemento aggiunto.|  
|Riferimento null ( `Nothing` in Visual Basic) con <xref:System.Windows.Forms.BindingSource.DataMember%2A> set|Non supportato. genera <xref:System.ArgumentException> .|  
|Tipo non elenco o oggetto di tipo "T"|Oggetto vuoto <xref:System.ComponentModel.IBindingList> di tipo "T".|  
|Istanza di matrice|Oggetto <xref:System.ComponentModel.IBindingList> contenente gli elementi della matrice.|  
|Istanza dell'interfaccia <xref:System.Collections.IEnumerable>|Oggetto <xref:System.ComponentModel.IBindingList> contenente gli <xref:System.Collections.IEnumerable> elementi|  
|Istanza di elenco che contiene il tipo "T"|<xref:System.ComponentModel.IBindingList>Istanza di che contiene il tipo "T".|  
  
 Inoltre, <xref:System.Windows.Forms.BindingSource.DataSource%2A> può essere impostato su altri tipi di elenco, ad esempio <xref:System.ComponentModel.IListSource> e <xref:System.ComponentModel.ITypedList> , e l'oggetto <xref:System.Windows.Forms.BindingSource> li gestirà in modo appropriato. In questo caso, il tipo contenuto nell'elenco deve avere un costruttore senza parametri.  
  
### <a name="bindingsource-as-an-ibindinglist"></a>BindingSource come IBindingList  
 Il <xref:System.Windows.Forms.BindingSource> componente fornisce i membri per l'accesso e la modifica dei dati sottostanti come <xref:System.ComponentModel.IBindingList> . Nella tabella seguente vengono descritti alcuni di questi membri.  
  
|Membro|Descrizione|  
|------------|-----------------|  
|Proprietà<xref:System.Windows.Forms.BindingSource.List%2A>|Ottiene l'elenco risultante dalla valutazione delle <xref:System.Windows.Forms.BindingSource.DataSource%2A> <xref:System.Windows.Forms.BindingSource.DataMember%2A> proprietà o.|  
|Metodo <xref:System.Windows.Forms.BindingSource.AddNew%2A>|Aggiunge un nuovo elemento all'elenco sottostante. Si applica alle origini dati che implementano l' <xref:System.ComponentModel.IBindingList> interfaccia e consentono l'aggiunta di elementi (ovvero la <xref:System.Windows.Forms.BindingSource.AllowNew%2A> proprietà è impostata su `true` ).|  
  
### <a name="custom-item-creation"></a>Creazione di elementi personalizzati  
 È possibile gestire l' <xref:System.Windows.Forms.BindingSource.AddingNew> evento per fornire la logica di creazione dell'elemento. L' <xref:System.Windows.Forms.BindingSource.AddingNew> evento si verifica prima che un nuovo oggetto venga aggiunto a <xref:System.Windows.Forms.BindingSource> . Questo evento viene generato dopo la <xref:System.Windows.Forms.BindingSource.AddNew%2A> chiamata del metodo, ma prima che il nuovo elemento venga aggiunto all'elenco sottostante. Gestendo questo evento, è possibile fornire un comportamento personalizzato per la creazione di elementi senza derivare dalla <xref:System.Windows.Forms.BindingSource> classe. Per altre informazioni, vedere [procedura: personalizzare l'aggiunta di elementi con il Windows Forms BindingSource](how-to-customize-item-addition-with-the-windows-forms-bindingsource.md).  
  
### <a name="transactional-item-creation"></a>Creazione di elementi transazionali  
 Il <xref:System.Windows.Forms.BindingSource> componente implementa l' <xref:System.ComponentModel.ICancelAddNew> interfaccia, che consente la creazione di elementi transazionali. Dopo la creazione provvisoria di un nuovo elemento tramite una chiamata a <xref:System.Windows.Forms.BindingSource.AddNew%2A> , è possibile eseguire il commit o il rollback dell'aggiunta nei modi seguenti:  
  
- Il <xref:System.ComponentModel.ICancelAddNew.EndNew%2A> metodo eseguirà il commit esplicito dell'addizione in sospeso.  
  
- L'esecuzione di un'altra operazione di raccolta, ad esempio l'inserimento, la rimozione o lo spostamento, eseguirà in modo implicito il commit dell'aggiunta in sospeso.  
  
- <xref:System.ComponentModel.ICancelAddNew.CancelNew%2A>Se non è già stato eseguito il commit del metodo, il metodo eseguirà il rollback dell'aggiunta in sospeso.  
  
### <a name="ienumerable-support"></a>Supporto di IEnumerable  
 Il <xref:System.Windows.Forms.BindingSource> componente consente di associare i controlli alle <xref:System.Collections.IEnumerable> origini dati. Con questo componente è possibile eseguire l'associazione a un'origine dati, ad esempio <xref:System.Data.SqlClient.SqlDataReader?displayProperty=nameWithType> .  
  
 Quando un' <xref:System.Collections.IEnumerable> origine dati viene assegnata al <xref:System.Windows.Forms.BindingSource> componente, <xref:System.Windows.Forms.BindingSource> Crea <xref:System.ComponentModel.IBindingList> e aggiunge il contenuto dell' <xref:System.Collections.IEnumerable> origine dati all'elenco.  
  
### <a name="design-time-support"></a>Supporto Design-Time  
 Non è possibile creare alcuni tipi di oggetto in fase di progettazione, ad esempio oggetti creati da una classe factory o oggetti restituiti da un servizio Web. Talvolta è necessario associare i controlli a questi tipi in fase di progettazione, anche se non è presente alcun oggetto in memoria a cui è possibile associare i controlli. È possibile, ad esempio, etichettare le intestazioni di colonna di un <xref:System.Windows.Forms.DataGridView> controllo con i nomi delle proprietà pubbliche del tipo personalizzato.  
  
 Per supportare questo scenario, il <xref:System.Windows.Forms.BindingSource> componente supporta l'associazione a un <xref:System.Type> . Quando si assegna un oggetto <xref:System.Type> alla <xref:System.Windows.Forms.BindingSource.DataSource%2A> proprietà, il <xref:System.Windows.Forms.BindingSource> componente crea un oggetto vuoto <xref:System.ComponentModel.BindingList%601> di <xref:System.Type> elementi. Tutti i controlli che successivamente vengono associati al <xref:System.Windows.Forms.BindingSource> componente verranno avvisati della presenza delle proprietà o dello schema del tipo in fase di progettazione o in fase di esecuzione. Per altre informazioni, vedere [procedura: associare un controllo Windows Forms a un tipo](how-to-bind-a-windows-forms-control-to-a-type.md).  
  
### <a name="static-listbindinghelper-methods"></a>Metodi ListBindingHelper statici  
 I <xref:System.Windows.Forms.BindingContext?displayProperty=nameWithType> <xref:System.Windows.Forms.CurrencyManager?displayProperty=nameWithType> tipi, e <xref:System.Windows.Forms.BindingSource> condividono la logica comune per generare un elenco da una `DataSource` / `DataMember` coppia. Questa logica comune è inoltre esposta pubblicamente per l'uso da parte degli autori di controlli e di terze parti nei `static` metodi seguenti:  
  
- <xref:System.Windows.Forms.ListBindingHelper.GetListItemProperties%2A>  
  
- <xref:System.Windows.Forms.ListBindingHelper.GetList%2A>.  
  
- <xref:System.Windows.Forms.ListBindingHelper.GetListName%2A>  
  
- <xref:System.Windows.Forms.ListBindingHelper.GetListItemType%2A>  
  
### <a name="sorting-and-filtering-with-the-ibindinglistview-interface"></a>Ordinamento e filtro con l'interfaccia IBindingListView  
 Il <xref:System.Windows.Forms.BindingSource> componente implementa l' <xref:System.ComponentModel.IBindingListView> interfaccia, che estende l' <xref:System.ComponentModel.IBindingList> interfaccia. <xref:System.ComponentModel.IBindingList>Offre l'ordinamento a colonna singola e <xref:System.ComponentModel.IBindingListView> offre funzionalità avanzate di ordinamento e filtro. Con <xref:System.ComponentModel.IBindingListView> è possibile ordinare e filtrare gli elementi nell'origine dati, se l'origine dati implementa anche una di queste interfacce. Il <xref:System.Windows.Forms.BindingSource> componente non fornisce un'implementazione di riferimento di questi membri. Al contrario, le chiamate vengono trasmesse all'elenco sottostante.  
  
 Nella tabella seguente vengono descritte le proprietà utilizzate per l'ordinamento e il filtro.  
  
|Membro|Descrizione|  
|------------|-----------------|  
|Proprietà<xref:System.Windows.Forms.BindingSource.Filter%2A>|Se l'origine dati è un <xref:System.ComponentModel.IBindingListView>, ottiene o imposta l'espressione usata per filtrare le righe da visualizzare.|  
|Proprietà<xref:System.Windows.Forms.BindingSource.Sort%2A>|Se l'origine dati è un <xref:System.ComponentModel.IBindingList>, ottiene o imposta un nome di colonna usato per l'ordinamento e il criterio di ordinamento.<br /><br /> -oppure-<br /><br /> Se l'origine dati è un oggetto <xref:System.ComponentModel.IBindingListView> e supporta l'ordinamento avanzato, ottiene più nomi di colonna usati per l'ordinamento e l'ordinamento|  
  
### <a name="integration-with-bindingnavigator"></a>Integrazione con BindingNavigator  
 È possibile utilizzare il <xref:System.Windows.Forms.BindingSource> componente per associare qualsiasi controllo Windows Forms a un'origine dati, ma il <xref:System.Windows.Forms.BindingNavigator> controllo è progettato specificamente per l'utilizzo con il <xref:System.Windows.Forms.BindingSource> componente. Il <xref:System.Windows.Forms.BindingNavigator> controllo fornisce un'interfaccia utente per il controllo dell' <xref:System.Windows.Forms.BindingSource> elemento corrente del componente. Per impostazione predefinita, il <xref:System.Windows.Forms.BindingNavigator> controllo fornisce pulsanti che corrispondono ai metodi di navigazione sul <xref:System.Windows.Forms.BindingSource> componente. Per altre informazioni, vedere [procedura: esplorare i dati con il controllo BindingNavigator Windows Forms](how-to-navigate-data-with-the-windows-forms-bindingnavigator-control.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.BindingNavigator>
- [Cenni preliminari sul componente BindingSource](bindingsource-component-overview.md)
- [Controllo BindingNavigator](bindingnavigator-control-windows-forms.md)
- [Data binding di Windows Form](../windows-forms-data-binding.md)
- [Controlli da usare in Windows Form](controls-to-use-on-windows-forms.md)
- [Procedura: Associare un controllo di Windows Forms a un tipo](how-to-bind-a-windows-forms-control-to-a-type.md)
- [Procedura: Riflettere gli aggiornamenti dell'origine dati in un controllo di Windows Forms con BindingSource](reflect-data-source-updates-in-a-wf-control-with-the-bindingsource.md)
