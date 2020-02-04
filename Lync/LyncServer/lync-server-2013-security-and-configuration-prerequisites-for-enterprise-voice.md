---
title: エンタープライズ VoIP のセキュリティおよび構成の前提条件
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
ms.openlocfilehash: 6530e00a942e2e839eaf4bc2d069212b746e2504
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732577"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-lync-server-2013"></a>Lync Server 2013 でのエンタープライズ Voip のセキュリティと構成の前提条件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-18_

インフラストラクチャが以下のセキュリティ、ユーザー構成、およびシナリオ固有のハードウェアの前提条件を満たしていることを確認します。

<div>

## <a name="administrative-rights-and-certificate-infrastructure"></a>管理者権限と証明書インフラストラクチャ

環境が、エンタープライズ Voip 展開プロセスで使用するために、次の管理者ユーザーグループと証明書インフラストラクチャを使って構成されていることを確認してください。

  - エンタープライズボイスを展開する管理者は、RTCUniversalServerAdmins グループのメンバーである必要があります。

  - 構成タスクを実行する管理者に十分な権限があること。
    
      - **CsVoiceAdministrator:** この管理者の役割では、音声構成タスクの実行、音声アプリケーションの管理、エンド ユーザーへの音声ポリシーの割り当てができます。
    
      - **CsUserAdministrator:** この管理者の役割では、ユーザーのエンタープライズ VoIP を有効にするなど、ユーザーのプロパティを管理できます。 また、この管理者の役割では、ユーザー単位のポリシーの割り当て (アーカイブ ポリシー以外)、ユーザーの移動、共通領域電話やアナログ デバイスの管理を行うこともできます。
    
      - **CsAdministrator:** この管理者の役割では、CsVoiceAdministrator と CsUserAdministrator のすべてのタスクを実行できます。
    
    <div>
    

    > [!NOTE]
    > 委任により、リソースへの不要なアクセスを開かずに、Lync Server の展開により多くの管理者が参加できるようになります。

    
    </div>

  - マイクロソフトまたはサードパーティの CA (証明機関) インフラストラクチャのいずれかを使用して、MKI (Managed key infrastructure) が展開され、構成されていること。
    
    <div>
    

    > [!NOTE]
    > Lync Server の証明書の要件の詳細については、「計画ドキュメントの「 <A href="lync-server-2013-certificate-infrastructure-requirements.md">Lync server 2013 の証明書インフラストラクチャの要件</A>」を参照してください。

    
    </div>

</div>

<div>

## <a name="user-configuration"></a>ユーザー構成

フロントエンドの展開時に、各フロントエンドプールまたは Standard Edition サーバーに仲介サーバーを併置した場合、エンタープライズボイスに必要なユーザー設定は、それらのサーバーロールのファイルのインストール中に自動的に構成されました。

現時点でエンタープライズ音声のワークロードを新しく展開している場合は、展開プロセスを開始する前に、エンタープライズ Voip を有効にする予定の各ユーザーのプライマリ電話番号を指定します。 管理者は、この番号が一意であることを確認する責任があります。 実装前に、すべての主要な電話番号を正規化し (適切に書式設定)、Lync Server コントロールパネルを使用して、各ユーザーの**行 URI**プロパティにコピーする必要があります。

<div>


> [!NOTE]
> エンタープライズ Voip の展開に必要な主要な電話番号の例については、計画ドキュメントの「lync server <A href="lync-server-2013-dial-plans-and-normalization-rules.md">2013 のダイヤルプランと正規化ルール</A>」セクションの「<A href="lync-server-2013-dial-plans-and-normalization-rules.md">ダイヤルプランと2013正規化</A>ルール」を参照してください。



</div>

</div>

<div>

## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a>次の手順: ファイルをインストールする、または PSTN 接続を構成する

エンタープライズ Voip のソフトウェアと環境の前提条件を確認した後、次のようなコンテンツを使うことができます。

  - 「 [Lync server 2013 に「仲介サーバー用のファイルをインストール](lync-server-2013-install-the-files-for-mediation-server.md)する」の説明に従って、仲介サーバーをインストールします。ただし、仲介された場合は、仲介サーバーがフロントエンドプールまたは Standard Edition サーバー展開プロセスの一環としてインストールされているためです。

  - または、「 [Lync Server 2013 での trunks の構成](lync-server-2013-configuring-trunks.md)」で説明されているように、エンタープライズ voip ユーザーの呼び出しをルーティングするための設定の構成を開始します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

