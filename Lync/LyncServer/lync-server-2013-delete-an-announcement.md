---
title: アナウンスの削除
TOCTitle: アナウンスの削除
ms:assetid: 26ea7149-4470-4c22-9bab-8a4065aca44e
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ687998(v=OCS.15)
ms:contentKeyID: 49886882
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# アナウンスの削除

 

_**トピックの最終更新日:** 2012-11-01_

未使用の番号への通話に使用されるアナウンスを削除するには、次の手順を実行します。

## アナウンスを削除するには

1.  Lync Server 管理シェルがインストールされているコンピューターに、RTCUniversalServerAdmins グループのメンバーとして、または「[Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」に説明されている必要なユーザー権限を使用してログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  組織のすべてのアナウンスの一覧を取得します。コマンド ラインで次のコマンドを実行します。
    
        Get-CsAnnouncement

4.  表示された一覧で、削除するアナウンスを見つけて、その GUID をコピーします。次に、コマンド ラインで次のコマンドを実行します。
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>" 
    
    次に例を示します。
    
        Remove-CsAnnouncement -Identity "ApplicationServer:Redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"
    
    > [!NOTE]
    > その他のオプションの詳細については、「<a href="https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsAnnouncement">Get-CsAnnouncement</a>」および「<a href="https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsAnnouncement">Remove-CsAnnouncement</a>」を参照してください。


## 関連項目

#### タスク

[Lync Server 2013 でのアナウンスの作成](lync-server-2013-create-an-announcement.md)  

#### その他のリソース

[Remove-CsAnnouncement](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsAnnouncement)  
[Get-CsAnnouncement](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsAnnouncement)

