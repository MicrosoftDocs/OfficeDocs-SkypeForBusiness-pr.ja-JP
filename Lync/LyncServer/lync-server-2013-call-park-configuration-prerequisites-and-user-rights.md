---
title: 'Lync Server 2013: コール パーク構成の前提条件とユーザー権限'
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
ms.openlocfilehash: 485c8ee5ba2f7d788ef2917488ebfd86607d48d8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742977"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-park-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a>Lync Server 2013 のコール パーク構成の前提条件とユーザー権限

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-10_

コールパークは、エンタープライズボイスの展開時に既定でインストールされる通話管理機能です。 このトピックでは、コールパークと構成タスクを実行するために必要なユーザー権利を設定する前に、準備しておく必要があることについて説明します。

<div>


> [!IMPORTANT]  
> 会議のカスタマイズされた保留中のファイルは Lync Server 2013 の障害回復プロセスの一部としてはバックアップされません。プールにアップロードされたファイルが破損、破損、または消去された場合、ファイルは失われます。 コール パーク用にアップロードされているカスタマイズした保留音ファイルについては、常に個別のバックアップ コピーを保持してください。



</div>

このセクションでは、通話パークに関連する計画ドキュメントを読み取っていることを前提としています (「 [Lync Server 2013 での通話管理機能の計画](lync-server-2013-planning-for-call-management-features.md)」を参照してください)。

<div>

## <a name="call-park-configuration-prerequisites"></a>コールパーク構成の前提条件

コールパークには、次のコンポーネントが必要です。

  - アプリケーション サービス

  - コール パーク アプリケーション

これらのコンポーネントは、エンタープライズボイスの展開時に自動的にインストールされます。

通話の保留中に発信者に音楽が聞こえるようにする場合は、音楽の保留ファイルも必要です。 既定の音楽の保留ファイルは、エンタープライズボイスの展開時に自動的にインストールされます。 既定のファイルは、独自の音楽の保留ファイルに置き換えることができます。 [コールパークファイルストアでは、オーディオファイルを保持します。

</div>

<div>

## <a name="call-park-configuration-user-rights"></a>コールパーク構成のユーザー権利

以下の管理ツールを使って、コールパークを構成することができます。

  - Lync Server コントロール パネル

  - Lync Server 管理シェル

これらのツールを使って、コールパークの軌道を設定したり、コールパークで使用される他の設定を構成したりします。

コールパークを構成するには、タスクに応じて次の管理者ロールが必要です。

  - **CsVoiceAdministrator:** この管理者ロールは、音声関連のすべての設定とポリシーを作成、構成、管理できます。

  - **Csuseradministrator:** この管理者の役割は、音声ポリシーでのコールパークを有効にすることができます。 この管理者ロールは、すべての音声構成に対して読み取り専用ビューでアクセスすることもできます。

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

