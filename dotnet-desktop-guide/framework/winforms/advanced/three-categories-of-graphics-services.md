---
title: Tre categorie di servizi grafici
ms.date: 03/30/2017
helpviewer_keywords:
- imaging
- graphics [Windows Forms], categories
- 2D vector graphics
- vector graphics
- typography
ms.assetid: 068c0ef3-f6ee-4d58-a7b6-eb2531ead408
ms.openlocfilehash: fa7391ef0f7170ddb9d9d24aa5a1a03635bf46e0
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952764"
---
# <a name="three-categories-of-graphics-services"></a>Tre categorie di servizi grafici
Le Offerte grafiche in Windows Forms rientrano nelle tre categorie generali seguenti:  
  
- Grafica vettoriale bidimensionale (2D)  
  
- Creazione delle immagini  
  
- Tipografia  
  
## <a name="2d-vector-graphics"></a>Grafica vettoriale 2D  
 La grafica vettoriale bidimensionale, ad esempio linee, curve e figure, è primitiva specificata da set di punti in un sistema di coordinate. Ad esempio, una linea retta viene specificata dai relativi due endpoint e un rettangolo viene specificato da un punto che fornisce la posizione dell'angolo superiore sinistro e una coppia di numeri che ne assegna la larghezza e l'altezza. Un percorso semplice viene specificato da una matrice di punti connessi da linee rette. Una spline di Bézier è una curva sofisticata specificata da quattro punti di controllo.  
  
 GDI+ fornisce le classi e le strutture in cui sono archiviate le informazioni sulle primitive, le classi in cui vengono archiviate le informazioni sulla modalità di disegno delle primitive e le classi che eseguono effettivamente il disegno. Ad esempio, la <xref:System.Drawing.Rectangle> struttura archivia la posizione e le dimensioni di un rettangolo; la <xref:System.Drawing.Pen> classe archivia le informazioni sul colore della linea, lo spessore della linea e lo stile della linea e la <xref:System.Drawing.Graphics> classe dispone di metodi per disegnare linee, rettangoli, percorsi e altre figure. Sono inoltre disponibili diverse <xref:System.Drawing.Brush> classi in cui vengono archiviate le informazioni sulla modalità con cui i percorsi e le figure chiuse verranno riempiti con colori o schemi.  
  
 È possibile registrare un'immagine vettoriale, ovvero una sequenza di comandi grafici, in un metafile. GDI+ fornisce la <xref:System.Drawing.Imaging.Metafile> classe per la registrazione, la visualizzazione e il salvataggio di metafile. Con le <xref:System.Drawing.Imaging.MetafileHeader> <xref:System.Drawing.Imaging.MetaHeader> classi e è possibile esaminare i dati archiviati in un'intestazione di metafile.  
  
## <a name="imaging"></a>Creazione delle immagini  
 Alcuni tipi di immagini sono difficili o impossibili da visualizzare con le tecniche di grafica vettoriale. Ad esempio, le immagini sui pulsanti della barra degli strumenti e le immagini visualizzate come icone sono difficili da specificare come raccolte di linee e curve. Una fotografia digitale ad alta risoluzione di uno stadio di baseball affollato è ancora più difficile da creare con le tecniche vettoriali. Le immagini di questo tipo vengono archiviate come bitmap, ovvero matrici di numeri che rappresentano i colori dei singoli punti sullo schermo. GDI+ fornisce la <xref:System.Drawing.Bitmap> classe per la visualizzazione, la modifica e il salvataggio di bitmap.  
  
## <a name="typography"></a>Tipografia  
 Tipografia è la visualizzazione del testo in un'ampia gamma di tipi di carattere, dimensioni e stili. GDI+ fornisce un supporto completo per questa attività complessa. Una delle nuove funzionalità di GDI+ è l'anti-aliasing dei subpixel, che fornisce un aspetto più uniforme del testo visualizzato sullo schermo LCD.  
  
 Windows Forms offre inoltre la possibilità di creare testo con funzionalità GDI nella relativa <xref:System.Windows.Forms.TextRenderer> classe.  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica sulla grafica](graphics-overview-windows-forms.md)
- [Informazioni sul codice gestito GDI+](about-gdi-managed-code.md)
- [Utilizzo di classi grafiche gestite](using-managed-graphics-classes.md)
