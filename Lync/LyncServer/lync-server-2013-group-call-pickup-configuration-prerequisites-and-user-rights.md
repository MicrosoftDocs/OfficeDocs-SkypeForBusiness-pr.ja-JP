---
title: グループ通話ピックアップの構成の前提条件とユーザー権限
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group Call Pickup configuration prerequisites and user rights
ms:assetid: 8757b1d3-751d-49c3-b1b8-b678f663f18e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945641(v=OCS.15)
ms:contentKeyID: 51541495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d0127ff5c196c14dc7844c6958ced9ae5478113
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213243"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="group-call-pickup-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a>Lync Server 2013 でのグループ通話ピックアップ構成の前提条件とユーザー権限

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-01-30_

グループ通話ピックアップは、エンタープライズ Voip を展開するときに既定でインストールされる通話管理機能です。 このトピックでは、グループ通話ピックアップおよび構成タスクを実行するために必要なユーザー権限を構成する前に行う必要のある事項について説明します。

このセクションでは、グループ通話ピックアップに関連する計画のドキュメントを読んでいることを前提としています (「 [Lync Server 2013 でグループ通話ピックアップを計画](lync-server-2013-planning-for-group-call-pickup.md)する」を参照してください)。

<div>

## <a name="group-call-pickup-configuration-prerequisites"></a>グループ通話ピックアップの構成の前提条件

グループ通話ピックアップでは、次のコンポーネントが必要です。

  - アプリケーション サービス

  - コール パーク アプリケーション

これらのコンポーネントは、エンタープライズ Voip を展開するときに自動的にインストールされます。

</div>

<div>

## <a name="group-call-pickup-configuration-user-rights"></a>グループ通話ピックアップ構成のユーザー権限

グループ通話ピックアップを構成するには、次の管理ツールを使用します。

  - Lync Server 管理シェル

  - SEFAUtil リソースキットツール

Lync Server 管理シェルを使用して、コールパークオービットテーブルで通話ピックアップグループを作成および管理します。 SEFAUtil リソースキットツールを使用して、通話ピックアップグループを割り当て、ユーザーのグループ通話ピックアップを有効にしたり、ユーザーのグループ通話ピックアップを無効にしたりします。

グループ通話ピックアップを構成するには、タスクに応じて、次の管理役割が必要です。

  - **CsVoiceAdministrator:** この管理者の役割は、音声関連のすべての設定とポリシーを作成、構成、および管理できます。

  - **Csuseradministrator:** この管理者の役割は、ユーザーのグループ通話ピックアップを有効にできます。 また、すべての音声構成に対する読み取り専用の表示アクセス権を持ちます。

  - **Csserveradministrator:** この管理者の役割は、サーバーとサービスを管理、監視、およびトラブルシューティングできます。

  - **Csadministrator:** この管理者の役割は、CsVoiceAdministrator、CsServerAdministrator、および Csserveradministrator のすべてのタスクを実行できます。

<div>


> [!NOTE]
> 管理権限の詳細については、「計画」のドキュメントの「 <A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 での役割ベースのアクセス制御の計画</A>」を参照してください。



</div>

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのエンタープライズ Voip の展開](lync-server-2013-deploying-enterprise-voice.md)  


[Lync Server 2013 での通話管理機能の計画](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

