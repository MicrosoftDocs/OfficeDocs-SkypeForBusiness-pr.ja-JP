---
title: 'Lync Server 2013: SIP トランク上の通話受付管理'
TOCTitle: SIP トランク上の通話受付管理
ms:assetid: 7eada098-3d47-4be2-839f-8f87d582efe8
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398632(v=OCS.15)
ms:contentKeyID: 48272657
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の SIP トランク上の通話受付管理

 

_**トピックの最終更新日:** 2012-09-22_

SIP トランクに通話受付管理 (CAC) を展開するには、インターネット テレフォニー サービス プロバイダー (ITSP) を表すためのネットワーク サイトを作成します。SIP トランクに帯域幅ポリシーの値を適用するには、企業内のネットワーク サイトと ITSP を表すために作成するネットワーク サイトのサイト間ポリシーを作成します。

次の図は、SIP トランクの CAC 展開の例を示しています。

**SIP トランクの CAC 構成**

![通話受付管理の SIP トランキングの図](images/Gg398632.276c0d8f-1dd5-4883-8499-c202399ddbe9(OCS.15).jpg "通話受付管理の SIP トランキングの図")

SIP トランクに CAC を構成するには、CAC の展開時に次の作業を行う必要があります。

1.  ITSP を表すためのネットワーク サイトを作成します。 ネットワーク サイトを適切なネットワーク地域に関連付けて、このネットワーク サイトの音声とビデオにゼロの帯域幅を割り当てます。詳細については、「展開」のドキュメントの「[Lync Server 2013 での CAC のネットワーク サイトの構成](lync-server-2013-configure-network-sites-for-cac.md)」を参照してください。
    
    > [!NOTE]
    > ITSP では、このネットワーク サイト構成は機能しません。 帯域幅ポリシーの値は、手順 2 で実際に適用されます。


2.  手順 1 で作成したサイトの関連するパラメーター値を使用して、SIP トランクのサイト間リンクを作成します。たとえば、企業内のネットワーク サイトの名前を NetworkSiteID1 パラメーターの値として使用し、ITSP ネットワーク サイトの名前を NetworkSiteID2 パラメーターの値として使用します。詳細については、「展開」のドキュメントの「[Lync Server 2013 でのネットワーク サイト間ポリシーの作成](lync-server-2013-create-network-intersite-policies.md)」を参照してください。New-CsNetworkInterSitePolicy コマンドレットについては、Lync Server 管理シェルのドキュメントを参照してください。

3.  ITSP からセッション ボーダー コントローラー (SCB) のメディア終端ポイントの IP アドレスを取得します。 サブネット マスクが 32 の IP アドレスを、ITSP を表すネットワーク サイトに追加します。詳細については、「[Lync Server 2013 でのネットワーク サイトとサブネットの関連付け](lync-server-2013-associate-a-subnet-with-a-network-site.md)」を参照してください。

