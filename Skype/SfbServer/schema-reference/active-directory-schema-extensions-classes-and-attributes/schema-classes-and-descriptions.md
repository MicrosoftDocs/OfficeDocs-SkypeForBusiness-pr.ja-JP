---
title: Skype for Business Server のスキーマ クラスと説明
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
description: このセクションでは、Skype for Business Server で使用されるスキーマ クラスについて説明します。
ms.openlocfilehash: 6c4b5d12baf85a1e9f168940fc889f6f18063616
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813557"
---
# <a name="schema-classes-and-descriptions-in-skype-for-business-server"></a>Skype for Business Server のスキーマ クラスと説明
 
このセクションでは、Skype for Business Server で使用されるスキーマ クラスについて説明します。 
  
## <a name="schema-classes-and-descriptions"></a>スキーマのクラスと説明

|**クラス**|**説明**|**コメント**|
|:-----|:-----|:-----|
|Mail-Recipient  <br/> |Exchange ユニファイド メッセージング (UM) 電子メール受信者。  <br/> |この補助クラスは Exchange UM と共有されます。  <br/> |
|msRTCSIP-ApplicationContacts  <br/> |複数のアプリケーションの連絡先のコンテナーです。属性そのものは含まれません。  <br/> |Communications Server 2007 R2 Microsoft Office新機能。  <br/> |
|msRTCSIP-ApplicationServer  <br/> |統合コミュニケーション アプリケーション サービス (UCAS) のインスタンスのサービス制御ポイントのエントリを保持するクラスです。  <br/> |Communications Server 2007 R2 Office新機能。  <br/> |
|msRTCSIP-ApplicationServerService  <br/> |このクラスは、特定のプールからアプリケーション サービスへの関連付けを提供します。  <br/> |Communications Server 2007 R2 の新機能。  <br/> |
|msRTCSIP-ApplicationServerSettings  <br/> |この msRTCSIP-ApplicationServer の補助クラスは、アプリケーション サービスのインスタンスの設定を表す属性を保持します。  <br/> |Communications Server 2007 R2 の新機能。  <br/> |
|msRTCSIP-Archive (廃止)  <br/> |アーカイブに関連するすべての設定を保持する msRTCSIP-GlobalContainer の補助型クラスです。  <br/> |Lync Server 2010 では使用されなくなりました。  <br/> |
|msRTCSIP-ArchivingServer (廃止)  <br/> |1 つのインスタント メッセージング アーカイブ サーバーを表すクラスです。 このクラスのインスタンスは、コンピューター (インスタント メッセージング アーカイブ サービスがインストールされたコンピューターなど) がインスタント メッセージング アーカイブ サーバーとしてアクティブ化されると作成されます。  <br/> |Lync Server 2010 では使用されなくなりました。  <br/> |
|msRTCSIP-ConferenceDirectories  <br/> |会議ディレクトリの複数のインスタンスを格納するコンテナーです。属性そのものは含まれません。  <br/> |Communications Server 2007 R2 の新機能。  <br/> |
|msRTCSIP-ConferenceDirectory  <br/> |特定の会議ディレクトリの設定を表す属性を保持します。  <br/> |Communications Server 2007 R2 の新機能。  <br/> |
|msRTCSIP-ConnectionPoint  <br/> |Skype for Business Server を実行しているサーバーとしてコンピューターを指定する汎用サービス コントロール ポイント (SCP)。  <br/> |Lync 2010 の新機能。  <br/> |
|msRTCSIP-DefaultCWABank  <br/> |この補助クラスは、Skype for Business Web App 銀行の設定を保持します。  <br/> |Communications Server 2007 R2 の新機能。  <br/> |
|msRTCSIP-Domain  <br/> |SIP レジストラーの構成済みドメインを定義する属性を保持するクラスです。  <br/> |-  <br/> |
|msRTCSIP-EdgeProxy  <br/> |このクラス コンテナーは、単一のアクセス エッジ サービスを表します。 アクセス エッジ サービスは境界ネットワークに展開され、通常、お客様は境界ネットワークからの Active Directory ドメイン サービスへのアクセスを許可しないので、アクセス エッジ サービスのインスタンスはイントラネットの Active Directory ネットワークに参加できません。 したがって、アクセス プロキシは、自動的には AD DS に登録されません。 管理者は、DS 内にアクセス エッジ サービスの各インスタンスが存在ADがあります。  <br/> |-  <br/> |
|msRTCSIP-EnterpriseMCUSettings  <br/> |電話会議サーバーの設定を表す属性を保持する msRTCSIP-MCU の補助型クラスです。  <br/> |Communications Server 2007 Microsoft Office新機能。  <br/> |
|msRTCSIP-EnterpriseMediationServerSettings  <br/> |仲介サーバーの設定を表す属性を保持する msRTCSIP-MediationServer の補助型クラスです。  <br/> |Communications Server 2007 Office新機能。  <br/> |
|msRTCSIP-EnterpriseServerSettings  <br/> |SIP サーバーの設定を表す属性を保持する msRTCSIP-Server の補助型クラスです。  <br/> |-  <br/> |
|msRTCSIP-Federation  <br/> |フェデレーションに関連するすべての設定を保持する msRTCSIP-GlobalContainer の補助型クラスです。  <br/> |-  <br/> |
|msRTCSIP-GlobalContainer  <br/> |このクラスには、Skype for Business Server の展開全体で適用される設定すべてが含まれるものがあります。  <br/> |-  <br/> |
|msRTCSIP-GlobalUserPolicy (廃止)  <br/> |このクラスは、Communications Server 会議ポリシー Officeを表します。  <br/> |Lync Server 2010 では使用されなくなりました。  <br/> |
|msRTCSIP-GlobalTopologySetting  <br/> |ローカルのグローバル トポロジ設定オブジェクトです。  <br/> |Lync Server 2010 の新機能。  <br/> |
|msRTCSIP-GlobalTopologySettings  <br/> |グローバル トポロジ設定オブジェクトを保持するコンテナーです。  <br/> |Lync Server 2010 の新機能。  <br/> |
|msRTCSIP-LocalNormalization  <br/> |ローカル正規化ルールのインスタンスを表すコンテナーです。  <br/> |-  <br/> |
|msRTCSIP-LocationContactMapping  <br/> |このクラスは、会議アテンダント アプリケーションによって作成され、電話会議の電話番号を地域別に分類するために使用される属性を保持します。  <br/> |Communications Server 2007 R2 の新機能。  <br/> |
|msRTCSIP-LocationContactMappings  <br/> |場所と連絡先のマッピングの複数のインスタンスを保持するコンテナーです。属性そのものは含まれません。  <br/> |Communications Server 2007 R2 の新機能。  <br/> |
|msRTCSIP-LocationProfile  <br/> |特定の場所のプロファイルを表すコンテナーです。  <br/> |-  <br/> |
|msRTCSIP-LocationProfiles (廃止)  <br/> |複数の場所のプロファイルのコンテナーです。属性そのものは含まれません。  <br/> |Lync Server 2010 では使用されなくなりました。  <br/> |
|msRTCSIP-LocalNormalizations (廃止)  <br/> |複数のローカル正規化ルールのコンテナーです。属性そのものは含まれません。  <br/> |Lync Server 2010 では使用されなくなりました。  <br/> |
|msRTCSIP-MCU  <br/> |1 つの電話会議サーバーを表すクラスです。  <br/> |Communications Server 2007 の新機能。  <br/> |
|msRTCSIP-MCUFactories  <br/> |複数の msRTCSIP-MCUFactory クラスを保持するクラスです。属性そのものは含まれません。  <br/> |Communications Server 2007 の新機能。  <br/> |
|msRTCSIP-MCUFactory  <br/> |1 つのメディアの種類の会議サーバー ファクトリを表すコンテナーです。 このクラスのインスタンスは、この特定の種類およびベンダーの最初の電話会議サーバーがアクティブ化されると作成されます。  <br/> |Communications Server 2007 の新機能。  <br/> |
|msRTCSIP-MCUFactoryService  <br/> |特定のプールからその会議サーバー ファクトリへの関連付けを提供するクラスです。  <br/> |Communications Server 2007 の新機能。  <br/> |
|msRTCSIP-MediationServer  <br/> |仲介サーバーのサービス制御ポイントのエントリを保持するクラスです。  <br/> |Communications Server 2007 の新機能。  <br/> |
|msRTCSIP-Meeting (廃止)  <br/> |構成可能な会議の設定を表す属性を保持する msRTCSIP-GlobalContainer の補助型クラスです。  <br/> |Lync Server 2010 では使用されなくなりました。  <br/> |
|msRTCSIP-Mobility  <br/> |グローバル モビリティ設定を格納するコンテナーです。  <br/> |-  <br/> |
|msRTCSIP-MonitoringServer  <br/> |このクラスは、1 つの監視サーバーの設定を表す属性を保持します。  <br/> |Communications Server 2007 R2 の新機能。  <br/> |
|msRTCSIP-PhoneRoute (廃止)  <br/> |ゲートウェイまたはゲートウェイのセットへの最小コスト経路のインスタンスを表すコンテナーです。 この情報は、すべてのエンタープライズ プールや Standard Edition サーバーによって、最もコストの小さい方法で、発信通話を公衆交換電話網 (PSTN) にルーティングするために使用されます。  <br/> |Lync Server 2010 では使用されなくなりました。  <br/> |
|msRTCSIP-PhoneRoutes (廃止)  <br/> |複数の最小コスト経路のコンテナーです。属性そのものは含まれません。  <br/> |Lync Server 2010 では使用されなくなりました。  <br/> |
|msRTCSIP-Policies (廃止)  <br/> |このクラスは、複数の Lync Server ポリシー クラスを保持し、属性自体を持つものはありません。  <br/> |Lync Server 2010 では使用されなくなりました。  <br/> |
|msRTCSIP-Pool  <br/> |このクラスは、単一の Skype for Business Server プールを表します。  <br/> |-  <br/> |
|msRTCSIP-Pools  <br/> |このクラスは、複数の Skype for Business Server プールを保持し、属性自体を持つものはありません。  <br/> |-  <br/> |
|msRTCSIP-PoolService  <br/> |プールのサービス制御ポイントを表すクラスです。プールでホストされるユーザーは、msRTCSIP-PrimaryHomeServer 属性をこのクラスのインスタンスに設定します。  <br/> |-  <br/> |
|msRTCSIP-Presence  <br/> |グローバル プレゼンス設定を格納するコンテナーです。  <br/> |-  <br/> |
|msRTCSIP-Registrar  <br/> |SIP レジストラー サーバーによって管理されるユーザー設定を表す属性を保持する msRTCSIP-GlobalContainer の補助型クラスです。  <br/> |-  <br/> |
|msRTCSIP-RouteUsage (廃止)  <br/> |電話ルート使用法のインスタンスを表すコンテナーです。電話ルート使用法クラスは、属性フィールドと説明フィールドで構成されています。属性フィールドは使用法の種類を定義します。管理者は説明フィールドに、電話ルートでのその属性の使用法の説明を記入できます。  <br/> |Lync Server 2010 では使用されなくなりました。  <br/> |
|msRTCSIP-RouteUsages (廃止)  <br/> |msRTCSIP-RouteUsage クラスの複数のインスタンスを保持するクラスです。属性そのものは含まれません。  <br/> |Lync Server 2010 では使用されなくなりました。  <br/> |
|msRTCSIP-Search  <br/> |検索結果の範囲を制限および制御する属性を保持する msRTCSIP-GlobalContainer の補助型クラスです。  <br/> |-  <br/> |
|msRTCSIP-Server  <br/> |このクラスは、Skype for Business Server を実行している 1 台のサーバーを表します。  <br/> |-  <br/> |
|msRTCSIP-Service  <br/> |グローバル設定コンテナーと msRTCSIP-Domain オブジェクトを保持するクラスです。  <br/> |-  <br/> |
|msRTCSIP-TrustedMCU  <br/> |1 つの信頼済み電話会議サーバーの設定を表す属性を保持するクラスです。  <br/> |Communications Server 2007 の新機能。  <br/> |
|msRTCSIP-TrustedMCUs  <br/> |msRTCSIP-TrustedMCU クラスの複数のインスタンスを保持するクラスです。属性そのものは含まれません。  <br/> |Communications Server 2007 の新機能。  <br/> |
|msRTCSIP-TrustedProxies  <br/> |複数の msRTCSIP-TrustedProxy クラスを保持するクラスです。属性そのものは含まれません。  <br/> |Communications Server 2007 の新機能。  <br/> |
|msRTCSIP-TrustedProxy  <br/> |プロキシ サーバーを実行しているサーバーを表すコンテナーです。 このクラスのインスタンスは、AD DS に参加しているコンピューターで新しいプロキシ サーバーがアクティブ化されると作成されます。  <br/> |Communications Server 2007 の新機能。  <br/> |
|msRTCSIP-TrustedServer  <br/> |1 つの信頼済みサーバーの設定を表す属性を保持するクラスです。  <br/> |-  <br/> |
|msRTCSIP-TrustedService  <br/> |グローバルにルーティング可能なユーザー エージェント (GRUU) アドレスを使用してルーティングできる信頼済みサービスを表すコンテナーです。 このクラスのインスタンスは、Skype for Business Server によって信頼されている新しいサーバーがアクティブ化されると作成されます。 この信頼済みサーバーは Active Directory ドメインに参加している必要があります。  <br/> |Communications Server 2007 の新機能。  <br/> |
|msRTCSIP-TrustedServices  <br/> |複数の GRUU サーバーのコンテナーです。属性そのものは含まれません。  <br/> |Communications Server 2007 の新機能。  <br/> |
|msRTCSIP-TrustedWebComponentsServer  <br/> |1 つの信頼済み Web コンポーネントの設定を表す属性を保持するクラスです。  <br/> |Communications Server 2007 の新機能。  <br/> |
|msRTCSIP-TrustedWebComponentsServers  <br/> |msRTCSIP-TrustedWebComponentServer クラスの複数のインスタンスを保持するクラスです。属性そのものは含まれません。  <br/> |Communications Server 2007 の新機能。  <br/> |
|msRTCSIP-UnifiedCommunications (廃止)  <br/> |統合コミュニケーションに関連する属性を保持する msRTCSIP-GlobalContainer の補助型クラスです。  <br/> |Lync Server 2010 では使用されなくなりました。  <br/> |
|msRTCSIP-WebComponents  <br/> |インターネット インフォメーション サーバー (IIS) のサービス制御ポイントを保持するクラスです。サーバーを Web コンポーネント サーバーとして識別します。  <br/> |Communications Server 2007 の新機能。  <br/> |
|msRTCSIP-WebComponentsService  <br/> |特定のプールからそのプールが使用する Web コンポーネントへの関連付けを提供するクラスです。  <br/> |Communications Server 2007 の新機能。  <br/> |
|msRTCSIP-WebComponentSettings  <br/> |Web コンポーネントの設定を表す属性を保持する msRTCSIP-WebComponents の補助型クラスです。  <br/> |Communications Server 2007 の新機能。  <br/> |
   

