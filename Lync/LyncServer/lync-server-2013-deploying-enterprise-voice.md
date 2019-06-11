---
title: 'Lync Server 2013: エンタープライズ Voip の展開'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Enterprise Voice
ms:assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412876(v=OCS.15)
ms:contentKeyID: 48185207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae445d954bd1be7c956d76aa48da2ad7854c6a54
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833561"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-enterprise-voice-in-lync-server-2013"></a>Lync Server 2013 でのエンタープライズボイスの展開

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-03_

Lync Server 2013、エンタープライズボイスは Lync Server 2013 インフラストラクチャの一部です。

エンタープライズボイスを展開するには、次のことを行う必要があります。

<div id="sectionSection0" class="section">

1.  計画ドキュメントの「 [Lync Server 2013 でのエンタープライズボイスの計画](lync-server-2013-planning-for-enterprise-voice.md)」セクションを確認します。

2.  この作業負荷と共に展開する機能とコンポーネントの計画を完了します。

3.  計画ツールを実行して、展開の決定を反映するトポロジを設計します。

4.  展開ドキュメントの「 [Lync Server 2013 でトポロジを定義して構成する](lync-server-2013-defining-and-configuring-the-topology.md)」の説明に従って、トポロジビルダーでトポロジの設計を開きます。
    
    <div>
    

    > [!NOTE]  
    > トポロジビルダーのインストールは、内部プールの展開プロセスの一部です。 詳細については、「 <A href="lync-server-2013-install-lync-server-administrative-tools.md">Lync Server 2013 管理ツール</A>を展開用のドキュメントにインストールする」を参照してください。

    
    </div>

さらに、展開するために選んだ参照トポロジに対応する、[セントラルサイト] と [ブランチサイト] に既に Lync Server、Enterprise Edition を展開している必要があります。 エンタープライズボイスコンポーネントは、少なくとも1つの内部プールに対して定義、発行、インストールされているファイルがあるまで展開できません。また、内部プールを定義して公開するには、トポロジビルダーを使用する必要があります。

</div>

<div id="sectionSection1" class="section">

<div class="subSection">

エンタープライズ Voip サーバーの役割 (および他の Lync Server 2013 サーバーの役割との関係) を展開する方法の例を参照トポロジで確認するには、計画ドキュメントの「 [Lync server 2013 のリファレンストポロジ](lync-server-2013-reference-topologies.md)」を参照してください。

ネットワーク領域、ネットワークサイト、サブネットなど、通話受付制御の展開のサンプルについて説明している参照トポロジを表示する方法については、「[例: Lync Server 2013 の通話受付制御の要件を収集](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md)する」を参照してください。計画ドキュメント

</div>

</div>

<div id="sectionSection2" class="section">

<div>


> [!IMPORTANT]  
> エンタープライズ Voip をセントラルサイトに展開するには、このセクションのトピックを参照してください。 ブランチサイトでエンタープライズボイスを展開するには、展開ドキュメントの<A href="lync-server-2013-deploying-branch-sites.md">Lync Server 2013 でブランチサイト</A>を展開するに進みます。



</div>

このセクションには、推奨に従って、各フロントエンド サーバーまたは各 Standard Edition サーバー上に仲介サーバーを併置する展開の手順、およびスタンドアロンの仲介サーバー プールでの展開の手順が含まれています。

トポロジビルダーを使用して、各フロントエンドサーバーまたは Standard Edition サーバー上で仲介サーバーを見つけて配布するトポロジを定義して公開している場合は、次のコンテンツをスキップできます。フロントエンドサーバープールまたは Standard Edition サーバーにファイルをインストールした場合の仲介サーバー:

  - [Lync Server 2013 でのトランクの構成](lync-server-2013-configuring-trunks.md)

単体プールで仲介サーバーを定義して公開するためにトポロジビルダーを使用している場合は、次のコンテンツを使うことができます。

  - 「 [Lync Server 2013 のエンタープライズボイスの前提条件](lync-server-2013-enterprise-voice-prerequisites.md)」で説明されているように、トポロジがソフトウェアと環境の前提条件を満たしていることを確認します。

</div>

<div>

## <a name="in-this-section"></a>このセクション中

  - <span></span>  
    [Lync Server 2013 のエンタープライズ VoIP の前提条件](lync-server-2013-enterprise-voice-prerequisites.md)

  - <span></span>  
    [Lync Server 2013 での仲介サーバーの展開とピアの定義](lync-server-2013-deploying-mediation-servers-and-defining-peers.md)

  - <span></span>  
    [Lync Server 2013 でのトランクの構成](lync-server-2013-configuring-trunks.md)

  - <span></span>  
    [Lync Server 2013 でのダイヤル プランの構成](lync-server-2013-configuring-dial-plans.md)

  - <span></span>  
    [Lync Server 2013 での音声ポリシー、PSTN 使用状況レコード、および音声ルートの構成](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)

  - <span></span>  
    [Lync Server 2013 での音声ルーティング構成のエクスポートとインポート](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - <span></span>  
    [Lync Server 2013 での音声ルーティングのテスト](lync-server-2013-test-voice-routing.md)

  - <span></span>  
    [Lync Server 2013 の音声ルーティング構成に保留中の変更を発行する](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - <span></span>  
    [内部設置型 Exchange UM を展開して Lync Server 2013 ボイス メールを提供する](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)

  - <span></span>  
    [Lync Server 2013 ユーザーに Hosted Exchange UM のボイス メールを提供する](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)

  - <span></span>  
    [オンプレミスの Lync Server 2013 と Exchange Online の統合を構成する](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)

  - <span></span>  
    [Lync Server 2013 での高度なエンタープライズ Voip 機能の展開](lync-server-2013-deploying-advanced-enterprise-voice-features.md)
    
      - [Lync Server 2013 ネットワーク領域、サイト、およびサブネットの構成](lync-server-2013-about-network-regions-sites-and-subnets.md)
    
      - [Lync Server 2013 でネットワークの領域を作成または変更する](lync-server-2013-create-or-modify-a-network-region.md)
    
      - [Lync Server 2013 でのネットワーク サイトの作成または変更](lync-server-2013-create-or-modify-a-network-site.md)
    
      - [Lync Server 2013 でのネットワーク サイトとサブネットの関連付け](lync-server-2013-associate-a-subnet-with-a-network-site.md)
    
      - [Lync Server 2013 での通話受付制御の構成](lync-server-2013-configure-call-admission-control.md)
    
      - [Lync Server 2013 での Enhanced 9-1-1 の構成](lync-server-2013-configure-enhanced-9-1-1.md)
    
      - [Lync Server 2013 メディア バイパスの構成](lync-server-2013-configure-media-bypass.md)

  - <span></span>  
    [Lync Server 2013 でのエンタープライズ Voip のユーザーの有効化](lync-server-2013-enable-users-for-enterprise-voice.md)

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのブランチ サイトの展開](lync-server-2013-deploying-branch-sites.md)  
[Lync Server 2013 でのダイヤルイン会議の構成](lync-server-2013-configuring-dial-in-conferencing.md)  
[Lync Server 2013 でのコール パークの構成](lync-server-2013-configuring-call-park.md)  
[Lync Server 2013 での、割り当てられていない番号用のアナウンスの構成](lync-server-2013-configuring-announcements-for-unassigned-numbers.md)  
[Lync Server 2013 での監視の展開](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

