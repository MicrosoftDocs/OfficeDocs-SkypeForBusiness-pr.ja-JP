---
title: 'Lync Server 2013: ダイヤル プランに地域が割り当てられていることの確認'
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
ms.openlocfilehash: cd8790671157b823464a3b4b594ea8428a888f46
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739607"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="make-sure-dial-plans-lync-server-2013-have-assigned-regions"></a>「ダイヤルプラン Lync Server 2013 に地域が割り当てられていることを確認する」

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2010-11-02_

ダイヤルイン会議に使用するダイヤルプランには、ダイヤルイン会議アクセス番号と適切なダイヤルプランを関連付けるために、**ダイヤルイン会議領域**が指定されている必要があります。 ダイヤル プランをセットアップするときに、そのダイヤル プランに適用されるダイヤルイン会議の地域を指定します。 次に、ダイヤルインアクセス番号を作成するときに、アクセス番号を適切なダイヤルプランに関連付ける地域を選択します。

すべてのダイヤルプランの地域を指定することが重要であるため、この手順を使用して、すべてのダイヤルプランに地域が設定されていることを確認することをお勧めします。 この手順は省略可能です。

**Get-CsDialPlan**コマンドレットを使用して、地域がすべてのダイヤルイン会議ダイヤルプランに設定されているかどうかを確認します。 ダイヤル プランに地域がない場合は、**Set-CsDialPlan** コマンドレットを使用して地域を設定できます。 Lync Server コントロールパネルを使用して、既存のダイヤルプランの領域を更新することもできます。 Lync Server コントロールパネルの使用について詳しくは、「 [Lync server 2013 でダイヤルプランを変更](lync-server-2013-modify-a-dial-plan.md)する」をご覧ください。

<div>

## <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a>ダイヤル プランで地域プロパティが設定されているかどうかを確認するには

1.  RTCUniversalServerAdmins グループのメンバーか、**Cs-VoiceAdministrator**、**Cs-ServerAdministrator**、または **CsAdministrator** の役割のメンバーとしてコンピューターにログオンします。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  コマンド プロンプトで次のコマンドを実行します。
    
        Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
    
    次に例を示します。
    
        Get-CsDialPlan
    
    この例では、組織で構成されているすべてのダイヤル プランが戻されます。

4.  戻されたダイヤル プランを確認して、ダイヤルイン会議の地域が含まれていないものを識別します。 詳細については、「Lync Server 管理シェルのドキュメント」を参照してください。

</div>

<div>

## <a name="to-set-the-region-property-for-a-dial-plan"></a>ダイヤル プランの地域プロパティを設定するには

1.  RTCUniversalServerAdmins グループのメンバーか、**Cs-VoiceAdministrator**、**Cs-ServerAdministrator**、または **CsAdministrator** の役割のメンバーとしてコンピューターにログオンします。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  ダイヤルイン会議の地域が含まれていないダイヤル プランで、以下を実行します。
    
        Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
    
    例:
    
        Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
    
    この例では、Redmond という Identity を持つダイヤル プランを変更して、DialinConferencingRegion プロパティを "US West Coast" に設定します。 詳細については、「Lync Server 管理シェルのドキュメント」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

