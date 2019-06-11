---
title: ダイヤルイン会議の前提条件とアクセス許可
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Dial-in conferencing configuration prerequisites and permissions
ms:assetid: b3b251e5-78ac-44a2-8c36-2a061c9b2314
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412865(v=OCS.15)
ms:contentKeyID: 48185165
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a60fc58e0ec40dadff044257d43629c2f3cb01ea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833407"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-configuration-prerequisites-and-permissions-in-lync-server-2013"></a>Lync Server 2013 のダイヤルイン会議の前提条件とアクセス許可

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-06-20_

ダイヤルイン会議は、Lync Server 2013 会議のワークロードのオプションコンポーネントです。 トポロジビルダーを使用してトポロジを設計し、フロントエンドプールまたは Standard Edition サーバーをセットアップするときに、ダイヤルイン会議を構成する前にインストールする必要があるコンポーネントを展開します。 このトピックでは、ダイヤルイン会議を構成する前に完了しておく必要があることについて説明します。

このセクションでは、会議のワークロードとダイヤルイン会議に関連する計画セクションを既に読んでいることを前提としています。

<div>

## <a name="dial-in-conferencing-configuration-prerequisites"></a>ダイヤルイン会議構成の前提条件

ダイヤルイン会議には、次の Lync Server 2013 コンポーネントが必要です。

  - 統合コミュニケーション アプリケーション サービス (UCAS) (*アプリケーション サービス*と呼ばれます)

  - 会議アテンダント アプリケーション

  - 会議アナウンス アプリケーション

  - ダイヤルイン会議設定 Web ページ

  - 少なくとも1つの Lync Server 2013 仲介サーバーと1つの PSTN ゲートウェイ

トポロジビルダーを使用してトポロジを定義および公開し、フロントエンドプールまたは Standard Edition サーバーを展開するときに、これらのコンポーネントを展開します。 エンタープライズ Voip を展開する場合は、ダイヤルイン会議を構成する前に展開する必要があります。 エンタープライズ Voip を展開していない場合は、フロントエンドプールまたは Standard Edition サーバーを展開するときに、仲介サーバーと公衆交換電話網 (PSTN) ゲートウェイを展開できます。

<div>


> [!NOTE]
> Office Communications Server 2007 R2 から Lync Server 2013 にアップグレードする場合は、Lync Server 2013 会議のホストに使用する予定のすべてのプールにダイヤルイン会議を展開します。 ダイヤルイン会議の移行の詳細については、「 <A href="migration-from-office-communications-server-2007-r2-to-lync-server-2013.md">Office Communications Server 2007 R2 から Lync Server 2013 への移行</A>」を参照してください。



</div>

このセクションでは、次の作業を行っていることを前提としています。

  - Lync Server 2013 に移行している場合は、Office Communications Server 2007 R2 環境に最新の更新プログラムを適用しました。

  - トポロジの設計と構成に使用されるトポロジビルダー。 会議のワークロードを指定しているときに、[ダイヤルイン会議] オプションを選択しました。 トポロジの定義の詳細については、展開ドキュメントの「 [Lync Server 2013 でトポロジを定義して構成する](lync-server-2013-defining-and-configuring-the-topology.md)」を参照してください。

  - トポロジを公開し、フロントエンドプールまたは Standard Edition サーバーをセットアップしました。 トポロジの発行と Lync Server 2013 のインストールの詳細については、「展開ドキュメントに[Lync server 2013 を展開](lync-server-2013-deploying-lync-server.md)する」を参照してください。
    
    <div>
    

    > [!NOTE]
    > 公開されたトポロジをインストールすると、ダイヤルイン会議の設定の web ページは、Web サービスの一部としてフロントエンドサーバーまたは Standard Edition サーバーにインストールされます。

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > Lync Server 2013 を展開した後に、トポロジビルダーでファイルストアのパスを変更する場合は、新しいパスを使用するために、会議アテンダントと会議のアナウンスメントアプリケーションを再起動する必要があります。

    
    </div>

  - 展開されたエンタープライズ Voip。 エンタープライズ Voip を展開していない場合は、Enterprise Edition フロントエンドサーバーまたは Standard Edition サーバーで仲介サーバーを使用しているか、スタンドアロンの仲介サーバーを展開して、PSTN ゲートウェイを展開しています。 エンタープライズ Voip の展開の詳細については、展開ドキュメントの「 [Lync Server 2013 でのエンタープライズ voip の展開](lync-server-2013-deploying-enterprise-voice.md)」を参照してください。 スタンドアロンの仲介サーバーと PSTN ゲートウェイのインストールの詳細については、展開ドキュメントの「 [Lync server 2013 での仲介サーバーの展開とピアの定義](lync-server-2013-deploying-mediation-servers-and-defining-peers.md)」を参照してください。

次のフローチャートは、ダイヤルイン会議を構成する前に実行する必要のある手順と、ダイヤルイン会議を構成するために実行する手順を示しています。

**ダイヤルイン会議の展開**

![ダイヤルイン会議の展開フローチャート](images/Gg412865.fde8c246-b5ed-4323-a6e7-af1983a5ec86(OCS.15).jpg "ダイヤルイン会議の展開フローチャート")

</div>

<div>

## <a name="dial-in-conferencing-permissions"></a>ダイヤルイン会議の権限

ダイヤルイン会議を構成するには、次の管理ツールを使用する必要があります。

  - Lync Server 2013 コントロール パネル

  - Lync Server 管理シェル

これらの管理ツールを使用して、ダイヤルイン会議の設定、ダイヤルイン会議に必要なダイヤルプラン、ポリシー、その他の設定を構成します。

ダイヤルイン会議を構成するには、タスクに応じて次の管理者ロールが必要です。

  - ****   この管理者の役割を CsVoiceAdministrator すると、音声関連の設定とポリシーを作成、構成、管理できます。

  - **Csuseradministrator**   この管理者ロールは、Lync Server のユーザーを有効または無効にして、会議ポリシーや PIN ポリシーなどの既存のポリシーをユーザーに割り当てることができます。

  - **Csadministrator**   この管理者ロールは、CsVoiceAdministrator と csuseradministrator のすべてのタスクを実行できます。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのエンタープライズボイスの展開](lync-server-2013-deploying-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

