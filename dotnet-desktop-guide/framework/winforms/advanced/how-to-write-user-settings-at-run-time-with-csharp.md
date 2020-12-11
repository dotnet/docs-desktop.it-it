---
title: 'Procedura: Scrivere le impostazioni utente in fase di esecuzione con C#'
description: Informazioni su come scrivere le impostazioni in fase di esecuzione con C# salvando in modo permanente le modifiche apportate alle impostazioni tra sessioni dell'applicazione chiamando il metodo Save.
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], run time
- application settings [Windows Forms], writing user settings
- application settings [Windows Forms], C#
ms.assetid: 9d061c7d-b33b-470f-a36d-edccb1d6f9a3
ms.openlocfilehash: 6154ff1b92d6c2d4c788299e59eb8f73e6b69c4b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962437"
---
# <a name="how-to-write-user-settings-at-run-time-with-c"></a>Procedura: scrivere le impostazioni utente in fase di esecuzione con C\#

Le impostazioni con ambito di applicazione sono di sola lettura e possono essere modificate solo in fase di progettazione o modificando il file .config tra sessioni dell'applicazione. Le impostazioni con ambito di utente possono invece essere scritte in fase di esecuzione usando la stessa procedura adottata per modificare il valore di una proprietà. Il nuovo valore viene mantenuto per la durata della sessione dell'applicazione. È possibile mantenere le modifiche alle impostazioni tra le sessioni dell'applicazione chiamando il metodo Save.  
  
## <a name="how-to-write-and-persist-user-settings-at-run-time-with-c"></a>Procedura: scrivere e salvare in modo permanente le impostazioni utente in fase di esecuzione con C\#
  
1. Accedere all'impostazione e assegnarle un nuovo valore come mostrato nell'esempio seguente:  
  
   ```csharp
   Properties.Settings.Default.myColor = Color.AliceBlue;  
   ```  
  
2. Se si vogliono mantenere le modifiche alle impostazioni tra sessioni dell'applicazione, chiamare il metodo Save, come mostrato nell'esempio seguente:  
  
    ```csharp
    Properties.Settings.Default.Save();  
    ```  
  
Le impostazioni utente vengono salvate in un file all'interno di una sottocartella della cartella dati applicazioni nascosta locale dell'utente.  
  
## <a name="see-also"></a>Vedere anche

- [Utilizzo delle impostazioni applicazione e delle impostazioni utente](using-application-settings-and-user-settings.md)
- [Procedura: Leggere le impostazioni in fase di esecuzione con C#](how-to-read-settings-at-run-time-with-csharp.md)
- [Cenni preliminari sulle impostazioni delle applicazioni](application-settings-overview.md)
