---
title: 'Lync Server 2013: グループ通話の集配番号の範囲を作成または変更する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a Group Call Pickup number range
ms:assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945627(v=OCS.15)
ms:contentKeyID: 51541472
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5a644cb6008976894c88de570aa9cb6530e10c3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758071"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-group-call-pickup-number-range-in-lync-server-2013"></a>Create or modify a Group Call Pickup number range in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-01-30_

次の手順を使用して、コール パーク オービット テーブルで通話ピックアップ グループ番号の範囲を作成または変更します。

<div>


> [!NOTE]  
> 通話パークの軌道の番号範囲を作成、変更、削除、および表示するには、Lync Server 管理シェルを使用する必要があります。 グループ通話の集配番号の範囲は Lync Server コントロールパネルでは利用できません。



</div>

<div>


> [!IMPORTANT]  
> 通話集配グループの番号範囲には、GroupPickup の種類を割り当てる必要があります。 ユーザーが割り当てられているグループ番号が GroupPickup 型である場合にのみ、グループ通話のピックアップが有効になります。



</div>

通話ピックアップ グループ番号の範囲は、次のルールに従っている必要があります。

  - 範囲の開始番号が終了番号より大きくならないようにしてください。

  - 範囲の開始番号の値は、範囲の終了番号と同じ長さである必要があります。

  - 番号範囲は一意である必要があります。この範囲が他のどの範囲とも重ならないようにしてください。

  - 数値の範囲が文字\*で始まる場合、 \#または範囲が100よりも大きい場合。

  - 有効な値: 正規表現文字列と一致する\[\\\*|\#\]必要\[があります (?1-9\]\\d{0,7}) |(\[1-9\]\\d{0,8})。 つまり、値は、文字\*また\#は 1 ~ 9 のいずれかの文字列である必要があります (最初の文字をゼロにすることはできません)。 最初の文字が\*または\#である場合、次の文字は 1 ~ 9 の数字である必要があります (ゼロにすることはできません)。 後続の文字には、0 ~ 9 までの追加文字を使用できます (たとえば\#、"6000"\*、"92000"\*、"95551212"、"915551212")。 最初の文字が指定さ\*れ\#ていない場合、または最初の文字が 1 ~ 9 の数字 (0 以外) で、先頭が8文字である必要があります (たとえば、"915551212"、"41212"、"300")。

<div>

## <a name="to-create-or-modify-a-call-pickup-group-range"></a>通話ピックアップ グループの範囲を作成するには

1.  Lync Server 管理シェルが RTCUniversalServerAdmins グループのメンバーとして、または「 [Lync server 2013 の委任セットアップの権限](lync-server-2013-delegate-setup-permissions.md)」で説明されているように、必要なユーザー権限を持つコンピューターにログオンします。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  通話ピックアップ グループ番号の新しい範囲を作成するには、**New-CsCallParkOrbit** を使用します。 通話ピックアップ番号の既存の範囲を変更するには、**Set-CsCallParkOrbit** を使用します。
    
    コマンド ラインで、次のコマンドを実行します。
    
        New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
    
    例:
    
        New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
    
    次の例は、番号の範囲をコール パーク オービットから通話ピックアップ グループに変更する方法を示しています。
    
        Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
    
    <div>
    

    > [!IMPORTANT]  
    > 最初に間違ったタイプを指定して、グループの範囲がまだ使用されていない場合にのみ、このコマンドレットを使用して、番号の範囲に割り当てられているタイプを変更します。 番号の範囲を CallPark から GroupPickup、または GroupPickup から CallPark に変更した場合、番号の範囲が既に使用されていると、コール パークまたはグループ通話ピックアップのどちらかが、その番号の範囲に対して無効になります。 たとえば、番号の範囲を [CallPark] から [GroupPick] に変更すると、その範囲の orbits を使用して通話をパークすることができなくなります。

    
    </div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのコールパークの範囲の削除](lync-server-2013-delete-a-call-park-orbit-range.md)  


[新規-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/New-CsCallParkOrbit)  
[Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

