---
title: 'Lync Server 2013: 存続可能ブランチ アプライアンスまたはサーバーの展開 - 中央サイトのタスク'
TOCTitle: 存続可能ブランチ アプライアンスまたはサーバーの展開 - 中央サイトのタスク
ms:assetid: 0f631a36-fc2e-41cd-8a0d-f27e84f4a89e
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398189(v=OCS.15)
ms:contentKeyID: 48271286
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 による存続可能ブランチ アプライアンスまたはサーバーの展開 - 中央サイトのタスク

 

_**トピックの最終更新日:** 2012-10-18_

このセクションに示すタスクをセントラル サイトで完了します。存続可能ブランチ サーバーを展開している場合は、最初のタスクを省略します。


> [!IMPORTANT]
> このセクションのタスクを実行する前に、次の条件が満たされている必要があります。 
> <UL>
> <LI>
> <P>Lync Server がセントラル サイトに設定されている必要があります。</P>
> <LI>
> <P>RTCUniversalSBATechnicians グループにブランチ サイトのインストール技術者が追加されている必要があります。</P></LI></UL>また、次の内容の実行をお勧めします。 
> <UL>
> <LI>
> <P>各ブランチ サイトで DHCP サーバーを展開し、クライアントが IP アドレスを取得できるようにします。</P>
> <LI>
> <P>各ブランチ サイトで DHCP サーバーを展開する代わりに、Lync Server 管理シェルのコマンドレット <STRONG>Set-CsRegistrarConfiguration –EnableDHCPServer $true</STRONG> を使用して、存続可能ブランチ アプライアンスまたは 存続可能ブランチ サーバーで Lync Server DHCP を有効にします。詳細については、「計画」のドキュメントの「<A href="lync-server-2013-branch-site-resiliency-requirements.md">Lync Server 2013 のブランチ サイトの復元要件</A>」の「ハードウェアおよびソフトウェア要件」を参照してください。</P></LI></UL>



## このセクション中

  - [Lync Server 2013 での、Active Directory への存続可能ブランチ アプライアンスの追加](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)

  - [Lync Server 2013 でのトポロジへのブランチ サイトの追加](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [Lync Server 2013 での存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーの定義](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

