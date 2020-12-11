---
title: "Procedura: Supportare l'interoperabilità COM visualizzando ogni Windows Form nel proprio thread"
ms.date: 03/30/2017
dev_langs:
- vb
helpviewer_keywords:
- COM interop [Windows Forms], Windows Forms
- COM [Windows Forms]
- Windows Forms, unmanaged
- ActiveX controls [Windows Forms], COM interop
- Windows Forms, interop
ms.assetid: a9e04765-d2de-4389-a494-a9a6d07aa6ee
ms.openlocfilehash: 074fc2d3fcfe1bf02bc6f6af65a3d9aed39fe786
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963244"
---
# <a name="how-to-support-com-interop-by-displaying-each-windows-form-on-its-own-thread"></a>Procedura: supportare l'interoperabilità COM visualizzando ogni Windows Form nel relativo thread

È possibile risolvere i problemi di interoperabilità COM visualizzando il form in un ciclo di messaggi .NET Framework, che è possibile creare tramite il <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType> metodo.

Perché un Windows Form funzioni correttamente da un'applicazione client COM, è necessario eseguire il form in un ciclo di messaggi Windows Form. Per eseguire questa operazione, adottare uno degli approcci seguenti:

- Usare il metodo <xref:System.Windows.Forms.Form.ShowDialog%2A?displayProperty=nameWithType> per visualizzare il Windows Form. Per altre informazioni, vedere [Procedura: supportare l'interoperabilità COM visualizzando un Windows Form con il metodo ShowDialog](com-interop-by-displaying-a-windows-form-shadow.md).

- Visualizzare ogni Windows Form in un thread separato.

In Visual Studio è disponibile un supporto completo per questa funzionalità.

Vedere anche [Procedura dettagliata: supporto dell'interoperabilità COM mediante la visualizzazione di ogni Windows Form nel relativo thread](/previous-versions/visualstudio/visual-studio-2010/ms233639(v=vs.100)).

## <a name="example"></a>Esempio

L'esempio di codice seguente illustra come visualizzare il form in un thread separato e chiamare il metodo <xref:System.Windows.Forms.Application.Run%2A?displayProperty=nameWithType> per avviare un message pump Windows Form su tale thread. Per adottare questo approccio, è necessario effettuare il marshalling di tutte le chiamate al form dall'applicazione non gestita usando il metodo <xref:System.Windows.Forms.Control.Invoke%2A> .

Questo approccio richiede che ogni istanza di un form venga eseguita nel rispettivo thread usando il proprio ciclo di messaggi. Non è possibile eseguire più di un ciclo di messaggi per ogni thread. Quindi non è possibile modificare il ciclo di messaggi dell'applicazione client. Tuttavia, è possibile modificare il componente .NET Framework per avviare un nuovo thread che usa il proprio ciclo di messaggi.

[!code-vb[System.Windows.Forms.ComInterop#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ComInterop/VB/COMForm.vb#1)]

[!code-vb[System.Windows.Forms.ComInterop#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ComInterop/VB/FormManager.vb#10)]

[!code-vb[System.Windows.Forms.ComInterop#100](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ComInterop/VB/Form1.vb#100)]

## <a name="compile-the-code"></a>Compilare il codice

Compilare i tipi `COMForm`, `Form1`e `FormManager` in un assembly denominato `COMWinform.dll`. Registrare l'assembly per l'interoperabilità COM usando uno dei metodi descritti in [Packaging an Assembly for COM](/dotnet/framework/interop/packaging-an-assembly-for-co). Ora è possibile usare l'assembly e il file libreria dei tipi (tlb) corrispondente nelle applicazioni non gestite. Ad esempio, è possibile usare la libreria dei tipi come riferimento in un progetto eseguibile di Visual Basic 6.0.

## <a name="see-also"></a>Vedere anche

- [Esposizione di componenti .NET Framework a COM](/dotnet/framework/interop/exposing-dotnet-components-to-co)
- [Preparazione di un assembly per COM](/dotnet/framework/interop/packaging-an-assembly-for-co)
- [Registrazione di assembly presso COM](/dotnet/framework/interop/registering-assemblies-with-co)
- [Procedura: Supportare l'interoperabilità COM visualizzando un Windows Form con il metodo ShowDialog](com-interop-by-displaying-a-windows-form-shadow.md)
- [Cenni preliminari su Windows Form e applicazioni non gestite](windows-forms-and-unmanaged-applications-overview.md)
