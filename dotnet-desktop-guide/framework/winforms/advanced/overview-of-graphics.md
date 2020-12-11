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
# <a name="overview-of-graphics"></a><span data-ttu-id="3c7e0-102">Cenni preliminari sulla grafica</span><span class="sxs-lookup"><span data-stu-id="3c7e0-102">Overview of Graphics</span></span>
<span data-ttu-id="3c7e0-103">GDI+ è un Application Programming Interface (API) che costituisce il sottosistema del sistema operativo Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="3c7e0-103">GDI+ is an application programming interface (API) that forms the subsystem of the Microsoft Windows operating system.</span></span> <span data-ttu-id="3c7e0-104">GDI+ è responsabile della visualizzazione di informazioni su schermate e stampanti.</span><span class="sxs-lookup"><span data-stu-id="3c7e0-104">GDI+ is responsible for displaying information on screens and printers.</span></span> <span data-ttu-id="3c7e0-105">Come suggerisce il nome, GDI+ è il successore di GDI, il Graphics Device Interface incluso nelle versioni precedenti di Windows.</span><span class="sxs-lookup"><span data-stu-id="3c7e0-105">As its name suggests, GDI+ is the successor to GDI, the Graphics Device Interface included with earlier versions of Windows.</span></span>  
  
## <a name="managed-class-interface"></a><span data-ttu-id="3c7e0-106">Interfaccia di classe gestita</span><span class="sxs-lookup"><span data-stu-id="3c7e0-106">Managed Class Interface</span></span>  
 <span data-ttu-id="3c7e0-107">L'API GDI+ viene esposta tramite un set di classi distribuite come codice gestito.</span><span class="sxs-lookup"><span data-stu-id="3c7e0-107">The GDI+ API is exposed through a set of classes deployed as managed code.</span></span> <span data-ttu-id="3c7e0-108">Questo set di classi è denominato *interfaccia di classe gestita* per GDI+.</span><span class="sxs-lookup"><span data-stu-id="3c7e0-108">This set of classes is called the *managed class interface* to GDI+.</span></span> <span data-ttu-id="3c7e0-109">Di seguito sono elencati gli spazi dei nomi che costituiscono l'interfaccia di classe gestita:</span><span class="sxs-lookup"><span data-stu-id="3c7e0-109">The following namespaces make up the managed class interface:</span></span>  
  
- <xref:System.Drawing>  
  
- <xref:System.Drawing.Drawing2D>  
  
- <xref:System.Drawing.Imaging>  
  
- <xref:System.Drawing.Text>  
  
- <xref:System.Drawing.Printing>  
  
 <span data-ttu-id="3c7e0-110">Con un Graphics Device Interface, ad esempio GDI+, è possibile visualizzare informazioni su una schermata o una stampante senza che sia necessario preoccuparsi dei dettagli di un particolare dispositivo di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="3c7e0-110">With a Graphics Device Interface, such as GDI+, you can display information on a screen or printer without having to be concerned about the details of a particular display device.</span></span> <span data-ttu-id="3c7e0-111">Il programmatore effettua chiamate ai metodi forniti dalle classi GDI+.</span><span class="sxs-lookup"><span data-stu-id="3c7e0-111">The programmer makes calls to methods provided by GDI+ classes.</span></span> <span data-ttu-id="3c7e0-112">Tali metodi, a loro volta, effettuano le chiamate appropriate a specifici driver di dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3c7e0-112">Those methods, in turn, make the appropriate calls to specific device drivers.</span></span> <span data-ttu-id="3c7e0-113">GDI+ isola l'applicazione dall'hardware grafico.</span><span class="sxs-lookup"><span data-stu-id="3c7e0-113">GDI+ insulates the application from the graphics hardware.</span></span> <span data-ttu-id="3c7e0-114">È questo isolamento che consente a un programmatore di creare applicazioni indipendenti dal dispositivo.</span><span class="sxs-lookup"><span data-stu-id="3c7e0-114">It is this insulation that enables a programmer to create device-independent applications.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c7e0-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3c7e0-115">See also</span></span>

- [<span data-ttu-id="3c7e0-116">Panoramica sulla grafica</span><span class="sxs-lookup"><span data-stu-id="3c7e0-116">Graphics Overview</span></span>](graphics-overview-windows-forms.md)
