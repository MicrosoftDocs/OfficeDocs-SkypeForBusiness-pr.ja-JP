---
title: Skype for Business Server の会議トポロジを計画する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7392dfa7-791a-4723-88ff-0ef8a9ef11c8
description: '概要: Skype for Business Server での会議トポロジの計画については、このトピックを参照してください。'
ms.openlocfilehash: 1b9d9024d90b4bd847c763747dad7a5f96616aa3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816016"
---
# <a name="plan-your-conferencing-topology-for-skype-for-business-server"></a>Skype for Business Server の会議トポロジを計画する
 
**概要:** このトピックでは、Skype for Business Server での会議トポロジの計画について説明します。
  
このトピックでは、Skype for Business Server の会議でのトポロジの基礎について説明します。
  
- サポートされるトポロジ
    
- ダイヤルイン会議の考慮事項
    
- Web 会議の考慮事項
    
- 大規模会議の要件
    
ハードウェアとソフトウェアの要件の詳細については、「 [Skype For Business Server の会議のハードウェアとソフトウェアの要件](hardware-and-software-requirements.md)」を参照してください。
  
## <a name="supported-topologies"></a>サポートされるトポロジ

Skype for Business Server では、会議サービスを実行しているサーバーは、常にフロントエンドサーバーまたは Standard Edition サーバーと連携しています。 Skype for Business Server を展開すると、IM 会議機能が自動的に展開されます。 トポロジ ビルダーを使用して Web、音声とビデオ (A/V)、およびダイヤルイン会議を展開するかどうかを指定できます。 また、トポロジ ビルダーを使用して、既存の展開に会議を追加することもできます。 トポロジの基礎と collocation のシナリオについて詳しくは、「 [Skype For Business Server のトポロジの基礎](../../plan-your-deployment/topology-basics/topology-basics.md)」をご覧ください。
  
次のトポロジと構成に会議を展開できます。
  
- Skype for Business Server Standard Edition
    
- Skype for Business Server Enterprise Edition
    
- エンタープライズ VoIP の有無は問いません
    
## <a name="dial-in-conferencing-considerations"></a>ダイヤルイン会議の考慮事項

ダイヤルイン会議を展開する場合は、以下の点を考慮する必要があります。
  
- ダイヤルイン会議では、Skype for Business Server と PSTN ゲートウェイの間でシグナリング (および一部の構成のメディア) を変換するために仲介サーバーを使用する必要があります。また、PSTN ゲートウェイは、仲介サーバーと PSTN ゲートウェイ間のシグナリングとメディアを変換します。.
    
   ダイヤルイン会議を構成する前に、エンタープライズ VoIP または仲介サーバーと、以下のうち少なくとも 1 つを展開する必要があります。
    
  - PSTN ゲートウェイ
    
  - IP-PBX
    
  - セッション ボーダー コントローラー (SBC) (SIP トランクを構成して接続するインターネット テレフォニー サービス プロバイダー (ITSP) のため)
    
- アプリケーション サービス、会議アテンダント アプリケーション、および会議アナウンス アプリケーションを中央サイトに展開できます。ブランチ サイトには展開できません。
    
- Skype for Business Server 会議を展開するすべてのプールにダイヤルイン会議を展開する必要があります。 プールごとにアクセス番号を割り当てる必要はありませんが、プールごとにダイヤルイン会議機能を展開する必要があります。 この要件は、ユーザーが1つのプールのアクセス番号を呼び出して、別のプールで Skype for Business Server 会議に参加したときに記録された名前の機能をサポートします。 
    
詳細については、「 [Skype For Business Server でのダイヤルイン会議の計画](dial-in-conferencing.md)」を参照してください。
  
## <a name="web-conferencing-considerations"></a>Web 会議の考慮事項

Web 会議には以下が必要です。 
  
- Web 会議のコンテンツを格納するために使用するファイル ストアへのアクセス。
    
- 会議中に PowerPoint ファイルを共有するために必要な Office Web Apps サーバー/Office Online Server との統合。
    
> [!NOTE]
> Office Web Apps サーバーの最新のイテレーションは、Skype for Business Server でサポートされている Office Online Server という名前です。 詳細については、「 [Office Online Server のドキュメント](https://technet.microsoft.com/en-us/library/jj219456%28v=office.16%29.aspx)」を参照してください。 
  
Skype for Business Server では、次の方法で Office Web Apps サーバー/Office Online Server を構成できます。 必要に応じて次のことができます。
  
- **Skype for Business Server、Office Web Apps Server、Office Online Server の両方を組織のファイアウォールと同じネットワークゾーンにインストールします。** With this topology, external access to Office Web Apps Server/Office Online Server will be provided through your reverse proxy server. 理想的には、Office Web Apps サーバー/Office Online Server を Skype for Business Server と同じネットワークゾーンにインストールすることをお勧めします。
    
    外部の Skype for Business クライアントは、インターネットからの要求を受け取り、内部ネットワークに転送するサーバーであるリバースプロキシサーバーを使用して、Skype for Business Server および Office Web Apps サーバー/Office Online Server に接続できます。 (内部クライアントは、Office Web Apps サーバー/Office Online Server に直接接続できるため、リバースプロキシサーバーを使用する必要はありません)。このトポロジは、専用の Office Web Apps サーバーと、Skype for Business Server でのみ使用されている Office Online Server ファームを使用する場合に最適です。
    
- **外部に展開された Office Web Apps サーバー/Office Online サーバーを使用する。** このトポロジでは、Skype for Business Server はオンプレミスで展開され、Skype for Business Server ネットワークゾーンの外部に展開されている Office Web Apps サーバー/Office Online サーバーを使用します。 この問題は、Office Web Apps サーバー/Office Online Server が企業内の複数のアプリケーションで共有されており、Skype for Business Server が Office Web Apps サーバー/Office Online Server の外部インターフェイスを使用する必要があるネットワークに展開されている場合に発生することがあります。
    
    リバースプロキシサーバーをインストールする必要はありません。代わりに、Office Web Apps サーバー/Office Online Server から Skype for Business Server へのすべての要求は、Edge サーバー経由でルーティングされます。 内部と外部の Skype for Business クライアントの両方が、外部 URL を使用して Office Web Apps サーバー/Office Online サーバーに接続されています。
    
    Office Web Apps サーバー/Office Online Server を内部ファイアウォールの外側に展開する場合は、トポロジ ビルダーで [**Office Web Apps サーバーは外部ネットワークで展開**] オプション (つまり、境界ネットワークまたはインターネット) を選択します。
    
詳細については、「 [Skype For Business server で Office Web Apps サーバーとの統合を構成する](../../deploy/deploy-conferencing/office-web-app-server.md)」を参照してください。 
  
選択するトポロジにかかわらず、ファイアウォールの正しいポートを開くことは重要です。 DNS 名、IP アドレス、およびポートが、Office Web Apps サーバー、Office Online Server、ロードバランサー、または Skype for Business Server 上のファイアウォールによってブロックされていないことを確認する必要があります。
  
> [!NOTE]
> Office Web Apps サーバー/Office Online Server への外部アクセスを提供するには、サーバーを境界ネットワークに展開するという方法もあります。この場合、Office Web Apps サーバー/Office Online Server をセットアップするために、サーバー コンピューターを Active Directory ドメインのメンバーにする必要があることに注意してください。境界ネットワーク内のコンピューターを Active Directory ドメインのメンバーにすることがネットワーク ポリシーで許可されていない場合は、Office Web Apps サーバー/Office Online Server を境界ネットワークにインストールしないことをお勧めします。その代わりに、Office Web Apps サーバー/Office Online Server を内部ネットワークにインストールし、リバース プロキシ サーバー経由で外部ユーザー アクセスを提供します。 
  
## <a name="topology-requirements-for-large-meetings"></a>大規模会議のトポロジ要件

1 つの大規模な会議には、少なくとも 1 つのフロントエンド サーバーと 1 つのバックエンド サーバーが必要です。ただし、高可用性を実現するために、次の図に示すように、バックエンド サーバーがミラーリングされている 2 つのフロントエンド サーバー プールを使用することをお勧めします。
  
**大規模会議のトポロジ**

![大規模会議のトポロジ](../../media/06858900-a262-4a47-96d0-51abd6827064.png)
  
大規模な会議を主催するユーザーには、フロントエンド プールに所属するユーザー アカウントが必要です。 ただし、このプールに他のユーザー アカウントをホストすることはお勧めしません。 代わりに、大規模な会議にのみ使用します。 ベスト プラクティスは、大規模な会議のホストにのみ使用する特殊なユーザー アカウントをこのプールに作成することです。 大規模な会議の設定はパフォーマンス用に最適化されているので、それを通常のユーザーとして使用すると、PSTN エンドポイントが関係する場合に P2P セッションを会議に昇格できないなどの問題が発生することがあります。
  
2 つのフロントエンド サーバーでプールを管理するには、特別な配慮が必要です。詳細については、「[Topology Basics for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md)」および「[Reference topologies for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/reference-topologies.md)」を参照してください。
  
また、オプションで大規模な会議に使用するプールの障害復旧バックアップおよびフェールオーバーを提供する場合は、これを異なるデータ センター内の同様に設定した専用プールと組み合わせることができます。 詳細については、「 [Skype For Business Server で高可用性と障害回復を計画する](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)」を参照してください。
  
トポロジについて次のような追加の注意事項があります。
  
- 会議コンテンツを格納するため、また、アーカイブ サーバーが展開されて有効になっている場合はアーカイブ ファイルを格納するために、ファイル共有が必要です。 ファイル共有は、プール専用にすることも、プールが展開されているサイトの別のプールで使用されているのと同じファイル共有にすることもできます。 ファイル共有の構成の詳細については、「 [Skype For Business Server 2015 でファイル共有を作成](../../deploy/install/create-a-file-share.md)する」を参照してください。
    
- 大規模な会議で PowerPoint プレゼンテーション機能を有効にするには、Office Web Apps サーバー/Office Online Server が必要です。 Office Web Apps サーバー/Office Online Server は、大規模な会議プール専用にすることも、専用プールが展開されているサイトの他のプールで使用されているのと同じ Office Web Apps サーバー/Office Online Server にすることもできます。 詳細については、「 [Skype For Business server で Office Web Apps サーバーとの統合を構成する](../../deploy/deploy-conferencing/office-web-app-server.md)」を参照してください。 
    
- フロントエンド サーバーの負荷分散には、HTTP トラフィック (会議コンテンツのダウンロードなど) 用のハードウェア負荷分散が必要です。SIP トラフィックには DNS 負荷分散をお勧めします。詳細については、「[Load balancing requirements for Skype for Business](../../plan-your-deployment/network-requirements/load-balancing.md)」を参照してください。 
    
- 専用の大規模な会議プール用に監視サーバーを使用する場合は、Skype for Business Server の展開で監視サーバーとそのデータベースをすべてのフロントエンドサーバープールで共有することをお勧めします。 詳細については、「 [Skype For Business Server で監視計画を立てる](../../plan-your-deployment/monitoring.md)」を参照してください。
    

