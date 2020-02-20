---
title: 'Lync Server 2013: グループ通話ピックアップ番号の範囲の作成または変更'
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
ms.openlocfilehash: d215fe6959b169ec5f092757174d105a75a5402a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145526"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-group-call-pickup-number-range-in-lync-server-2013"></a>Lync Server 2013 でグループ通話ピックアップ番号の範囲を作成または変更する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-01-30_

次の手順を使用して、コールパークオービットテーブルで通話ピックアップグループの番号範囲を作成または変更します。

<div>


> [!NOTE]  
> 通話パークオービットテーブルでグループ通話ピックアップ番号の範囲を作成、変更、削除、表示するには、Lync Server 管理シェルを使用する必要があります。 グループ通話ピックアップ番号の範囲は、Lync Server コントロールパネルでは使用できません。



</div>

<div>


> [!IMPORTANT]  
> 通話ピックアップグループ番号の範囲には、GroupPickup の種類を割り当てる必要があります。 ユーザーが割り当てられているグループ番号が GroupPickup の場合にのみ、グループ通話ピックアップが有効になります。



</div>

通話ピックアップグループ番号の範囲は、次のルールに準拠している必要があります。

  - 範囲の開始番号が終了番号より大きくならないようにしてください。

  - 範囲の開始番号の値は、範囲の終了番号と同じ長さである必要があります。

  - 番号範囲は一意である必要があります。この範囲が他のどの範囲とも重ならないようにしてください。

  - 番号範囲が文字\*または\#で始まる場合、範囲は100より大きくなければなりません。

  - 有効な値: 正規表現文字列である必要\[\\\*|\#\]が\[あります (?1-9\]\\d{0,7}) |(\[1-9\]\\d{0,8})。 つまり、値は、文字\*また\#は 1 ~ 9 の数字で始まる文字列である必要があります (最初の文字を0にすることはできません)。 最初の文字が\*または\#の場合、次の文字は 1 ~ 9 の数字である必要があります (ゼロにすることはできません)。 後続の文字には、0から9までの任意の文字を追加できます (\#たとえば、"6000\*"、"92000\*"、"95551212"、"915551212" など)。 最初の文字がまたは\*で\#はない場合、最初の文字は 1 ~ 9 の数字 (0 にはできません)、数字 0 ~ 9 (例: "915551212"、"41212"、"300") のいずれかである必要があります。

<div>

## <a name="to-create-or-modify-a-call-pickup-group-range"></a>通話ピックアップグループの範囲を作成または変更するには

1.  Lync Server 管理シェルがインストールされているコンピューターに、RTCUniversalServerAdmins グループのメンバーとして、または「 [Lync server 2013 のセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」に説明されている必要なユーザー権限を使用してログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  新しい通話ピックアップグループ番号の範囲を作成するには、 **get-cscallparkorbit**を使用します。 通話ピックアップ番号の既存の範囲を変更するには、 **get-cscallparkorbit**を使用します。
    
    コマンド ラインで、次のコマンドを実行します。
    
        New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
    
    次に例を示します。
    
        New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
    
    次の例は、電話パークオービットからピックアップグループを呼び出すために番号の範囲を変更する方法を示しています。
    
        Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
    
    <div>
    

    > [!IMPORTANT]  
    > 番号範囲に割り当てられる種類を変更するには、最初に間違った種類を指定し、グループ範囲がまだ使用されていない場合にのみ、このコマンドレットを使用します。 番号範囲を CallPark から GroupPickup に変更した場合や、番号範囲が既に使用されている場合は、コールパークまたはグループ通話ピックアップのいずれかがその番号範囲に対して機能しなくなります。 たとえば、番号の範囲を CallPark から GroupPick に変更した場合、コールパークアプリケーションはその範囲のオービットを使用して通話をパークすることができなくなります。

    
    </div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのコールパークオービット範囲の削除](lync-server-2013-delete-a-call-park-orbit-range.md)  


[Get-cscallparkorbit](https://docs.microsoft.com/powershell/module/skype/New-CsCallParkOrbit)  
[Get-cscallparkorbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

