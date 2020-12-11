---
title: Cenni preliminari sull'uso dei controlli
description: Informazioni sul modo in cui i controlli vengono usati nei Windows Forms per .NET. I controlli sono componenti riutilizzabili che forniscono funzionalità all'utente. Sono disponibili molti controlli pronti per l'uso. È anche possibile creare nuovi controlli.
ms.date: 10/26/2020
ms.topic: overview
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, controls
- controls [Windows Forms]
- custom controls [Windows Forms]
ms.openlocfilehash: 7476ce47a1767a2ab13c25a7408f5861014e7de8
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96968794"
---
# <a name="overview-of-using-controls-windows-forms-net"></a>Cenni preliminari sull'utilizzo di controlli (Windows Forms .NET)

Windows Forms controlli sono componenti riutilizzabili che incapsulano le funzionalità dell'interfaccia utente e vengono usati nelle applicazioni basate su Windows sul lato client. Windows Form fornisce numerosi controlli pronti per l'uso, nonché l'infrastruttura per lo sviluppo di controlli personalizzati. È possibile combinare ed estendere i controlli esistenti oppure creare controlli personalizzati. Per altre informazioni, vedere [tipi di controlli personalizzati](custom.md).

[!INCLUDE [desktop guide under construction](../../includes/desktop-guide-preview-note.md)]

## <a name="adding-controls"></a>Aggiunta di controlli

I controlli vengono aggiunti tramite la finestra di progettazione di Visual Studio. Con la finestra di progettazione è possibile inserire, ridimensionare, allineare e spostare i controlli. In alternativa, è possibile aggiungere i controlli tramite codice. Per ulteriori informazioni, vedere [aggiungere un controllo (Windows Forms)](how-to-add-to-a-form.md).

## <a name="layout-options"></a>Opzioni di layout

La posizione in cui un controllo viene visualizzato in un elemento padre è determinata dal valore della <xref:System.Windows.Forms.Control.Location> proprietà rispetto alla parte superiore sinistra della superficie padre. La coordinata della posizione in alto a sinistra nell'elemento padre è `(x0,y0)` . La dimensione del controllo è determinata dalla <xref:System.Windows.Forms.Control.Size> proprietà e rappresenta la larghezza e l'altezza del controllo.

Oltre al posizionamento manuale e al ridimensionamento, vengono forniti diversi controlli contenitore che consentono di posizionare automaticamente i controlli.

Per altre informazioni, vedere [posizione e layout dei controlli](layout.md).
<!-- TODO

## Control events

-->

## <a name="see-also"></a>Vedere anche

- [Posizione e layout dei controlli](layout.md)
- [Cenni preliminari sul controllo Label (Windows Forms .NET)](labels.md)
- [Aggiungere un controllo (Windows Forms .NET)](how-to-add-to-a-form.md)
