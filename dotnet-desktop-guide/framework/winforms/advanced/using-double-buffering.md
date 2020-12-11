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
# <a name="using-double-buffering"></a><span data-ttu-id="0a4d9-102">Utilizzo del doppio buffer</span><span class="sxs-lookup"><span data-stu-id="0a4d9-102">Using Double Buffering</span></span>
<span data-ttu-id="0a4d9-103">È possibile utilizzare la grafica con doppio buffer per ridurre lo sfarfallio nelle applicazioni che contengono operazioni di disegno complesse.</span><span class="sxs-lookup"><span data-stu-id="0a4d9-103">You can use double-buffered graphics to reduce flicker in your applications that contain complex painting operations.</span></span> <span data-ttu-id="0a4d9-104">Il .NET Framework contiene supporto incorporato per il doppio buffer oppure è possibile gestire ed eseguire il rendering della grafica manualmente.</span><span class="sxs-lookup"><span data-stu-id="0a4d9-104">The .NET Framework contains built-in support for double-buffering or you can manage and render graphics manually.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0a4d9-105">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="0a4d9-105">In This Section</span></span>  
 [<span data-ttu-id="0a4d9-106">Grafica a doppio buffer</span><span class="sxs-lookup"><span data-stu-id="0a4d9-106">Double Buffered Graphics</span></span>](double-buffered-graphics.md)  
 <span data-ttu-id="0a4d9-107">Introduce il concetto di doppio buffer e delinea .NET Framework supporto.</span><span class="sxs-lookup"><span data-stu-id="0a4d9-107">Introduces double buffering concept and outlines .NET Framework support.</span></span>  
  
 [<span data-ttu-id="0a4d9-108">Procedura: Ridurre lo sfarfallio nella grafica con il doppio buffering per form e controlli</span><span class="sxs-lookup"><span data-stu-id="0a4d9-108">How to: Reduce Graphics Flicker with Double Buffering for Forms and Controls</span></span>](how-to-reduce-graphics-flicker-with-double-buffering-for-forms-and-controls.md)  
 <span data-ttu-id="0a4d9-109">Viene illustrato come utilizzare il supporto di doppio buffer predefinito nel .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="0a4d9-109">Demonstrates how to use the default double buffering support in the .NET Framework.</span></span>  
  
 [<span data-ttu-id="0a4d9-110">Procedura: Gestire manualmente la grafica memorizzata nel buffer</span><span class="sxs-lookup"><span data-stu-id="0a4d9-110">How to: Manually Manage Buffered Graphics</span></span>](how-to-manually-manage-buffered-graphics.md)  
 <span data-ttu-id="0a4d9-111">Viene illustrato come gestire il doppio buffer nelle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="0a4d9-111">Shows how to manage double buffering in applications.</span></span>  
  
 [<span data-ttu-id="0a4d9-112">Procedura: Eseguire il rendering manuale della grafica memorizzata nel buffer</span><span class="sxs-lookup"><span data-stu-id="0a4d9-112">How to: Manually Render Buffered Graphics</span></span>](how-to-manually-render-buffered-graphics.md)  
 <span data-ttu-id="0a4d9-113">Viene illustrato come eseguire il rendering di grafica con doppio buffer.</span><span class="sxs-lookup"><span data-stu-id="0a4d9-113">Demonstrates how to render double-buffered graphics.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="0a4d9-114">Informazioni di riferimento</span><span class="sxs-lookup"><span data-stu-id="0a4d9-114">Reference</span></span>  
 <span data-ttu-id="0a4d9-115"><xref:System.Windows.Forms.Control.SetStyle%2A> Metodo di controllo che consente il doppio buffering.</span><span class="sxs-lookup"><span data-stu-id="0a4d9-115"><xref:System.Windows.Forms.Control.SetStyle%2A> Control method that enables double buffering.</span></span>  
  
 <span data-ttu-id="0a4d9-116"><xref:System.Drawing.BufferedGraphicsContext> Fornisce metodi per la creazione di buffer grafici.</span><span class="sxs-lookup"><span data-stu-id="0a4d9-116"><xref:System.Drawing.BufferedGraphicsContext> Provides methods for creating graphics buffers.</span></span>  
  
 <xref:System.Drawing.BufferedGraphicsManager>  
 <span data-ttu-id="0a4d9-117">Fornisce l'accesso al contesto grafico memorizzato nel buffer per un dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="0a4d9-117">Provides access to the buffered graphics context for a application domain.</span></span>
