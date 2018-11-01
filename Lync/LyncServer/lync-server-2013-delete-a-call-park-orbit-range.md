---
title: Lync Server 2013 でのコール パーク オービット範囲の削除
TOCTitle: Lync Server 2013 でのコール パーク オービット範囲の削除
ms:assetid: 85e9f916-062d-450d-ac0a-aeaefc0f7cdc
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg182546(v=OCS.15)
ms:contentKeyID: 48272774
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのコール パーク オービット範囲の削除

 

_**トピックの最終更新日:** 2013-02-20_

コール パーク オービット範囲を削除するには、次のいずれかの手順を使用します。

## Lync Server コントロール パネルを使用してコール パーク オービット範囲を削除するには

1.  RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。詳細については、「[Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**音声機能**\] をクリックし、\[**コール パーク**\] をクリックします。

4.  \[**コール パーク**\] ページの検索フィールドで、削除するオービット範囲の名前または名前の一部を入力します。

5.  結果のオービット一覧でオービットをクリックし、\[**編集**\] をクリックして、\[**削除**\] をクリックします。

6.  \[**OK**\] をクリックします。

## コマンドレットを使用してコール パーク オービット範囲を削除するには

1.  Lync Server 管理シェルがインストールされているコンピューターに、RTCUniversalServerAdmins グループのメンバーとして、または「[Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」に説明されている必要なユーザー権限を使用してログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  コマンドラインで、次のように入力します。
    
        Remove-CsCallParkOrbit -Identity "<orbit range name>" 
    
    次に例を示します。
    
        Remove-CsCallParkOrbit -Identity "Redmond orbit 1"
    
    > [!NOTE]
    > 他のオプションの詳細については、「<a href="https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</a>」を参照してください。


## 関連項目

#### タスク

[Lync Server 2013 でのコール パーク オービット範囲の作成または変更](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)  

#### その他のリソース

[Remove-CsCallParkOrbit](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsCallParkOrbit)  
[Get-CsCallParkOrbit](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsCallParkOrbit)

