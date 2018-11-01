---
title: QoE (Quality of Experience) の有効化
TOCTitle: QoE (Quality of Experience) の有効化
ms:assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg182583(v=OCS.15)
ms:contentKeyID: 48273549
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# QoE (Quality of Experience) の有効化

 

_**トピックの最終更新日:** 2013-02-23_

QoE (Quality of Experience) は、メディアの品質と、通話およびセッションに関係する参加者、デバイス名、ドライバー、IP アドレス、およびエンドポイントの種類についての情報を示す数値データを記録します。詳細については、「計画」のドキュメントの「[Lync Server 2013 での監視の計画](lync-server-2013-planning-for-monitoring.md)」を参照してください。

組織全体または組織内の各サイトで QoE を有効にするには、次の手順を実行します。

> [!NOTE]
> QoE を有効にするには、まず、監視を構成して、監視バック エンド データベースに接続する必要があります。詳細については、「<a href="lync-server-2013-deploying-monitoring.md">Lync Server 2013 での監視の展開</a>」を参照してください。


## Lync Server コントロール パネル を使用して QoE を有効にするには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Lync Server 2013 を展開したネットワーク内の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**監視およびアーカイブ**\] をクリックし、\[**QoE データ**\] をクリックします。

4.  \[**QoE データ**\] ページで、表から該当するコレクションをクリックして、\[**操作**\]、\[**QoE を有効にする**\] の順にクリックします。

## Windows PowerShell コマンドレットを使用して QoE を有効にする

Windows PowerShell と **Set-CsQoEConfiguration** コマンドレットを使用して、QoE を有効にできます。このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## 1 つの場所に対して QoE を有効にするには

  - QoE を有効にするには、EnableQoE パラメーターを True ($True) に設定します。
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True

## 1 つの場所に対して QoE を無効にするには

  - QoE を無効にするには、EnableQoE パラメーターを False ($False) に設定します。これによって監視がアンインストールされることはありません。QoE データの収集と保存が停止されるだけです。
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

## 複数の場所の QoE を 1 つのコマンドで有効にするには

  - このコマンドを実行すると、組織内で現在使用されているすべての QoE 構成設定に対して QoE が有効になります。
    
        Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True

詳細については、「[Set-CsQoEConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsQoEConfiguration)」を参照してください。

## 関連項目

#### その他のリソース

[Lync Server 2013 での監視の計画](lync-server-2013-planning-for-monitoring.md)  
[Lync Server 2013 での監視の展開](lync-server-2013-deploying-monitoring.md)

