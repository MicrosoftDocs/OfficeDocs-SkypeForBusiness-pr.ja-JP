---
title: 'Lync Server 2013: アナウンスの構成の前提条件と役割'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Announcement configuration prerequisites and roles
ms:assetid: 82f2dfe9-4c5e-4d65-96a1-96495d506ea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398658(v=OCS.15)
ms:contentKeyID: 48184674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb5f909170e1de2566e21e9305175211c306fee6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841039"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="announcement-configuration-prerequisites-and-roles-in-lync-server-2013"></a>Lync Server 2013 のアナウンスの構成の前提条件と役割

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-25_

"お知らせ" は、エンタープライズの音声通話管理機能です。 このトピックでは、アナウンスメントを構成するために必要な準備と、構成タスクを実行するために必要な役割の割り当てについて説明します。

このセクションでは、お知らせに関連する計画ドキュメントを読み取っていることを前提としています (「 [Lync Server 2013 の通話管理機能の計画](lync-server-2013-planning-for-call-management-features.md)」を参照してください)。

<div>

## <a name="announcement-configuration-prerequisites"></a>アナウンスメント構成の前提条件

アナウンスメントアプリケーションには、次のコンポーネントが必要です。

  - アプリケーション サービス

  - 応答グループ アプリケーション

  - ファイルストア、オーディオファイルを保持する場合

エンタープライズボイスを展開すると、これらのすべてのコンポーネントが既定でインストールされます。

</div>

<div>

## <a name="announcement-configuration-roles"></a>アナウンスメント構成ロール

以下の管理ツールを使用して、お知らせを構成することができます。

  - Lync Server コントロール パネル

  - Lync Server 管理シェル

アナウンスメントアプリケーションを構成するには、次の管理者ロールのいずれかが必要です。

  - ****   この管理者の役割を CsVoiceAdministrator すると、お知らせの設定など、音声に関連するすべての設定とポリシーを作成、構成、管理できます。

  - **Csserveradministrator**   この管理者ロールは、サーバーとサービスの管理、監視、トラブルシューティング、すべてのアナウンスメント設定の構成を行うことができます。

  - **Csadministrator**   この管理者ロールは、すべての管理タスクを実行し、すべての設定を変更することができます。

  - **Csviewonlyadministrator**   この管理者ロールは展開の正常性を監視するために展開を表示できます。

<div>


> [!NOTE]  
> 管理ユーザー権限の詳細については、計画ドキュメントの「 <A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 での役割ベースのアクセス制御の計画</A>」を参照してください。



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

