---
title: Cenni preliminari sulla grafica
ms.date: 03/30/2017
ms.topic: overview
helpviewer_keywords:
- graphics [Windows Forms], using managed interface
- graphics [Windows Forms], about graphics
ms.assetid: a602aef8-a8c8-4c36-9816-74e7bad96a68
ms.openlocfilehash: e2cc534c32c24f3ac13248bd16b177205e480820
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96960655"
---
# <a name="overview-of-graphics"></a>Cenni preliminari sulla grafica
GDI+ è un Application Programming Interface (API) che costituisce il sottosistema del sistema operativo Microsoft Windows. GDI+ è responsabile della visualizzazione di informazioni su schermate e stampanti. Come suggerisce il nome, GDI+ è il successore di GDI, il Graphics Device Interface incluso nelle versioni precedenti di Windows.  
  
## <a name="managed-class-interface"></a>Interfaccia di classe gestita  
 L'API GDI+ viene esposta tramite un set di classi distribuite come codice gestito. Questo set di classi è denominato *interfaccia di classe gestita* per GDI+. Di seguito sono elencati gli spazi dei nomi che costituiscono l'interfaccia di classe gestita:  
  
- <xref:System.Drawing>  
  
- <xref:System.Drawing.Drawing2D>  
  
- <xref:System.Drawing.Imaging>  
  
- <xref:System.Drawing.Text>  
  
- <xref:System.Drawing.Printing>  
  
 Con un Graphics Device Interface, ad esempio GDI+, è possibile visualizzare informazioni su una schermata o una stampante senza che sia necessario preoccuparsi dei dettagli di un particolare dispositivo di visualizzazione. Il programmatore effettua chiamate ai metodi forniti dalle classi GDI+. Tali metodi, a loro volta, effettuano le chiamate appropriate a specifici driver di dispositivo. GDI+ isola l'applicazione dall'hardware grafico. È questo isolamento che consente a un programmatore di creare applicazioni indipendenti dal dispositivo.  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica sulla grafica](graphics-overview-windows-forms.md)
