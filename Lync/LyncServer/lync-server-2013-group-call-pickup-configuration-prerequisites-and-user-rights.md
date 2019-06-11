---
title: グループ通話のピックアップ構成の前提条件とユーザー権利
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Group Call Pickup configuration prerequisites and user rights
ms:assetid: 8757b1d3-751d-49c3-b1b8-b678f663f18e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945641(v=OCS.15)
ms:contentKeyID: 51541495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2eb0af5b78d5d391ba055e557ad71da79484b5c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833113"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-call-pickup-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a>グループ通話の集配構成の前提条件とユーザー権限 Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-01-30_

グループ通話のピックアップは、エンタープライズボイスの展開時に既定でインストールされる通話管理機能です。 このトピックでは、グループ通話のピックアップと構成タスクを実行するために必要なユーザー権限を構成する前に必要な準備について説明します。

このセクションでは、グループ通話のピックアップに関連する計画ドキュメントを読み取っていることを前提としています (「 [Lync Server 2013 でのグループ通話のピックアップの計画](lync-server-2013-planning-for-group-call-pickup.md)」を参照してください)。

<div>

## <a name="group-call-pickup-configuration-prerequisites"></a>グループ通話のピックアップ構成の前提条件

グループ通話のピックアップには次のコンポーネントが必要です。

  - アプリケーション サービス

  - コール パーク アプリケーション

これらのコンポーネントは、エンタープライズボイスの展開時に自動的にインストールされます。

</div>

<div>

## <a name="group-call-pickup-configuration-user-rights"></a>グループ通話のピックアップ構成のユーザー権利

グループ通話のピックアップを構成するには、次の管理ツールを使用します。

  - Lync Server 管理シェル

  - SEFAUtil リソースキットツール

Lync Server 管理シェルを使用して、通話パークの軌道テーブルにある通話ピックアップグループの作成と管理を行います。 SEFAUtil リソースキットツールを使用して、通話ピックアップグループを割り当て、ユーザーに対してグループ通話のピックアップを有効にするか、ユーザーのグループ通話のピックアップを無効にします。

グループ通話のピックアップを構成するには、タスクに応じて次の管理者ロールが必要です。

  - **CsVoiceAdministrator:** この管理者ロールは、音声関連のすべての設定とポリシーを作成、構成、管理できます。

  - **Csuseradministrator:** この管理者の役割は、ユーザーに対してグループ通話のピックアップを有効にすることができます。 この管理者ロールは、すべての音声構成に対して読み取り専用ビューでアクセスすることもできます。

  - **Csserveradministrator:** この管理者の役割は、サーバーとサービスの管理、監視、トラブルシューティングを行うことができます。

  - **Csadministrator:** この管理者ロールは、CsVoiceAdministrator、CsServerAdministrator、Csserveradministrator のすべてのタスクを実行できます。

<div>


> [!NOTE]
> 管理権限の詳細については、計画ドキュメントの「 <A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 での役割ベースのアクセス制御の計画</A>」を参照してください。



</div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのエンタープライズボイスの展開](lync-server-2013-deploying-enterprise-voice.md)  


[Lync Server 2013 の通話管理機能の計画](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

