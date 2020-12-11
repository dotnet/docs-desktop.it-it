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
# <a name="autosize-behavior-in-the-tablelayoutpanel-control"></a>Comportamento di AutoSize nel controllo TableLayoutPanel
## <a name="distinct-autosize-behaviors"></a>Comportamenti AutoSize distinti  
 Il <xref:System.Windows.Forms.TableLayoutPanel> controllo supporta il comportamento di dimensionamento automatico nei modi seguenti:  
  
- Tramite la <xref:System.Windows.Forms.Control.AutoSize%2A> Proprietà;  
  
- Tramite la <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> proprietà sugli <xref:System.Windows.Forms.TableLayoutPanel> stili di riga e colonna del controllo.  
  
### <a name="the-autosize-property-with-row-and-column-styles"></a>Proprietà AutoSize con stili di riga e colonna  
 Nella tabella seguente viene descritta l'interazione tra la <xref:System.Windows.Forms.Control.AutoSize%2A> proprietà e gli <xref:System.Windows.Forms.TableLayoutPanel> stili di colonna e riga del controllo.  
  
|Impostazione AutoSize|Interazione stile|  
|----------------------|-----------------------|  
|`false`|Il <xref:System.Windows.Forms.TableLayoutPanel> controllo procede da sinistra verso destra e alloca spazio per la colonna o la riga o nell'ordine seguente.<br /><br /> 1. se la <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> proprietà è impostata su <xref:System.Windows.Forms.SizeType.Absolute> , <xref:System.Windows.Forms.ColumnStyle.Width%2A> viene allocato il numero di pixel specificato da o <xref:System.Windows.Forms.RowStyle.Height%2A> .<br />2. se la <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> proprietà è impostata su <xref:System.Windows.Forms.SizeType.AutoSize> , viene allocato il numero di pixel restituiti dal metodo del controllo figlio <xref:System.Windows.Forms.Control.GetPreferredSize%2A> .<br />3. dopo l'allocazione dello spazio per tutte le <xref:System.Windows.Forms.SizeType.Absolute> <xref:System.Windows.Forms.SizeType.AutoSize> colonne e o le righe, le colonne o le righe con <xref:System.Windows.Forms.TableLayoutStyle.SizeType%2A> impostate su <xref:System.Windows.Forms.SizeType.Percent> vengono utilizzate per allocare in modo proporzionale lo spazio libero rimanente|  
|`true`|Simile all'interazione precedente, con l'eccezione che le <xref:System.Windows.Forms.SizeType.Percent> colonne o le righe acquisiscono un aspetto di ridimensionamento automatico.<br /><br /> Il <xref:System.Windows.Forms.TableLayoutPanel> controllo espande la colonna o la riga per creare spazio disponibile adeguato, in modo che nessuna colonna o riga con stile ritaglia il <xref:System.Windows.Forms.SizeType.Percent> contenuto. Il <xref:System.Windows.Forms.TableLayoutPanel> controllo consente di allocare il nuovo spazio proporzionalmente in base alla <xref:System.Windows.Forms.ColumnStyle.Width%2A> <xref:System.Windows.Forms.RowStyle.Height%2A> proprietà o.|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Forms.TableLayoutPanel>
- [Cenni preliminari sul controllo TableLayoutPanel](tablelayoutpanel-control-overview.md)
