---
title: 割り当てられていない番号の範囲の削除
TOCTitle: 割り当てられていない番号の範囲の削除
ms:assetid: a8141bfb-b94d-4d0f-a7a9-2e60d10b103a
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg182565(v=OCS.15)
ms:contentKeyID: 48273209
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 割り当てられていない番号の範囲の削除

 

_**トピックの最終更新日:** 2012-11-01_

アナウンスの割り当てられていない番号範囲を削除するには、次のいずれかの手順を使用します。

## Lync Server コントロール パネルを使用して割り当てられていない番号範囲を削除するには

1.  RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。詳細については、「[Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**音声機能**\] をクリックし、\[**割り当てられていない番号**\] をクリックします。

4.  \[**割り当てられていない番号**\] ページの検索フィールドで、削除する割り当てられていない番号範囲の名前または名前の一部を入力します。

5.  結果の番号範囲の一覧で、名前をクリックして、\[**編集**\] をクリックし、\[**削除**\] をクリックします。

6.  \[**すべて確定**\] をクリックします。

## コマンドレットを使用して割り当てられていない番号範囲を削除するには

1.  Lync Server 管理シェルがインストールされているコンピューターに、RTCUniversalServerAdmins グループのメンバーとして、または「[Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」に説明されている必要なユーザー権限を使用してログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  コマンドラインで、次のように入力します。
    
        Remove-CsUnassignedNumber -Identity "<name of unassigned number range>" 
    
    次に例を示します。
    
        Remove-CsUnassignedNumber -Identity "Unassigned range 1"
    
    > [!NOTE]
    > その他のオプションの詳細については、「<a href="https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</a>」を参照してください。


## 関連項目

#### タスク

[Lync Server 2013 での割り当てられていない番号範囲の作成または変更](lync-server-2013-create-or-modify-an-unassigned-number-range.md)  

#### その他のリソース

[Remove-CsUnassignedNumber](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsUnassignedNumber)  
[Get-CsUnassignedNumber](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUnassignedNumber)

