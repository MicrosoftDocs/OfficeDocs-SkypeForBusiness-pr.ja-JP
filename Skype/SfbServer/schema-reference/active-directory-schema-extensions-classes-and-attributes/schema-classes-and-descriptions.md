---
title: スキーマのクラスおよび Skype のビジネス サーバー用の説明
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
description: このセクションでは、Skype でビジネスのサーバーが使用するすべてのスキーマのクラスについて説明します。
ms.openlocfilehash: 0bb34a93ec23df67d19026e82e29769e0aeb9ab2
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30926561"
---
# <a name="schema-classes-and-descriptions-in-skype-for-business-server"></a>スキーマのクラスおよび Skype のビジネス サーバー用の説明
 
このセクションでは、Skype でビジネスのサーバーが使用するすべてのスキーマのクラスについて説明します。 
  
## <a name="schema-classes-and-descriptions"></a>スキーマのクラスと説明

|**クラス**|**説明**|**コメント**|
|:-----|:-----|:-----|
|メール受信者  <br/> |電子メールの受信者を Exchange ユニファイド メッセージング (UM)。  <br/> |この補助型クラスは、Exchange UM で共有されています。  <br/> |
|msRTCSIP ApplicationContacts  <br/> |このクラスは複数のアプリケーションの連絡先のコンテナーであり、含まれていない任意の属性自体です。  <br/> |Microsoft Office 通信 Server 2007 R2 で新たに追加します。  <br/> |
|アプリケーション サーバーの msRTCSIP  <br/> |このクラスでは、統合コミュニケーション アプリケーション サービス (UCAS) のインスタンスのサービス コントロール ポイントのエントリを保持します。  <br/> |Office 通信 Server 2007 R2 で新たに追加します。  <br/> |
|msRTCSIP ApplicationServerService  <br/> |このクラスは、特定のプールからそのアプリケーション サービスへの関連付けを提供します。  <br/> |通信 Server 2007 R2 で新たに追加します。  <br/> |
|msRTCSIP ApplicationServerSettings  <br/> |この補助型クラスをアプリケーション サーバーの msRTCSIP には、設定を表す属性を保持しているアプリケーション サービスのインスタンスです。  <br/> |通信 Server 2007 R2 で新たに追加します。  <br/> |
|msRTCSIP アーカイブ (古い形式)  <br/> |この補助型クラスを msRTCSIP GlobalContainer には、アーカイブに関連するすべての設定を保持します。  <br/> |Lync Server 2010 で使用されなくなった。  <br/> |
|msRTCSIP ArchivingServer (古い形式)  <br/> |このクラスは、1 つのインスタント メッセージのアーカイブ サーバーを表します。 インスタント メッセージング アーカイブ サービス コンピューターにインストールされているなど、インスタント メッセージング アーカイブ サーバーとして、コンピューターがアクティブになるとこのクラスのインスタンスが作成されます。  <br/> |Lync Server 2010 で使用されなくなった。  <br/> |
|msRTCSIP ConferenceDirectories  <br/> |このクラスは、会議ディレクトリの複数のインスタンスのコンテナーであり、含まれていない任意の属性自体です。  <br/> |通信 Server 2007 R2 で新たに追加します。  <br/> |
|msRTCSIP ConferenceDirectory  <br/> |このクラスは、特定の会議ディレクトリの設定を表す属性を保持します。  <br/> |通信 Server 2007 R2 で新たに追加します。  <br/> |
|msRTCSIP ConnectionPoint  <br/> |汎用サービス コントロール ポイント ビジネス サーバーの Skype を実行するサーバー コンピューターを指定するには、(SCP)。  <br/> |Lync 2010 の新機能です。  <br/> |
|msRTCSIP DefaultCWABank  <br/> |この補助型クラスは、ビジネス Web アプリケーションの銀行のための Skype の設定を保持します。  <br/> |通信 Server 2007 R2 で新たに追加します。  <br/> |
|msRTCSIP ドメイン  <br/> |このクラスでは、SIP レジストラーの構成済みのドメインを定義する属性を保持します。  <br/> |-  <br/> |
|msRTCSIP EdgeProxy  <br/> |このクラスのコンテナーは、1 つのアクセス エッジ サービスを表します。 境界領域のネットワークに、アクセス エッジ サービスが展開されて、通常の顧客を境界ネットワークからの Active Directory ドメイン サービスのアクセス許可しないため、アクセス エッジ サービスのインスタンスは、イントラネットの Active Directory のネットワークには参加していません。 したがって、アクセス プロキシは、AD DS に自動的には登録されません。 管理者は、AD DS にアクセス エッジ サービスの各インスタンスの存在を手動で構成する必要があります。  <br/> |-  <br/> |
|msRTCSIP EnterpriseMCUSettings  <br/> |この補助クラス msRTCSIP MCU 会議サーバーの設定を表す属性を保持します。  <br/> |Microsoft Office Communications Server 2007 の新機能です。  <br/> |
|msRTCSIP EnterpriseMediationServerSettings  <br/> |この補助型クラスを msRTCSIP MediationServer には、仲介サーバーの設定を表す属性を保持します。  <br/> |Office Communications Server 2007 の新機能です。  <br/> |
|msRTCSIP EnterpriseServerSettings  <br/> |この補助型クラスを msRTCSIP サーバーには、SIP サーバーの設定を表す属性を保持します。  <br/> |-  <br/> |
|msRTCSIP フェデレーション  <br/> |この補助型クラスを msRTCSIP GlobalContainer には、フェデレーションに関連するすべての設定を保持します。  <br/> |-  <br/> |
|msRTCSIP GlobalContainer  <br/> |このクラスは、Skype ビジネス サーバーの展開の全体に適用されるすべての設定を保持します。  <br/> |-  <br/> |
|msRTCSIP GlobalUserPolicy (古い形式)  <br/> |このクラスは、1 つの Office Communications Server の会議ポリシーを表します。  <br/> |Lync Server 2010 で使用されなくなった。  <br/> |
|msRTCSIP GlobalTopologySetting  <br/> |ローカルのグローバル トポロジ設定オブジェクトです。  <br/> |Lync Server 2010 の新機能です。  <br/> |
|msRTCSIP GlobalTopologySettings  <br/> |グローバル トポロジ設定オブジェクトを保持するコンテナーです。  <br/> |Lync Server 2010 の新機能です。  <br/> |
|msRTCSIP LocalNormalization  <br/> |このクラスは、所在地の正規化ルールのインスタンスを表すコンテナーです。  <br/> |-  <br/> |
|msRTCSIP LocationContactMapping  <br/> |このクラスでは、会議アテンダント アプリケーションによって作成し、地域別会議の電話番号を分類するために使用する属性を保持しています。  <br/> |通信 Server 2007 R2 で新たに追加します。  <br/> |
|msRTCSIP LocationContactMappings  <br/> |このクラスでは、連絡先のマッピングの場所の複数のインスタンスのコンテナーし、が含まれていない任意の属性には自体。  <br/> |通信 Server 2007 R2 で新たに追加します。  <br/> |
|msRTCSIP LocationProfile  <br/> |このクラスは、特定の場所のプロファイルを表すコンテナーです。  <br/> |-  <br/> |
|msRTCSIP LocationProfiles (古い形式)  <br/> |このクラスは複数の場所のプロファイルのコンテナーであり、含まれていない任意の属性自体です。  <br/> |Lync Server 2010 で使用されなくなった。  <br/> |
|msRTCSIP LocalNormalizations (古い形式)  <br/> |このクラスは複数のローカル正規化ルールのコンテナーであり、含まれていない任意の属性自体です。  <br/> |Lync Server 2010 で使用されなくなった。  <br/> |
|msRTCSIP MCU  <br/> |このクラスは、1 つの会議サーバーを表します。  <br/> |Communications Server 2007 の新機能です。  <br/> |
|msRTCSIP MCUFactories  <br/> |このクラスは、msRTCSIP MCUFactory の複数のクラスを保持しがない属性自体。  <br/> |Communications Server 2007 の新機能です。  <br/> |
|msRTCSIP MCUFactory  <br/> |このクラスは、1 つのメディアの種類の会議サーバー ファクトリを表すコンテナーです。 この特定の種類およびベンダーの最初の会議サーバーがアクティブになったときは、このクラスのインスタンスが作成されます。  <br/> |Communications Server 2007 の新機能です。  <br/> |
|msRTCSIP MCUFactoryService  <br/> |このクラスは、特定のプールからその会議サーバー ファクトリへの関連付けを提供します。  <br/> |Communications Server 2007 の新機能です。  <br/> |
|msRTCSIP MediationServer  <br/> |このクラスでは、仲介サーバーのサービス コントロール ポイントのエントリを保持します。  <br/> |Communications Server 2007 の新機能です。  <br/> |
|msRTCSIP 会議 (古い形式)  <br/> |この補助型クラスを msRTCSIP GlobalContainer には、構成可能な会議の設定を表す属性を保持します。  <br/> |Lync Server 2010 で使用されなくなった。  <br/> |
|msRTCSIP 移動  <br/> |グローバル モビリティ設定を格納するコンテナーです。  <br/> |-  <br/> |
|msRTCSIP MonitoringServer  <br/> |このクラスは、1 つの監視サーバーの設定を表す属性を保持します。  <br/> |通信 Server 2007 R2 で新たに追加します。  <br/> |
|msRTCSIP PhoneRoute (古い形式)  <br/> |このクラスは、ゲートウェイまたはゲートウェイのセットへの最小コストのルートのインスタンスを表すコンテナーです。 この情報は、最もコスト効率の高い方法で公衆交換電話網 (PSTN) への発信呼び出しをルーティングするのには、すべてのエンタープライズ プールまたは Standard Edition を実行しているサーバーによって使用されます。  <br/> |Lync Server 2010 で使用されなくなった。  <br/> |
|msRTCSIP PhoneRoutes (古い形式)  <br/> |このクラスは複数の最低コストのルートのコンテナーであり、含まれていない任意の属性自体です。  <br/> |Lync Server 2010 で使用されなくなった。  <br/> |
|msRTCSIP-ポリシー (古い形式)  <br/> |このクラスは、複数の Lync Server ポリシーのクラスを保持しがない任意の属性自体。  <br/> |Lync Server 2010 で使用されなくなった。  <br/> |
|msRTCSIP プール  <br/> |このクラスは、ビジネスのサーバー プールの 1 つの Skype を表します。  <br/> |-  <br/> |
|msRTCSIP プール  <br/> |このクラスは、ビジネス サーバー プールに複数の Skype を保持しが、属性自体。  <br/> |-  <br/> |
|msRTCSIP PoolService  <br/> |このクラスでは、プールのサービス コントロールの pointservice コントロール ポイントを表します。 プールでホストされているユーザーが、msRTCSIP ・ PrimaryHomeServer にある属性のこのクラスのインスタンスをポイントします。  <br/> |-  <br/> |
|msRTCSIP プレゼンス  <br/> |グローバル プレゼンス設定を格納するコンテナーです。  <br/> |-  <br/> |
|msRTCSIP レジストラー  <br/> |この補助型クラスを msRTCSIP GlobalContainer には、SIP レジストラー サーバーが管理しているユーザーの設定を表す属性を保持します。  <br/> |-  <br/> |
|msRTCSIP RouteUsage (古い形式)  <br/> |このクラスは、電話ルート使用法のインスタンスを表すコンテナーです。 電話ルート使用法クラスは、属性フィールドと説明フィールドで構成されます。 属性フィールドは、使用法の種類を定義します。 [説明] フィールドでは、電話のルートでは、この属性の使用法を説明することができます。  <br/> |Lync Server 2010 で使用されなくなった。  <br/> |
|msRTCSIP RouteUsages (古い形式)  <br/> |このクラスは、msRTCSIP RouteUsage クラスの複数のインスタンスを保持しが、属性自体。  <br/> |Lync Server 2010 で使用されなくなった。  <br/> |
|msRTCSIP 検索  <br/> |この補助型クラスを msRTCSIP GlobalContainer には、制限および検索結果の範囲を制御する属性を保持します。  <br/> |-  <br/> |
|msRTCSIP サーバー  <br/> |このクラスでは、Skype を実行して、ビジネスのサーバーの 1 台のサーバーを表します。  <br/> |-  <br/> |
|msRTCSIP サービス  <br/> |このクラスは、グローバル設定コンテナーと msRTCSIP ドメインのオブジェクトを保持します。  <br/> |-  <br/> |
|msRTCSIP TrustedMCU  <br/> |このクラスでは、信頼されている会議サーバーの設定を表す属性を保持します。  <br/> |Communications Server 2007 の新機能です。  <br/> |
|msRTCSIP TrustedMCUs  <br/> |このクラスは、msRTCSIP TrustedMCU クラスの複数のインスタンスを保持しが、属性自体。  <br/> |Communications Server 2007 の新機能です。  <br/> |
|msRTCSIP TrustedProxies  <br/> |このクラスは、msRTCSIP TrustedProxy の複数のクラスを保持しが含まれていない任意の属性には自体。  <br/> |Communications Server 2007 の新機能です。  <br/> |
|msRTCSIP TrustedProxy  <br/> |このクラスは、プロキシ サーバーを実行しているサーバーを表すコンテナーです。 AD DS に参加しているコンピューターで新しいプロキシ サーバーをアクティブにするときは、このクラスのインスタンスが作成されます。  <br/> |Communications Server 2007 の新機能です。  <br/> |
|msRTCSIP の向こう側にあります。  <br/> |このクラスでは、信頼されたサーバーの設定を表す属性を保持します。  <br/> |-  <br/> |
|msRTCSIP TrustedService  <br/> |このクラスは、グローバルにルーティング可能なユーザー エージェント URI (GRUU) アドレスを使用してルーティング可能である信頼されたサービスを表すコンテナーです。 ビジネス サーバーの Skype によって信頼されている新しいサーバーがアクティブになったときは、このクラスのインスタンスが作成されます。 これは、信頼されたサーバーは、Active Directory ドメインに参加する必要があります。  <br/> |Communications Server 2007 の新機能です。  <br/> |
|msRTCSIP TrustedServices  <br/> |このクラスは複数の GRUU サーバーのコンテナーでありが含まれていない任意の属性には自体。  <br/> |Communications Server 2007 の新機能です。  <br/> |
|msRTCSIP TrustedWebComponentsServer  <br/> |このクラスでは、信頼済み web コンポーネントの設定を表す属性を保持します。  <br/> |Communications Server 2007 の新機能です。  <br/> |
|msRTCSIP TrustedWebComponentsServers  <br/> |このクラスは、msRTCSIP TrustedWebComponentServer クラスの複数のインスタンスを保持しが、属性自体。  <br/> |Communications Server 2007 の新機能です。  <br/> |
|msRTCSIP UnifiedCommunications (古い形式)  <br/> |この補助型クラスを msRTCSIP GlobalContainer には、ユニファイド コミュニケーションに関連する属性を保持します。  <br/> |Lync Server 2010 で使用されなくなった。  <br/> |
|web コンポーネントの msRTCSIP  <br/> |このクラスでは、インターネット インフォメーション サービス (IIS) のサービス コントロールの pointservice コントロール ポイントを保持します。 Web コンポーネント サーバーとしてサーバーを識別します。  <br/> |Communications Server 2007 の新機能です。  <br/> |
|msRTCSIP WebComponentsService  <br/> |このクラスは、特定のプールからプールを使用する web コンポーネントへの関連付けを提供します。  <br/> |Communications Server 2007 の新機能です。  <br/> |
|msRTCSIP WebComponentSettings  <br/> |この補助型クラスを web コンポーネントの msRTCSIP には、web コンポーネントの設定を表す属性を保持します。  <br/> |Communications Server 2007 の新機能です。  <br/> |
   

