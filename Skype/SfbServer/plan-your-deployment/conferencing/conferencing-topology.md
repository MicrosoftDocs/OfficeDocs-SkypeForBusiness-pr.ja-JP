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
ms.openlocfilehash: dc7c62d45a2ebd84f38cc67ce996ba0ac72aa794
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814097"
---
# <a name="plan-your-conferencing-topology-for-skype-for-business-server"></a>Skype for Business Server の会議トポロジを計画する
 
**概要:** このトピックでは、Skype for Business Server での会議トポロジの計画について説明します。
  
このトピックでは、Skype for Business Server での会議のトポロジの基本について説明します。
  
- サポートされるトポロジ
    
- ダイヤルイン会議に関する考慮事項
    
- Web 会議に関する考慮事項
    
- 大規模な会議の要件
    
ハードウェアおよびソフトウェアの要件の詳細については、「Skype for Business Server での会議のハードウェア要件およびソフトウェア要件」 [を参照してください](hardware-and-software-requirements.md)。
  
## <a name="supported-topologies"></a>サポートされるトポロジ

Skype for Business Server では、会議サービスを実行しているサーバーは常にフロントエンド サーバーまたは Standard Edition サーバーと一緒に展開されます。 Skype for Business Server を展開すると、IM 会議機能が自動的に展開されます。 トポロジ ビルダーを使用して、Web、音声およびビデオ (A/V)、およびダイヤルイン会議を展開するかどうかを指定できます。 トポロジー ビルダーを使用して、既存の展開に会議を追加することもできます。 トポロジの基本とコロケーションシナリオの詳細については [、「Topology Basics for Skype for Business Server」を参照してください](../../plan-your-deployment/topology-basics/topology-basics.md)。
  
会議は、次のトポロジと構成で展開できます。
  
- Skype for Business Server Standard Edition
    
- Skype for Business Server Enterprise Edition
    
- 使用する場合と使用しない場合エンタープライズ VoIP
    
## <a name="dial-in-conferencing-considerations"></a>ダイヤルイン会議に関する考慮事項

ダイヤルイン会議を展開する場合は、次の点を考慮する必要があります。
  
- ダイヤルイン会議では、仲介サーバーが Skype for Business Server と PSTN ゲートウェイの間の信号 (および一部の構成のメディア) を変換し、PSTN ゲートウェイが仲介サーバーと PSTN ゲートウェイの間で信号とメディアを変換する必要があります。
    
   ダイヤルイン会議を構成する前に、エンタープライズ VoIP または仲介サーバー、および次のいずれか少なくとも 1 つを展開する必要があります。
    
  - PSTN ゲートウェイ
    
  - IP-PBX
    
  - セッション ボーダー コントローラー (SBC) (SIP トランクを構成して接続するインターネット テレフォニー サービス プロバイダー (ITSP) のため)
    
- アプリケーション サービス、会議アテンダント アプリケーション、および会議アナウンス アプリケーションは中央サイトに展開できますが、ブランチ サイトには展開できます。
    
- ダイヤルイン会議は、Skype for Business Server 会議を展開するプールごとに展開する必要があります。 プールごとにアクセス番号を割り当てる必要はありませんが、プールごとにダイヤルイン会議機能を展開する必要があります。 この要件は、ユーザーが 1 つのプールからアクセス番号を呼び出して、別のプールで Skype for Business Server 会議に参加する場合に、記録された名前機能をサポートします。 
    
詳細については [、「Plan for dial-in conferencing in Skype for Business Server」を参照してください](dial-in-conferencing.md)。
  
## <a name="web-conferencing-considerations"></a>Web 会議に関する考慮事項

Web 会議には以下が必要です。 
  
- Web 会議のコンテンツを格納するために使用するファイル ストアへのアクセス。
    
- 会議中Office PowerPoint ファイルを共有するために必要Office Web Apps サーバー/Office Online Server との統合。
    
> [!NOTE]
> Web Apps サーバーの最新Officeは、Skype for Business Server Officeサポートされている Office Online Server という名前です。 詳細については、オンライン サーバーのドキュメント [Office参照してください](https://technet.microsoft.com/library/jj219456%28v=office.16%29.aspx)。 
  
Skype for Business Server では、Web Apps サーバー/Office Online Server を構成Office方法を提供します。 必要に応じて次のことができます。
  
- **Skype for Business Server と Office Web Apps サーバー/Office Online Server の両方を組織のファイアウォールの背後と同じネットワーク ゾーンにインストールします。** このトポロジでは、リバース プロキシ サーバー Office Web Apps サーバー/Office Web Apps サーバーへの外部アクセスが提供されます。 Skype for Business Server と同Officeネットワーク ゾーンOffice Web Apps サーバー/Office Web Apps サーバーをインストールする必要があります。
    
    外部の Skype for Business クライアントは、リバース プロキシ サーバー (インターネットからの要求を受け取って内部ネットワークに転送するサーバー) を使用して、Skype for Business Server および Office Web Apps サーバー/Office Online Server に接続できます。 (内部クライアントは直接 Web Apps サーバー/Office Online Server に接続Officeリバース プロキシ サーバーを使用する必要があります)。このトポロジは、Skype for Business Server でのみ使用される Office Web Apps サーバー/Office Online Server ファームを使用する場合に最適です。
    
- **外部に展開された Web Apps Office Web Apps サーバー/Office Online Server を使用します。** このトポロジでは、Skype for Business Server はオンプレミスに展開され、Skype for Business Server ネットワーク ゾーンの外部に展開される Office Web Apps サーバー/Office Online Server を使用します。 これは、Office Web Apps サーバー/Office Online Server が企業内の複数のアプリケーション間で共有され、Skype for Business Server が Office Web Apps サーバー/Office Online Server の外部インターフェイスを使用する必要があるネットワークに展開されている場合に発生する可能性があります。
    
    リバース プロキシ サーバーをインストールする必要は不要です。代わりに、Office Web Apps サーバー/Office Online Server から Skype for Business Server へのすべての要求は、エッジ サーバー経由でルーティングされます。 内部クライアントと外部 Skype for Business クライアントの両方が、外部 URL を使用Office Web Apps サーバー/Office Online Server に接続します。
    
    Office Web Apps サーバー/Office Online Server が内部ファイアウォールの外側に展開されている場合は、トポロジ ビルダーで Office **Web Apps サーバー** を外部ネットワーク (境界/インターネット) に展開するオプションを選択します。
    
詳細については [、「Configure integration with Office Web Apps Server in Skype for Business Server 」を参照してください](../../deploy/deploy-conferencing/office-web-app-server.md)。 
  
選択するトポロジにかかわらず、ファイアウォールの正しいポートを開くことは重要です。 Office Web Apps サーバー/Office Online Server、ロード バランサー、または Skype for Business Server のファイアウォールによって DNS 名、IP アドレス、およびポートがブロックされない必要があります。
  
> [!NOTE]
> Web Apps サーバー/Office Online Server への外部アクセスをOffice別のオプションは、境界ネットワークにサーバーを展開する方法です。 これを行う場合は、Office Web Apps サーバー/Office Online Server のセットアップでは、サーバー コンピューターが Active Directory ドメインのメンバーである必要があります。 ネットワーク ポリシーで境界ネットワーク内のコンピューターを Active Directory ドメイン メンバーに設定できない場合は、境界ネットワークに Office Web Apps サーバー/Office Online Server をインストールしない方が推奨されます。 代わりに、内部ネットワークに Office Web Apps サーバー/Office Online Server をインストールし、リバース プロキシ サーバーを介して外部ユーザー アクセスを提供する必要があります。 
  
## <a name="topology-requirements-for-large-meetings"></a>大規模な会議のトポロジ要件

1 つの大規模な会議には、少なくとも 1 つのフロントエンド サーバーと 1 つのバック エンド サーバーが必要です。 ただし、高可用性を実現するには、次の図に示すように、ミラー化されたバック エンド サーバーを持つ 2 つのフロントエンド サーバー プールをお勧めします。
  
**大規模会議トポロジ**

![大規模会議トポロジ](../../media/06858900-a262-4a47-96d0-51abd6827064.png)
  
大規模な会議をホストするユーザーは、フロントエンド プールにユーザー アカウントを設定する必要があります。 ただし、このプールに他のユーザー アカウントをホストすることはお勧めしません。 代わりに、大規模な会議にのみ使用します。 ベスト プラクティスは、大規模な会議のホストにのみ使用する特殊なユーザー アカウントをこのプールに作成することです。 大規模な会議の設定はパフォーマンスのために最適化されています。このため、通常のユーザーとして使用すると、PSTN エンドポイントが関係する場合に P2P セッションを会議に昇格させる可能性などの問題が発生する可能性があります。
  
2 つのフロントエンド サーバーでプールを管理するには、特別な考慮が必要です。 詳細については [、「Topology Basics for Skype for Business Server 2015」](../../plan-your-deployment/topology-basics/topology-basics.md) および [「Reference topologies for Skype for Business Server 2015」](../../plan-your-deployment/topology-basics/reference-topologies.md)を参照してください。
  
また、必要に応じて、大規模な会議に使用されるプールに対して障害復旧のバックアップとフェールオーバーを提供する場合は、別のデータ センターで同様にセットアップされた専用プールとペアリングできます。 詳細については [、「Plan for high availability and disaster recovery in Skype for Business Server 」を参照してください](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。
  
トポロジについて次のような追加の注意事項があります。
  
- 会議コンテンツを保存するにはファイル共有が必要です。また、アーカイブ サーバーが展開され有効になっている場合は、アーカイブ ファイルを保存するために必要です。 ファイル共有は、プール専用にすることも、プールが展開されているサイトの別のプールで使用されているのと同じファイル共有にすることもできます。 ファイル共有の構成の詳細については [、「Skype for Business Server 2015](../../deploy/install/create-a-file-share.md)でファイル共有を作成する」を参照してください。
    
- 大規模Officeで PowerPoint Office機能を有効にするには、Web Apps サーバーまたは Web Apps サーバーを使用する必要があります。 Office Web Apps サーバー/Office Online Server は、大規模な会議プール専用にすることもできますし、専用プールが展開されているサイトの他のプールで使用されるのと同じ Office Web Apps サーバー/Office Online Server にすることもできます。 詳細については [、「Configure integration with Office Web Apps Server in Skype for Business Server 」を参照してください](../../deploy/deploy-conferencing/office-web-app-server.md)。 
    
- フロントエンド サーバーの負荷分散では、HTTP トラフィック (会議コンテンツのダウンロードなど) にハードウェア負荷分散が必要です。 SIP トラフィックには DNS 負荷分散をお勧めします。 詳細については [、Skype for Business の負荷分散要件を参照してください](../../plan-your-deployment/network-requirements/load-balancing.md)。 
    
- 専用の大規模会議プールに監視サーバーを使用する場合は、Skype for Business Server 展開内のすべてのフロントエンド サーバー プールで共有される監視サーバーとそのデータベースを使用することをお勧めします。 詳細については [、「Skype for Business Server での監視の計画」を参照してください](../../plan-your-deployment/monitoring.md)。
    

