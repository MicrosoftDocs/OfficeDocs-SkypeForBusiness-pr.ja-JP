---
title: ネットワーク帯域幅ポリシー プロファイルの削除
TOCTitle: ネットワーク帯域幅ポリシー プロファイルの削除
ms:assetid: 4d6beda8-6aa5-4d5e-8a07-363598f0e0c8
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688050(v=OCS.15)
ms:contentKeyID: 49886951
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ネットワーク帯域幅ポリシー プロファイルの削除

 

_**トピックの最終更新日:** 2012-11-01_

帯域幅ポリシーは、通話受付管理 (CAC) の一部として、特定のモダリティの帯域幅制限を定義する際に使用します。Microsoft Lync Server 2013 では、オーディオとビデオのモダリティのみを帯域幅の制限に割り当てることができます。全体の帯域幅制限とセッション制限を設定できます。Lync Server コントロール パネルを使用して、これらのポリシーのコンテナー プロファイルを作成、変更、または削除できます。次の手順を使用して、ネットワーク帯域幅ポリシー プロファイルを削除します。ネットワーク帯域幅ポリシー プロファイルの作成または変更の詳細については、「 [帯域幅ポリシー プロファイルの作成または変更](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)」を参照してください。

## 帯域幅ポリシー プロファイルを削除するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**ネットワーク構成**\] をクリックし、\[**帯域幅ポリシー**\] をクリックします。

4.  \[**帯域幅ポリシー**\] ページで、削除する帯域幅ポリシー プロファイルをクリックします。
    
    > [!NOTE]
    > 1 つ以上のプロファイルを一度に削除できます。これを実行するには、Ctrl キーを押しながら、複数のプロファイルを選択します。また、すべてのプロファイルを選択するには、[<strong>編集</strong>] メニューの [<strong>すべて選択</strong>] をクリックします。


5.  \[**編集**\] メニューの \[**削除**\] をクリックします。
    

    > [!WARNING]
    > ネットワーク サイトに関連付けられている帯域幅ポリシー プロファイルを削除することはできません。プロファイルを削除するには、まず、ネットワーク サイトとの関連付けを削除する必要があります。ネットワーク サイトの変更方法の詳細については、「<A href="lync-server-2013-creating-or-modifying-network-sites.md">ネットワーク サイトの作成または変更</A>」を参照してください。



## 関連項目

#### タスク

[帯域幅ポリシー プロファイルの作成または変更](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[ネットワーク帯域幅ポリシー プロファイル情報の表示](lync-server-2013-viewing-network-bandwidth-policy-profile-information.md)  

#### その他のリソース

[Lync Server 2013 での通話管理受付の構成](lync-server-2013-configure-call-admission-control.md)  
[Remove-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)

