---
title: Progettare un layout descrittivo per la localizzazione
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TableLayoutPanel control [Windows Forms]
- application design [Windows Forms], localization
- Windows Forms, localization
- localization [Windows Forms], Windows Forms layout
ms.assetid: d13eff2d-701c-4b6e-8838-3885cbfb7223
ms.openlocfilehash: ae52669d2547532fcdaabab9aeb2cf40a4a6fa2d
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96963853"
---
# <a name="how-to-design-a-windows-forms-layout-that-responds-well-to-localization"></a>Procedura: progettare un layout di Windows Form che risponda correttamente alla localizzazione

La creazione di form pronti per la localizzazione accelera notevolmente lo sviluppo per i mercati internazionali. È possibile usare il controllo <xref:System.Windows.Forms.TableLayoutPanel> per implementare layout che rispondano correttamente man mano che i controlli vengono ridimensionati in seguito alle modifiche dei valori della proprietà <xref:System.Windows.Forms.Control.Text%2A>.

## <a name="example"></a>Esempio

 In questo form viene illustrato come creare un layout che viene modificato proporzionalmente quando si traducono i valori stringa visualizzati in altre lingue. Questo processo di traduzione è denominato *localizzazione*. Per altre informazioni, vedere [Localizzazione](/dotnet/standard/globalization-localization/localization).

 In Visual Studio è disponibile supporto completo per questa attività.  Vedere anche [Procedura dettagliata: creazione di un layout dalle proporzioni adattabili per la localizzazione](/previous-versions/visualstudio/visual-studio-2010/7k9fa71y(v=vs.100)).

 [!code-csharp[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/CS/localizableform.cs#1)]
 [!code-vb[System.Windows.Forms.TableLayoutPanel.LocalizableForm#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.TableLayoutPanel.LocalizableForm/VB/localizableform.vb#1)]

## <a name="additional-resources"></a>Risorse aggiuntive

1. [Procedura: Allineare ed estendere un controllo in un controllo TableLayoutPanel](how-to-align-and-stretch-a-control-in-a-tablelayoutpanel-control.md)

2. [Procedura dettagliata: Disposizione dei controlli in Windows Forms usando FlowLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-flowlayoutpanel.md)

3. [Procedura: Inserire righe e colonne in un controllo TableLayoutPanel](how-to-span-rows-and-columns-in-a-tablelayoutpanel-control.md)

4. [Procedura: Modificare colonne e righe in un controllo TableLayoutPanel](how-to-edit-columns-and-rows-in-a-tablelayoutpanel-control.md)

5. [Procedura dettagliata: eseguire attività comuni utilizzando le azioni della finestra di progettazione](perform-common-tasks-design-actions.md)

6. [Procedura dettagliata: disposizione di controlli in Windows Form usando TableLayoutPanel](walkthrough-arranging-controls-on-windows-forms-using-a-tablelayoutpanel.md)

7. [Procedura dettagliata: Disposizione dei controlli Windows Forms con spaziatura interna, margini e la proprietà AutoSize](windows-forms-controls-padding-autosize.md)

8. [Procedura: Supportare la localizzazione in Windows Form usando la proprietà AutoSize e il controllo TableLayoutPanel](/previous-versions/visualstudio/visual-studio-2010/1zkt8b33(v=vs.100))

9. [Procedura dettagliata: creazione di un Windows Form ridimensionabile per l'inserimento di dati](/previous-versions/visualstudio/visual-studio-2010/991eahec(v=vs.100))

## <a name="compiling-the-code"></a>Compilazione del codice

 L'esempio presenta i requisiti seguenti:

- Riferimenti agli assembly System, System.Data, System.Drawing e System.Windows.Forms.

## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.TableLayoutPanel>
- <xref:System.Windows.Forms.FlowLayoutPanel>
- [Localizzazione](/dotnet/standard/globalization-localization/localization)
