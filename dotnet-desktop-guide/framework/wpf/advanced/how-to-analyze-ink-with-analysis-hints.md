---
title: "Procedura: analizzare l'input penna con i suggerimenti dell'analisi"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ink [WPF], analyzing
- analyzing ink [WPF]
- ink [WPF], AnalysisHintNode objects [WPF]
- AnalysisHintNode objects [WPF]
ms.assetid: d4421ed4-77f5-4640-829e-9f1de50b2ff2
ms.openlocfilehash: 5e94628d357a2ca75ad1b6fb7e464a3355f1fd5f
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96964081"
---
# <a name="how-to-analyze-ink-with-analysis-hints"></a>Procedura: analizzare l'input penna con i suggerimenti dell'analisi

Un oggetto [System. Windows. Ink. AnalysisHintNode](/previous-versions/dotnet/netframework-3.5/ms610344(v=vs.90)) fornisce un suggerimento per [System. Windows. Ink. InkAnalyzer](/previous-versions/dotnet/netframework-3.5/ms616754(v=vs.90)) a cui è collegato.  L'hint si applica all'area specificata dalla proprietà [System. Windows. Ink. ContextNode. location% 2a](/previous-versions/dotnet/netframework-3.5/ms594508(v=vs.90)) di [System. Windows. Ink. AnalysisHintNode](/previous-versions/dotnet/netframework-3.5/ms610344(v=vs.90)) e fornisce un contesto aggiuntivo all'analizzatore input penna per migliorare l'accuratezza del riconoscimento. [System. Windows. Ink. InkAnalyzer](/previous-versions/dotnet/netframework-3.5/ms616754(v=vs.90)) applica queste informazioni sul contesto durante l'analisi dell'input penna ottenuto dall'interno dell'area dell'hint.  
  
## <a name="example"></a>Esempio  

 L'esempio seguente è un'applicazione che usa più oggetti [System. Windows. Ink. AnalysisHintNode](/previous-versions/dotnet/netframework-3.5/ms610344(v=vs.90)) in un modulo che accetta input penna. L'applicazione usa la proprietà [System. Windows. Ink. AnalysisHintNode. controllore% 2a](/previous-versions/dotnet/netframework-3.5/ms594341(v=vs.90)) per fornire informazioni di contesto per ogni voce nel form.  L'applicazione usa l'analisi in background per analizzare l'input penna e cancella il modulo di tutti gli input penna cinque secondi dopo che l'utente ha interrotto l'aggiunta dell'input penna.  
  
 [!code-xaml[HowToAnalyzeInk#1](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToAnalyzeInk/CSharp/FormAnalyzer.xaml#1)]  
  
 [!code-csharp[HowToAnalyzeInk#2](~/samples/snippets/csharp/VS_Snippets_Wpf/HowToAnalyzeInk/CSharp/FormAnalyzer.xaml.cs#2)]
 [!code-vb[HowToAnalyzeInk#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HowToAnalyzeInk/VisualBasic/FormAnalyzer.xaml.vb#2)]
