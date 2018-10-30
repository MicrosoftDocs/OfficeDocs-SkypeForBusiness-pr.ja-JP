---
title: 通話受付管理の有効化
TOCTitle: 通話受付管理の有効化
ms:assetid: 80201105-18f7-4c02-9c71-8df5a952f6c7
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398642(v=OCS.15)
ms:contentKeyID: 48272697
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 通話受付管理の有効化

 

_**トピックの最終更新日:** 2012-10-19_

通話受付管理展開のネットワーク設定を構成したなら、帯域幅ポリシーを反映させるために CAC を有効にする必要があります。

詳細については、Lync Server 管理シェルのドキュメントに記載されている次のコマンドレットを参照してください。

  - [Get-CsNetworkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkConfiguration)

  - [Set-CsNetworkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkConfiguration)

  - [Remove-CsNetworkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkConfiguration)

## 管理シェルを使用して通話受付管理を有効にするには

1.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

2.  Set-CsNetworkConfiguration コマンドレットを実行して、ネットワークの CAC を有効にします。たとえば、以下を実行します。
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 1
    
    ネットワークの CAC を無効にする場合は、次のように実行します。
    
        Set-CsNetworkConfiguration -EnableBandwidthPolicyCheck 0

## Lync Server コントロール パネルを使用して通話受付管理を有効にするには

1.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

2.  左側のナビゲーション バーで \[**ネットワーク構成**\] をクリックします。

3.  \[**グローバル**\] ナビゲーション ボタンをクリックします。

4.  一覧で \[**グローバル**\] をクリックし、\[**編集**\] メニューの \[**詳細の表示**\] をクリックします。

5.  \[**グローバル設定の編集**\] ページの \[**通話受付管理の有効化**\] チェック ボックスをオンにします。
    
    > [!NOTE]
    > 展開全体で通話受付管理を無効にする場合は、このチェック ボックスをオフにします。


6.  \[**確定**\] をクリックします。

