---
title: "Procedura: aggiungere dati personalizzati ai dati dell'input penna"
ms.date: 03/30/2017
helpviewer_keywords:
- ink data [WPF], adding custom data
- InkCanvas [WPF], displaying
ms.assetid: f02aac6f-3436-4f7c-b6ea-0452cba5332c
ms.openlocfilehash: 7c59a205df5358daec101339cc6a308c8e38a9d6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964615"
---
# <a name="how-to-add-custom-data-to-ink-data"></a>Procedura: aggiungere dati personalizzati ai dati dell'input penna
È possibile aggiungere dati personalizzati a input penna che verranno salvati quando l'input penna viene salvato come formato ISF (Ink Serialized Format).  È possibile salvare i dati personalizzati in <xref:System.Windows.Ink.DrawingAttributes> , <xref:System.Windows.Ink.StrokeCollection> o <xref:System.Windows.Ink.Stroke> .  La possibilità di salvare dati personalizzati su tre oggetti consente di decidere la posizione migliore in cui salvare i dati.  Tutte e tre le classi utilizzano metodi simili per archiviare e accedere ai dati personalizzati.  
  
 Solo i tipi seguenti possono essere salvati come dati personalizzati:  
  
- <xref:System.Boolean>  
  
- <xref:System.Boolean>[]  
  
- <xref:System.Byte>  
  
- <xref:System.Byte>[]  
  
- <xref:System.Char>  
  
- <xref:System.Char>[]  
  
- <xref:System.DateTime>  
  
- <xref:System.DateTime>[]  
  
- <xref:System.Decimal>  
  
- <xref:System.Decimal>[]  
  
- <xref:System.Double>  
  
- <xref:System.Double>[]  
  
- <xref:System.Int16>  
  
- <xref:System.Int16>[]  
  
- <xref:System.Int32>  
  
- <xref:System.Int32>[]  
  
- <xref:System.Int64>  
  
- <xref:System.Int64>[]  
  
- <xref:System.Single>  
  
- <xref:System.Single>[]  
  
- <xref:System.String>  
  
- <xref:System.UInt16>  
  
- <xref:System.UInt16>[]  
  
- <xref:System.UInt32>  
  
- <xref:System.UInt32>[]  
  
- <xref:System.UInt64>  
  
- <xref:System.UInt64>[]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come aggiungere e recuperare dati personalizzati da un oggetto <xref:System.Windows.Ink.StrokeCollection> .  
  
 [!code-csharp[HowToAddCustomDataToInk#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#1)]  
  
 Nell'esempio seguente viene creata un'applicazione in cui vengono visualizzati un oggetto <xref:System.Windows.Controls.InkCanvas> e due pulsanti.  Il pulsante, `switchAuthor` , consente l'utilizzo di due penne da parte di due autori diversi.  Il pulsante `changePenColors` modifica il colore di ogni tratto nell'oggetto in <xref:System.Windows.Controls.InkCanvas> base all'autore.  L'applicazione definisce due <xref:System.Windows.Ink.DrawingAttributes> oggetti e aggiunge una proprietà personalizzata a ciascuna di esse che indica quale autore ha disegnato <xref:System.Windows.Ink.Stroke> .  Quando l'utente fa clic `changePenColors` , l'applicazione modifica l'aspetto del tratto in base al valore della proprietà personalizzata.  
  
 [!code-xaml[HowToAddCustomDataToInk#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml#2)]  
  
 [!code-csharp[HowToAddCustomDataToInk#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#3)]
