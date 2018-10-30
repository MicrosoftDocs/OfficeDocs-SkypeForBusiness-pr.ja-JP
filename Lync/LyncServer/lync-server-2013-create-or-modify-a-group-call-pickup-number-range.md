---
title: グループ通話ピックアップ番号の範囲の作成または変更
TOCTitle: グループ通話ピックアップ番号の範囲の作成または変更
ms:assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ945627(v=OCS.15)
ms:contentKeyID: 52056596
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# グループ通話ピックアップ番号の範囲の作成または変更

 

_**トピックの最終更新日:** 2013-01-30_

次の手順を使用して、コール パーク オービット テーブルで通話ピックアップ グループ番号の範囲を作成または変更します。

> [!NOTE]
> コール パーク オービット テーブルにあるグループ通話ピックアップの番号範囲を作成、変更、削除、および表示するには、Lync Server 管理シェルを使用する必要があります。Lync Server コントロール パネルでは、グループ通話ピックアップの番号範囲を使用できません。



> [!IMPORTANT]
> 通話ピックアップ グループ番号の範囲には、タイプ GroupPickup を割り当てる必要があります。ユーザーに割り当てられているグループ番号がタイプ GroupPickup である場合にのみ、ユーザーがグループ通話ピックアップに対して有効になります。



通話ピックアップ グループ番号の範囲は、次のルールに従っている必要があります。

  - 範囲の開始番号が終了番号より大きくならないようにしてください。

  - 範囲の開始番号の値は、範囲の終了番号と同じ長さである必要があります。

  - 番号範囲は一意である必要があります。この範囲が他のどの範囲とも重ならないようにしてください。

  - 番号範囲が、文字 \* または \# で始まる場合、範囲は 100 を超える必要があります。

  - 有効な値: 正規表現文字列 (\[\\\*|\#\]?\[1-9\]\\d{0,7})|(\[1-9\]\\d{0,8}) に一致する必要があります。つまり、値には \* または \# の文字あるいは 1 ～ 9 の数字で始まる文字列を指定する必要があります (最初の文字を 0 にすることはできません)。最初の文字が \* または \# である場合、次の文字には 1 ～ 9 の数字 (0 は不可) を指定します。この後には 0 ～ 9 の数字を最大 7 文字まで追加できます ("\#6000"、"\*92000"、"\*95551212"、"915551212" など)。最初の文字が \* または \# ではない場合、最初の文字には 1 ～ 9 の数字 (0 は不可) を指定し、その後に 0 ～ 9 の数字を最大 8 文字まで指定します ("915551212"、"41212"、"300" など)。

## 通話ピックアップ グループの範囲を作成するには

1.  Lync Server 管理シェルがインストールされているコンピューターに、RTCUniversalServerAdmins グループのメンバーとして、または「[Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」に説明されている必要なユーザー権限を使用してログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  通話ピックアップ グループ番号の新しい範囲を作成するには、**New-CsCallParkOrbit** を使用します。通話ピックアップ番号の既存の範囲を変更するには、**Set-CsCallParkOrbit** を使用します。
    
    コマンド ラインで、次のコマンドを実行します。
    
        New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
    
    たとえば、次のようになります。
    
        New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
    
    次の例は、番号の範囲をコール パーク オービットから通話ピックアップ グループに変更する方法を示しています。
    
        Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
    

    > [!IMPORTANT]
    > 最初に間違ったタイプを指定して、グループの範囲がまだ使用されていない場合にのみ、このコマンドレットを使用して、番号の範囲に割り当てられているタイプを変更します。番号の範囲を CallPark から GroupPickup、または GroupPickup から CallPark に変更した場合、番号の範囲が既に使用されていると、コール パークまたはグループ通話ピックアップのどちらかが、その番号の範囲に対して無効になります。たとえば、番号の範囲を CallPark から GroupPick に変更した場合、コール パーク アプリケーションでは、パーク コールに対するオービットの範囲を使用できなくなります。



## 関連項目

#### タスク

[Lync Server 2013 でのコール パーク オービット範囲の削除](lync-server-2013-delete-a-call-park-orbit-range.md)  

#### その他のリソース

[New-CsCallParkOrbit](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsCallParkOrbit)  
[Set-CsCallParkOrbit](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCallParkOrbit)

