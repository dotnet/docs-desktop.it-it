---
title: Sicurezza delle proprietà di dipendenza
ms.date: 03/30/2017
helpviewer_keywords:
- wrappers [WPF], access
- wrappers [WPF], security
- dependency properties [WPF], security
- security [WPF], wrappers
- validation [WPF], dependency properties
- dependency properties [WPF], access
- security [WPF], dependency properties
ms.assetid: d10150ec-90c5-4571-8d35-84bafa2429a4
ms.openlocfilehash: 4bb3f0e4264c8de2513fc757f5e1a5a2efdd541c
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96966493"
---
# <a name="dependency-property-security"></a>Sicurezza delle proprietà di dipendenza
Le proprietà di dipendenza in genere devono essere considerate come proprietà pubbliche. A causa della natura stessa del sistema di proprietà di [!INCLUDE[TLA#tla_winclient](../../../includes/tlasharptla-winclient-md.md)], è impossibile avere delle garanzie di sicurezza sul valore di una proprietà di dipendenza.  

<a name="AccessSecurity"></a>
## <a name="access-and-security-of-wrappers-and-dependency-properties"></a>Accesso e sicurezza delle proprietà wrapper e di dipendenza  
 In genere, le proprietà di dipendenza vengono implementate insieme alle proprietà "wrapper" Common Language Runtime (CLR) che semplificano il recupero o l'impostazione della proprietà da un'istanza di. Tuttavia, i wrapper sono solo metodi pratici che implementano le <xref:System.Windows.DependencyObject.GetValue%2A> chiamate statiche e sottostanti <xref:System.Windows.DependencyObject.SetValue%2A> utilizzate quando si interagisce con le proprietà di dipendenza. Considerandola in un altro modo, le proprietà vengono esposte come proprietà Common Language Runtime (CLR) che vengono supportate da una proprietà di dipendenza anziché da un campo privato. I meccanismi di sicurezza applicati ai wrapper non sono paralleli al comportamento del sistema di proprietà e all'accesso della proprietà di dipendenza sottostante. L'inserimento di una richiesta di sicurezza sul wrapper impedisce solo l'utilizzo del metodo convenience, ma non impedisce le chiamate a <xref:System.Windows.DependencyObject.GetValue%2A> o <xref:System.Windows.DependencyObject.SetValue%2A> . Analogamente, inserendo un livello di accesso protetto o privato sui wrapper non viene garantita alcuna sicurezza effettiva.  
  
 Se si scrivono proprietà di dipendenza personalizzate, è necessario dichiarare i wrapper e il <xref:System.Windows.DependencyProperty> campo identificatore come membri pubblici, in modo che i chiamanti non ottengano informazioni fuorvianti sul livello di accesso reale della proprietà, a causa dell'implementazione dell'archivio come proprietà di dipendenza.  
  
 Per una proprietà di dipendenza personalizzata, è possibile registrare la proprietà come proprietà di dipendenza di sola lettura e questo fornisce un metodo efficace per impedire che una proprietà venga impostata da chiunque che non contenga un riferimento a <xref:System.Windows.DependencyPropertyKey> per la proprietà. Per altre informazioni, vedere [Proprietà di dipendenza di sola lettura](read-only-dependency-properties.md).  
  
> [!NOTE]
> La dichiarazione di un <xref:System.Windows.DependencyProperty> campo identificatore privato non è consentita e può essere usata per ridurre lo spazio dei nomi esposto immediatamente di una classe personalizzata, ma tale proprietà non deve essere considerata "privata" nello stesso senso delle definizioni di linguaggio Common Language Runtime (CLR) che definiscono il livello di accesso, per i motivi descritti nella sezione successiva.  
  
<a name="PropertySystemExposure"></a>
## <a name="property-system-exposure-of-dependency-properties"></a>Esposizione di proprietà di dipendenza del sistema di proprietà  
 Non è in genere utile ed è potenzialmente fuorviante dichiarare <xref:System.Windows.DependencyProperty> come un livello di accesso diverso da Public. L'impostazione di questo livello di accesso impedisce solo che qualcuno possa ottenere un riferimento all'istanza dalla classe dichiarante. Esistono tuttavia diversi aspetti del sistema di proprietà che restituiscono un oggetto <xref:System.Windows.DependencyProperty> come mezzo per identificare una determinata proprietà in un'istanza di una classe o un'istanza della classe derivata e questo identificatore è ancora utilizzabile in una <xref:System.Windows.DependencyObject.SetValue%2A> chiamata anche se l'identificatore statico originale viene dichiarato come non pubblico. Inoltre, <xref:System.Windows.DependencyObject.OnPropertyChanged%2A> i metodi virtuali ricevono informazioni di qualsiasi proprietà di dipendenza esistente che ha modificato il valore. Inoltre, il <xref:System.Windows.DependencyObject.GetLocalValueEnumerator%2A> metodo restituisce gli identificatori per qualsiasi proprietà nelle istanze con un valore impostato localmente.  
  
### <a name="validation-and-security"></a>Convalida e sicurezza  
 Se si applica una richiesta a un oggetto <xref:System.Windows.DependencyProperty.ValidateValueCallback%2A> e si prevede che l'errore di convalida in caso di errore della richiesta per impedire l'impostazione di una proprietà non è un meccanismo di sicurezza adeguato. L'invalidamento set-value applicato tramite <xref:System.Windows.DependencyProperty.ValidateValueCallback%2A> può anche essere eliminato da chiamanti malintenzionati, se tali chiamanti operano all'interno del dominio applicazione.  
  
## <a name="see-also"></a>Vedere anche

- [Proprietà di dipendenza personalizzate](custom-dependency-properties.md)
