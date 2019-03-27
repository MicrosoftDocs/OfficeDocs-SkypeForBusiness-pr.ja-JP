---
title: Skype のビジネス サーバーの会議トポロジを計画します。
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7392dfa7-791a-4723-88ff-0ef8a9ef11c8
description: '概要: ビジネス サーバーの Skype で会議トポロジを計画する詳細について参照してください。'
ms.openlocfilehash: e6269986bd5c011f43b5f6374053441e3aca54ec
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30893606"
---
# <a name="plan-your-conferencing-topology-for-skype-for-business-server"></a>Skype のビジネス サーバーの会議トポロジを計画します。
 
**の概要:** ビジネス サーバーを Skype で会議トポロジを計画する方法については、このトピックを参照してください。
  
このトピックでは、ビジネス サーバーの Skype での会議のためのトポロジの基本について説明します。
  
- サポートされるトポロジ
    
- ダイヤルイン会議の考慮事項
    
- Web 会議の考慮事項
    
- 大規模会議の要件
    
ハードウェアおよびソフトウェア要件の詳細については、[ビジネスのサーバー用の Skype での会議のためのハードウェアおよびソフトウェアの要件](hardware-and-software-requirements.md)を参照してください。
  
## <a name="supported-topologies"></a>サポートされるトポロジ

ビジネス サーバーの Skype で会議サービスを実行するサーバーは常と同じ場所にフロント エンド サーバーまたは Standard Edition サーバーです。 Skype ビジネス サーバーを配置すると、IM 会議の機能が自動的に展開します。 トポロジ ビルダーを使用して Web、音声とビデオ (A/V)、およびダイヤルイン会議を展開するかどうかを指定できます。 また、トポロジ ビルダーを使用して、既存の展開に会議を追加することもできます。 トポロジーの基本事項とコロケーションに関する詳細のシナリオでは、 [Skype のビジネス サーバーのトポロジの基礎](../../plan-your-deployment/topology-basics/topology-basics.md)を参照してください。
  
次のトポロジと構成に会議を展開できます。
  
- Skype ビジネス サーバーの標準エディション
    
- ビジネス Server Enterprise Edition の Skype
    
- エンタープライズ VoIP の有無は問いません
    
## <a name="dial-in-conferencing-considerations"></a>ダイヤルイン会議の考慮事項

ダイヤルイン会議を展開する場合は、以下の点を考慮する必要があります。
  
- ダイヤルイン会議は Skype ビジネス サーバーの PSTN ゲートウェイおよび PSTN ゲートウェイ シグナリングとメディアが仲介サーバーと PSTN ゲートウェイとの間を変換するための間に信号を変換するための仲介サーバー (と構成によっては、メディア) を必要とします。.
    
   ダイヤルイン会議を構成する前に、エンタープライズ VoIP または仲介サーバーと、以下のうち少なくとも 1 つを展開する必要があります。
    
  - PSTN ゲートウェイ
    
  - IP-PBX
    
  - セッション ボーダー コントローラー (SBC) (SIP トランクを構成して接続するインターネット テレフォニー サービス プロバイダー (ITSP) のため)
    
- アプリケーション サービス、会議アテンダント アプリケーション、および会議アナウンス アプリケーションを中央サイトに展開できます。ブランチ サイトには展開できません。
    
- ビジネス サーバーの会議のための Skype を展開するすべてのプールにダイヤルイン会議を展開する必要があります。 プールごとにアクセス番号を割り当てる必要はありませんが、プールごとにダイヤルイン会議機能を展開する必要があります。 この要件は、ユーザーが別のプールにサーバーのビジネス会議に、Skype を結合する 1 つのプールからアクセス番号を呼び出すときに、記録された名前の機能をサポートしています。 
    
詳細については、 [Skype のビジネス サーバーにダイヤルイン会議の計画](dial-in-conferencing.md)を参照してください。
  
## <a name="web-conferencing-considerations"></a>Web 会議の考慮事項

Web 会議には以下が必要です。 
  
- Web 会議のコンテンツを格納するために使用するファイル ストアへのアクセス。
    
- 会議中に PowerPoint ファイルを共有するために必要な Office Web Apps サーバー/Office Online Server との統合。
    
> [!NOTE]
> Office オンライン サーバー、ビジネス サーバーの Skype がサポートしている Office Web アプリケーション サーバーの最新のイテレーションの名前です。 詳細については、 [Office オンラインのサーバーのマニュアル](https://technet.microsoft.com/en-us/library/jj219456%28v=office.16%29.aspx)を参照してください。 
  
Skype ビジネス サーバーは、Office Web アプリケーション サーバーと Office オンラインのサーバーを構成するのには次の方法を提供します。 必要に応じて次のことができます。
  
- **Business Server と Office Web アプリケーション サーバーと Office オンライン サーバー設置、組織のファイアウォールの背後にある、および同じネットワーク ゾーンの両方の Skype をインストールします。** With this topology, external access to Office Web Apps Server/Office Online Server will be provided through your reverse proxy server. 理想的には、Skype と同じネットワーク ゾーンでビジネスのサーバーに Office Web アプリケーション サーバーと Office オンラインのサーバーをインストールしてください。
    
    ビジネス クライアント用の外部の Skype は、インターネットからの要求を受け取るし、内部ネットワークに転送するサーバーでは、リバース プロキシ サーバーを使用して Skype ビジネス サーバーにし、Office Web アプリケーション サーバーと Office オンライン サーバーに接続できます。 (内部クライアント必要はありません Office Web アプリケーション サーバーと Office オンラインのサーバーに直接接続することができますので、リバース プロキシ サーバーを使用する。)このトポロジは、ビジネスのサーバーの Skype でのみ使用される専用の Office Web アプリケーション サーバーと Office オンラインのサーバー ファームを使用する場合に適しています。
    
- **外部から配置された Office Web アプリケーション サーバーと Office オンラインのサーバーを使用します。** このトポロジでは、Skype ビジネス サーバーの導入、設置型を使用している Office Web アプリケーション サーバーと Office オンラインの Skype ビジネス サーバー ネットワーク ゾーンの外で展開されています。 これは、Office Web アプリケーション サーバーと Office オンライン サーバー企業内の複数のアプリケーション間で共有し、オフィスの Web アプリケーション サーバーと Office オンラインのサーバーの外部インターフェイスを使用してサーバーをビジネス用の Skype を必要とするネットワークに展開するときに発生可能性があります。その逆です。
    
    リバース プロキシ サーバーをインストールする必要はありません。代わりに、Skype のビジネス サーバーに Office Web アプリケーション サーバーと Office オンライン サーバーからすべての要求は、エッジ サーバーを通してルーティングされます。 内部と、外部の Skype ビジネス クライアント用 Office Web アプリケーション サーバーと Office オンライン サーバー外部の URL を使用して接続します。
    
    Office Web Apps サーバー/Office Online Server を内部ファイアウォールの外側に展開する場合は、トポロジ ビルダーで [**Office Web Apps サーバーは外部ネットワークで展開**] オプション (つまり、境界ネットワークまたはインターネット) を選択します。
    
詳細については、 [Skype ビジネス サーバー用に Office の Web アプリケーション サーバーと構成の統合](../../deploy/deploy-conferencing/office-web-app-server.md)を参照してください。 
  
選択するトポロジにかかわらず、ファイアウォールの正しいポートを開くことは重要です。 ある DNS 名、IP アドレス、およびポートはファイアウォールでブロックされない、Office Web アプリケーション サーバーと Office オンライン サーバーでは、ロード バランサー、または Skype のビジネス サーバーのことを確認する必要があります。
  
> [!NOTE]
> Office Web Apps サーバー/Office Online Server への外部アクセスを提供するには、サーバーを境界ネットワークに展開するという方法もあります。この場合、Office Web Apps サーバー/Office Online Server をセットアップするために、サーバー コンピューターを Active Directory ドメインのメンバーにする必要があることに注意してください。境界ネットワーク内のコンピューターを Active Directory ドメインのメンバーにすることがネットワーク ポリシーで許可されていない場合は、Office Web Apps サーバー/Office Online Server を境界ネットワークにインストールしないことをお勧めします。その代わりに、Office Web Apps サーバー/Office Online Server を内部ネットワークにインストールし、リバース プロキシ サーバー経由で外部ユーザー アクセスを提供します。 
  
## <a name="topology-requirements-for-large-meetings"></a>大規模会議のトポロジ要件

1 つの大規模な会議には、少なくとも 1 つのフロントエンド サーバーと 1 つのバックエンド サーバーが必要です。ただし、高可用性を実現するために、次の図に示すように、バックエンド サーバーがミラーリングされている 2 つのフロントエンド サーバー プールを使用することをお勧めします。
  
**大規模会議のトポロジ**

![大規模会議のトポロジ](../../media/06858900-a262-4a47-96d0-51abd6827064.png)
  
大規模な会議を主催するユーザーには、フロントエンド プールに所属するユーザー アカウントが必要です。 ただし、このプールに他のユーザー アカウントをホストすることはお勧めしません。 代わりに、大規模な会議にのみ使用します。 ベスト プラクティスは、大規模な会議のホストにのみ使用する特殊なユーザー アカウントをこのプールに作成することです。 大規模な会議の設定はパフォーマンス用に最適化されているので、それを通常のユーザーとして使用すると、PSTN エンドポイントが関係する場合に P2P セッションを会議に昇格できないなどの問題が発生することがあります。
  
2 つのフロントエンド サーバーでプールを管理するには、特別な配慮が必要です。詳細については、「[Topology Basics for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md)」および「[Reference topologies for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/reference-topologies.md)」を参照してください。
  
また、オプションで大規模な会議に使用するプールの障害復旧バックアップおよびフェールオーバーを提供する場合は、これを異なるデータ センター内の同様に設定した専用プールと組み合わせることができます。 詳細については、[高可用性とビジネスのサーバー用の Skype での災害復旧の計画](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)を参照してください。
  
トポロジについて次のような追加の注意事項があります。
  
- 会議コンテンツを格納するため、また、アーカイブ サーバーが展開されて有効になっている場合はアーカイブ ファイルを格納するために、ファイル共有が必要です。 ファイル共有は、プール専用にすることも、プールが展開されているサイトの別のプールで使用されているのと同じファイル共有にすることもできます。 ファイル共有を構成する方法の詳細は、[ビジネス サーバー 2015 の Skype でのファイル共有を作成する](../../deploy/install/create-a-file-share.md)を参照してください。
    
- 大規模な会議で PowerPoint プレゼンテーション機能を有効にするには、Office Web Apps サーバー/Office Online Server が必要です。 Office Web Apps サーバー/Office Online Server は、大規模な会議プール専用にすることも、専用プールが展開されているサイトの他のプールで使用されているのと同じ Office Web Apps サーバー/Office Online Server にすることもできます。 詳細については、 [Skype ビジネス サーバー用に Office の Web アプリケーション サーバーと構成の統合](../../deploy/deploy-conferencing/office-web-app-server.md)を参照してください。 
    
- フロントエンド サーバーの負荷分散には、HTTP トラフィック (会議コンテンツのダウンロードなど) 用のハードウェア負荷分散が必要です。SIP トラフィックには DNS 負荷分散をお勧めします。詳細については、「[Load balancing requirements for Skype for Business](../../plan-your-deployment/network-requirements/load-balancing.md)」を参照してください。 
    
- 専用の会議では大規模なプールの監視サーバーを使用するには、ビジネス サーバー配置の Skype 内のフロント エンド サーバー プールのすべての間で、監視サーバーとそのデータベースが共有しているを使用することをお勧めします。 詳細については、 [Skype のビジネス サーバーで監視するための計画](../../plan-your-deployment/monitoring.md)を参照してください。
    

