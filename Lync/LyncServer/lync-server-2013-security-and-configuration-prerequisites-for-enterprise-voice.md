---
title: エンタープライズ Voip のセキュリティおよび構成の前提条件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Security and configuration prerequisites for Enterprise Voice
ms:assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398221(v=OCS.15)
ms:contentKeyID: 48183495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa8f0f3dd113b10a01f18a0542561de946d4acd0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510474"
---
# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-lync-server-2013"></a>Lync Server 2013 でのエンタープライズ Voip のセキュリティおよび構成の前提条件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-18_

インフラストラクチャが次のセキュリティ、ユーザー構成、およびシナリオ固有のハードウェアの前提条件を満たしていることを確認します。

<div>

## <a name="administrative-rights-and-certificate-infrastructure"></a>管理者権限と証明書インフラストラクチャ

エンタープライズ VoIP の展開プロセス時に使用する次の管理者ユーザー グループと証明書インフラストラクチャで環境が構成されていることを確認します。

  - エンタープライズ VoIP を展開する管理者が RTCUniversalServerAdmins グループのメンバーであること。

  - 構成タスクを実行する管理者に十分な権限があること。
    
      - **CsVoiceAdministrator: **この管理者の役割では、音声構成タスクの実行、音声アプリケーションの管理、エンド ユーザーへの音声ポリシーの割り当てができます。
    
      - **CsUserAdministrator: **この管理者の役割では、ユーザーのエンタープライズ VoIP を有効にするなど、ユーザーのプロパティを管理できます。 また、この管理者の役割では、ユーザー単位のポリシーの割り当て (アーカイブ ポリシー以外)、ユーザーの移動、共通領域電話やアナログ デバイスの管理を行うこともできます。
    
      - **CsAdministrator: **この管理者の役割では、CsVoiceAdministrator と CsUserAdministrator のすべてのタスクを実行できます。
    
    <div>
    

    > [!NOTE]
    > 委任を使用すると、リソースへの不必要なアクセスを開かなくても、Lync Server の展開により多くの管理者が参加できます。

    
    </div>

  - マイクロソフトまたはサードパーティの CA (証明機関) インフラストラクチャのいずれかを使用して、MKI (Managed key infrastructure) が展開され、構成されていること。
    
    <div>
    

    > [!NOTE]
    > Lync Server での証明書の要件の詳細については、「計画」のドキュメントの「 <A href="lync-server-2013-certificate-infrastructure-requirements.md">Lync server 2013 の証明書インフラストラクチャ要件</A> 」を参照してください。

    
    </div>

</div>

<div>

## <a name="user-configuration"></a>ユーザー構成

フロントエンドの展開時に、各フロントエンドプールまたは Standard Edition サーバーに仲介サーバーを併置した場合、エンタープライズ Voip に必要なユーザー設定は、それらのサーバーの役割のファイルのインストール時に自動的に構成されました。

この時点でエンタープライズ VoIP のワークロードを新たに展開する場合、展開プロセスを開始する前に、エンタープライズ VoIP を有効にする各ユーザーの主要電話番号を指定します。 管理者は、この番号が一意であることを確認する責任があります。 実装の前に、Lync Server コントロールパネルを使用して、すべてのプライマリ電話番号を正規化 (整形) し、各ユーザーの **回線 URI** プロパティにコピーする必要があります。

<div>


> [!NOTE]
> エンタープライズ Voip の展開に必要な主要電話番号の例については、「計画」のドキュメントの「 <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Lync server 2013</A> でのダイヤルプランと正規化ルール」セクション <A href="lync-server-2013-dial-plans-and-normalization-rules.md">と「lync server 2013 の正規化ルール</A> 」を参照してください。



</div>

</div>

<div>

## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a>次のステップ:  ファイルのインストールや PSTN 接続の構成

エンタープライズ VoIP のソフトウェアおよび環境の前提条件を確認したら、以下の情報を参照して次のいずれかの操作を実行できます。

  - 「 [Lync server 2013 の仲介サーバーのファイル](lync-server-2013-install-the-files-for-mediation-server.md)をインストールする」の説明に従って、仲介サーバーをインストールします。これは、仲介サーバーがフロントエンドプールまたは Standard Edition サーバー展開プロセスの一部としてインストールされているためで、スタンドアロンの仲介サーバーまたはプールを展開する場合に限られます。

  - または、「 [構成トランク In Lync Server 2013](lync-server-2013-configuring-trunks.md)」の説明に従って、エンタープライズ voip ユーザーの通話をルーティングするための設定の構成を開始します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

