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
# <a name="how-to-change-the-value-of-a-setting-between-application-sessions"></a>Procedura: Modificare il valore di un'impostazione tra le sessioni dell'applicazione
In alcuni casi potrebbe essere necessario modificare il valore di un'impostazione tra le sessioni dell'applicazione dopo che l'applicazione è stata compilata e distribuita. Ad esempio, potrebbe essere necessario modificare una stringa di connessione in modo che punti al percorso del database corretto. Poiché gli strumenti della fase di progettazione non sono disponibili dopo che l'applicazione è stata compilata e distribuita, è necessario modificare il valore dell'impostazione manualmente nel file.  
  
### <a name="to-change-the-value-of-a-setting-between-application-sessions"></a>Per modificare il valore di un'impostazione tra le sessioni dell'applicazione  
  
1. Utilizzando il blocco note Microsoft o un altro editor di testo o XML, aprire il file con estensione config associato all'applicazione.  
  
2. Individuare la voce per l'impostazione che si desidera modificare. Dovrebbe essere simile all'esempio illustrato di seguito.  
  
    ```xml  
    <setting name="Setting1" serializeAs="String" >  
       <value>My Setting Value</value>  
    </setting>  
    ```  
  
3. Digitare un nuovo valore per l'impostazione e salvare il file.  
  
## <a name="see-also"></a>Vedere anche

- [Utilizzo delle impostazioni applicazione e delle impostazioni utente](using-application-settings-and-user-settings.md)
- [Cenni preliminari sulle impostazioni delle applicazioni](application-settings-overview.md)
