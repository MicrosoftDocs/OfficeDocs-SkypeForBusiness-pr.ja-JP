---
title: 'Lync Server 2013: ダイヤルプランに地域が割り当てられていることを確認する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Make sure dial plans have assigned regions
ms:assetid: 3da3a907-0dbf-4440-b12f-370f94dd4c17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425903(v=OCS.15)
ms:contentKeyID: 48183937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f25ca766ab7292aeeba0d2e621eccff5a0c47fb8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037567"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="make-sure-dial-plans-lync-server-2013-have-assigned-regions"></a>ダイヤルプラン Lync Server 2013 に地域が割り当てられていることを確認する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2010-11-02_

ダイヤルイン会議で使用されるダイヤル プランでは、ダイヤルイン会議のアクセス番号と適切なダイヤル プランを関連付ける [**ダイヤルイン会議の地域**] が指定されている必要があります。 ダイヤル プランを設定する際に、そのダイヤル プランに適用されるダイヤルイン会議の地域を指定します。 続いてダイヤルイン アクセス番号を作成する際に、そのアクセス番号と適切なダイヤル プランを関連付ける地域を選択します。

すべてのダイヤル プランに地域を指定することは重要であるため、この手順を使用して、すべてのダイヤル プランに地域があることを確認することをお勧めします。このステップはオプションです。

**Get-CsDialPlan** コマンドレットを使用して、すべてのダイヤルイン会議のダイヤル プランで地域が設定されているかどうかを確認します。 ダイヤル プランに地域がない場合は、**Set-CsDialPlan** コマンドレットを使用して地域を設定できます。 また、Lync Server コントロールパネルを使用して、既存のダイヤルプランの地域を更新することもできます。 Lync Server コントロールパネルの使用の詳細については、「 [Modify a dial plan In Lync server 2013](lync-server-2013-modify-a-dial-plan.md)」を参照してください。

<div>

## <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a>ダイヤル プランで地域プロパティが設定されているかどうかを確認するには

1.  RTCUniversalServerAdmins グループのメンバーか、**CsVoiceAdministrator**、**CsServerAdministrator**、または **CsAdministrator** の役割のメンバーとしてコンピューターにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  コマンド プロンプトで次のコマンドを実行します。
    
        Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
    
    例:
    
        Get-CsDialPlan
    
    この例では、組織で構成されているすべてのダイヤル プランが戻されます。

4.  戻されたダイヤル プランを確認して、ダイヤルイン会議の地域が含まれていないものを識別します。 詳細については、Lync Server 管理シェルのドキュメントを参照してください。

</div>

<div>

## <a name="to-set-the-region-property-for-a-dial-plan"></a>ダイヤル プランの地域プロパティを設定するには

1.  RTCUniversalServerAdmins グループのメンバーか、**CsVoiceAdministrator**、**CsServerAdministrator**、または **CsAdministrator** の役割のメンバーとしてコンピューターにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  ダイヤルイン会議の地域が含まれていないダイヤル プランで、以下を実行します。
    
        Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
    
    次にその例を示します。
    
        Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
    
    この例では、Redmond という ID を持つダイヤル プランを変更して、DialinConferencingRegion プロパティを "US West Coast" に設定します。 詳細については、Lync Server 管理シェルのドキュメントを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

