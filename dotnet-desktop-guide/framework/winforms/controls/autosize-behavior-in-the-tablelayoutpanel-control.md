---
title: Comportamento di AutoSize nel controllo TableLayoutPanel
ms.date: 03/30/2017
ms.topic: overview
helpviewer_keywords:
- AutoSize property [Windows Forms], tableLayoutPanel control
- controls [Windows Forms], sizing
- localizing forms
- layout [Windows Forms], AutoSize
- sizing [Windows Forms], automatic
- TableLayoutPanel control [Windows Forms], AutoSize behavior
- automatic sizing
- AutoSizeMode property
ms.assetid: 9233e0c3-2fa6-405e-8701-959479b1250e
ms.openlocfilehash: daeca48c4fcfaf83d6506ba07d60ec2dcfdcace7
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/09/2020
ms.locfileid: "96962245"
---
# <a name="autosize-behavior-in-the-tablelayoutpanel-control"></a><span data-ttu-id="07363-102">Comportamento di AutoSize nel controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="07363-102">AutoSize Behavior in the TableLayoutPanel Control</span></span>
## <a name="distinct-autosize-behaviors"></a><span data-ttu-id="07363-103">Comportamenti AutoSize distinti</span><span class="sxs-lookup"><span data-stu-id="07363-103">Distinct AutoSize Behaviors</span></span>  
 <span data-ttu-id="07363-104">Il <xref:System.Windows.Forms.TableLayoutPanel> controllo supporta il comportamento di dimensionamento automatico nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="07363-104">The <xref:System.Windows.Forms.TableLayoutPanel> control supports automatic sizing behavior in the following ways:</span></span>  
  
- <span data-ttu-id="07363-105">Tramite la <xref:System.Windows.Forms.Control.AutoSize%2A> Proprietà;</span><span class="sxs-lookup"><span data-stu-id="07363-105">Through the <xref:System.Windows.Forms.Control.AutoSize%2A> property;</span></span>  
  
- <span data-ttu-id="07363-106">Tramite la <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> proprietà sugli <xref:System.Windows.Forms.TableLayoutPanel> stili di riga e colonna del controllo.</span><span class="sxs-lookup"><span data-stu-id="07363-106">Through the <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> property on the <xref:System.Windows.Forms.TableLayoutPanel> control’s column and row styles.</span></span>  
  
### <a name="the-autosize-property-with-row-and-column-styles"></a><span data-ttu-id="07363-107">Proprietà AutoSize con stili di riga e colonna</span><span class="sxs-lookup"><span data-stu-id="07363-107">The AutoSize Property with Row and Column Styles</span></span>  
 <span data-ttu-id="07363-108">Nella tabella seguente viene descritta l'interazione tra la <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà e gli <xref:System.Windows.Forms.TableLayoutPanel> stili di colonna e riga del controllo.</span><span class="sxs-lookup"><span data-stu-id="07363-108">The following table describes the interaction between the <xref:System.Windows.Forms.Control.AutoSize%2A> property and the <xref:System.Windows.Forms.TableLayoutPanel> control’s column and row styles.</span></span>  
  
|<span data-ttu-id="07363-109">Impostazione AutoSize</span><span class="sxs-lookup"><span data-stu-id="07363-109">AutoSize setting</span></span>|<span data-ttu-id="07363-110">Interazione stile</span><span class="sxs-lookup"><span data-stu-id="07363-110">Style interaction</span></span>|  
|----------------------|-----------------------|  
|`false`|<span data-ttu-id="07363-111">Il <xref:System.Windows.Forms.TableLayoutPanel> controllo procede da sinistra verso destra e alloca spazio per la colonna o la riga o nell'ordine seguente.</span><span class="sxs-lookup"><span data-stu-id="07363-111">The <xref:System.Windows.Forms.TableLayoutPanel> control proceeds from left to right, and allocates space for the column or row or in the following order.</span></span><br /><br /> <span data-ttu-id="07363-112">1. se la <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> proprietà è impostata su <xref:System.Windows.Forms.SizeType.Absolute> , <xref:System.Windows.Forms.ColumnStyle.Width%2A> viene allocato il numero di pixel specificato da o <xref:System.Windows.Forms.RowStyle.Height%2A> .</span><span class="sxs-lookup"><span data-stu-id="07363-112">1.  If the <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> property is set to <xref:System.Windows.Forms.SizeType.Absolute>, the number of pixels specified by <xref:System.Windows.Forms.ColumnStyle.Width%2A> or <xref:System.Windows.Forms.RowStyle.Height%2A> is allocated.</span></span><br /><span data-ttu-id="07363-113">2. se la <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> proprietà è impostata su <xref:System.Windows.Forms.SizeType.AutoSize> , viene allocato il numero di pixel restituiti dal metodo del controllo figlio <xref:System.Windows.Forms.Control.GetPreferredSize%2A> .</span><span class="sxs-lookup"><span data-stu-id="07363-113">2.  If the <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> property is set to <xref:System.Windows.Forms.SizeType.AutoSize>, the number of pixels returned by the child control’s <xref:System.Windows.Forms.Control.GetPreferredSize%2A> method is allocated.</span></span><br /><span data-ttu-id="07363-114">3. dopo l'allocazione dello spazio per tutte le <xref:System.Windows.Forms.SizeType.Absolute> <xref:System.Windows.Forms.SizeType.AutoSize> colonne e o le righe, le colonne o le righe con <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> impostate su <xref:System.Windows.Forms.SizeType.Percent> vengono utilizzate per allocare in modo proporzionale lo spazio libero rimanente</span><span class="sxs-lookup"><span data-stu-id="07363-114">3.  After space for all <xref:System.Windows.Forms.SizeType.Absolute> and <xref:System.Windows.Forms.SizeType.AutoSize> columns or rows is allocated, any columns or rows with <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> set to <xref:System.Windows.Forms.SizeType.Percent> are used to proportionally allocate the remaining free space</span></span>|  
|`true`|<span data-ttu-id="07363-115">Simile all'interazione precedente, con l'eccezione che le <xref:System.Windows.Forms.SizeType.Percent> colonne o le righe acquisiscono un aspetto di ridimensionamento automatico.</span><span class="sxs-lookup"><span data-stu-id="07363-115">Similar to the previous interaction, with the exception that <xref:System.Windows.Forms.SizeType.Percent> columns or rows acquire an automatic sizing aspect.</span></span><br /><br /> <span data-ttu-id="07363-116">Il <xref:System.Windows.Forms.TableLayoutPanel> controllo espande la colonna o la riga per creare spazio disponibile adeguato, in modo che nessuna colonna o riga con stile ritaglia il <xref:System.Windows.Forms.SizeType.Percent> contenuto.</span><span class="sxs-lookup"><span data-stu-id="07363-116">The <xref:System.Windows.Forms.TableLayoutPanel> control expands the column or row to create adequate free space, so that no column or row with <xref:System.Windows.Forms.SizeType.Percent> styling clips its contents.</span></span> <span data-ttu-id="07363-117">Il <xref:System.Windows.Forms.TableLayoutPanel> controllo consente di allocare il nuovo spazio proporzionalmente in base alla <xref:System.Windows.Forms.ColumnStyle.Width%2A> <xref:System.Windows.Forms.RowStyle.Height%2A> proprietà o.</span><span class="sxs-lookup"><span data-stu-id="07363-117">The <xref:System.Windows.Forms.TableLayoutPanel> control allocates the new space proportionally according to the <xref:System.Windows.Forms.ColumnStyle.Width%2A> or <xref:System.Windows.Forms.RowStyle.Height%2A> property.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="07363-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="07363-118">See also</span></span>

- <xref:System.Windows.Forms.TableLayoutPanel>
- [<span data-ttu-id="07363-119">Cenni preliminari sul controllo TableLayoutPanel</span><span class="sxs-lookup"><span data-stu-id="07363-119">TableLayoutPanel Control Overview</span></span>](tablelayoutpanel-control-overview.md)
