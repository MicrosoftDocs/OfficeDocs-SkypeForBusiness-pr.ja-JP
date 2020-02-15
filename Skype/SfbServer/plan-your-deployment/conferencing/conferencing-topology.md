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
description: '概要: このトピックでは、Skype for Business Server での会議トポロジの計画について説明します。'
ms.openlocfilehash: 68ee859979deb7d977ee546e711474d0b6ba06e5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030781"
---
# <a name="plan-your-conferencing-topology-for-skype-for-business-server"></a>Skype for Business Server の会議トポロジを計画する
 
**概要:** このトピックでは、Skype for Business Server での会議トポロジの計画について説明します。
  
ここでは、Skype for Business Server での会議のトポロジの基本について説明します。
  
- サポートされるトポロジ
    
- ダイヤルイン会議の考慮事項
    
- Web 会議に関する考慮事項
    
- 大規模会議の要件
    
ハードウェアとソフトウェアの要件の詳細については、「 [Skype For Business Server での会議のハードウェアおよびソフトウェア要件](hardware-and-software-requirements.md)」を参照してください。
  
## <a name="supported-topologies"></a>サポートされるトポロジ

Skype for Business Server では、会議サービスを実行しているサーバーは、常にフロントエンドサーバーまたは Standard Edition サーバーと併置されます。 Skype for Business Server を展開すると、IM 会議機能が自動的に展開されます。 トポロジビルダーを使用して、web、オーディオ、ビデオ (A/V)、およびダイヤルイン会議を展開するかどうかを指定できます。 トポロジー ビルダーを使用して、既存の展開に会議を追加することもできます。 トポロジの基礎および併置シナリオの詳細については、「 [topology の基礎 (Skype For Business Server](../../plan-your-deployment/topology-basics/topology-basics.md))」を参照してください。
  
会議は、次のトポロジと構成で展開できます。
  
- Skype for Business Server Standard Edition
    
- Skype for Business Server Enterprise Edition
    
- エンタープライズ Voip の有無にかかわらず
    
## <a name="dial-in-conferencing-considerations"></a>ダイヤルイン会議の考慮事項

ダイヤルイン会議を展開している場合は、次の点を考慮する必要があります。
  
- ダイヤルイン会議では、Skype for Business Server と PSTN ゲートウェイ間、および仲介サーバーと PSTN ゲートウェイ間の信号とメディアを変換する PSTN ゲートウェイの間で、仲介サーバーを使用する必要があります。.
    
   ダイヤルイン会議を構成する前に、エンタープライズ Voip または仲介サーバーと、次のうち少なくとも1つを展開する必要があります。
    
  - PSTN ゲートウェイ
    
  - IP-PBX
    
  - セッション ボーダー コントローラー (SBC) (SIP トランクを構成して接続するインターネット テレフォニー サービス プロバイダー (ITSP) のため)
    
- アプリケーションサービス、会議アテンダントアプリケーション、および会議アナウンスアプリケーションは、中央サイトに展開できますが、ブランチサイトに展開することはできません。
    
- Skype for Business Server 会議を展開するすべてのプールにダイヤルイン会議を展開する必要があります。 プールごとにアクセス番号を割り当てる必要はありませんが、プールごとにダイヤルイン会議機能を展開する必要があります。 この要件では、ユーザーが1つのプールのアクセス番号を呼び出して、別のプールにある Skype for Business Server の会議に参加するときに記録された名前の機能がサポートされます。 
    
詳細については、「 [Skype For Business Server でのダイヤルイン会議の計画](dial-in-conferencing.md)」を参照してください。
  
## <a name="web-conferencing-considerations"></a>Web 会議に関する考慮事項

Web 会議には次のものが必要です。 
  
- Web 会議のコンテンツを格納するために使用するファイル ストアへのアクセス。
    
- 会議中に PowerPoint ファイルを共有するために必要な Office Web Apps サーバー/Office Online Server との統合。
    
> [!NOTE]
> Office Web Apps サーバーの最新のイテレーションは、Skype for Business Server でサポートされている Office Online Server と呼ばれています。 詳細については、 [Office Online Server のドキュメント](https://technet.microsoft.com/library/jj219456%28v=office.16%29.aspx)を参照してください。 
  
Skype for Business Server には、Office Web Apps サーバーまたは Office Online Server を構成するための次のような方法が用意されています。 必要に応じて次のことができます。
  
- **組織のファイアウォールの背後にあるオンプレミスの Skype for Business Server と Office Web Apps サーバーまたは Office Online Server の両方を、同じネットワークゾーンにインストールします。** このトポロジでは、Office Web Apps サーバーまたは Office Online Server への外部アクセスはリバースプロキシサーバー経由で提供されます。 理想的には、Office Web Apps サーバー/Office Online Server を Skype for Business Server と同じネットワークゾーンにインストールすることをお勧めします。
    
    外部の Skype for Business クライアントは、リバースプロキシサーバーを使用して Skype for Business Server および Office Web Apps サーバー/Office Online Server に接続することができます。これは、インターネットからの要求を受けて内部ネットワークに転送するサーバーです。 (内部クライアントは、Office Web Apps サーバー/Office Online Server に直接接続できるため、リバースプロキシサーバーを使用する必要はありません)。このトポロジは、Skype for Business Server のみで使用される専用の Office Web Apps サーバーまたは Office Online Server ファームを使用する場合に最適に機能します。
    
- **外部に展開された Office Web Apps サーバーまたは Office Online Server を使用します。** このトポロジでは、Skype for Business Server がオンプレミスで展開されており、Skype for business Server ネットワークゾーンの外側に展開されている Office Web Apps サーバーまたは Office Online Server を使用します。 これは、Office Web Apps サーバーまたは Office Online Server が企業内の複数のアプリケーション間で共有されており、Skype for Business Server が Office Web Apps サーバー/Office Online Server の外部インターフェイスを使用する必要があるネットワークに展開されている場合に発生する可能性があります。
    
    リバースプロキシサーバーをインストールする必要はありません。その代わりに、Office Web Apps サーバーまたは Office Online Server から Skype for Business Server へのすべての要求が、エッジサーバーを経由してルーティングされます。 内部と外部の Skype for Business の両方のクライアントは、外部 URL を使用して Office Web Apps サーバーまたは Office Online Server に接続します。
    
    Office Web Apps サーバーまたは Office Online Server が内部ファイアウォールの外側に展開されている場合は、[トポロジビルダー] の [ **Office Web Apps サーバーは外部ネットワークに展開され**ます (つまり、境界またはインターネット)] オプションを選択します。
    
詳細については、「 [Configure integration With Office Web Apps server In Skype For Business server](../../deploy/deploy-conferencing/office-web-app-server.md)」を参照してください。 
  
選択するトポロジにかかわらず、ファイアウォールの正しいポートを開くことは重要です。 Office Web Apps サーバーまたは Office Online Server、ロードバランサー、または Skype for Business Server のファイアウォールによって、DNS 名、IP アドレス、およびポートがブロックされないようにする必要があります。
  
> [!NOTE]
> Office Web Apps サーバーまたは Office Online Server への外部アクセスを提供するもう1つの方法は、境界ネットワークにサーバーを展開することです。 これを行う場合は、Office Web Apps サーバー/Office Online Server セットアップでは、サーバーコンピューターが Active Directory ドメインのメンバーである必要があることに注意してください。 ネットワークポリシーによって、境界ネットワーク内のコンピューターが Active Directory ドメインのメンバーになることが許可されていない場合は、境界ネットワークに Office Web Apps サーバーまたは Office Online Server をインストールしないことをお勧めします。 その代わりに、Office Web Apps Server/Office Online Server を内部ネットワークにインストールし、リバースプロキシサーバー経由で外部ユーザーアクセスを提供する必要があります。 
  
## <a name="topology-requirements-for-large-meetings"></a>大規模会議のトポロジ要件

1つの大規模な会議には、少なくとも1台のフロントエンドサーバーと1台のバックエンドサーバーが必要です。 ただし、高可用性を実現するには、次の図に示すように、バックエンドサーバーがミラー化された2台のフロントエンドサーバープールをお勧めします。
  
**大規模会議のトポロジ**

![大規模会議のトポロジ](../../media/06858900-a262-4a47-96d0-51abd6827064.png)
  
大規模な会議をホストするユーザーは、フロントエンドプールに所属するユーザーアカウントを持っている必要があります。 ただし、このプールに他のユーザー アカウントをホストすることはお勧めしません。 代わりに、大規模な会議にのみ使用します。 ベスト プラクティスは、大規模な会議のホストにのみ使用する特殊なユーザー アカウントをこのプールに作成することです。 大規模な会議の設定はパフォーマンスのために最適化されているため、通常のユーザーとして使用すると、PSTN エンドポイントが関与しているときに、P2P セッションを会議に昇格できないなどの問題が発生する可能性があります。
  
2 つのフロントエンド サーバーでプールを管理するには、特別な考慮が必要です。 詳細については、「Skype for business [server 2015 のトポロジの基本](../../plan-your-deployment/topology-basics/topology-basics.md)」および「 [Skype for business Server 2015 のリファレンストポロジ](../../plan-your-deployment/topology-basics/reference-topologies.md)」を参照してください。
  
さらに、大規模な会議に使用されているプールに対して、必要に応じて障害回復のバックアップとフェールオーバーを提供する場合は、別のデータセンターに専用プールを設定するのと同じように組み合わせることができます。 詳細については、「 [Plan for high availability and disaster recovery In Skype For Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)」を参照してください。
  
トポロジについて次のような追加の注意事項があります。
  
- アーカイブファイルを保存するために、アーカイブサーバーが展開されて有効になっている場合は、会議コンテンツを格納するためにファイル共有が必要です。 ファイル共有は、プール専用にすることも、プールが展開されているサイトの別のプールで使用されているのと同じファイル共有にすることもできます。 ファイル共有の構成の詳細については、「 [Create a file share In Skype For Business Server 2015](../../deploy/install/create-a-file-share.md)」を参照してください。
    
- 大規模な会議で PowerPoint プレゼンテーション機能を有効にするには、Office Web Apps サーバーまたは Office Online Server が必要です。 Office Web Apps Server/Office Online Server は、大規模な会議プール専用にすることも、専用プールを展開しているサイトの他のプールが使用する Office Web Apps サーバー/Office Online Server と同じにすることもできます。 詳細については、「 [Configure integration With Office Web Apps server In Skype For Business server](../../deploy/deploy-conferencing/office-web-app-server.md)」を参照してください。 
    
- フロントエンドサーバーの負荷分散では、HTTP トラフィック (会議コンテンツのダウンロードなど) にハードウェア負荷分散が必要になります。 SIP トラフィックには DNS 負荷分散をお勧めします。 詳細については、「 [Skype For business の負荷分散の要件」を](../../plan-your-deployment/network-requirements/load-balancing.md)参照してください。 
    
- 専用の大規模会議プールに対して監視サーバーを使用する場合は、Skype for Business Server 展開のすべてのフロントエンドサーバープールで共有されている監視サーバーとデータベースを使用することをお勧めします。 詳細については、「 [Skype For Business Server で監視を計画する](../../plan-your-deployment/monitoring.md)」を参照してください。
    

