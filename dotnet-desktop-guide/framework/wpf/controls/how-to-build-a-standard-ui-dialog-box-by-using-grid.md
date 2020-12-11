---
title: "Procedura: compilare una finestra di dialogo standard dell'interfaccia utente utilizzando l'elemento Grid"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dialog boxes [WPF], creating
- Grid control [WPF], creating [WPF], dialog box
ms.assetid: d6ac3d51-844b-4d29-96d8-81a696a7b960
ms.openlocfilehash: 442d69f891d53365653c01ef4dca296398ae7195
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96969523"
---
# <a name="how-to-build-a-standard-ui-dialog-box-by-using-grid"></a><span data-ttu-id="49871-102">Procedura: compilare una finestra di dialogo standard dell'interfaccia utente utilizzando l'elemento Grid</span><span class="sxs-lookup"><span data-stu-id="49871-102">How to: Build a Standard UI Dialog Box by Using Grid</span></span>
<span data-ttu-id="49871-103">Questo esempio illustra come creare una finestra [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] di dialogo standard usando l' <xref:System.Windows.Controls.Grid> elemento.</span><span class="sxs-lookup"><span data-stu-id="49871-103">This example shows how to create a standard [!INCLUDE[TLA#tla_ui](../../../includes/tlasharptla-ui-md.md)] dialog box by using the <xref:System.Windows.Controls.Grid> element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="49871-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="49871-104">Example</span></span>  
 <span data-ttu-id="49871-105">Nell'esempio seguente viene creata una finestra di dialogo come la finestra di dialogo **Esegui** nel sistema operativo Windows.</span><span class="sxs-lookup"><span data-stu-id="49871-105">The following example creates a dialog box like the **Run** dialog box in the Windows operating system.</span></span>  
  
 <span data-ttu-id="49871-106">Nell'esempio viene creato un oggetto <xref:System.Windows.Controls.Grid> e vengono utilizzate le <xref:System.Windows.Controls.ColumnDefinition> <xref:System.Windows.Controls.RowDefinition> classi e per definire cinque colonne e quattro righe.</span><span class="sxs-lookup"><span data-stu-id="49871-106">The example creates a <xref:System.Windows.Controls.Grid> and uses the <xref:System.Windows.Controls.ColumnDefinition> and <xref:System.Windows.Controls.RowDefinition> classes to define five columns and four rows.</span></span>  
  
 <span data-ttu-id="49871-107">Nell'esempio viene quindi aggiunto e posizionato un oggetto <xref:System.Windows.Controls.Image> , `RunIcon.png` , per rappresentare l'immagine presente nella finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="49871-107">The example then adds and positions an <xref:System.Windows.Controls.Image>, `RunIcon.png`, to represent the image that is found in the dialog box.</span></span> <span data-ttu-id="49871-108">L'immagine viene posizionata nella prima colonna e nella prima riga di <xref:System.Windows.Controls.Grid> (angolo superiore sinistro).</span><span class="sxs-lookup"><span data-stu-id="49871-108">The image is placed in the first column and row of the <xref:System.Windows.Controls.Grid> (the upper-left corner).</span></span>  
  
 <span data-ttu-id="49871-109">Successivamente, nell'esempio viene aggiunto un <xref:System.Windows.Controls.TextBlock> elemento alla prima colonna, che si estende sulle colonne rimanenti della prima riga.</span><span class="sxs-lookup"><span data-stu-id="49871-109">Next, the example adds a <xref:System.Windows.Controls.TextBlock> element to the first column, which spans the remaining columns of the first row.</span></span> <span data-ttu-id="49871-110">Aggiunge un altro <xref:System.Windows.Controls.TextBlock> elemento alla seconda riga della prima colonna, per rappresentare la casella di testo **aperta** .</span><span class="sxs-lookup"><span data-stu-id="49871-110">It adds another <xref:System.Windows.Controls.TextBlock> element to the second row in the first column, to represent the **Open** text box.</span></span> <span data-ttu-id="49871-111"><xref:System.Windows.Controls.TextBlock>Segue, che rappresenta l'area di immissione dati.</span><span class="sxs-lookup"><span data-stu-id="49871-111">A <xref:System.Windows.Controls.TextBlock> follows, which represents the data entry area.</span></span>  
  
 <span data-ttu-id="49871-112">Infine, nell'esempio vengono aggiunti tre <xref:System.Windows.Controls.Button> elementi alla riga finale, che rappresentano gli eventi **OK**, **Cancel** e **Browse** .</span><span class="sxs-lookup"><span data-stu-id="49871-112">Finally, the example adds three <xref:System.Windows.Controls.Button> elements to the final row, which represent the **OK**, **Cancel**, and **Browse** events.</span></span>  
  
 [!code-csharp[GridRunDialog#1](~/samples/snippets/csharp/VS_Snippets_Wpf/GridRunDialog/CSharp/window1.xaml.cs#1)]
 [!code-vb[GridRunDialog#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/GridRunDialog/VisualBasic/grid_vb.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="49871-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49871-113">See also</span></span>

- <xref:System.Windows.Controls.Grid>
- <xref:System.Windows.GridUnitType>
- [<span data-ttu-id="49871-114">Cenni preliminari sugli elementi Panel</span><span class="sxs-lookup"><span data-stu-id="49871-114">Panels Overview</span></span>](panels-overview.md)
- [<span data-ttu-id="49871-115">Procedure</span><span class="sxs-lookup"><span data-stu-id="49871-115">How-to Topics</span></span>](grid-how-to-topics.md)
