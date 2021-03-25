---
title: Skype for Business Server の会議トポロジを計画する
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
description: '概要: このトピックでは、Skype for Business Server での会議トポロジの計画について説明します。'
ms.openlocfilehash: acf1fecc4ab7c3ea19ca9b65b9ff2ffa2a1e93d1
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121585"
---
# <a name="plan-your-conferencing-topology-for-skype-for-business-server"></a>Skype for Business Server の会議トポロジを計画する
 
**概要:** Skype for Business Server で会議トポロジを計画する方法については、このトピックを参照してください。
  
このトピックでは、Skype for Business Server での会議のトポロジの基本について説明します。
  
- サポートされるトポロジ
    
- ダイヤルイン会議の考慮事項
    
- Web 会議の考慮事項
    
- 大規模な会議の要件
    
ハードウェア要件とソフトウェア要件の詳細については、「Skype for Business Server での会議のハードウェア要件とソフトウェア要件 [」を参照してください](hardware-and-software-requirements.md)。
  
## <a name="supported-topologies"></a>サポートされるトポロジ

Skype for Business Server では、会議サービスを実行しているサーバーは常にフロント エンド サーバーまたは Standard Edition サーバーと一緒に展開されます。 Skype for Business Server を展開すると、IM 会議機能が自動的に展開されます。 トポロジ ビルダーを使用して、Web、オーディオ、ビデオ (A/V)、およびダイヤルイン会議を展開するかどうかを指定できます。 トポロジー ビルダーを使用して、既存の展開に会議を追加することもできます。 トポロジの基本シナリオとコロケーション シナリオの詳細については [、「Topology Basics for Skype for Business Server」を参照してください](../../plan-your-deployment/topology-basics/topology-basics.md)。
  
会議は、次のトポロジと構成で展開できます。
  
- Skype for Business Server Standard Edition
    
- Skype for Business Server Enterprise Edition
    
- データの使用またはエンタープライズ VoIP
    
## <a name="dial-in-conferencing-considerations"></a>ダイヤルイン会議の考慮事項

ダイヤルイン会議を展開する場合は、次の点を考慮する必要があります。
  
- ダイヤルイン会議では、仲介サーバーが Skype for Business Server と PSTN ゲートウェイの間でシグナリング (および一部の構成のメディア) を変換し、仲介サーバーと PSTN ゲートウェイの間でシグナリングとメディアを変換する PSTN ゲートウェイが必要です。
    
   ダイヤルイン会議を構成する前に、エンタープライズ VoIPまたは仲介サーバーを展開し、少なくとも次のいずれかを展開する必要があります。
    
  - PSTN ゲートウェイ
    
  - IP-PBX
    
  - セッション ボーダー コントローラー (SBC) (SIP トランクを構成して接続するインターネット テレフォニー サービス プロバイダー (ITSP) のため)
    
- アプリケーション サービス、会議アテンダント アプリケーション、および会議アナウンス アプリケーションは、中央サイトに展開できますが、ブランチ サイトには展開できます。
    
- Skype for Business Server 会議を展開するすべてのプールにダイヤルイン会議を展開する必要があります。 プールごとにアクセス番号を割り当てる必要はありませんが、プールごとにダイヤルイン会議機能を展開する必要があります。 この要件は、ユーザーが別のプールで Skype for Business Server 会議に参加するために 1 つのプールからアクセス番号を呼び出す場合に、記録された名前機能をサポートします。 
    
詳細については [、「Plan for dial-in conferencing in Skype for Business Server」を参照してください](dial-in-conferencing.md)。
  
## <a name="web-conferencing-considerations"></a>Web 会議の考慮事項

Web 会議では、次の情報が必要です。 
  
- Web 会議のコンテンツを格納するために使用するファイル ストアへのアクセス。
    
- 会議中Office PowerPoint ファイルを共有するためにOffice Web Apps Server/Office Online Server との統合。
    
> [!NOTE]
> Web Apps Server の最新Officeは、Skype for Business Server でOfficeオンライン サーバーという名前です。 詳細については、オンライン サーバーのドキュメント [Office参照してください](/officeonlineserver/office-online-server)。 
  
Skype for Business Server では、Web Apps サーバー/オンライン サーバー Officeを構成Office方法を提供します。 必要に応じて次のことができます。
  
- **Skype for Business Server と web Apps Server/Office Web Apps Server/Office Online Server の両方を組織のファイアウォールの背後と同じネットワーク 領域にインストールします。** このトポロジを使用すると、Web Apps Server/Office Web Apps Server/Officeへの外部アクセスがリバース プロキシ サーバーを介して提供されます。 理想的には、Web Apps Server/Office Web Apps Server/Office Skype for Business Server と同じネットワーク 領域にインストールする必要があります。
    
    外部 Skype for Business クライアントは、インターネットからの要求を受け取って内部ネットワークに転送するサーバーであるリバース プロキシ サーバーを使用して、Skype for Business Server および Office Web Apps Server/Office Online Server に接続できます。 (内部クライアントは、Web Apps Server/Office オンライン サーバーに直接接続Officeリバース プロキシ サーバーを使用する必要があります)。このトポロジは、Skype for Business Server でのみ使用Office Web Apps Server/Office オンライン サーバー ファームを使用する場合に最適です。
    
- **Web Apps Server/Officeサーバーに外部Office使用します。** このトポロジでは、Skype for Business Server はオンプレミスで展開され、Skype for Business Server ネットワーク ゾーンの外部に展開される Office Web Apps Server/Office Online Server を使用します。 これは、Office Web Apps Server/Office Online Server が企業内の複数のアプリケーション間で共有され、Skype for Business Server が Office Web Apps Server/Office Online Server の外部インターフェイスを使用する必要があるネットワークに展開されている場合に発生する可能性があります。
    
    リバース プロキシ サーバーをインストールする必要があります。代わりに、Web Apps Server/Office オンライン Officeから Skype for Business Server へのすべての要求は、エッジ サーバー経由でルーティングされます。 内部クライアントと外部 Skype for Business クライアントの両方が、外部 URL をOffice Web Apps Server/Office オンライン サーバーに接続します。
    
    Office Web Apps Server/Office Online Server が内部ファイアウォールの外部に展開されている場合は、トポロジ ビルダーの外部ネットワーク (境界/インターネット) に **Office Web Apps** Server を展開するオプションを選択します。
    
詳細については [、「Configure integration with Office Web Apps Server in Skype for Business Server」を参照してください](../../deploy/deploy-conferencing/office-web-app-server.md)。 
  
選択するトポロジにかかわらず、ファイアウォールの正しいポートを開くことは重要です。 Office Web Apps Server/Office Online Server、ロード バランサー、Skype for Business Server のファイアウォールによって DNS 名、IP アドレス、ポートがブロックされない必要があります。
  
> [!NOTE]
> Web Apps Server/Officeオンライン サーバー Office外部アクセスを提供するもう 1 つのオプションは、境界ネットワークにサーバーを展開する方法です。 これを行う場合は、Office Web Apps Server/Office Online Server のセットアップでは、サーバー コンピューターが Active Directory ドメインのメンバーである必要があります。 ネットワーク ポリシーで境界ネットワーク内のコンピューターに Active Directory ドメイン メンバーを許可しない限り、境界ネットワークに Office Web Apps Server/Office Online Server をインストールしない方が推奨されます。 代わりに、内部ネットワークOffice Web Apps Server/Office Web Apps Server/Officeをインストールし、リバース プロキシ サーバーを介して外部ユーザー アクセスを提供する必要があります。 
  
## <a name="topology-requirements-for-large-meetings"></a>大規模な会議のトポロジ要件

1 つの大規模な会議では、少なくとも 1 つのフロント エンド サーバーと 1 つのバック エンド サーバーが必要です。 ただし、高可用性を提供するには、次の図に示すように、ミラー化されたバック エンド サーバーを備えた 2 つのフロントエンド サーバー プールをお勧めします。
  
**大規模な会議トポロジ**

![大規模な会議トポロジ](../../media/06858900-a262-4a47-96d0-51abd6827064.png)
  
大規模な会議をホストするユーザーは、フロントエンド プールに自分のユーザー アカウントを持っている必要があります。 ただし、このプールに他のユーザー アカウントをホストすることはお勧めしません。 代わりに、大規模な会議にのみ使用します。 ベスト プラクティスは、大規模な会議のホストにのみ使用する特殊なユーザー アカウントをこのプールに作成することです。 大規模な会議設定はパフォーマンスに最適化されています。通常のユーザーとして使用すると、PSTN エンドポイントが関係する場合に P2P セッションを会議に昇格させるなど、問題が発生する可能性があります。
  
2 つのフロントエンド サーバーでプールを管理するには、特別な考慮が必要です。 詳細については [、「Topology Basics for Skype for Business Server 2015」](../../plan-your-deployment/topology-basics/topology-basics.md) および [「Reference toppology for Skype for Business Server 2015」を参照](../../plan-your-deployment/topology-basics/reference-topologies.md)してください。
  
さらに、大規模な会議に使用されるプールに障害復旧のバックアップとフェールオーバーをオプションで提供する場合は、別のデータ センターで同様にセットアップされた専用プールとペアリングできます。 詳細については、「Skype for Business Server で高可用性と障害復旧を計画 [する」を参照してください](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。
  
トポロジについて次のような追加の注意事項があります。
  
- 会議のコンテンツを保存するにはファイル共有が必要で、アーカイブ サーバーが展開され有効になっている場合は、アーカイブ ファイルを保存するために必要です。 ファイル共有は、プール専用にすることも、プールが展開されているサイトの別のプールで使用されているのと同じファイル共有にすることもできます。 ファイル共有の構成の詳細については、「Create a file share [in Skype for Business Server 2015」を参照してください](../../deploy/install/create-a-file-share.md)。
    
- 大規模Office PowerPoint プレゼンテーション機能を有効Office Web Apps Server/Office Web Apps Server/Officeが必要です。 Office Web Apps Server/Office Online Server は、大規模な会議プール専用にすることもできますし、専用プールが展開されているサイトの他のプールで使用される Office Web Apps Server/Office Online Server と同じものにすることもできます。 詳細については [、「Configure integration with Office Web Apps Server in Skype for Business Server」を参照してください](../../deploy/deploy-conferencing/office-web-app-server.md)。 
    
- フロントエンド サーバーの負荷分散には、HTTP トラフィック (会議コンテンツのダウンロードなど) のハードウェア負荷分散が必要です。 SIP トラフィックには DNS 負荷分散をお勧めします。 詳細については [、「Skype for Business の負荷分散要件」を参照してください](../../plan-your-deployment/network-requirements/load-balancing.md)。 
    
- 専用の大規模会議プールに監視サーバーを使用する場合は、Skype for Business Server 展開内のすべてのフロント エンド サーバー プールで共有されている監視サーバーとそのデータベースを使用することをお勧めします。 詳細については [、「Plan for monitoring in Skype for Business Server」を参照してください](../../plan-your-deployment/monitoring.md)。
