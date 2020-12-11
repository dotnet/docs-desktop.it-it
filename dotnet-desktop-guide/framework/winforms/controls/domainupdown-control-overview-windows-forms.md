---
title: Panoramica del controllo DomainUpDown
ms.date: 03/30/2017
f1_keywords:
- DomainUpDown
helpviewer_keywords:
- spin button control [Windows Forms], about spin button
- DomainUpDown control [Windows Forms], about DomainUpDown control
ms.assetid: 3f40f9c1-20ad-4331-b9b5-b0127eb36eb3
ms.openlocfilehash: 86703a96d4845414d043161e0efa67bfde9278db
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962917"
---
# <a name="domainupdown-control-overview-windows-forms"></a>Cenni preliminari sul controllo DomainUpDown (Windows Form)
Il <xref:System.Windows.Forms.DomainUpDown> controllo Windows Forms è essenzialmente una combinazione di una casella di testo e di una coppia di pulsanti per spostarsi verso l'alto o verso il basso in un elenco. Il controllo Visualizza e imposta una stringa di testo da un elenco di scelte. L'utente può selezionare la stringa facendo clic sui pulsanti su e giù per spostarsi in un elenco, premendo i tasti freccia su e giù oppure digitando una stringa corrispondente a un elemento dell'elenco. Un possibile utilizzo di questo controllo è la selezione di elementi da un elenco di nomi ordinati in ordine alfabetico.  
  
> [!NOTE]
> Per ordinare l'elenco, impostare la <xref:System.Windows.Forms.DomainUpDown.Sorted%2A> proprietà su `true` .  
  
 La funzione di questo controllo è molto simile alla casella di riepilogo o casella combinata, ma occupa molto spazio.  
  
## <a name="key-properties"></a>Proprietà chiave  
 Le proprietà chiave del controllo sono <xref:System.Windows.Forms.DomainUpDown.Items%2A> , <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> e <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> . La <xref:System.Windows.Forms.DomainUpDown.Items%2A> proprietà contiene l'elenco di oggetti i cui valori di testo vengono visualizzati nel controllo. Se <xref:System.Windows.Forms.UpDownBase.ReadOnly%2A> è impostato su `false` , il controllo completa automaticamente il testo che l'utente digita e corrisponde a un valore nell'elenco. Se <xref:System.Windows.Forms.DomainUpDown.Wrap%2A> è impostato su `true` , lo scorrimento oltre l'ultimo elemento consente di passare al primo elemento dell'elenco e viceversa. I metodi principali del controllo sono <xref:System.Windows.Forms.DomainUpDown.UpButton%2A> e <xref:System.Windows.Forms.DomainUpDown.DownButton%2A> .  
  
 Questo controllo consente di visualizzare solo le stringhe di testo. Se si vuole un controllo che Visualizza i valori numerici, usare il <xref:System.Windows.Forms.NumericUpDown> controllo. Per altre informazioni, vedere [Cenni preliminari sul controllo NumericUpDown](numericupdown-control-overview-windows-forms.md).  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.DomainUpDown>
- [Controllo DomainUpDown](domainupdown-control-windows-forms.md)
