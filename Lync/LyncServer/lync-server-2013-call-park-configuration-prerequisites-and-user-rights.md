---
title: 'Lync Server 2013: コールパーク構成の前提条件とユーザー権限'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Park configuration prerequisites and user rights
ms:assetid: 25b8cfe0-e4e7-487c-9e78-8c040f629059
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425730(v=OCS.15)
ms:contentKeyID: 48183648
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 809f39bd78d4c04ffef6763e3d1f48e40ca55089
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508264"
---
# <a name="call-park-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a>Lync Server 2013 のコールパーク構成の前提条件とユーザー権限

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-10_

コールパークは、エンタープライズ Voip を展開するときに既定でインストールされる通話管理機能です。 このトピックでは、コールパークおよび構成タスクを実行するために必要なユーザー権限を構成する前に行う必要のある事項について説明します。

<div>


> [!IMPORTANT]  
> コールパークアプリケーションのカスタマイズされた保留中のファイルは、Lync Server 2013 の障害復旧プロセスの一部としてはバックアップされず、プールにアップロードされたファイルが破損、破損、または消去されると、ファイルは失われます。 コールパーク用にアップロードしたカスタマイズされた保留音ファイルのバックアップコピーを常に別個に保持します。



</div>

このセクションでは、コールパークに関連する計画のドキュメントを読んでいることを前提としています (「 [Lync Server 2013 の通話管理機能の計画](lync-server-2013-planning-for-call-management-features.md)」を参照してください)。

<div>

## <a name="call-park-configuration-prerequisites"></a>コールパーク構成の前提条件

コールパークには、次のコンポーネントが必要です。

  - アプリケーション サービス

  - コール パーク アプリケーション

これらのコンポーネントは、エンタープライズ Voip を展開するときに自動的にインストールされます。

通話の保留中に発信者が音楽を聞けるようにするには、保留音ファイルも必要です。 エンタープライズ Voip を展開すると、既定の保留音ファイルが自動的にインストールされます。 既定のファイルを独自の保留音ファイルと入れ替えることができます。 コールパークは、ファイルストアを使用してオーディオファイルを保持します。

</div>

<div>

## <a name="call-park-configuration-user-rights"></a>コールパーク構成のユーザー権限

次の管理ツールを使用して、コールパークを構成できます。

  - Lync Server コントロール パネル

  - Lync Server 管理シェル

これらのツールを使用して、コールパークオービットテーブルを設定し、コールパークで使用される他の設定を構成します。

コールパークを構成するには、タスクに応じて、次の管理役割が必要です。

  - **CsVoiceAdministrator:** この管理者の役割は、音声関連のすべての設定とポリシーを作成、構成、および管理できます。

  - **Csuseradministrator:** この管理者の役割では、音声ポリシーのコールパークを有効にすることができます。 また、すべての音声構成に対する読み取り専用の表示アクセス権を持ちます。

  - **Csserveradministrator:** この管理者の役割は、サーバーとサービスを管理、監視、およびトラブルシューティングできます。

  - **Csadministrator:** この管理者の役割は、CsVoiceAdministrator、CsServerAdministrator、および Csserveradministrator のすべてのタスクを実行できます。

<div>


> [!NOTE]  
> 管理権限の詳細については、「計画」のドキュメントの「 <A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013 での役割ベースのアクセス制御の計画</A> 」を参照してください。



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

