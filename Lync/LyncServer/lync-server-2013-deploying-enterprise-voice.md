---
title: 'Lync Server 2013: エンタープライズ Voip の展開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Enterprise Voice
ms:assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412876(v=OCS.15)
ms:contentKeyID: 48185207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b2784c5cb04994004503010426ebc98763c0250
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531154"
---
# <a name="deploying-enterprise-voice-in-lync-server-2013"></a>Lync Server 2013 でのエンタープライズ Voip の展開

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-03_

Lync Server 2013、エンタープライズ Voip は Lync Server 2013 インフラストラクチャの一部です。

エンタープライズ VoIP の展開には以下のことが必要になります。

<div id="sectionSection0" class="section">

1.  「計画」のドキュメントの「 [Lync Server 2013 でのエンタープライズ voip の計画](lync-server-2013-planning-for-enterprise-voice.md) 」を参照してください。

2.  このワークロードで展開する機能およびコンポーネントの計画が完了していること。

3.  計画ツールを実行して、展開の決定を反映するトポロジを設計します。

4.  「展開」のドキュメントの「 [Lync Server 2013 でのトポロジの定義と構成](lync-server-2013-defining-and-configuring-the-topology.md) 」の説明に従って、トポロジビルダーでトポロジ設計を開きます。
    
    <div>
    

    > [!NOTE]  
    > トポロジビルダーのインストールは、内部プールの展開プロセスの一部です。 詳細については、「展開」のドキュメントの「 <A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 管理ツール</A> 」を参照してください。

    
    </div>

また、展開するために選択した参照トポロジに対応する、中央サイトとブランチサイトに Lync Server、Enterprise Edition が既に展開されている必要があります。 エンタープライズ Voip コンポーネントを展開するには、少なくとも1つの内部プールに対してファイルを定義、発行、およびインストールする必要があります。また、トポロジビルダーを使用して内部プールを定義して発行する必要があります。

</div>

<div id="sectionSection1" class="section">

<div class="subSection">

エンタープライズ Voip サーバーの役割を展開できる場所 (およびそれらの関係と、他の Lync Server 2013 のサーバーの役割との関係) を示す参照トポロジを表示するには、「計画」のドキュメントの「 [reference トポロジ In Lync server 2013](lync-server-2013-reference-topologies.md) 」を参照してください。

ネットワーク地域、ネットワークサイト、およびサブネットを含む、通話受付管理の展開の例について説明する参照トポロジを表示するには、「計画」のドキュメントの「 [Example: Lync Server 2013 での通話受付管理の要件の収集](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) 」を参照してください。

</div>

</div>

<div id="sectionSection2" class="section">

<div>


> [!IMPORTANT]  
> 中央サイトにエンタープライズ Voip を展開するには、このセクションのトピックを参照してください。 ブランチサイトでエンタープライズ Voip を展開するには、「展開」のドキュメントの「 <A href="lync-server-2013-deploying-branch-sites.md">Lync Server 2013 でブランチサイト</A> を展開する」に進みます。



</div>

このセクションには、推奨に従って、各フロントエンド サーバーまたは各 Standard Edition サーバー上に仲介サーバーを併置する展開の手順、およびスタンドアロンの仲介サーバー プールでの展開の手順が含まれています。

トポロジビルダーを使用して、フロントエンドサーバープールまたは standard edition サーバーに、仲介サーバーのファイルが既にインストールされている場合は、次のコンテンツをスキップできます。これは、フロントエンドサーバープールまたは Standard Edition サーバーにファイルをインストールするときに、展開ウィザードによって自動的に仲介サーバーのファイルがインストールされたためです

  - [Lync Server 2013 でのトランクの構成](lync-server-2013-configuring-trunks.md)

トポロジビルダーを使用してスタンドアロンプールで仲介サーバーを定義して公開した場合は、次のコンテンツを使用できます。

  - 「 [Lync Server 2013 のエンタープライズ voip の前提条件](lync-server-2013-enterprise-voice-prerequisites.md)」で説明されているように、トポロジがソフトウェアおよび環境の前提条件を満たしていることを確認します。

</div>

<div>

## <a name="in-this-section"></a>このセクションの内容

  - <span></span>  
    [Lync Server 2013 のエンタープライズ Voip の前提条件](lync-server-2013-enterprise-voice-prerequisites.md)

  - <span></span>  
    [Lync Server 2013 での仲介サーバーの展開とピアの定義](lync-server-2013-deploying-mediation-servers-and-defining-peers.md)

  - <span></span>  
    [Lync Server 2013 でのトランクの構成](lync-server-2013-configuring-trunks.md)

  - <span></span>  
    [Lync Server 2013 でのダイヤルプランの構成](lync-server-2013-configuring-dial-plans.md)

  - <span></span>  
    [Lync Server 2013 での音声ポリシー、PSTN 使用法レコード、およびボイスルートの構成](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)

  - <span></span>  
    [Lync Server 2013 での音声ルーティング構成のエクスポートとインポート](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - <span></span>  
    [Lync Server 2013 での音声ルーティングのテスト](lync-server-2013-test-voice-routing.md)

  - <span></span>  
    [Lync Server 2013 で保留中の変更を音声ルーティング構成に公開する](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - <span></span>  
    [社内 Exchange UM を展開して Lync Server 2013 ボイスメールを提供する](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)

  - <span></span>  
    [Lync Server 2013 ユーザーに hosted Exchange UM のボイスメールを提供する](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)

  - <span></span>  
    [社内の Lync Server 2013 と Exchange Online との統合の構成](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)

  - <span></span>  
    [Lync Server 2013 での高度なエンタープライズ Voip 機能の展開](lync-server-2013-deploying-advanced-enterprise-voice-features.md)
    
      - [Lync Server 2013 のネットワーク地域、サイト、およびサブネットについて](lync-server-2013-about-network-regions-sites-and-subnets.md)
    
      - [Lync Server 2013 でネットワーク地域を作成または変更する](lync-server-2013-create-or-modify-a-network-region.md)
    
      - [Lync Server 2013 でのネットワークサイトの作成または変更](lync-server-2013-create-or-modify-a-network-site.md)
    
      - [Lync Server 2013 でのサブネットとネットワークサイトの関連付け](lync-server-2013-associate-a-subnet-with-a-network-site.md)
    
      - [Lync Server 2013 で通話受付管理を構成する](lync-server-2013-configure-call-admission-control.md)
    
      - [Lync Server 2013 での拡張9-1-1 の構成](lync-server-2013-configure-enhanced-9-1-1.md)
    
      - [Lync Server 2013 でメディアバイパスを構成する](lync-server-2013-configure-media-bypass.md)

  - <span></span>  
    [Lync Server 2013 のエンタープライズ Voip でユーザーを有効にする](lync-server-2013-enable-users-for-enterprise-voice.md)

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのブランチサイトの展開](lync-server-2013-deploying-branch-sites.md)  
[Lync Server 2013 でのダイヤルイン会議の構成](lync-server-2013-configuring-dial-in-conferencing.md)  
[Lync Server 2013 でのコールパークの構成](lync-server-2013-configuring-call-park.md)  
[Lync Server 2013 で割り当てられていない番号のアナウンスを構成する](lync-server-2013-configuring-announcements-for-unassigned-numbers.md)  
[Lync Server 2013 での監視の展開](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

