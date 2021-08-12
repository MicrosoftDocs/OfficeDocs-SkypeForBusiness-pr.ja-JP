---
title: 電話会議のトポロジを計画Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7392dfa7-791a-4723-88ff-0ef8a9ef11c8
description: '概要: このトピックを参照して、会議トポロジを計画する方法についてSkype for Business Server。'
ms.openlocfilehash: 711db1309ce31838f02bd705252693a58992e2ee9a21e12931c8a9c5fe064d92
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54283109"
---
# <a name="plan-your-conferencing-topology-for-skype-for-business-server"></a>電話会議のトポロジを計画Skype for Business Server
 
**概要:** このトピックでは、会議トポロジを計画する方法について説明します。Skype for Business Server。
  
このトピックでは、会議のトポロジの基本について説明Skype for Business Server。
  
- サポートされるトポロジ
    
- ダイヤルイン会議の考慮事項
    
- Web 会議の考慮事項
    
- 大規模な会議の要件
    
ハードウェア要件とソフトウェア要件の詳細については、「ハードウェアとソフトウェアの要件」を参照[Skype for Business Server。](hardware-and-software-requirements.md)
  
## <a name="supported-topologies"></a>サポートされるトポロジ

このSkype for Business Server会議サービスを実行しているサーバーは、常にフロント エンド サーバーまたはサーバーとStandard Editionされます。 クライアントを展開するとSkype for Business Server IM 会議機能が自動的に展開されます。 トポロジ ビルダーを使用して、Web、オーディオ、ビデオ (A/V)、およびダイヤルイン会議を展開するかどうかを指定できます。 トポロジー ビルダーを使用して、既存の展開に会議を追加することもできます。 トポロジの基本シナリオとコロケーション シナリオの詳細については、「[トポロジの基本」を参照Skype for Business Server。](../../plan-your-deployment/topology-basics/topology-basics.md)
  
会議は、次のトポロジと構成で展開できます。
  
- Skype for Business Server Standard Edition
    
- Skype for Business Server Enterprise Edition
    
- データの使用またはエンタープライズ VoIP
    
## <a name="dial-in-conferencing-considerations"></a>ダイヤルイン会議の考慮事項

ダイヤルイン会議を展開する場合は、次の点を考慮する必要があります。
  
- ダイヤルイン会議では、仲介サーバーが Skype for Business Server と PSTN ゲートウェイの間でシグナリング (および一部の構成のメディア) を変換し、仲介サーバーと PSTN ゲートウェイの間で信号とメディアを変換する PSTN ゲートウェイが必要です。
    
   ダイヤルイン会議を構成する前に、エンタープライズ VoIPまたは仲介サーバーを展開し、少なくとも次のいずれかを展開する必要があります。
    
  - PSTN ゲートウェイ
    
  - IP-PBX
    
  - セッション ボーダー コントローラー (SBC) (SIP トランクを構成して接続するインターネット テレフォニー サービス プロバイダー (ITSP) のため)
    
- Application Service、会議アテンダント アプリケーション、および会議アナウンス アプリケーションは、ブランチ サイトではなく、中央サイトに展開できます。
    
- ダイヤルイン会議は、電話会議を展開するプールSkype for Business Serverがあります。 プールごとにアクセス番号を割り当てる必要はありませんが、プールごとにダイヤルイン会議機能を展開する必要があります。 この要件は、ユーザーが 1 つのプールからアクセス番号を呼び出して、別のプール内の会議に参加Skype for Business Server記録された名前機能をサポートします。 
    
詳細については、「Plan [for dial-in conferencing in](dial-in-conferencing.md)Skype for Business Server」 を参照してください。
  
## <a name="web-conferencing-considerations"></a>Web 会議の考慮事項

Web 会議では、次の情報が必要です。 
  
- Web 会議のコンテンツを格納するために使用するファイル ストアへのアクセス。
    
- 会議中OfficeファイルをOffice Online Serverするために必要な Web Apps Server/PowerPoint との統合。
    
> [!NOTE]
> Web Apps Server Officeの最新のイテレーションには、Office Online Serverという名前が付Skype for Business Server。 詳細については、次のドキュメント[を参照Office Online Serverしてください](/officeonlineserver/office-online-server)。 
  
Skype for Business Server Web Apps Server/Officeを構成する次Office Online Server。 必要に応じて次のことができます。
  
- **組織のファイアウォールSkype for Business Server、Officeネットワーク ゾーンの背後Office Online Server Web Apps Server/Office Online Server と Web Apps Server/Office Online Serverの両方をインストールします。** このトポロジでは、Web Apps Server/OfficeへのOffice Online Serverアクセスがリバース プロキシ サーバーを介して提供されます。 理想的には、Web Apps Server/Officeサーバー/Office Online Serverと同じネットワーク ゾーンにインストールSkype for Business Server。
    
    外部 Skype for Business クライアントは、インターネットからの要求を受け取って内部ネットワークに転送するサーバーであるリバース プロキシ サーバーを使用して、Skype for Business Server および Office Web Apps Server/Office Online Server に接続できます。 (内部クライアントは、Web Apps Server/Officeに直接接続できるOffice Online Server必要があります)。このトポロジは、Web Apps Server/Office/Office Online Server専用のサーバー ファームを使用する場合に最適Skype for Business Server。
    
- **Web Apps Server/Officeの外部に展開されたOffice Online Server。** このトポロジでは、Skype for Business Server はオンプレミスで展開され、Office Web Apps Server/Office Online Server を使用して、Skype for Business Server ネットワーク ゾーンの外部に展開されます。 これは、Office Web Apps Server/Office Online Server が企業内の複数のアプリケーション間で共有され、Skype for Business Server が Office Web Apps Server/Office Online Server の外部インターフェイスを使用する必要があるネットワークに展開されている場合に発生する可能性があります。
    
    リバース プロキシ サーバーをインストールする必要があります。代わりに、Web Apps Server/Office から Office Online ServerへのSkype for Business Serverは、エッジ サーバー経由でルーティングされます。 内部クライアントと外部クライアントの両方Skype for Business外部 URL をOffice Web Apps Server/Office Online Serverに接続します。
    
    Office Web Apps Server/Office Online Server が内部ファイアウォールの外部に展開されている場合は、トポロジ ビルダーの **外部** ネットワーク (境界/インターネット) に展開されるオプション Office Web Apps Server を選択します。
    
詳細については、「Configure [integration with Office Web Apps Server in Skype for Business Server」 を参照してください](../../deploy/deploy-conferencing/office-web-app-server.md)。 
  
選択するトポロジにかかわらず、ファイアウォールの正しいポートを開くことは重要です。 dns 名、IP アドレス、ポートが Office Web Apps Server/Office Online Server、ロード バランサー、または Skype for Business Server のファイアウォールによってブロックされない必要があります。
  
> [!NOTE]
> Web Apps Server/Officeへの外部アクセスをOffice Online Server別のオプションは、境界ネットワークにサーバーを展開する方法です。 これを行う場合は、Office Web Apps Server/Office Online Server セットアップでは、サーバー コンピューターが Active Directory ドメインのメンバーである必要があります。 ネットワーク ポリシーで境界ネットワーク内のコンピューターに Active Directory ドメイン メンバーを許可しない限り、境界ネットワークに Office Web Apps Server/Office Online Server をインストールしない方が推奨されます。 代わりに、内部ネットワークOffice Web Apps Server/Office Online Serverをインストールし、リバース プロキシ サーバーを介して外部ユーザー アクセスを提供する必要があります。 
  
## <a name="topology-requirements-for-large-meetings"></a>大規模な会議のトポロジ要件

1 つの大規模な会議では、少なくとも 1 つのフロント エンド サーバーと 1 つのバック エンド サーバーが必要です。 ただし、高可用性を提供するには、次の図に示すように、ミラー化されたバック エンド サーバーを備えた 2 つのフロントエンド サーバー プールをお勧めします。
  
**大規模な会議トポロジ**

![大規模な会議トポロジ](../../media/06858900-a262-4a47-96d0-51abd6827064.png)
  
大規模な会議をホストするユーザーは、フロントエンド プールに自分のユーザー アカウントを持っている必要があります。 ただし、このプールに他のユーザー アカウントをホストすることはお勧めしません。 代わりに、大規模な会議にのみ使用します。 ベスト プラクティスは、大規模な会議のホストにのみ使用する特殊なユーザー アカウントをこのプールに作成することです。 大規模な会議設定はパフォーマンスに最適化されています。通常のユーザーとして使用すると、PSTN エンドポイントが関係する場合に P2P セッションを会議に昇格させるなど、問題が発生する可能性があります。
  
2 つのフロントエンド サーバーでプールを管理するには、特別な考慮が必要です。 詳細については[、「Topology Basics for Skype for Business Server 2015」](../../plan-your-deployment/topology-basics/topology-basics.md)および「Reference [toppology for Skype for Business Server 2015」を参照](../../plan-your-deployment/topology-basics/reference-topologies.md)してください。
  
さらに、大規模な会議に使用されるプールに障害復旧のバックアップとフェールオーバーをオプションで提供する場合は、別のデータ センターで同様にセットアップされた専用プールとペアリングできます。 詳細については、「Plan for high availability and disaster recovery in Skype for Business Server 」[を参照してください](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。
  
トポロジについて次のような追加の注意事項があります。
  
- 会議のコンテンツを保存するにはファイル共有が必要で、アーカイブ サーバーが展開され有効になっている場合は、アーカイブ ファイルを保存するために必要です。 ファイル共有は、プール専用にすることも、プールが展開されているサイトの別のプールで使用されているのと同じファイル共有にすることもできます。 ファイル共有の構成の詳細については、「Create a file share [in a file share in Skype for Business Server 2015」を参照](../../deploy/install/create-a-file-share.md)してください。
    
- 大規模な会議Officeプレゼンテーション機能を有効Office Online Server Web Apps Server/PowerPoint Web Apps Server/PowerPoint必要です。 Office Web Apps Server/Office Online Server は、大規模な会議プール専用にすることもできますし、専用プールが展開されているサイトの他のプールで使用される Office Web Apps Server/Office Online Server と同じものにすることもできます。 詳細については、「Configure [integration with Office Web Apps Server in Skype for Business Server」 を参照してください](../../deploy/deploy-conferencing/office-web-app-server.md)。 
    
- フロントエンド サーバーの負荷分散には、HTTP トラフィック (会議コンテンツのダウンロードなど) のハードウェア負荷分散が必要です。 SIP トラフィックには DNS 負荷分散をお勧めします。 詳細については、「[負荷分散の要件」を参照Skype for Business。](../../plan-your-deployment/network-requirements/load-balancing.md) 
    
- 専用の大規模会議プールに監視サーバーを使用する場合は、Skype for Business Server 展開内のすべてのフロント エンド サーバー プールで共有されている監視サーバーとそのデータベースを使用することをお勧めします。 詳細については、「Plan [for monitoring in Skype for Business Server」 を参照してください](../../plan-your-deployment/monitoring.md)。
