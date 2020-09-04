---
title: Cloud Connector エディション PSTN サイトの計画
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/30/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: cec2d9bf-2deb-482c-841b-0e3599f94b50
description: このトピックでは、効率的で費用効果の高い通話ルーティングを実現するために、Cloud Connector エディションの PSTN サイトを計画する方法について説明します。
ms.openlocfilehash: 3b4320e12a87c771e28fce445102327c7783a5d2
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358803"
---
# <a name="plan-for-cloud-connector-edition-pstn-sites"></a>Cloud Connector エディション PSTN サイトの計画

> [!Important]
> Cloud Connector エディションは、2021年7月31日、Skype for Business Online と共に廃止されます。 組織が Teams にアップグレードされたら、 [直接ルーティング](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)を使用してオンプレミスのテレフォニーネットワークを teams に接続する方法について説明します。
 
このトピックでは、効率的で費用効果の高い通話ルーティングを実現するために、Cloud Connector エディションの PSTN サイトを計画する方法について説明します。
  
このトピックでは、Cloud Connector の PSTN サイトを計画できるようにするために、Cloud Connector エディションと通話ルーティングについて知っておく必要のある事項について説明します。 PSTN サイトは、クラウドコネクタアプライアンスを組み合わせたもので、同じ場所に展開され、共通の PSTN ゲートウェイが接続されています。 このトピックでは、クラウドコネクタサイトトポロジを設定して、サイトに割り当てられているすべてのユーザーについて、最もコスト効率と効果的な方法で受信と送信の両方のルーティングを処理できるようにする方法について説明します。 Cloud Connector および PSTN サイトの利点の詳細については、「Plan for [Skype for Business Cloud Connector Edition](plan-skype-for-business-cloud-connector-edition.md)」を参照してください。 
  
## <a name="cloud-connector-pstn-sites-and-call-routing"></a>Cloud Connector PSTN サイトと通話ルーティング

Cloud Connector PSTN サイトは、不必要な長距離および国内間 tariffs を防止するために作成されたトポロジ構成要素で、送信緊急電話が適切なトランクにルーティングされるようにします。 緊急サービスへの通話を含む、通話の費用効果の高い効率的なルーティングを実現するには、PSTN サイトと各サイトへのユーザーの割り当て方法を慎重に計画する必要があります。 
  
Cloud Connector の計画の一環として、オフィスとユーザーの所在地や、PSTN トランクがキャリアから終了する場所について、carrier に連絡することが重要です。 緊急通話をルーティングする方法を決定するために、配送業者と協力して、その情報を使用して Cloud Connector PSTN サイトを定義し、ユーザーを適切なサイトに割り当てる必要があります。 たとえば、PSTN サイトが拡張されたデータセンターで終了するトランクが、そのサイトのユーザーに割り当てられたすべての番号について、受信および送信ルーティングの両方を処理するように構成されていることを確認する必要があります。 
  
各 Cloud Connector アプライアンスは、複数の IP ゲートウェイ、IP Pbx、またはセッションボーダーコントローラー (sbc) に接続できます。 ゲートウェイと Pbx は、電話会社のトランク (PRI または SIP トランク) に接続されているため、クラウドコネクタアプライアンスは、着信および発信通話の PSTN トランクに論理的に接続されています。 Cloud Connector とオンプレミスの PSTN 接続を使用して、トランクおよび関連する電話番号をローカルの通信事業者から取得します。 企業が大規模な企業の場合は、複数の電話会社が存在することがあります。特に、事業者が複数の市区町村、州、または国を対象としている場合などが考えられます。 Carrier は電話番号を所有しているため、電話会社は緊急電話の処理を担当します。
  
Skype for Business Online は、サイト内のすべての Cloud Connector アプライアンスを均等に扱っており、同じサイト内の Cloud Connector アプライアンスに対して、発信通話をルーティングします。 サイト内の各 Cloud Connector は、PSTN トランクの同じセットに交差しています (完全にメッシュ化されています)。 各ユーザーは Cloud Connector PSTN サイトに関連付けられているため、そのユーザーからの発信通話 (通常または緊急) は、ユーザーが関連付けられている PSTN サイト内の Cloud Connector アプライアンスの1つに割り当てられます。 
  
Cloud Connector は、接続されている IP ゲートウェイ、IP-PBX、または直接 PSTN トランクに対して静的な通話ルーティングを行います。 Cloud Connector は、接続先 (最小コストルーティング) または発信元 (静的または動的な緊急通話) に基づいて、トランクへの動的ルーティングがまだできません。 通話は番号に関連付けられたトランクからのみ取得できるため、着信呼び出しは問題になりません。 ただし、発信通話は、サイト内の任意の Cloud Connector アプライアンス (およびその Cloud Connector アプライアンスに接続されている PSTN トランク) にアクセスできます。これにより、不要な長距離電話が発生する可能性があります。 さらに、クラウドコネクタの PSTN サイトが異なるエリアコードまたは通信事業者を使用してデータセンター間でストレッチされている場合、緊急通話は行われません。
  
## <a name="an-example"></a>例

次の例は、トランクを PSTN サイトにグループ化する方法と、ユーザーをサイトに割り当てる方法を示しています。 Contoso 社の場合、以下のことを想定します。
  
- 次の4人のユーザーがいます。 
    
  - Redmond ワシントン州のユーザー A (米国)
    
  - べレビュー WA のユーザー B (米国)
    
  - セントラリア WA のユーザー C (米国)
    
  - ポートランドまたは (米国) のユーザー D
    
- Carrier A は、電話番号とトランクを提供します。
    
  - Redmond (市外局番 425)
    
  - べレビュー (市外局番 425)
    
  - セントラリア (市外局番 360)
    
- Carrier B は電話番号とトランクを提供します。
    
  -  ポートランド (市外局番 503)
    
Redmond のユーザー A (データセンター A) とべレビュー (データセンター B) のユーザー B が相互に隣接していて、同じ市外局番 (425) に含まれているため、Carrier A は、べレビューのトランクにある Redmond のユーザー A から緊急電話を受けることができる必要があります。 
  
その結果、ユーザー A と B、およびべレビューとレドモンドの Cloud Connector トランクは、次の図に示すように、同じ Cloud Connector PSTN サイトに存在する可能性があります。 あるオフィスのユーザーからの緊急電話は、もう一方のトランクにルーティングすることができます。 ただし、これが機能することをキャリアに確認する必要があります。
  
![PSTN サイトをセットアップする方法](../../media/2659caa7-9c18-4d4f-9c7a-61d0e6a07dc3.png)
  
次の例も考慮してください。
  
- セントラリアのユーザー C。これは、電話会社 A によって番号が提供されており、他の電話会社からべレビューおよび Redmond 425 の市外局番に入っているユーザーとは異なる市外局番 (360) で提供されています。 
    
    そのため、通話が Carrier A から来たとしても、セントラリア area code 360 のキャリアの通話ルーティングソフトウェアは、べレビューエリアコード425のユーザー B からの着信緊急電話を拒否する可能性があります。 この場合、電話会社は、セントラリア PSTN サイト内の Cloud Connector とそれに関連付けられているトランクが距離と市外局番を越えて通話を処理できることを確認することが重要です。
    
- ポートランドのユーザー D は、Carrier B によって提供される番号とトランクを使用しているため、carrier A が所有する電話番号からの緊急電話が必要になる可能性が高くなります。そのため、ユーザー D および Cloud Connector アプライアンスと、ポートランドに関連付けられているトランクは、別の PSTN サイトに配置する必要があります。
    

