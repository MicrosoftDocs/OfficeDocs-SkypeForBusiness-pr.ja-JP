---
title: ダイヤルイン会議の構成の前提条件とアクセス許可
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing configuration prerequisites and permissions
ms:assetid: b3b251e5-78ac-44a2-8c36-2a061c9b2314
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412865(v=OCS.15)
ms:contentKeyID: 48185165
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 791fa7e697622a4274655a77a2f02a6cdee140cb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213453"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-configuration-prerequisites-and-permissions-in-lync-server-2013"></a>Lync Server 2013 でのダイヤルイン会議構成の前提条件とアクセス許可

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-06-20_

ダイヤルイン会議は、Lync Server 2013 会議ワークロードのオプションコンポーネントです。 トポロジビルダーを使用してトポロジを設計し、フロントエンドプールまたは Standard Edition サーバーをセットアップするときには、ダイヤルイン会議を構成する前にインストールする必要があるコンポーネントが展開されます。 ここでは、ダイヤルイン会議を構成する前に実装されている必要があるコンポーネントについて説明します。

このセクションは、特に会議ワークロードおよびダイヤルイン会議に関連する「計画」のセクションを既に読んでいることを前提としています。

<div>

## <a name="dial-in-conferencing-configuration-prerequisites"></a>ダイヤルイン会議の構成の前提条件

ダイヤルイン会議には、次の Lync Server 2013 コンポーネントが必要です。

  - 統合コミュニケーション アプリケーション サービス (UCAS) (*アプリケーション サービス*と呼ばれます)

  - 会議アテンダント アプリケーション

  - 会議アナウンス アプリケーション

  - ダイヤルイン会議設定 Web ページ

  - 少なくとも1つの Lync Server 2013 仲介サーバーおよび少なくとも1つの PSTN ゲートウェイ

トポロジビルダーを使用してトポロジを定義および公開し、フロントエンドプールまたは Standard Edition サーバーを展開するときに、これらのコンポーネントを展開します。 エンタープライズ Voip を展開する場合は、ダイヤルイン会議を構成する前に展開する必要があります。 エンタープライズ Voip を展開していない場合は、フロントエンドプールまたは Standard Edition サーバーを展開するときに、仲介サーバーと公衆交換電話網 (PSTN) ゲートウェイを展開することができます。

<div>


> [!NOTE]
> Office Communications Server 2007 R2 から Lync Server 2013 にアップグレードする場合は、Lync Server 2013 会議のホストに使用する予定のすべてのプールにダイヤルイン会議を展開します。 ダイヤルイン会議の移行の詳細については、「 <A href="migration-from-office-communications-server-2007-r2-to-lync-server-2013.md">Migration From Office Communications server 2007 R2 To Lync Server 2013</A>」を参照してください。



</div>

このセクションは、次が実現されていることを前提としています。

  - Lync Server 2013 に移行する場合は、Office Communications Server 2007 R2 環境に最新の更新プログラムを適用しました。

  - トポロジビルダーを使用して、トポロジを設計および構成します。 会議ワークロードを指定したときに、ダイヤルイン会議のオプションを選択したこと。 トポロジの定義の詳細については、「展開」のドキュメントの「 [Lync Server 2013 でのトポロジの定義と構成](lync-server-2013-defining-and-configuring-the-topology.md)」を参照してください。

  - トポロジが公開され、フロント エンド プールまたは Standard Edition サーバーがセットアップされていること。 トポロジの公開および Lync Server 2013 のインストールの詳細については、「展開」のドキュメントの「[展開 Lync server 2013](lync-server-2013-deploying-lync-server.md) 」を参照してください。
    
    <div>
    

    > [!NOTE]
    > 公開されたトポロジをインストールするときは、ダイヤルイン会議設定 Web ページが、Web サービスの一部としてフロント エンド サーバーまたは Standard Edition サーバーにインストールされます。

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > Lync Server 2013 を展開した後に、トポロジビルダーでファイルストアのパスを変更する場合は、新しいパスを使用するために、会議アテンダントおよび会議アナウンスアプリケーションを再起動する必要があります。

    
    </div>

  - 展開されたエンタープライズ Voip。 エンタープライズ Voip を展開していない場合は、Enterprise Edition フロントエンドサーバーまたは Standard Edition サーバーに仲介サーバーを併置するか、スタンドアロンの仲介サーバーを展開して PSTN ゲートウェイを展開したかを確認します。 エンタープライズ Voip の展開の詳細については、「展開」のドキュメントの「展開[エンタープライズ voip In Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) 」を参照してください。 スタンドアロンの仲介サーバーと PSTN ゲートウェイのインストールの詳細については、「展開」のドキュメントの「 [Lync server 2013 での仲介サーバーの展開とピアの定義](lync-server-2013-deploying-mediation-servers-and-defining-peers.md)」を参照してください。

次のフローチャートは、ダイヤルイン会議を構成する前に実行する必要のあるステップと、ダイヤルイン会議を構成するときのステップを示しています。

**ダイヤルイン会議の展開**

![ダイヤルイン会議の展開フローチャート](images/Gg412865.fde8c246-b5ed-4323-a6e7-af1983a5ec86(OCS.15).jpg "ダイヤルイン会議の展開フローチャート")

</div>

<div>

## <a name="dial-in-conferencing-permissions"></a>ダイヤルイン会議のアクセス許可

ダイヤルイン会議を構成するには、次の管理ツールを使用する必要があります。

  - Lync Server 2013 コントロール パネル

  - Lync Server 管理シェル

この管理ツールは、ダイヤルイン会議設定、ダイヤル プラン、ポリシー、その他ダイヤルイン会議で必要な設定を構成するために使用します。

ダイヤルイン会議の構成には、タスクによって異なりますが、次の管理者の役割のいずれかが必要です。

  - **CsVoiceAdministrator**   この管理者の役割は、音声関連の設定とポリシーを作成、構成、および管理できます。

  - **Csuseradministrator**   この管理者の役割は、Lync Server のユーザーを有効または無効にして、会議ポリシーや PIN ポリシーなどの既存のポリシーをユーザーに割り当てることができます。

  - **Csadministrator**   この管理者の役割は、CsVoiceAdministrator および csuseradministrator のすべてのタスクを実行できます。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのエンタープライズ Voip の展開](lync-server-2013-deploying-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

