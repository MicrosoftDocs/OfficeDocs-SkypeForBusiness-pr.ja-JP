---
title: 帯域幅ポリシー プロファイルの作成または変更
TOCTitle: 帯域幅ポリシー プロファイルの作成または変更
ms:assetid: 08a2e18f-9b0d-4a2f-aa14-13bbf79ec745
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg520945(v=OCS.15)
ms:contentKeyID: 48271174
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 帯域幅ポリシー プロファイルの作成または変更

 

_**トピックの最終更新日:** 2012-10-15_

帯域幅ポリシーは、通話受付管理 (CAC) の一部として、特定のモダリティの帯域幅制限を定義する際に使用します。Microsoft Lync Server 2013 では、オーディオとビデオのモダリティのみを帯域幅の制限に割り当てることができます。全体の帯域幅制限とセッション制限を設定できます。Lync Server コントロール パネルを使用して、これらのポリシーのコンテナー プロファイルを作成、変更、または削除できます。各帯域幅ポリシー プロファイルは、1 つ以上のネットワーク サイトに関連付けることができます。帯域幅ポリシー プロファイルを作成または変更するには、以下の手順を使用します。帯域幅ポリシー プロファイルを削除する方法については、「[ネットワーク帯域幅ポリシー プロファイルの削除](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)」を参照してください。

## 新しい帯域幅ポリシー プロファイルを作成するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**ネットワーク構成**\] をクリックし、\[**帯域幅ポリシー**\] をクリックします。

4.  \[**帯域幅ポリシー**\] ページで、\[**新規**\] をクリックします。

5.  \[**新規帯域幅ポリシー プロファイル**\] で、\[**名前**\] フィールドに名前を入力します。 この名前は、すべての帯域幅ポリシー プロファイルの中で一意である必要があります。

6.  \[**オーディオ リミット**\] フィールドで、数値を入力します。 この値は、すべてのオーディオ接続に割り当てられる最大帯域幅 (kbps 単位) です。

7.  \[**オーディオ セッション リミット**\] フィールドに、数値を入力します。 この値は、個々のオーディオ接続に割り当てられる最大帯域幅 (kbps 単位) です。 この値は 40 以上である必要があります。

8.  \[**ビデオ リミット**\] フィールドに、数値を入力します。 この値は、すべてのビデオ接続に割り当てられる最大帯域幅 (kbps 単位) です。

9.  \[**ビデオ セッション リミット**\] フィールドに、数値を入力します。 この値は、個々のビデオ接続に割り当てられる最大帯域幅 (kbps 単位) です。 この値は 100 以上である必要があります。

10. (オプション) \[**説明**\] フィールドに値を入力して、名前だけでは表現することのできないこの帯域幅ポリシー プロファイルの詳細情報を提供します。

11. \[**確定**\] をクリックします。
    
    > [!NOTE]
    > 新しい帯域幅ポリシー プロファイルを作成しても、帯域幅制限が自動で強制的に適用されるわけではありません。 まず、ポリシー プロファイルをサイトに関連付ける必要があります。 ポリシー プロファイルのサイトへの関連付け方法の詳細については、「<a href="lync-server-2013-creating-or-modifying-network-sites.md">ネットワーク サイトの作成または変更</a>」を参照してください。


## 帯域幅ポリシー プロファイルを変更するには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**ネットワーク構成**\] をクリックし、\[**帯域幅ポリシー**\] をクリックします。

4.  \[**帯域幅ポリシー**\] ページで、変更する帯域幅ポリシー プロファイルをクリックします。

5.  \[**編集**\] メニューの \[**詳細の表示**\] をクリックします。

6.  \[**帯域幅ポリシー プロファイルの編集**\] ページで、必要に応じてフィールドの内容を変更します (詳細については、このトピックの「新しい帯域幅ポリシー プロファイルを作成するには」を参照)。

7.  \[**確定**\] をクリックします。
    
    > [!NOTE]
    > 帯域幅ポリシー プロファイルを変更すると、この帯域幅ポリシー プロファイルに関連付けられたすべてのネットワーク サイトの帯域幅制限がすぐに更新されます。


## 関連項目

#### タスク

[ネットワーク帯域幅ポリシー プロファイルの削除](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  

#### その他のリソース

[Lync Server 2013 での通話管理受付の構成](lync-server-2013-configure-call-admission-control.md)  
[New-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  
[Set-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  
[Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)

