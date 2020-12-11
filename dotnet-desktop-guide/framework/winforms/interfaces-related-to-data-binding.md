---
title: Interfacce correlate al data binding
ms.date: 03/30/2017
ms.topic: overview
helpviewer_keywords:
- data [Windows Forms], data-binding interfaces
- INotifyPropertyChanged interface
- IBindingListView interface
- IList interface [Windows Forms], Windows Forms data binding
- IBindingList interface [Windows Forms], Windows Forms data binding
- interfaces [Windows Forms], Windows Forms data binding
- IEditableObject interface [Windows Forms], Windows Forms data binding
- data binding [Windows Forms], interfaces
- IDataErrorInfo interface [Windows Forms], Windows Forms data binding
ms.assetid: 14e49a2e-3e46-47ca-b491-70d546333277
ms.openlocfilehash: 779b3f755d57014996af042d24236135293ce8ed
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96965629"
---
# <a name="interfaces-related-to-data-binding"></a>Interfacce correlate al data binding

Con ADO.NET è possibile creare molte strutture di dati diverse in base alle esigenze di binding dell'applicazione e ai dati in uso. Si consiglia di creare classi che forniscono o usano dati in Windows Forms. Questi oggetti possono offrire diversi livelli di funzionalità e complessità, dal data binding, all'offerta di supporto in fase di progettazione, al controllo degli errori, alla notifica delle modifiche o anche al supporto per un annullamento strutturato delle modifiche apportate ai dati.

## <a name="consumers-of-data-binding-interfaces"></a>Consumer delle interfacce di data binding

Nelle sezioni seguenti vengono descritti due gruppi di oggetti interfaccia. Nel primo gruppo sono elencate le interfacce implementate nell'origine dati dagli autori dell'origine dati. Queste interfacce sono progettate per essere usate dai consumer dell'origine dati, che sono nella maggior parte dei casi dei controlli o componenti di Windows Forms. Nel secondo gruppo sono elencate le interfacce destinate ad essere usate dagli autori di componenti. Gli autori di componenti usano queste interfacce al momento della creazione di un componente che supporta l'uso del data binding da parte del motore del data-binding di Windows Forms. È possibile implementare queste interfacce all'interno delle classi associate al modulo per consentire il data-binding; ogni caso presenta una classe che implementa un'interfaccia che abilita l'interazione con i dati. Gli strumenti dell'esperienza di progettazione dei dati di Visual Studio Rapid Application Development (RAD) sfruttano già questa funzionalità.

### <a name="interfaces-for-implementation-by-data-source-authors"></a>Interfacce per l'implementazione da parte degli autori dell'origine dati

Le interfacce seguenti sono progettate per essere usate dai controlli di Windows Forms:

- Interfaccia <xref:System.Collections.IList>

  Una classe che implementa l' <xref:System.Collections.IList> interfaccia può essere <xref:System.Array> , <xref:System.Collections.ArrayList> o <xref:System.Collections.CollectionBase> . Si tratta di elenchi indicizzati di elementi di tipo <xref:System.Object> . Questi elenchi devono contenere tipi omogenei, perché il primo elemento dell'indice determina il tipo. <xref:System.Collections.IList> sarebbe disponibile per l'associazione solo in fase di esecuzione.

  > [!NOTE]
  > Se si desidera creare un elenco di oggetti business per l'associazione con Windows Forms, è consigliabile utilizzare <xref:System.ComponentModel.BindingList%601> . <xref:System.ComponentModel.BindingList%601>È una classe estendibile che implementa le interfacce primarie necessarie per la data binding di Windows Forms bidirezionale.

- Interfaccia <xref:System.ComponentModel.IBindingList>

  Una classe che implementa l' <xref:System.ComponentModel.IBindingList> interfaccia fornisce un livello di funzionalità di data binding molto più elevato. Questa implementazione offre funzionalità di ordinamento di base e la notifica delle modifiche, sia quando gli elementi dell'elenco cambiano (ad esempio, il terzo elemento in un elenco di clienti include una modifica al campo indirizzo), sia quando l'elenco stesso cambia (ad esempio, il numero di elementi nell'elenco aumenta o diminuisce). La notifica della modifica è importante se si prevede di disporre di più controlli associati agli stessi dati e si desidera che le modifiche apportate in uno dei controlli si propaghi agli altri controlli associati.

  > [!NOTE]
  > La notifica delle modifiche è abilitata per l' <xref:System.ComponentModel.IBindingList> interfaccia tramite la <xref:System.ComponentModel.IBindingList.SupportsChangeNotification%2A> proprietà che, quando `true` , genera un <xref:System.ComponentModel.IBindingList.ListChanged> evento, che indica che l'elenco è stato modificato o che un elemento nell'elenco è stato modificato.

  Il tipo di modifica è descritto dalla <xref:System.ComponentModel.ListChangedType> proprietà del <xref:System.ComponentModel.ListChangedEventArgs> parametro. Di conseguenza, ogni volta che viene aggiornato il modello di dati, anche tutte le visualizzazioni dipendenti, ad esempio gli altri controlli associati alla stessa origine dati, verranno aggiornate. Tuttavia, gli oggetti contenuti all'interno dell'elenco dovranno inviare una notifica all'elenco quando cambiano, in modo che l'elenco possa generare l' <xref:System.ComponentModel.IBindingList.ListChanged> evento.

  > [!NOTE]
  > <xref:System.ComponentModel.BindingList%601>Fornisce un'implementazione generica dell' <xref:System.ComponentModel.IBindingList> interfaccia.

- Interfaccia <xref:System.ComponentModel.IBindingListView>

  Una classe che implementa l' <xref:System.ComponentModel.IBindingListView> interfaccia fornisce tutte le funzionalità di un'implementazione di <xref:System.ComponentModel.IBindingList> , nonché le funzionalità di filtro e ordinamento avanzato. Questa implementazione fornisce un filtro basato sulle stringhe, e un ordinamento a più colonne con coppie descrittore-direzione della proprietà.

- Interfaccia <xref:System.ComponentModel.IEditableObject>

  Una classe che implementa l' <xref:System.ComponentModel.IEditableObject> interfaccia consente a un oggetto di controllare quando le modifiche apportate a tale oggetto vengono rese permanenti. Questa implementazione fornisce i <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> <xref:System.ComponentModel.IEditableObject.EndEdit%2A> metodi, e <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> , che consentono di eseguire il rollback delle modifiche apportate all'oggetto. Di seguito è riportata una breve spiegazione del funzionamento dei <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> <xref:System.ComponentModel.IEditableObject.EndEdit%2A> metodi, e <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> e del modo in cui funzionano insieme tra loro per consentire un possibile rollback delle modifiche apportate ai dati:

  - Il <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> metodo segnala l'inizio di una modifica in un oggetto. Un oggetto che implementa questa interfaccia dovrà archiviare eventuali aggiornamenti dopo la chiamata al <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> metodo in modo che gli aggiornamenti possano essere rimossi se <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> viene chiamato il metodo. In data binding Windows Forms è possibile chiamare <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> più volte nell'ambito di una singola transazione di modifica, ad esempio,, <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> <xref:System.ComponentModel.IEditableObject.EndEdit%2A> . Le implementazioni di <xref:System.ComponentModel.IEditableObject> devono tenere traccia di se <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> è già stato chiamato e ignorare le chiamate successive a <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> . Poiché questo metodo può essere chiamato più volte, è importante che le chiamate successive non siano distruttive; ovvero, le <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> chiamate successive non possono eliminare gli aggiornamenti che sono stati apportati o modificare i dati salvati alla prima <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> chiamata.

  - Il <xref:System.ComponentModel.IEditableObject.EndEdit%2A> metodo effettua il push di tutte le modifiche apportate dopo che <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> è stato chiamato nell'oggetto sottostante, se l'oggetto è attualmente in modalità di modifica.

  - Il <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> metodo rimuove tutte le modifiche apportate all'oggetto.

  Per ulteriori informazioni sul funzionamento dei <xref:System.ComponentModel.IEditableObject.BeginEdit%2A> <xref:System.ComponentModel.IEditableObject.EndEdit%2A> metodi, e <xref:System.ComponentModel.IEditableObject.CancelEdit%2A> , vedere salvare i [dati nel database](/visualstudio/data-tools/save-data-back-to-the-database).

  Questa nozione transazionale della funzionalità dei dati viene utilizzata dal <xref:System.Windows.Forms.DataGridView> controllo.

- Interfaccia <xref:System.ComponentModel.ICancelAddNew>

  Una classe che implementa l' <xref:System.ComponentModel.ICancelAddNew> interfaccia in genere implementa l' <xref:System.ComponentModel.IBindingList> interfaccia e consente di eseguire il rollback di un'aggiunta apportata all'origine dati con il <xref:System.ComponentModel.IBindingList.AddNew%2A> metodo. Se l'origine dati implementa l' <xref:System.ComponentModel.IBindingList> interfaccia, è necessario che venga implementata anche l' <xref:System.ComponentModel.ICancelAddNew> interfaccia.

- Interfaccia <xref:System.ComponentModel.IDataErrorInfo>

  Una classe che implementa l' <xref:System.ComponentModel.IDataErrorInfo> interfaccia consente agli oggetti di offrire informazioni personalizzate sugli errori ai controlli associati:

  - La <xref:System.ComponentModel.IDataErrorInfo.Error%2A> proprietà restituisce il testo del messaggio di errore generale (ad esempio, "si è verificato un errore").

  - La <xref:System.ComponentModel.IDataErrorInfo.Item%2A> proprietà restituisce una stringa con il messaggio di errore specifico della colonna (ad esempio, "il valore nella `State` colonna non è valido").

- Interfaccia <xref:System.Collections.IEnumerable>

  Una classe che implementa l' <xref:System.Collections.IEnumerable> interfaccia viene in genere utilizzata da ASP.NET. Il supporto Windows Forms per questa interfaccia è disponibile solo tramite il <xref:System.Windows.Forms.BindingSource> componente.

  > [!NOTE]
  > Il <xref:System.Windows.Forms.BindingSource> componente copia tutti <xref:System.Collections.IEnumerable> gli elementi in un elenco separato a scopo di associazione.

- Interfaccia <xref:System.ComponentModel.ITypedList>

  Una classe Collections che implementa l' <xref:System.ComponentModel.ITypedList> interfaccia fornisce la possibilità di controllare l'ordine e il set di proprietà esposte al controllo associato.

  > [!NOTE]
  > Quando si implementa il <xref:System.ComponentModel.ITypedList.GetItemProperties%2A> metodo e la <xref:System.ComponentModel.PropertyDescriptor> matrice non è null, l'ultima voce nella matrice sarà il descrittore di proprietà che descrive la proprietà List che rappresenta un altro elenco di elementi.

- Interfaccia <xref:System.ComponentModel.ICustomTypeDescriptor>

  Una classe che implementa l' <xref:System.ComponentModel.ICustomTypeDescriptor> interfaccia fornisce informazioni dinamiche su se stessa. Questa interfaccia è simile a <xref:System.ComponentModel.ITypedList> ma viene utilizzata per gli oggetti anziché gli elenchi. Questa interfaccia viene utilizzata da <xref:System.Data.DataRowView> per proiettare lo schema delle righe sottostanti. Una semplice implementazione di <xref:System.ComponentModel.ICustomTypeDescriptor> viene fornita dalla <xref:System.ComponentModel.CustomTypeDescriptor> classe.

  > [!NOTE]
  > Per supportare l'associazione in fase di progettazione ai tipi che implementano <xref:System.ComponentModel.ICustomTypeDescriptor> , il tipo deve implementare anche <xref:System.ComponentModel.IComponent> ed esistere come istanza nel form.

- Interfaccia <xref:System.ComponentModel.IListSource>

  Una classe che implementa l' <xref:System.ComponentModel.IListSource> interfaccia consente l'associazione basata sull'elenco su oggetti non di elenco. Il <xref:System.ComponentModel.IListSource.GetList%2A> metodo di <xref:System.ComponentModel.IListSource> viene utilizzato per restituire un elenco associabile da un oggetto che non eredita da <xref:System.Collections.IList> . <xref:System.ComponentModel.IListSource> viene usato dalla <xref:System.Data.DataSet> classe.

- Interfaccia <xref:System.ComponentModel.IRaiseItemChangedEvents>

  Una classe che implementa l' <xref:System.ComponentModel.IRaiseItemChangedEvents> interfaccia è un elenco associabile che implementa anche l' <xref:System.ComponentModel.IBindingList> interfaccia. Questa interfaccia viene utilizzata per indicare se il tipo genera <xref:System.ComponentModel.IBindingList.ListChanged> eventi di tipo <xref:System.ComponentModel.ListChangedType.ItemChanged> tramite la relativa <xref:System.ComponentModel.IRaiseItemChangedEvents.RaisesItemChangedEvents%2A> Proprietà.

  > [!NOTE]
  > È necessario implementare <xref:System.ComponentModel.IRaiseItemChangedEvents> se l'origine dati fornisce la proprietà per elencare la conversione degli eventi descritta in precedenza e interagisce con il <xref:System.Windows.Forms.BindingSource> componente. In caso contrario, <xref:System.Windows.Forms.BindingSource> eseguirà anche la proprietà per elencare la conversione degli eventi, con conseguente rallentamento delle prestazioni.

- Interfaccia <xref:System.ComponentModel.ISupportInitialize>

  Un componente che implementa l' <xref:System.ComponentModel.ISupportInitialize> interfaccia trae vantaggio dalle ottimizzazioni batch per l'impostazione di proprietà e l'inizializzazione di proprietà co-dipendenti. <xref:System.ComponentModel.ISupportInitialize>Contiene due metodi:

  - <xref:System.ComponentModel.ISupportInitialize.BeginInit%2A> segnala l'avvio dell'inizializzazione di un oggetto.

  - <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> segnala la fine dell'inizializzazione dell'oggetto.

- Interfaccia <xref:System.ComponentModel.ISupportInitializeNotification>

  Un componente che implementa l' <xref:System.ComponentModel.ISupportInitializeNotification> interfaccia implementa anche l' <xref:System.ComponentModel.ISupportInitialize> interfaccia. Questa interfaccia consente di notificare ad altri <xref:System.ComponentModel.ISupportInitialize> componenti che l'inizializzazione è stata completata. L' <xref:System.ComponentModel.ISupportInitializeNotification> interfaccia contiene due membri:

  - <xref:System.ComponentModel.ISupportInitializeNotification.IsInitialized%2A> Restituisce un `boolean` valore che indica se il componente è inizializzato.

  - <xref:System.ComponentModel.ISupportInitializeNotification.Initialized> si verifica quando <xref:System.ComponentModel.ISupportInitialize.EndInit%2A> viene chiamato il metodo.

- Interfaccia <xref:System.ComponentModel.INotifyPropertyChanged>

  Una classe che implementa questa interfaccia è un tipo che genera un evento quando uno dei valori delle proprietà viene modificato. Questa interfaccia è progettata per sostituire il criterio di disporre di un evento di modifica per ogni proprietà di un controllo. Quando viene utilizzato in un <xref:System.ComponentModel.BindingList%601> oggetto, un oggetto business deve implementare l' <xref:System.ComponentModel.INotifyPropertyChanged> interfaccia e l'oggetto BindingList \` 1 convertirà <xref:System.ComponentModel.INotifyPropertyChanged.PropertyChanged> gli eventi in <xref:System.ComponentModel.BindingList%601.ListChanged> eventi di tipo <xref:System.ComponentModel.ListChangedType.ItemChanged> .

  > [!NOTE]
  > Affinché la notifica delle modifiche venga eseguita in un'associazione tra un client associato e un'origine dati, il tipo di origine dati associato deve implementare l' <xref:System.ComponentModel.INotifyPropertyChanged> interfaccia (scelta consigliata) oppure è possibile fornire eventi *PropertyName* `Changed` per il tipo associato, ma non è necessario eseguire entrambe le operazioni.

### <a name="interfaces-for-implementation-by-component-authors"></a>Interfacce per l'implementazione da parte degli autori del componente

Le interfacce seguenti sono progettate per l'uso da parte del motore di data-binding di Windows Forms:

- Interfaccia <xref:System.Windows.Forms.IBindableComponent>

  Una classe che implementa questa interfaccia è un componente di non-controllo che supporta il data-binding. Questa classe restituisce le associazioni dati e il contesto di associazione del componente tramite le <xref:System.Windows.Forms.IBindableComponent.DataBindings%2A> <xref:System.Windows.Forms.IBindableComponent.BindingContext%2A> proprietà e di questa interfaccia.

  > [!NOTE]
  > Se il componente eredita da <xref:System.Windows.Forms.Control> , non è necessario implementare l' <xref:System.Windows.Forms.IBindableComponent> interfaccia.

- Interfaccia <xref:System.Windows.Forms.ICurrencyManagerProvider>

  Una classe che implementa l' <xref:System.Windows.Forms.ICurrencyManagerProvider> interfaccia è un componente che fornisce un proprio oggetto <xref:System.Windows.Forms.CurrencyManager> per gestire le associazioni associate a questo particolare componente. L'accesso a custom <xref:System.Windows.Forms.CurrencyManager> viene fornito dalla <xref:System.Windows.Forms.ICurrencyManagerProvider.CurrencyManager%2A> Proprietà.

  > [!NOTE]
  > Una classe che eredita da <xref:System.Windows.Forms.Control> gestisce automaticamente le associazioni tramite la relativa <xref:System.Windows.Forms.Control.BindingContext%2A> proprietà, quindi i casi in cui è necessario implementare <xref:System.Windows.Forms.ICurrencyManagerProvider> sono piuttosto rari.

## <a name="see-also"></a>Vedere anche

- [Associazione dati e Windows Form](data-binding-and-windows-forms.md)
- [Procedura: Creare un controllo con associazione semplice in un Windows Form](how-to-create-a-simple-bound-control-on-a-windows-form.md)
- [Data binding di Windows Form](windows-forms-data-binding.md)
