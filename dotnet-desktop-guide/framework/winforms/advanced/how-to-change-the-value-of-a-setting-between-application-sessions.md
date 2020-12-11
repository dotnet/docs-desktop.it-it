---
title: "Procedura: Modificare il valore di un'impostazione tra le sessioni dell'applicazione"
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], changing
- application settings [Windows Forms], between application sessions
ms.assetid: 1a85911f-97b2-476c-930b-83379edd890c
ms.openlocfilehash: 95e613cb280813cd75d887d3cf147d7c897bc2e6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96952434"
---
# <a name="how-to-change-the-value-of-a-setting-between-application-sessions"></a><span data-ttu-id="a87ad-102">Procedura: Modificare il valore di un'impostazione tra le sessioni dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="a87ad-102">How To: Change the Value of a Setting Between Application Sessions</span></span>
<span data-ttu-id="a87ad-103">In alcuni casi potrebbe essere necessario modificare il valore di un'impostazione tra le sessioni dell'applicazione dopo che l'applicazione è stata compilata e distribuita.</span><span class="sxs-lookup"><span data-stu-id="a87ad-103">At times, you might want to change the value of a setting between application sessions after the application has been compiled and deployed.</span></span> <span data-ttu-id="a87ad-104">Ad esempio, potrebbe essere necessario modificare una stringa di connessione in modo che punti al percorso del database corretto.</span><span class="sxs-lookup"><span data-stu-id="a87ad-104">For example, you might want to change a connection string to point to the correct database location.</span></span> <span data-ttu-id="a87ad-105">Poiché gli strumenti della fase di progettazione non sono disponibili dopo che l'applicazione è stata compilata e distribuita, è necessario modificare il valore dell'impostazione manualmente nel file.</span><span class="sxs-lookup"><span data-stu-id="a87ad-105">Since design-time tools are not available after the application has been compiled and deployed, you must change the setting value manually in the file.</span></span>  
  
### <a name="to-change-the-value-of-a-setting-between-application-sessions"></a><span data-ttu-id="a87ad-106">Per modificare il valore di un'impostazione tra le sessioni dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="a87ad-106">To Change the Value of a Setting Between Application Sessions</span></span>  
  
1. <span data-ttu-id="a87ad-107">Utilizzando il blocco note Microsoft o un altro editor di testo o XML, aprire il file con estensione config associato all'applicazione.</span><span class="sxs-lookup"><span data-stu-id="a87ad-107">Using Microsoft Notepad or some other text or XML editor, open the .config file associated with your application.</span></span>  
  
2. <span data-ttu-id="a87ad-108">Individuare la voce per l'impostazione che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="a87ad-108">Locate the entry for the setting you want to change.</span></span> <span data-ttu-id="a87ad-109">Dovrebbe essere simile all'esempio illustrato di seguito.</span><span class="sxs-lookup"><span data-stu-id="a87ad-109">It should look similar to the example presented below.</span></span>  
  
    ```xml  
    <setting name="Setting1" serializeAs="String" >  
       <value>My Setting Value</value>  
    </setting>  
    ```  
  
3. <span data-ttu-id="a87ad-110">Digitare un nuovo valore per l'impostazione e salvare il file.</span><span class="sxs-lookup"><span data-stu-id="a87ad-110">Type a new value for your setting and save the file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a87ad-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a87ad-111">See also</span></span>

- [<span data-ttu-id="a87ad-112">Utilizzo delle impostazioni applicazione e delle impostazioni utente</span><span class="sxs-lookup"><span data-stu-id="a87ad-112">Using Application Settings and User Settings</span></span>](using-application-settings-and-user-settings.md)
- [<span data-ttu-id="a87ad-113">Cenni preliminari sulle impostazioni delle applicazioni</span><span class="sxs-lookup"><span data-stu-id="a87ad-113">Application Settings Overview</span></span>](application-settings-overview.md)
