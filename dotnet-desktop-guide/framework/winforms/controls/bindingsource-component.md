---
title: Componente BindingSource
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [Windows Forms], Windows Forms
- Windows Forms, data binding control
- BindingSource component [Windows Forms]
ms.assetid: 3e2faf4c-f5b8-4fa6-9fbc-f59c37ec2fb9
ms.openlocfilehash: 54639edb512a8bc6c5909282d5e4c210439e2a6e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952596"
---
# <a name="bindingsource-component"></a>Componente BindingSource
Incapsula un'origine dati per l'associazione ai controlli.  
  
 Il componente <xref:System.Windows.Forms.BindingSource> ha due scopi. Innanzitutto fornisce un livello di riferimento indiretto durante l'associazione dei controlli di un form ai dati. Questo si ottiene associando il componente <xref:System.Windows.Forms.BindingSource> all'origine dati e quindi associando i controlli del form al componente <xref:System.Windows.Forms.BindingSource>. Tutte le altre interazioni con i dati, tra cui l'esplorazione, l'ordinamento, il filtro e l'aggiornamento, vengono eseguite mediante chiamate al componente <xref:System.Windows.Forms.BindingSource>.  
  
 In secondo luogo, il componente <xref:System.Windows.Forms.BindingSource> può fungere da origine dati fortemente tipizzata. Aggiungendo un tipo al componente <xref:System.Windows.Forms.BindingSource> con il metodo <xref:System.Windows.Forms.BindingSource.Add%2A>, viene creato un elenco di tale tipo.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Cenni preliminari sul componente BindingSource](bindingsource-component-overview.md)  
 Introduce i concetti generali del componente <xref:System.Windows.Forms.BindingSource>, che consente di associare un'origine dati a un controllo.  
  
 [Procedura: Associare i controlli di Windows Forms a valori di database DBNull](how-to-bind-windows-forms-controls-to-dbnull-database-values.md)  
 Mostra come gestire un valore <xref:System.DBNull> dell'origine dati con il componente <xref:System.Windows.Forms.BindingSource>.  
  
 [Procedura: Ordinare e filtrare i dati ADO.NET con il componente BindingSource di Windows Forms](sort-and-filter-ado-net-data-with-wf-bindingsource-component.md)  
 Illustra l'uso del componente <xref:System.Windows.Forms.BindingSource> per applicare criteri di ordinamento e filtri ai dati visualizzati.  
  
 [Procedura: Binding a un servizio Web tramite BindingSource di Windows Forms](how-to-bind-to-a-web-service-using-the-windows-forms-bindingsource.md)  
 Mostra come usare il componente <xref:System.Windows.Forms.BindingSource> per eseguire il binding a un servizio Web.  
  
 [Procedura: Gestire errori ed eccezioni relativi al data binding](how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)  
 Illustra l'uso del componente <xref:System.Windows.Forms.BindingSource> per gestire normalmente gli errori che si verificano in un'operazione di data binding.  
  
 [Procedura: Associare un controllo di Windows Forms a un tipo](how-to-bind-a-windows-forms-control-to-a-type.md)  
 Illustra l'uso di un componente <xref:System.Windows.Forms.BindingSource> per eseguire il binding a un tipo.  
  
 [Procedura: Associare un controllo di Windows Forms a un oggetto Factory](how-to-bind-a-windows-forms-control-to-a-factory-object.md)  
 Illustra l'uso di un componente <xref:System.Windows.Forms.BindingSource> per eseguire il binding a un oggetto o metodo factory.  
  
 [Procedura: Personalizzare l'aggiunta di elementi con BindingSource di Windows Forms](how-to-customize-item-addition-with-the-windows-forms-bindingsource.md)  
 Illustra l'uso di un componente <xref:System.Windows.Forms.BindingSource> per creare nuovi elementi e aggiungerli a un'origine dati.  
  
 [Procedura: Generare notifiche di modifica usando il metodo ResetItem di BindingSource](how-to-raise-change-notifications-using-the-bindingsource-resetitem-method.md)  
 Illustra l'uso di un componente <xref:System.Windows.Forms.BindingSource> per generare eventi di notifica di modifica per le origini dati che non supportano la notifica di modifica.  
  
 [Procedura: Generare notifiche di modifica usando BindingSource e l'interfaccia INotifyPropertyChanged](raise-change-notifications--bindingsource.md)  
 Illustra come usare un tipo che eredita da <xref:System.ComponentModel.INotifyPropertyChanged> con un controllo <xref:System.Windows.Forms.BindingSource>.  
  
 [Procedura: Riflettere gli aggiornamenti dell'origine dati in un controllo di Windows Forms con BindingSource](reflect-data-source-updates-in-a-wf-control-with-the-bindingsource.md)  
 Illustra come rispondere alle modifiche nell'origine dati con il componente <xref:System.Windows.Forms.BindingSource>.  
  
 [Procedura: Condividere i dati associati tra moduli usando il componente BindingSource](how-to-share-bound-data-across-forms-using-the-bindingsource-component.md)  
 Mostra come usare <xref:System.Windows.Forms.BindingSource> per associare più form alla stessa origine dati.  
  
## <a name="reference"></a>Informazioni di riferimento  
 <xref:System.Windows.Forms.BindingSource>  
 Fornisce la documentazione di riferimento per il componente <xref:System.Windows.Forms.BindingSource>.  
  
 <xref:System.Windows.Forms.BindingNavigator>  
 Fornisce la documentazione di riferimento per il controllo <xref:System.Windows.Forms.BindingNavigator>.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Data binding di Windows Form](../windows-forms-data-binding.md)  
 Contiene i collegamenti agli argomenti che descrivono l'architettura di data binding di Windows Form.  
  
 Vedere anche [Associazione di controlli ai dati in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).
