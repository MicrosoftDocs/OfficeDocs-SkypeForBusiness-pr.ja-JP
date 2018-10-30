---
title: グループ通話ピックアップ番号の範囲の削除
TOCTitle: グループ通話ピックアップ番号の範囲の削除
ms:assetid: 521891f3-7a5d-45de-92dc-d57025453159
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ945629(v=OCS.15)
ms:contentKeyID: 52056605
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# グループ通話ピックアップ番号の範囲の削除

 

_**トピックの最終更新日:** 2013-01-30_

グループ通話ピックアップ番号の範囲を削除するには、次の手順を実行します。

## 通話ピックアップ グループ番号の範囲を削除するには

1.  Lync Server 管理シェルがインストールされているコンピューターに、RTCUniversalServerAdmins グループのメンバーとして、または「[Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」に説明されている必要なユーザー権限を使用してログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  コマンドラインで、次のように入力します。
    
        Remove-CsCallParkOrbit -Identity "<group number range name>" 
    
    たとえば、次のようになります。
    
        Remove-CsCallParkOrbit -Identity "Redmond call pickup"
    
    > [!NOTE]
    > その他のオプションの詳細については、「<a href="https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsCallParkOrbit">Remove-CsCallParkOrbit</a>」を参照してください。


## 関連項目

#### タスク

[Lync Server 2013 でのコール パーク オービット範囲の作成または変更](lync-server-2013-create-or-modify-a-call-park-orbit-range.md)  

#### その他のリソース

[Remove-CsCallParkOrbit](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsCallParkOrbit)  
[Get-CsCallParkOrbit](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsCallParkOrbit)

