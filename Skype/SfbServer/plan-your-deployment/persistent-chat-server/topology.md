---
title: 常設チャット サーバー トポロジを計画する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 5/17/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
description: '概要: このトピックでは、Skype for Business Server 2015 の常設チャット サーバーのコンポーネントとトポロジについて説明します。'
ms.openlocfilehash: 548fc5ebecb0f123172ee4733346c03cf44aba7f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825507"
---
# <a name="plan-persistent-chat-server-topology"></a>常設チャット サーバー トポロジを計画する
 
**概要:** このトピックでは、Skype for Business Server 2015 の常設チャット サーバーのコンポーネントとトポロジについて説明します。
  
常設チャット サーバーは、単一サーバー構成と複数サーバー構成の両方をサポートします。 常設チャット サーバーは、Skype for Business Server 2015 Enterprise Edition または Standard Edition サーバーにインストールできます。 

> [!NOTE] 
> 常設チャットは Skype for Business Server 2015 で使用できますが、Skype for Business Server 2019 ではサポートされなくなりました。 Teams でも同じ機能を使用できます。 詳細については、「Microsoft Teams のアップグレード [の開始」を参照してください](/microsoftteams/upgrade-start-here)。 常設チャットを使用する必要がある場合は、この機能を必要とするユーザーを Teams に移行するか、Skype for Business Server 2015 を引き続き使用するかのどちらかを選択できます。 
  
## <a name="persistent-chat-server-components"></a>常設チャット サーバー のコンポーネント

常設チャット サーバーは、次のコンポーネントで構成されます。
  
- 常設チャット サーバーを実行し、次のサービスを提供する 1 台以上のコンピューター:
    
  - Persistent Chat Service
    
  - コンプライアンスが有効な場合にオンになるコンプライアンス サービス
    
- チャット ルームのコンテンツ、ルーム、およびカテゴリが格納されている常設チャット コンテンツ データベースをホストする SQL Server のバック エンド データベースを実行する 1 つ以上のサーバー (ミラーリングを使用する場合は複数)。
    
    > [!NOTE]
    > バック エンド データベースには、作成されたカテゴリと常設チャット ルームに関する情報を含むチャット履歴データが格納されます。 
  
- コンプライアンスが有効な場合は、コンプライアンス イベントとコンプライアンスを目的としてチャット コンテンツが格納される常設チャット コンプライアンス データベースをホストするために SQL Server のバック エンド データベースを実行する 1 つ以上のサーバー (ミラーリングを使用する場合は複数)。
    
常設チャット サーバーのハードウェア要件およびソフトウェア要件の詳細については [、「Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) and [Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015](hardware-and-software-requirements.md)」を参照してください。 
  
## <a name="persistent-chat-server-topologies"></a>常設チャット サーバーのトポロジ

常設チャット サーバーは、単一サーバープールまたは複数サーバー プール、および単一プールまたは複数プール トポロジで展開できます。 常設チャット サーバーは、次のトポロジをサポートします。
  
-  フロントエンド サーバーに常設チャット サーバーが一緒に表示された Standard Edition サーバー
    
-  別のサーバーに常設チャット サーバーがある Standard Edition サーバー
    
-  別のサーバーに単一の常設チャット サーバーがある Enterprise Edition サーバー
    
-  別々のサーバーに複数の常設チャット サーバーがある Enterprise Edition サーバー
    
Standard Edition サーバーに常設チャット サーバーを展開することもできますが、パフォーマンスと規模に影響を及ぼすので、高可用性はオプションではありません。 したがって、主に概念実証と評価を目的として、常設チャットを Standard Edition サーバーに展開する方法をお勧めします。 
  
Skype for Business Server 2015 は、さまざまなコロケーション シナリオをサポートしています。1 台のサーバーで複数のコンポーネントを実行する (小規模な組織の場合)、個々のコンポーネントを異なるサーバーで実行する (スケーラビリティとパフォーマンスを必要とする大規模な組織の場合) ハードウェア コストを柔軟に節約できます。 コンポーネントを共に使用するかどうかを決定する前に、スケーラビリティ要因を考慮する必要があります。 Skype for Business Server 2015 Enterprise Edition サーバーと Standard Edition サーバーでは、同じ機能のシナリオが異なります。 
  
以下のセクションでは、トポロジについて詳しく説明します。このトポロジには、バック エンド データベース サーバーのコロケーション シナリオとオプションが含まれます。 すべてのサーバーの役割とデータベースのコロケーションの詳細については [、「Topology Basics for Skype for Business Server 2015」](../../plan-your-deployment/topology-basics/topology-basics.md)を参照してください。
  
### <a name="standard-edition-server-with-persistent-chat-server-collocated-on-the-front-end-server"></a>フロントエンド サーバーに常設チャット サーバーが一緒に表示された Standard Edition サーバー

Standard Edition では、フロント エンド サーバーに常設チャットを共に使用できます。 これは最も簡単で最も基本的な構成です。 物理リソース (CPU、メモリ、ディスク領域など) の観点から、既存のフロントエンド サーバーに十分な容量が備わっている必要があります。
  
さらに、常設チャット サーバーのバック エンド サーバーと常設チャット コンプライアンス データベース (有効な場合) をローカル SQL Server Express のバック エンド サーバーに共に作成することもできます。 また、専用インスタンスで個別のSQL Serverを使用する方法を選択できます。 
  
> [!IMPORTANT]
> 最初の常設チャット サーバーが Standard Edition フロントエンド サーバーと一緒に展開されている場合、常設チャット サーバー プールにサーバーを追加することはできません。 必要に応じて、後でサーバーを追加できるよう、最初のサーバーをスタンドアロン インスタンスとしてインストールしてください。 
  
### <a name="standard-edition-server-with-persistent-chat-server-installed-on-a-separate-server"></a>Standard Edition サーバーと常設チャット サーバーが別のサーバーにインストールされている

Standard Edition では、常設チャット サーバーをスタンドアロン インスタンスとしてインストールし、必要に応じて後でサーバーを追加できます。 
  
常設チャット サーバーのバック エンド サーバーと常設チャット コンプライアンス データベース (有効な場合) をローカル SQL Server Express のバック エンド サーバーに共に作成できます。 また、専用インスタンスで個別のSQL Serverを使用する方法を選択できます。 
  
### <a name="enterprise-edition-server-with-a-single-persistent-chat-server"></a>単一の常設チャット サーバーを使用する Enterprise Edition サーバー

Enterprise Edition では、常設チャット サーバーを別のコンピューターにインストールする必要があります。 つまり、常設チャット サーバーを Enterprise Edition フロントエンド サーバーに共に作成することはできません。 この展開には、常設チャット サーバーとコンプライアンス サービスを実行する別のサーバー (有効な場合) が必要です。
  
ただし、常設チャット サーバーの SQL Server データベースは、Enterprise Edition フロントエンド プールのバック エンド データベースに同一にできます。
  
> [!NOTE]
> HA DR の AlwaysOn 可用性SQL使用する予定の場合は、常設チャット サーバー データベースではサポートされていません。 
  
常設チャット データベースをバック エンド データベースと共に使用する場合は、一部またはすべてのデータベースに対して SQL Server の 1 つのインスタンスを使用するか、データベースごとに SQL Server の個別のインスタンスを使用できます。
  
> [!IMPORTANT]
> 常設チャット データベースをホストするサーバーは、他のデータベースをホストできます。 ただし、常設チャット データベースを他のデータベースと共に使用する場合は、数名を超えるユーザーのメッセージを保存する場合、常設チャット データベースに必要なディスク領域が非常に大きくなる可能性があります。 このため、常設チャット データベースをバック エンド データベースと共に使用はお勧めしません。 
  
次の図は、コンプライアンスが有効になっている単一の常設チャット サーバーのトポロジのすべてのコンポーネントを示しています (オプション)。
  
**単一サーバー トポロジ**

![常設チャット サーバー - 単一サーバー トポロジ](../../media/e1b39c28-8a4d-4c03-983b-4392889c2d14.png)
  
### <a name="enterprise-edition-server-with-multiple-persistent-chat-servers"></a>複数の常設チャット サーバーを含む Enterprise Edition サーバー

Enterprise Edition では、容量と信頼性を向上するために複数サーバー トポロジを展開できます。 複数サーバー トポロジは、複数のサーバーが常設チャット サーバーをホストする場合を除き、単一サーバー トポロジと同じであり、より高く拡張できます。 複数サーバー トポロジには、常設チャット サーバーを実行しているアクティブなコンピューターを最大 4 台まで含めできます (高可用性および障害復旧構成では最大 8 台まで使用できますが、アクティブにできるのは 4 台で、残りの 4 台はスタンバイ状態にできます)。 各サーバーは最大 20,000 人の同時ユーザーをサポートできます。合計 80,000 人の同時ユーザーが 4 台のサーバーを持つ常設チャット サーバー プールに接続しています。 常設チャット サーバーを実行している複数のコンピューターは、Skype for Business Server およびコンプライアンス サービスと同じ Active Directory ドメイン サービス ドメインに存在する必要があります。
  
次の図は、常設チャット サーバー、オプションのコンプライアンス サービス、および個別のコンプライアンス データベースを実行する複数のコンピューターを使用する複数サーバー トポロジのすべてのコンポーネントを示しています。
  
**複数サーバー トポロジ**

![常設チャット サーバー - 複数サーバー トポロジ](../../media/8fc20997-7acc-46ea-8dea-11239ffd9458.png)
  
複数サーバー トポロジでは、サーバー機能をプールできます。 サーバー プールでは、常設チャット サービスはデータの通信と共有を行います。 たとえば、最初に 1 つの常設チャット サービスに投稿されたチャット履歴は、システム内の任意の常設チャット サービスから使用できます。 1 つの常設チャット サービスを介してアップロードされたファイルには、任意の常設チャット サービスからアクセスできます。 ユーザーは、異なる常設チャット サーバー フロントエンド サーバーに接続して、互いに通信できます。 TCP 8011 の既定のポートは、サーバーをサーバー プールに接続し、常設チャット サービスが自身間または管理上の目的で通信するために使用します。
  
たとえば、4 台のサーバーで構成される常設チャット サーバーの展開では、80,000 ユーザーが同時に常設チャットにサインインできる場合、負荷はサーバーごとに 20,000 ユーザーに均等に分散されます。 1 つのサーバーが使用できなくなった場合、そのサーバーに接続しているユーザーは常設チャット サーバーにアクセスできません。 切断されたユーザーは、利用できなくなったサーバーが復元されるまでは、残りのサーバーに自動的に転送されます。 
  

