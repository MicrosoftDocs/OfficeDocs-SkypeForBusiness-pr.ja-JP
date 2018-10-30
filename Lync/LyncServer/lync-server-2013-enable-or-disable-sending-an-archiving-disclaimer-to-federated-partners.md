---
title: 'Lync Server 2013: フェデレーション パートナーに対するアーカイブ免責事項の送信の有効化または無効化'
TOCTitle: フェデレーション パートナーに対するアーカイブ免責事項の送信の有効化または無効化
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48273553
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのフェデレーション パートナーに対するアーカイブ免責事項の送信の有効化または無効化

 

_**トピックの最終更新日:** 2013-02-23_

エッジ サーバーを展開し、組織に対してフェデレーションを有効にした時点で、フェデレーション パートナーにアーカイブについての免責事項を自動で送信するかどうかを指定する必要があります。外部通信をアーカイブする場合は、アーカイブについての免責事項の送信を有効にする必要があります。このトピックの手順を使用して、この構成を変更します。

> [!NOTE]
> 次の手順では、既に組織に対してフェデレーションを有効にしていることを前提としています。フェデレーションを有効にする方法の詳細については、「展開」または「操作」のドキュメントの「<a href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013 でのリモート ユーザー アクセスの有効化または無効化</a>」を参照してください。


## フェデレーション パートナーへのアーカイブ免責事項の送信を有効または無効にするには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**外部ユーザー アクセス**\] をクリックし、\[**アクセス エッジ構成**\] をクリックします。

4.  \[**アクセス エッジ構成**\] タブで、\[**グローバル**\] をクリックし、\[**編集**\] をクリックしてから、\[**詳細の表示**\] をクリックします。

5.  \[**アクセス エッジ構成の編集**\] の \[**フェデレーション ユーザーとの通信を有効にする**\] で、\[**フェデレーション パートナーにアーカイブについての免責事項を送信する**\] チェック ボックスをオンまたはオフにして、アーカイブについての免責事項の自動送信を有効または無効にします。

6.  \[**確定**\] をクリックします。

フェデレーション ユーザーが Lync Server 2013 展開内のユーザーと共同作業できるようにするには、少なくとも 1 つの外部アクセス ポリシーも構成してフェデレーション ユーザー アクセスをサポートする必要があります。詳細については、「展開」または「操作」のドキュメントの「[Lync Server 2013 での組織の XMPP フェデレーション パートナーの管理](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)」を参照してください。特定のフェデレーション ドメインのアクセス制御の詳細については、「展開」または「操作」のドキュメントの「[Lync Server 2013 での、許可された外部ドメイン向けサポートの構成](lync-server-2013-configure-support-for-allowed-external-domains.md)」を参照してください。

## Windows PowerShell コマンドレットを使用してアーカイブについての免責事項を有効または無効にする

アーカイブについての免責事項を使用するかどうかは、Windows PowerShell と Set-CsAccessEdgeConfiguration コマンドレットを使用して管理できます。このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## アーカイブについての免責事項を有効にするには

  - アーカイブについての免責事項を有効にするには、 **EnableArchivingDisclaimer** プロパティの値を True ($True) に設定します。
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

## アーカイブについての免責事項を無効にするには

  - アーカイブについての免責事項を有効にするには、 **EnableArchivingDisclaimer** プロパティの値を False ($False) に設定します。
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False

