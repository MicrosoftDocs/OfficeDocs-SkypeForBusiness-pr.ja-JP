---
title: 'Lync Server 2013: 応答グループの構成'
TOCTitle: 応答グループの構成
ms:assetid: c56db929-cb21-4af0-be3f-c8f807b78a5a
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205249(v=OCS.15)
ms:contentKeyID: 48273512
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での応答グループの構成

 

_**トピックの最終更新日:** 2016-12-08_

応答グループは、ヘルプ デスクやカスタマー サービス デスクなどの、*エージェント* と呼ばれるグループに着信通話をルーティングし、キューに配置する エンタープライズ VoIP 機能です。

応答グループで必要なコンポーネントは、エンタープライズ VoIP を展開するときに、フロントエンド サーバーまたは Standard Edition サーバーに自動的にインストールされ、有効になります。応答グループをユーザーが利用できるようにするには、エージェント グループ、キュー、およびワークフローを順に構成する必要があります。さらに、応答グループの管理者は既存のワークフローの構成を 応答グループのマネージャーに委任でき、マネージャーはワークフローおよびそれに関連するエージェント グループとキューを変更、再構成できます。

このセクションでは、Lync Server 2013応答グループの構成について説明します。読者が 応答グループに関する計画の項目を既に読んでおり、Enterprise Edition または Standard Edition サーバーが エンタープライズ VoIP と共に展開済みであることを前提としています。


> [!TIP]
> Lync Server 管理シェルを使用して 応答グループを作成する方法の詳細 (サンプル スクリプトを含む) については、「Creating Your First Response Group Using Lync Server Management Shell (Lync Server 管理シェルを使用して最初の応答グループを作成する)」(<A class=uri href="http://go.microsoft.com/fwlink/?linkid=204108%26clcid=0x411">http://go.microsoft.com/fwlink/?linkid=204108&amp;clcid=0x411</A>) を参照してください。



## このセクション中

  - [Lync Server 2013 の応答グループ構成のアクセス許可と前提条件](lync-server-2013-response-group-configuration-permissions-and-prerequisites.md)

  - [Lync Server 2013 の応答グループの展開プロセス](lync-server-2013-deployment-process-for-response-group.md)

  - [Lync Server 2013 でのワークフロー作成のシナリオの概要](lync-server-2013-overview-of-workflow-creation-scenarios.md)

  - [Lync Server 2013 での応答グループのエージェント グループの作成](lync-server-2013-create-response-group-agent-groups.md)

  - [Lync Server 2013 での応答グループのキューの作成](lync-server-2013-create-response-group-queues.md)

  - [(オプション) Lync Server 2013 での応答グループの営業時間の定義](lync-server-2013-optional-define-response-group-business-hours.md)

  - [(オプション) 応答グループ休日セットの定義](lync-server-2013-optional-define-response-group-holiday-sets.md)

  - [Lync Server 2013 での応答グループのワークフローの作成](lync-server-2013-create-response-group-workflows.md)

  - [(オプション) 応答グループの展開の確認](lync-server-2013-optional-verify-response-group-deployment.md)

## 関連項目

#### その他のリソース

[Lync Server 2013 通話管理機能の計画](lync-server-2013-planning-for-call-management-features.md)

