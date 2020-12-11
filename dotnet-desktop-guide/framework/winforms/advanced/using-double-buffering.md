---
title: Utilizzo del doppio buffer
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], double buffering
- double buffering
- flicker [Windows Forms], reducing in Windows Forms
- buffering [Windows Forms], double buffering
ms.assetid: dc484e33-7101-4e4b-ada5-d3c96155fbcd
ms.openlocfilehash: 5b22336221c7bdda3c9dd7adf23308a2b0bad450
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952775"
---
# <a name="using-double-buffering"></a>Utilizzo del doppio buffer
È possibile utilizzare la grafica con doppio buffer per ridurre lo sfarfallio nelle applicazioni che contengono operazioni di disegno complesse. Il .NET Framework contiene supporto incorporato per il doppio buffer oppure è possibile gestire ed eseguire il rendering della grafica manualmente.  
  
## <a name="in-this-section"></a>Contenuto della sezione  
 [Grafica a doppio buffer](double-buffered-graphics.md)  
 Introduce il concetto di doppio buffer e delinea .NET Framework supporto.  
  
 [Procedura: Ridurre lo sfarfallio nella grafica con il doppio buffering per form e controlli](how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)  
 Viene illustrato come utilizzare il supporto di doppio buffer predefinito nel .NET Framework.  
  
 [Procedura: Gestire manualmente la grafica memorizzata nel buffer](how-to-manually-manage-buffered-graphics.md)  
 Viene illustrato come gestire il doppio buffer nelle applicazioni.  
  
 [Procedura: Eseguire il rendering manuale della grafica memorizzata nel buffer](how-to-manually-render-buffered-graphics.md)  
 Viene illustrato come eseguire il rendering di grafica con doppio buffer.  
  
## <a name="reference"></a>Informazioni di riferimento  
 <xref:System.Windows.Forms.Control.SetStyle%2A> Metodo di controllo che consente il doppio buffering.  
  
 <xref:System.Drawing.BufferedGraphicsContext> Fornisce metodi per la creazione di buffer grafici.  
  
 <xref:System.Drawing.BufferedGraphicsManager>  
 Fornisce l'accesso al contesto grafico memorizzato nel buffer per un dominio dell'applicazione.
