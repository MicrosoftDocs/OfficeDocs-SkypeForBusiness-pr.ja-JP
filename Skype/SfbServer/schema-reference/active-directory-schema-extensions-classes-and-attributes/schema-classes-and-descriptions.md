---
title: スキーマ クラスと説明 (Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
description: このセクションでは、ユーザーが使用するスキーマ クラスについてSkype for Business Server。
ms.openlocfilehash: d7f05cd76074740e49f3972c97875e8993dd7b06
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743263"
---
# <a name="schema-classes-and-descriptions-in-skype-for-business-server"></a>スキーマ クラスと説明 (Skype for Business Server
 
このセクションでは、ユーザーが使用するスキーマ クラスについてSkype for Business Server。 
  
## <a name="schema-classes-and-descriptions"></a>スキーマのクラスと説明

|**クラス**|**説明**|**コメント**|
|:-----|:-----|:-----|
|Mail-Recipient  <br/> |Exchangeユニファイド メッセージング (UM) 電子メール受信者。  <br/> |この補助クラスは、UM のExchangeされます。  <br/> |
|msRTCSIP-ApplicationContacts  <br/> |複数のアプリケーションの連絡先のコンテナーです。属性そのものは含まれません。  <br/> |コミュニケーション サーバー 2007 R2 Microsoft Officeの新機能。  <br/> |
|msRTCSIP-ApplicationServer  <br/> |統合コミュニケーション アプリケーション サービス (UCAS) のインスタンスのサービス制御ポイントのエントリを保持するクラスです。  <br/> |コミュニケーション サーバー 2007 R2 Officeの新機能。  <br/> |
|msRTCSIP-ApplicationServerService  <br/> |このクラスは、特定のプールからアプリケーション サービスへの関連付けを提供します。  <br/> |コミュニケーション サーバー 2007 R2 の新機能。  <br/> |
|msRTCSIP-ApplicationServerSettings  <br/> |msRTCSIP-ApplicationServer に対するこの補助クラスは、Application サービスのインスタンスの設定を表す属性を保持します。  <br/> |コミュニケーション サーバー 2007 R2 の新機能。  <br/> |
|msRTCSIP-Archive (廃止)  <br/> |アーカイブに関連するすべての設定を保持する msRTCSIP-GlobalContainer の補助型クラスです。  <br/> |Lync Server 2010 では使用されていません。  <br/> |
|msRTCSIP-ArchivingServer (廃止)  <br/> |1 つのインスタント メッセージング アーカイブ サーバーを表すクラスです。 このクラスのインスタンスは、コンピューター (インスタント メッセージング アーカイブ サービスがインストールされたコンピューターなど) がインスタント メッセージング アーカイブ サーバーとしてアクティブ化されると作成されます。  <br/> |Lync Server 2010 では使用されていません。  <br/> |
|msRTCSIP-ConferenceDirectories  <br/> |会議ディレクトリの複数のインスタンスを格納するコンテナーです。属性そのものは含まれません。  <br/> |コミュニケーション サーバー 2007 R2 の新機能。  <br/> |
|msRTCSIP-ConferenceDirectory  <br/> |特定の会議ディレクトリの設定を表す属性を保持します。  <br/> |コミュニケーション サーバー 2007 R2 の新機能。  <br/> |
|msRTCSIP-ConnectionPoint  <br/> |汎用サービスコントロール ポイント (SCP) を使用して、コンピューターをサーバーとして指定し、Skype for Business Server。  <br/> |Lync 2010 の新機能。  <br/> |
|msRTCSIP-DefaultCWABank  <br/> |この補助クラスは、銀行の設定を保持Skype for Business Web アプリします。  <br/> |コミュニケーション サーバー 2007 R2 の新機能。  <br/> |
|msRTCSIP-Domain  <br/> |SIP レジストラーの構成済みドメインを定義する属性を保持するクラスです。  <br/> |-  <br/> |
|msRTCSIP-EdgeProxy  <br/> |このクラス コンテナーは、1 つの Access Edge サービスを表します。 Access Edge サービスは境界ネットワークに展開され、顧客は通常、境界ネットワークからの Active Directory ドメイン サービスアクセスを許可しないので、Access Edge サービスのインスタンスはイントラネットの Active Directory ネットワークに参加できません。 したがって、アクセス プロキシは、自動的には AD DS に登録されません。 管理者は、DS で Access Edge サービスの各インスタンスの存在を手動ADがあります。  <br/> |-  <br/> |
|msRTCSIP-EnterpriseMCUSettings  <br/> |電話会議サーバーの設定を表す属性を保持する msRTCSIP-MCU の補助型クラスです。  <br/> |コミュニケーション サーバー 2007 Microsoft Officeの新機能。  <br/> |
|msRTCSIP-EnterpriseMediationServerSettings  <br/> |仲介サーバーの設定を表す属性を保持する msRTCSIP-MediationServer の補助型クラスです。  <br/> |コミュニケーション サーバー 2007 Officeの新機能。  <br/> |
|msRTCSIP-EnterpriseServerSettings  <br/> |SIP サーバーの設定を表す属性を保持する msRTCSIP-Server の補助型クラスです。  <br/> |-  <br/> |
|msRTCSIP-Federation  <br/> |フェデレーションに関連するすべての設定を保持する msRTCSIP-GlobalContainer の補助型クラスです。  <br/> |-  <br/> |
|msRTCSIP-GlobalContainer  <br/> |このクラスは、展開全体で適用される設定Skype for Business Serverします。  <br/> |-  <br/> |
|msRTCSIP-GlobalUserPolicy (廃止)  <br/> |このクラスは、コミュニケーション サーバー会議ポリシー Officeを表します。  <br/> |Lync Server 2010 では使用されていません。  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |ローカルのグローバル トポロジ設定オブジェクトです。  <br/> |Lync Server 2010 の新機能。  <br/> |
|msRTCSIP-GlobalTopologySettings  <br/> |グローバル トポロジ設定オブジェクトを保持するコンテナーです。  <br/> |Lync Server 2010 の新機能。  <br/> |
|msRTCSIP-LocalNormalization  <br/> |ローカル正規化ルールのインスタンスを表すコンテナーです。  <br/> |-  <br/> |
|msRTCSIP-LocationContactMapping  <br/> |このクラスは、会議アテンダント アプリケーションによって作成され、電話会議の電話番号を地域別に分類するために使用される属性を保持します。  <br/> |コミュニケーション サーバー 2007 R2 の新機能。  <br/> |
|msRTCSIP-LocationContactMappings  <br/> |場所と連絡先のマッピングの複数のインスタンスを保持するコンテナーです。属性そのものは含まれません。  <br/> |コミュニケーション サーバー 2007 R2 の新機能。  <br/> |
|msRTCSIP-LocationProfile  <br/> |特定の場所のプロファイルを表すコンテナーです。  <br/> |-  <br/> |
|msRTCSIP-LocationProfiles (廃止)  <br/> |複数の場所のプロファイルのコンテナーです。属性そのものは含まれません。  <br/> |Lync Server 2010 では使用されていません。  <br/> |
|msRTCSIP-LocalNormalizations (廃止)  <br/> |複数のローカル正規化ルールのコンテナーです。属性そのものは含まれません。  <br/> |Lync Server 2010 では使用されていません。  <br/> |
|msRTCSIP-MCU  <br/> |1 つの電話会議サーバーを表すクラスです。  <br/> |コミュニケーション サーバー 2007 の新機能。  <br/> |
|msRTCSIP-MCUFactories  <br/> |複数の msRTCSIP-MCUFactory クラスを保持するクラスです。属性そのものは含まれません。  <br/> |コミュニケーション サーバー 2007 の新機能。  <br/> |
|msRTCSIP-MCUFactory  <br/> |1 つのメディアの種類の会議サーバー ファクトリを表すコンテナーです。 このクラスのインスタンスは、この特定の種類およびベンダーの最初の電話会議サーバーがアクティブ化されると作成されます。  <br/> |コミュニケーション サーバー 2007 の新機能。  <br/> |
|msRTCSIP-MCUFactoryService  <br/> |特定のプールからその会議サーバー ファクトリへの関連付けを提供するクラスです。  <br/> |コミュニケーション サーバー 2007 の新機能。  <br/> |
|msRTCSIP-MediationServer  <br/> |仲介サーバーのサービス制御ポイントのエントリを保持するクラスです。  <br/> |コミュニケーション サーバー 2007 の新機能。  <br/> |
|msRTCSIP-Meeting (廃止)  <br/> |構成可能な会議の設定を表す属性を保持する msRTCSIP-GlobalContainer の補助型クラスです。  <br/> |Lync Server 2010 では使用されていません。  <br/> |
|msRTCSIP-Mobility  <br/> |グローバル モビリティ設定を格納するコンテナーです。  <br/> |-  <br/> |
|msRTCSIP-MonitoringServer  <br/> |このクラスには、1 つの監視サーバーの設定を表す属性が保持されます。  <br/> |コミュニケーション サーバー 2007 R2 の新機能。  <br/> |
|msRTCSIP-PhoneRoute (廃止)  <br/> |ゲートウェイまたはゲートウェイのセットへの最小コスト経路のインスタンスを表すコンテナーです。 この情報は、すべてのエンタープライズ プールや Standard Edition サーバーによって、最もコストの小さい方法で、発信通話を公衆交換電話網 (PSTN) にルーティングするために使用されます。  <br/> |Lync Server 2010 では使用されていません。  <br/> |
|msRTCSIP-PhoneRoutes (廃止)  <br/> |複数の最小コスト経路のコンテナーです。属性そのものは含まれません。  <br/> |Lync Server 2010 では使用されていません。  <br/> |
|msRTCSIP-Policies (廃止)  <br/> |このクラスには、複数の Lync Server ポリシー クラスが保持され、属性自体はありません。  <br/> |Lync Server 2010 では使用されていません。  <br/> |
|msRTCSIP-Pool  <br/> |このクラスは、1 つのプールSkype for Business Serverします。  <br/> |-  <br/> |
|msRTCSIP-Pools  <br/> |このクラスには複数のSkype for Business Serverが保持され、属性自体はありません。  <br/> |-  <br/> |
|msRTCSIP-PoolService  <br/> |プールのサービス制御ポイントを表すクラスです。プールでホストされるユーザーは、msRTCSIP-PrimaryHomeServer 属性をこのクラスのインスタンスに設定します。  <br/> |-  <br/> |
|msRTCSIP-Presence  <br/> |グローバル プレゼンス設定を格納するコンテナーです。  <br/> |-  <br/> |
|msRTCSIP-Registrar  <br/> |SIP レジストラー サーバーによって管理されるユーザー設定を表す属性を保持する msRTCSIP-GlobalContainer の補助型クラスです。  <br/> |-  <br/> |
|msRTCSIP-RouteUsage (廃止)  <br/> |電話ルート使用法のインスタンスを表すコンテナーです。電話ルート使用法クラスは、属性フィールドと説明フィールドで構成されています。属性フィールドは使用法の種類を定義します。管理者は説明フィールドに、電話ルートでのその属性の使用法の説明を記入できます。  <br/> |Lync Server 2010 では使用されていません。  <br/> |
|msRTCSIP-RouteUsages (廃止)  <br/> |msRTCSIP-RouteUsage クラスの複数のインスタンスを保持するクラスです。属性そのものは含まれません。  <br/> |Lync Server 2010 では使用されていません。  <br/> |
|msRTCSIP-Search  <br/> |検索結果の範囲を制限および制御する属性を保持する msRTCSIP-GlobalContainer の補助型クラスです。  <br/> |-  <br/> |
|msRTCSIP-Server  <br/> |このクラスは、サーバーを実行している 1 つのSkype for Business Server。  <br/> |-  <br/> |
|msRTCSIP-Service  <br/> |グローバル設定コンテナーと msRTCSIP-Domain オブジェクトを保持するクラスです。  <br/> |-  <br/> |
|msRTCSIP-TrustedMCU  <br/> |1 つの信頼済み電話会議サーバーの設定を表す属性を保持するクラスです。  <br/> |コミュニケーション サーバー 2007 の新機能。  <br/> |
|msRTCSIP-TrustedMCUs  <br/> |msRTCSIP-TrustedMCU クラスの複数のインスタンスを保持するクラスです。属性そのものは含まれません。  <br/> |コミュニケーション サーバー 2007 の新機能。  <br/> |
|msRTCSIP-TrustedProxies  <br/> |複数の msRTCSIP-TrustedProxy クラスを保持するクラスです。属性そのものは含まれません。  <br/> |コミュニケーション サーバー 2007 の新機能。  <br/> |
|msRTCSIP-TrustedProxy  <br/> |プロキシ サーバーを実行しているサーバーを表すコンテナーです。 このクラスのインスタンスは、AD DS に参加しているコンピューターで新しいプロキシ サーバーがアクティブ化されると作成されます。  <br/> |コミュニケーション サーバー 2007 の新機能。  <br/> |
|msRTCSIP-TrustedServer  <br/> |1 つの信頼済みサーバーの設定を表す属性を保持するクラスです。  <br/> |-  <br/> |
|msRTCSIP-TrustedService  <br/> |グローバルにルーティング可能なユーザー エージェント (GRUU) アドレスを使用してルーティングできる信頼済みサービスを表すコンテナーです。 このクラスのインスタンスは、ユーザーが信頼する新しいサーバーがアクティブ化Skype for Business Serverされます。 この信頼済みサーバーは Active Directory ドメインに参加している必要があります。  <br/> |コミュニケーション サーバー 2007 の新機能。  <br/> |
|msRTCSIP-TrustedServices  <br/> |複数の GRUU サーバーのコンテナーです。属性そのものは含まれません。  <br/> |コミュニケーション サーバー 2007 の新機能。  <br/> |
|msRTCSIP-TrustedWebComponentsServer  <br/> |1 つの信頼済み Web コンポーネントの設定を表す属性を保持するクラスです。  <br/> |コミュニケーション サーバー 2007 の新機能。  <br/> |
|msRTCSIP-TrustedWebComponentsServers  <br/> |msRTCSIP-TrustedWebComponentServer クラスの複数のインスタンスを保持するクラスです。属性そのものは含まれません。  <br/> |コミュニケーション サーバー 2007 の新機能。  <br/> |
|msRTCSIP-UnifiedCommunications (廃止)  <br/> |統合コミュニケーションに関連する属性を保持する msRTCSIP-GlobalContainer の補助型クラスです。  <br/> |Lync Server 2010 では使用されていません。  <br/> |
|msRTCSIP-WebComponents  <br/> |インターネット インフォメーション サーバー (IIS) のサービス制御ポイントを保持するクラスです。サーバーを Web コンポーネント サーバーとして識別します。  <br/> |コミュニケーション サーバー 2007 の新機能。  <br/> |
|msRTCSIP-WebComponentsService  <br/> |特定のプールからそのプールが使用する Web コンポーネントへの関連付けを提供するクラスです。  <br/> |コミュニケーション サーバー 2007 の新機能。  <br/> |
|msRTCSIP-WebComponentSettings  <br/> |Web コンポーネントの設定を表す属性を保持する msRTCSIP-WebComponents の補助型クラスです。  <br/> |コミュニケーション サーバー 2007 の新機能。  <br/> |
   

