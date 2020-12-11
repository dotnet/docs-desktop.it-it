---
title: Controllo DomainUpDown
ms.date: 03/30/2017
helpviewer_keywords:
- DomainUpDown control [Windows Forms]
- spin button control [Windows Forms], up-down controls
- up-down controls
- spin button control
- up-down controls [Windows Forms], spin button controls
ms.assetid: fb7cf017-e931-4a95-9d21-8caee4ee122a
ms.openlocfilehash: b538350a84e341d6b2759a7db28f8799f3777a86
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962908"
---
# <a name="domainupdown-control-windows-forms"></a>Controllo DomainUpDown (Windows Form)
Il controllo Windows Forms è <xref:System.Windows.Forms.DomainUpDown> simile a una combinazione di una casella di testo e una coppia di pulsanti per spostarsi verso l'alto o verso il basso in un elenco. Il controllo Visualizza e imposta una stringa di testo da un elenco di scelte. L'utente può selezionare la stringa facendo clic sui pulsanti su e giù per spostarsi in un elenco, premendo i tasti freccia su e giù oppure digitando una stringa corrispondente a un elemento dell'elenco. Un possibile utilizzo di questo controllo è la selezione di elementi da un elenco di nomi ordinati in ordine alfabetico. (Per ordinare l'elenco, impostare la <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> proprietà su `true` .) La funzione di questo controllo è molto simile alla casella di riepilogo o casella combinata, ma occupa molto spazio.  
  
 Le proprietà chiave del controllo sono <xref:System.Windows.Forms.DomainUpDown.Items%2A> , <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> e <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> . La <xref:System.Windows.Forms.DomainUpDown.Items%2A> proprietà contiene l'elenco di oggetti i cui valori di testo vengono visualizzati nel controllo. Se <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> è impostato su `false` , il controllo completa automaticamente il testo che l'utente digita e corrisponde a un valore nell'elenco. Se <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> è impostato su `true` , lo scorrimento oltre l'ultimo elemento consente di passare al primo elemento dell'elenco e viceversa. I metodi principali del controllo sono <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> e <xref:System.Windows.Forms.DomainUpDown.DownButton%2A> .  
  
 Questo controllo consente di visualizzare solo le stringhe di testo. Se si vuole un controllo che Visualizza i valori numerici, usare il <xref:System.Windows.Forms.NumericUpDown> controllo. Per ulteriori informazioni, vedere [controllo NumericUpDown](numericupdown-control-windows-forms.md) .  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Panoramica del controllo DomainUpDown](domainupdown-control-overview-windows-forms.md)  
 Introduce i concetti generali del <xref:System.Windows.Forms.DomainUpDown> controllo, che consente agli utenti di esplorare e selezionare da un elenco di stringhe di testo.  
  
 [Procedura: aggiungere elementi ai controlli DomainUpDown Windows Form a livello di codice](how-to-add-items-to-windows-forms-domainupdown-controls-programmatically.md)  
 Viene descritto come specificare le stringhe di testo da <xref:System.Windows.Forms.DomainUpDown> visualizzare nel controllo.  
  
 [Procedura: Rimuovere elementi dai controlli DomainUpDown di Windows Forms](how-to-remove-items-from-windows-forms-domainupdown-controls.md)  
 Viene descritto come eliminare elementi dal <xref:System.Windows.Forms.DomainUpDown> controllo nel codice.  
  
## <a name="reference"></a>Informazioni di riferimento  
 <xref:System.Windows.Forms.DomainUpDown>  
 Descrive la classe e fornisce i collegamenti a tutti i relativi membri.  
  
 <xref:System.Windows.Forms.NumericUpDown>  
 Descrive questa classe e contiene collegamenti a tutti i relativi membri.  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Controlli utilizzabili in Windows Form](controls-to-use-on-windows-forms.md)  
 Fornisce un elenco completo dei controlli Windows Form, con collegamenti alle informazioni sul relativo uso.
