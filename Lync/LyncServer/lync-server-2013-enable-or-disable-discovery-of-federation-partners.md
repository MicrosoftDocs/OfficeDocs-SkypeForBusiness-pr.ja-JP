---
title: 'Lync Server 2013: フェデレーション パートナーの検出の有効化または無効化'
TOCTitle: フェデレーション パートナーの検出の有効化または無効化
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48272872
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのフェデレーション パートナーの検出の有効化または無効化

 

_**トピックの最終更新日:** 2013-02-23_

エッジ サーバーを展開して組織のフェデレーションを有効にした際に、フェデレーション パートナー ドメインの自動検出をサポートするかどうかを指定しています。このトピックの手順を使用して、この構成を変更します。

> [!NOTE]
> 次の手順では、既に組織に対してフェデレーションを有効にしていることを前提としています。フェデレーションを有効にする方法の詳細については、「展開」または「操作」のドキュメントの「<a href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013 でのリモート ユーザー アクセスの有効化または無効化</a>」を参照してください。


## 組織に対してフェデレーション ドメインの自動検出を有効または無効にするには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**外部ユーザー アクセス**\] をクリックし、\[**アクセス エッジ構成**\] をクリックします。

4.  \[**アクセス エッジ構成**\] ページで、\[**グローバル**\]、\[**編集**\]、\[**詳細の表示**\] の順にクリックします。

5.  \[**アクセス エッジ構成の編集**\] で、\[**フェデレーション ユーザーとの通信を有効にする**\] の \[**パートナー ドメインの検出を有効にする**\] チェック ボックスをオンまたはオフにして、パートナー ドメインの自動検出を有効また無効にします。

6.  \[**確定**\] をクリックします。

フェデレーション ユーザーが Lync Server 展開内のユーザーと共同作業できるようにするには、少なくとも 1 つの外部アクセス ポリシーも構成してフェデレーション ユーザー アクセスをサポートする必要があります。詳細については、「展開」または「操作」のドキュメントの「[Lync Server 2013 でのフェデレーションおよびパブリック IM 接続の有効化または無効化](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)」を参照してください。特定のフェデレーション ドメインのアクセス制御の詳細については、「操作」のドキュメントの「[Lync Server 2013 での組織の SIP フェデレーション ドメインの管理](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)」、「[Lync Server 2013 での組織の SIP フェデレーション プロバイダーの管理](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)」、および「[Lync Server 2013 での組織の XMPP フェデレーション パートナーの管理](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)」を参照してください。

## Windows PowerShell コマンドレットを使用したフェデレーション パートナーの検出の有効化または無効化

Windows PowerShell および Set-CsAccessEdgeConfiguration コマンドレットを使用してフェデレーション パートナーの検出を管理できます。このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## フェデレーション パートナーの検出を有効にするには

  - フェデレーション パートナーの検出を有効にするには、 **EnablePartnerDiscovery** プロパティの値を True ($True) に設定します。このプロパティの値を変更するには、DNS SRV ルーティングを有効にする必要があります。
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True

## フェデレーション パートナーの検出を無効にするには

  - フェデレーション パートナーの検出を無効にするには、 **EnablePartnerDiscovery** プロパティの値を False ($False) に設定します。
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

