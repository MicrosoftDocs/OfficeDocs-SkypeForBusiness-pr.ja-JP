---
title: 'Lync Server 2013: 応答グループの構成'
description: 'Lync Server 2013: 応答グループの構成。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Response Group
ms:assetid: c56db929-cb21-4af0-be3f-c8f807b78a5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205249(v=OCS.15)
ms:contentKeyID: 48185359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 92674bb971ec5216051d75d788dc58b9c7ca641c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547933"
---
# <a name="configuring-response-group-in-lync-server-2013"></a>Lync Server 2013 で応答グループを構成する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-30_

応答グループは、ヘルプデスクやカスタマーサービスデスクなどの、 *エージェント*と呼ばれるユーザーのグループへの着信呼び出しをルーティングし、キューに記録するエンタープライズ voip 機能です。

応答グループで必要なコンポーネントは、エンタープライズ VoIP を展開するときに、フロント エンド サーバーまたは Standard Edition サーバーに自動的にインストールされ、有効にされます。 応答グループをユーザーが利用できるようにするには、エージェント グループ、キュー、およびワークフローを順に構成する必要があります。 さらに、応答グループ管理者は、既存のワークフローの構成を応答グループマネージャーに委任できます。これにより、ワークフローとそれに関連するエージェントグループおよびキューを変更および再構成できます。

このセクションでは、Lync Server 2013 応答グループの構成について説明します。 これは、応答グループに関連する計画セクションを既に読んでおり、enterprise Edition サーバーまたは Standard Edition サーバーがエンタープライズ Voip を使用して展開されていることを前提としています。

<div>


> [!TIP]  
> Lync Server 管理シェルを使用して応答グループを作成する方法の詳細については、「」の「Lync Server 管理シェルを使用して最初の応答グループを作成する」を参照してください <A href="https://go.microsoft.com/fwlink/p/?linkid=204108">https://go.microsoft.com/fwlink/p/?linkId=204108</A> 。



</div>

<div>

## <a name="in-this-section"></a>このセクションの内容

  - [Lync Server 2013 での応答グループ構成のアクセス許可と前提条件](lync-server-2013-response-group-configuration-permissions-and-prerequisites.md)

  - [Lync Server 2013 の応答グループの展開プロセス](lync-server-2013-deployment-process-for-response-group.md)

  - [Lync Server 2013 でのワークフロー作成シナリオの概要](lync-server-2013-overview-of-workflow-creation-scenarios.md)

  - [応答グループエージェントグループの作成 Lync Server 2013](lync-server-2013-create-response-group-agent-groups.md)

  - [Lync Server 2013 で応答グループキューを作成する](lync-server-2013-create-response-group-queues.md)

  - [オプションLync Server 2013 で応答グループの営業時間を定義する](lync-server-2013-optional-define-response-group-business-hours.md)

  - [オプションLync Server 2013 で応答グループの休日セットを定義する](lync-server-2013-optional-define-response-group-holiday-sets.md)

  - [Lync Server 2013 で応答グループのワークフローを作成する](lync-server-2013-create-response-group-workflows.md)

  - [オプションLync Server 2013 での応答グループの展開の確認](lync-server-2013-optional-verify-response-group-deployment.md)

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での通話管理機能の計画](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

