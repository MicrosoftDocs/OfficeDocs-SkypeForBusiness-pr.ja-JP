---
title: ネットワーク帯域幅ポリシー プロファイル情報の表示
TOCTitle: ネットワーク帯域幅ポリシー プロファイル情報の表示
ms:assetid: eed453fc-04e9-4971-959c-6fad54bf1c96
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ721931(v=OCS.15)
ms:contentKeyID: 49887210
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ネットワーク帯域幅ポリシー プロファイル情報の表示

 

_**トピックの最終更新日:** 2013-02-23_

帯域幅ポリシーは、通話受付管理 (CAC) の一部として、特定のモダリティの帯域幅制限を定義する際に使用します。Microsoft Lync Server 2013 では、オーディオとビデオのモダリティのみを帯域幅の制限に割り当てることができます。全体の帯域幅制限とセッション制限を設定できます。Lync Server コントロール パネル を使用して、これらのポリシーのコンテナー プロファイルを作成、変更、または削除できます。各帯域幅ポリシー プロファイルは、1 つ以上のネットワーク サイトに関連付けることができます。以下の手順に従って、帯域幅ポリシー プロファイルを表示します。帯域幅ポリシー プロファイルを作成または変更するには、「[帯域幅ポリシー プロファイルの作成または変更](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)」を参照してください。

## 帯域幅ポリシー プロファイルを変更するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**ネットワーク構成**\] をクリックし、\[**帯域幅ポリシー**\] をクリックします。

4.  \[**帯域幅ポリシー**\] ページで、変更する帯域幅ポリシー プロファイルをクリックします。

5.  \[**編集**\] メニューの \[**詳細の表示**\] をクリックします。

## Lync Server PowerShell コマンドレットを使用したネットワーク帯域幅ポリシー プロファイル情報の表示

ネットワーク帯域幅プロファイルは、Lync Server PowerShell と Get-CsNetworkBandwidthPolicyProfile コマンドレットを使用して表示することもできます。このコマンドレットは、Lync Server 2013 管理シェル または Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## ネットワーク帯域幅ポリシー プロファイルの表示

  - すべてのネットワーク帯域幅ポリシー プロファイルに関する情報を表示するには、Lync Server 管理シェル で次のコマンドを入力して Enter キーを押します。
    
        Get-CsNetworkBandwidthPolicyProfile
    
    次のような情報が表示されます。
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :

詳細については、[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) コマンドレットのヘルプ トピックを参照してください。

## 関連項目

#### タスク

[帯域幅ポリシー プロファイルの作成または変更](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[ネットワーク帯域幅ポリシー プロファイルの削除](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  

#### その他のリソース

[Lync Server 2013 での通話管理受付の構成](lync-server-2013-configure-call-admission-control.md)

