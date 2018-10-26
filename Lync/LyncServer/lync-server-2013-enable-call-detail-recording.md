---
title: 通話詳細記録の有効化
TOCTitle: 通話詳細記録の有効化
ms:assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg520980(v=OCS.15)
ms:contentKeyID: 48271813
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 通話詳細記録の有効化

 

_**トピックの最終更新日:** 2013-02-23_

通話詳細記録 (CDR) は、インスタント メッセージング、ボイス オーバー IP (VoIP) 通話、アプリケーション共有、ファイル送信などのピアツーピア アクティビティ、および会議に関する使用状況および診断情報を記録します。使用状況データは投資収益率 (ROI) の計算に、診断データはピアツーピア アクティビティおよび会議のトラブルシューティングに使用できます。

組織全体または組織内の各サイトで CDR を有効にするには、次の手順を実行します。

> [!NOTE]
> CDR を有効にするには、監視および監視データベースを構成する必要があります。詳細については、「<a href="lync-server-2013-deploying-monitoring.md">Lync Server 2013 での監視の展開</a>」を参照してください。


## Lync Server コントロール パネルを使用して CDR を有効にするには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Lync Server 2013 を展開したネットワーク内の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで、\[**監視とアーカイブ**\] をクリックし、\[**通話詳細記録**\] をクリックします。

4.  \[**通話詳細記録**\] ページで、表から該当するサイトをクリックして、\[**アクション**\] をクリックし、\[**CDR の有効化**\] をクリックします。
    
    > [!NOTE]
    > CDR は、既定では有効になっています。


## Lync Server 管理シェル コマンドレットを使用して CDR を有効にするには

Windows PowerShell および **Set-CsCdrConfiguration** コマンドレットを使用して、CDR を有効にすることもできます。このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## 1 つの場所の CDR を有効にするには

  - CDR を無効にするには、EnableCDR パラメーターを True ($True) に設定します。
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True

## 1 つの場所の CDR を無効にするには

  - CDR を無効にするには、EnableCDR パラメーターを False ($False) に設定します。これにより、監視がアンインストールされることはありません。CDR データの収集と保存が一時停止されます。
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

## 1 つのコマンドで複数の場所にある CDR を有効にするには

  - このコマンドによって、組織で現在使用されているすべての CDR 構成設定の CDR が有効になります。
    
        Get-CsCdrConfiguration | Set-CsCdrConfiguration "site:Redmond" -EnableCDR $True

詳細については、[Set-CsCdrConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCdrConfiguration) コマンドレットのヘルプ トピックを参照してください。

## 関連項目

#### その他のリソース

[Lync Server 2013 での監視の計画](lync-server-2013-planning-for-monitoring.md)  
[Lync Server 2013 での監視の展開](lync-server-2013-deploying-monitoring.md)

