---
title: 'Lync Server 2013: 存続可能ブランチ アプライアンスまたはサーバーの展開'
TOCTitle: 存続可能ブランチ アプライアンスまたはサーバーの展開
ms:assetid: cb780c14-dc5f-41ba-8092-f20ae905bd16
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398849(v=OCS.15)
ms:contentKeyID: 48273586
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 を使用した存続可能ブランチ アプライアンスまたはサーバーの展開

 

_**トピックの最終更新日:** 2014-12-10_

復元性 エンタープライズ VoIP とはブランチサイトの復元性のことです。つまり、中央サイトへのリンクが使用不能になってもブランチ サイトのユーザーに エンタープライズ VoIP サービスを継続して提供する機能のことです。

小中規模のブランチ サイト (ユーザーが 25 ～ 1,000 のブランチ サイト) の場合は、 存続可能ブランチ アプライアンスを展開し、公衆交換電話網 (PSTN) 通話を、組み込み PSTN ゲートウェイまたは SIP トランクを使用して電話サービス プロバイダーに終結させることをお勧めします。 存続可能ブランチ アプライアンスは、 Windows Server 2008 R2 オペレーティング システム、 Lync Server 2013 レジストラー、 仲介サーバー ソフトウェア、および PSTN ゲートウェイを実行するブレード サーバーを含み、すべてが 1 つのアプライアンス シャーシに組み込まれたサードパーティ デバイスです。

ユーザー数が 1,000 ～ 5,000 で、復元性 WAN が存在しないブランチ サイトの場合は、PSTN ゲートウェイと SIP トランクのどちらかを経由して 存続可能ブランチ サーバーを電話サービス プロバイダーに接続するようお勧めします。 存続可能ブランチ サーバーは、レジストラーと 仲介サーバー ソフトウェアがインストールされている Windows Server ベースのコンピューターです。

> [!NOTE]
> ユーザーと専任の Lync Server 管理者の総数が 5,000 を超えるブランチ サイトの場合は、中央サイトの展開とは別の完全な Lync Server 2013 の展開をお勧めします。<br />
> 各自のブランチ サイトにとって最善の復元性ソリューションを選択するための前提条件、計画、考慮事項など詳細については、「計画」のドキュメントの「<a href="lync-server-2013-branch-site-resiliency-requirements.md">Lync Server 2013 のブランチ サイトの復元要件</a>」を参照してください。


## このセクション中

  - [Lync Server 2013 による存続可能ブランチ アプライアンスまたはサーバーの展開 - 中央サイトのタスク](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)

  - [Lync Server 2013 での存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーの展開 - ブランチ サイトのタスク](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

  - [Lync Server 2013 でブランチ サイト復元を実現するためのユーザーの構成](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

  - [Lync Server 2013 で存続可能ブランチ アプライアンスまたは存続可能ブランチ サーバーにユーザーを所属させる](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)

  - [付録: Lync Server 2013 の存続可能ブランチ アプライアンスとサーバー](lync-server-2013-appendices-survivable-branch-appliances-and-servers.md)

## 関連項目

#### その他のリソース

[Lync Server 2013 の展開](lync-server-2013-deploying-lync-server.md)

