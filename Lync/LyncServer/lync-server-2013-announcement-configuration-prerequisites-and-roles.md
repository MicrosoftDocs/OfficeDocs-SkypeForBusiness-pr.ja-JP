---
title: 'Lync Server 2013: アナウンスの構成の前提条件と役割'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Announcement configuration prerequisites and roles
ms:assetid: 82f2dfe9-4c5e-4d65-96a1-96495d506ea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398658(v=OCS.15)
ms:contentKeyID: 48184674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 09a7a8a17e3431c382ce4f49534336d266bbaa13
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "41998082"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="announcement-configuration-prerequisites-and-roles-in-lync-server-2013"></a>Lync Server 2013 でのアナウンスの構成の前提条件と役割

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-25_

アナウンスメントは、エンタープライズ Voip の通話管理機能です。 このトピックでは、アナウンスを構成する前に行う必要のある内容と、構成タスクを実行するために必要な役割の割り当てについて説明します。

このセクションでは、「アナウンスに関連する計画」のドキュメントを読んでいることを前提としています (「 [Lync Server 2013 の通話管理機能の計画](lync-server-2013-planning-for-call-management-features.md)」を参照してください)。

<div>

## <a name="announcement-configuration-prerequisites"></a>アナウンスの構成の前提条件

アナウンスメントアプリケーションには、次のコンポーネントが必要です。

  - アプリケーション サービス

  - 応答グループ アプリケーション

  - ファイル ストア (オーディオ ファイルを格納)

これらのコンポーネントはすべて、エンタープライズ VoIP を展開するときに既定でインストールされます。

</div>

<div>

## <a name="announcement-configuration-roles"></a>アナウンスの構成の役割

以下の管理ツールを使用してアナウンスを構成できます。

  - Lync Server コントロール パネル

  - Lync Server 管理シェル

アナウンスアプリケーションを構成するには、次の管理役割のいずれかが必要です。

  - **CsVoiceAdministrator**   この管理者の役割は、アナウンス設定を含むすべての音声関連の設定とポリシーを作成、構成、および管理できます。

  - **Csserveradministrator**   この管理役割は、サーバーとサービスを管理、監視、およびトラブルシューティングし、すべてのアナウンス設定を構成できます。

  - **Csadministrator**   この管理者の役割は、すべての管理タスクを実行し、すべての設定を変更できます。

  - **Csviewonlyadministrator**   この管理役割は展開を表示して、展開の状態を監視できます。

<div>


> [!NOTE]  
> 管理ユーザー権限の詳細については、「計画」のドキュメントの「 <A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 でのロールベースのアクセス制御の計画</A>」を参照してください。



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

