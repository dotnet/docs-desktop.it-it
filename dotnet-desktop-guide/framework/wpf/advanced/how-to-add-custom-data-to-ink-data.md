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
# <a name="how-to-add-custom-data-to-ink-data"></a><span data-ttu-id="4eaf2-102">Procedura: aggiungere dati personalizzati ai dati dell'input penna</span><span class="sxs-lookup"><span data-stu-id="4eaf2-102">How to: Add Custom Data to Ink Data</span></span>
<span data-ttu-id="4eaf2-103">È possibile aggiungere dati personalizzati a input penna che verranno salvati quando l'input penna viene salvato come formato ISF (Ink Serialized Format).</span><span class="sxs-lookup"><span data-stu-id="4eaf2-103">You can add custom data to ink that will be saved when the ink is saved as ink serialized format (ISF).</span></span>  <span data-ttu-id="4eaf2-104">È possibile salvare i dati personalizzati in <xref:System.Windows.Ink.DrawingAttributes> , <xref:System.Windows.Ink.StrokeCollection> o <xref:System.Windows.Ink.Stroke> .</span><span class="sxs-lookup"><span data-stu-id="4eaf2-104">You can save the custom data to the <xref:System.Windows.Ink.DrawingAttributes>, the <xref:System.Windows.Ink.StrokeCollection>, or the <xref:System.Windows.Ink.Stroke>.</span></span>  <span data-ttu-id="4eaf2-105">La possibilità di salvare dati personalizzati su tre oggetti consente di decidere la posizione migliore in cui salvare i dati.</span><span class="sxs-lookup"><span data-stu-id="4eaf2-105">Being able to save custom data on three objects gives you the ability to decide the best place to save the data.</span></span>  <span data-ttu-id="4eaf2-106">Tutte e tre le classi utilizzano metodi simili per archiviare e accedere ai dati personalizzati.</span><span class="sxs-lookup"><span data-stu-id="4eaf2-106">All three classes use similar methods to store and access custom data.</span></span>  
  
 <span data-ttu-id="4eaf2-107">Solo i tipi seguenti possono essere salvati come dati personalizzati:</span><span class="sxs-lookup"><span data-stu-id="4eaf2-107">Only the following types can be saved as custom data:</span></span>  
  
- <xref:System.Boolean>  
  
- <span data-ttu-id="4eaf2-108"><xref:System.Boolean>[]</span><span class="sxs-lookup"><span data-stu-id="4eaf2-108"><xref:System.Boolean>[]</span></span>  
  
- <xref:System.Byte>  
  
- <span data-ttu-id="4eaf2-109"><xref:System.Byte>[]</span><span class="sxs-lookup"><span data-stu-id="4eaf2-109"><xref:System.Byte>[]</span></span>  
  
- <xref:System.Char>  
  
- <span data-ttu-id="4eaf2-110"><xref:System.Char>[]</span><span class="sxs-lookup"><span data-stu-id="4eaf2-110"><xref:System.Char>[]</span></span>  
  
- <xref:System.DateTime>  
  
- <span data-ttu-id="4eaf2-111"><xref:System.DateTime>[]</span><span class="sxs-lookup"><span data-stu-id="4eaf2-111"><xref:System.DateTime>[]</span></span>  
  
- <xref:System.Decimal>  
  
- <span data-ttu-id="4eaf2-112"><xref:System.Decimal>[]</span><span class="sxs-lookup"><span data-stu-id="4eaf2-112"><xref:System.Decimal>[]</span></span>  
  
- <xref:System.Double>  
  
- <span data-ttu-id="4eaf2-113"><xref:System.Double>[]</span><span class="sxs-lookup"><span data-stu-id="4eaf2-113"><xref:System.Double>[]</span></span>  
  
- <xref:System.Int16>  
  
- <span data-ttu-id="4eaf2-114"><xref:System.Int16>[]</span><span class="sxs-lookup"><span data-stu-id="4eaf2-114"><xref:System.Int16>[]</span></span>  
  
- <xref:System.Int32>  
  
- <span data-ttu-id="4eaf2-115"><xref:System.Int32>[]</span><span class="sxs-lookup"><span data-stu-id="4eaf2-115"><xref:System.Int32>[]</span></span>  
  
- <xref:System.Int64>  
  
- <span data-ttu-id="4eaf2-116"><xref:System.Int64>[]</span><span class="sxs-lookup"><span data-stu-id="4eaf2-116"><xref:System.Int64>[]</span></span>  
  
- <xref:System.Single>  
  
- <span data-ttu-id="4eaf2-117"><xref:System.Single>[]</span><span class="sxs-lookup"><span data-stu-id="4eaf2-117"><xref:System.Single>[]</span></span>  
  
- <xref:System.String>  
  
- <xref:System.UInt16>  
  
- <span data-ttu-id="4eaf2-118"><xref:System.UInt16>[]</span><span class="sxs-lookup"><span data-stu-id="4eaf2-118"><xref:System.UInt16>[]</span></span>  
  
- <xref:System.UInt32>  
  
- <span data-ttu-id="4eaf2-119"><xref:System.UInt32>[]</span><span class="sxs-lookup"><span data-stu-id="4eaf2-119"><xref:System.UInt32>[]</span></span>  
  
- <xref:System.UInt64>  
  
- <span data-ttu-id="4eaf2-120"><xref:System.UInt64>[]</span><span class="sxs-lookup"><span data-stu-id="4eaf2-120"><xref:System.UInt64>[]</span></span>  
  
## <a name="example"></a><span data-ttu-id="4eaf2-121">Esempio</span><span class="sxs-lookup"><span data-stu-id="4eaf2-121">Example</span></span>  
 <span data-ttu-id="4eaf2-122">Nell'esempio seguente viene illustrato come aggiungere e recuperare dati personalizzati da un oggetto <xref:System.Windows.Ink.StrokeCollection> .</span><span class="sxs-lookup"><span data-stu-id="4eaf2-122">The following example demonstrates how to add and retrieve custom data from a <xref:System.Windows.Ink.StrokeCollection>.</span></span>  
  
 [!code-csharp[HowToAddCustomDataToInk#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#1)]  
  
 <span data-ttu-id="4eaf2-123">Nell'esempio seguente viene creata un'applicazione in cui vengono visualizzati un oggetto <xref:System.Windows.Controls.InkCanvas> e due pulsanti.</span><span class="sxs-lookup"><span data-stu-id="4eaf2-123">The following example creates an application that displays an <xref:System.Windows.Controls.InkCanvas> and two buttons.</span></span>  <span data-ttu-id="4eaf2-124">Il pulsante, `switchAuthor` , consente l'utilizzo di due penne da parte di due autori diversi.</span><span class="sxs-lookup"><span data-stu-id="4eaf2-124">The button, `switchAuthor`, enables two pens to be used by two different authors.</span></span>  <span data-ttu-id="4eaf2-125">Il pulsante `changePenColors` modifica il colore di ogni tratto nell'oggetto in <xref:System.Windows.Controls.InkCanvas> base all'autore.</span><span class="sxs-lookup"><span data-stu-id="4eaf2-125">The button `changePenColors` changes the color of each stroke on the <xref:System.Windows.Controls.InkCanvas> according to the author.</span></span>  <span data-ttu-id="4eaf2-126">L'applicazione definisce due <xref:System.Windows.Ink.DrawingAttributes> oggetti e aggiunge una proprietà personalizzata a ciascuna di esse che indica quale autore ha disegnato <xref:System.Windows.Ink.Stroke> .</span><span class="sxs-lookup"><span data-stu-id="4eaf2-126">The application defines two <xref:System.Windows.Ink.DrawingAttributes> objects and adds a custom property to each one that indicates which author drew the <xref:System.Windows.Ink.Stroke>.</span></span>  <span data-ttu-id="4eaf2-127">Quando l'utente fa clic `changePenColors` , l'applicazione modifica l'aspetto del tratto in base al valore della proprietà personalizzata.</span><span class="sxs-lookup"><span data-stu-id="4eaf2-127">When the user clicks `changePenColors`, the application changes the appearance of the stroke according to the value of the custom property.</span></span>  
  
 [!code-xaml[HowToAddCustomDataToInk#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml#2)]  
  
 [!code-csharp[HowToAddCustomDataToInk#3](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToAddCustomDataToInk/CSharp/Window1.xaml.cs#3)]
