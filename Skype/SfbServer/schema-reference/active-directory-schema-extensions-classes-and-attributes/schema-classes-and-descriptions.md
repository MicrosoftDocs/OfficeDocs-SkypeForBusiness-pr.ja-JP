---
title: Skype for Business Server のスキーマクラスと説明
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
description: このセクションでは、Skype for Business Server で使用されるすべてのスキーマクラスについて説明します。
ms.openlocfilehash: 6d27ff464bcd4613f12180b8f263686c9cc04bcd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296596"
---
# <a name="schema-classes-and-descriptions-in-skype-for-business-server"></a>Skype for Business Server のスキーマクラスと説明
 
このセクションでは、Skype for Business Server で使用されるすべてのスキーマクラスについて説明します。 
  
## <a name="schema-classes-and-descriptions"></a>スキーマのクラスと説明

|**クラス**|**説明**|**コメント**|
|:-----|:-----|:-----|
|メール受信者  <br/> |Exchange ユニファイドメッセージング (UM) メール受信者。  <br/> |この補助クラスは Exchange UM と共有されます。  <br/> |
|Msrtcsip-userenabled true-ApplicationContacts  <br/> |このクラスは、複数のアプリケーションの連絡先のコンテナーであり、属性自体は含まれません。  <br/> |Microsoft Office Communications Server 2007 R2 の新製品。  <br/> |
|Msrtcsip-userenabled true-ApplicationServer  <br/> |このクラスは、ユニファイドコミュニケーションアプリケーションサービス (UCAS) のインスタンスのサービスコントロールポイントのエントリを保持します。  <br/> |Office Communications Server 2007 R2 の新製品。  <br/> |
|Msrtcsip-userenabled true-ApplicationServerService  <br/> |このクラスは、特定のプールからそのアプリケーションサービスへの関連付けを提供します。  <br/> |Communications Server 2007 R2 の新サービスです。  <br/> |
|Msrtcsip-userenabled true-ApplicationServerSettings  <br/> |この補助クラスと Msrtcsip-userenabled true-ApplicationServer は、アプリケーションサービスのインスタンスの設定を表す属性を保持します。  <br/> |Communications Server 2007 R2 の新サービスです。  <br/> |
|Msrtcsip-userenabled true-アーカイブ (廃止)  <br/> |この補助クラス to Msrtcsip-userenabled true-GlobalContainer は、アーカイブに関連するすべての設定を保持します。  <br/> |Lync Server 2010 では廃止されています。  <br/> |
|Msrtcsip-userenabled true-ArchivingServer (廃止)  <br/> |このクラスは、単一のインスタントメッセージングアーカイブサーバーを表します。 このクラスのインスタンスは、インスタントメッセージアーカイブサービスがインストールされているコンピューターなど、コンピューターがインスタントメッセージングアーカイブサーバーとしてアクティブ化されたときに作成されます。  <br/> |Lync Server 2010 では廃止されています。  <br/> |
|Msrtcsip-userenabled true-ConferenceDirectories  <br/> |このクラスは、会議ディレクトリの複数のインスタンスのコンテナーであり、属性自体は含まれません。  <br/> |Communications Server 2007 R2 の新サービスです。  <br/> |
|Msrtcsip-userenabled true-ConferenceDirectory  <br/> |このクラスには、特定の会議ディレクトリの設定を表す属性が保持しています。  <br/> |Communications Server 2007 R2 の新サービスです。  <br/> |
|Msrtcsip-userenabled true-ConnectionPoint  <br/> |[汎用サービス制御ポイント (SCP)] は、Skype for Business Server が実行されているサーバーとしてコンピューターを指定します。  <br/> |Lync 2010 の新方法。  <br/> |
|Msrtcsip-userenabled true-DefaultCWABank  <br/> |この補助クラスは、Skype for Business Web App bank の設定を保持します。  <br/> |Communications Server 2007 R2 の新サービスです。  <br/> |
|Msrtcsip-userenabled true-ドメイン  <br/> |このクラスは、SIP レジストラーの構成済みドメインを定義する属性を保持します。  <br/> |-  <br/> |
|Msrtcsip-userenabled true-EdgeProxy  <br/> |このクラスコンテナーは、単一のアクセスエッジサービスを表します。 アクセスエッジサービスは境界ネットワークに展開されているため、ユーザーは通常、境界ネットワークからの Active Directory ドメインサービスへのアクセスを許可しません。アクセスエッジサービスのインスタンスは、イントラネットの Active Directory ネットワークには参加していません。 そのため、アクセスプロキシは AD DS に自動的に登録されません。 管理者は、AD DS のアクセスエッジサービスの各インスタンスの存在を手動で構成する必要があります。  <br/> |-  <br/> |
|Msrtcsip-userenabled true-EnterpriseMCUSettings  <br/> |この補助クラスから Msrtcsip-userenabled true への属性は、会議サーバーの設定を表す属性を保持します。  <br/> |Microsoft Office Communications Server 2007 の新製品。  <br/> |
|Msrtcsip-userenabled true-EnterpriseMediationServerSettings  <br/> |この補助クラスの Msrtcsip-userenabled true-MediationServer は、仲介サーバーの設定を表す属性を保持します。  <br/> |Office Communications Server 2007 の新製品。  <br/> |
|Msrtcsip-userenabled true-EnterpriseServerSettings  <br/> |Msrtcsip-userenabled true への補助クラスは、SIP サーバーの設定を表す属性を保持します。  <br/> |-  <br/> |
|Msrtcsip-userenabled true-フェデレーション  <br/> |この補助クラス to Msrtcsip-userenabled true-GlobalContainer は、フェデレーションに関連するすべての設定を保持します。  <br/> |-  <br/> |
|Msrtcsip-userenabled true-GlobalContainer  <br/> |このクラスは、Skype for Business Server の展開全体で適用されるすべての設定を保持します。  <br/> |-  <br/> |
|Msrtcsip-userenabled true-GlobalUserPolicy (廃止)  <br/> |このクラスは、1つの Office Communications Server 会議ポリシーを表します。  <br/> |Lync Server 2010 では廃止されています。  <br/> |
|Msrtcsip-userenabled true-GlobalTopologySetting  <br/> |ローカルグローバルトポロジ設定オブジェクト。  <br/> |Lync Server 2010 の新サービスです。  <br/> |
|Msrtcsip-userenabled true-GlobalTopologySettings  <br/> |グローバルトポロジ設定オブジェクトを保持するコンテナー。  <br/> |Lync Server 2010 の新サービスです。  <br/> |
|Msrtcsip-userenabled true-LocalNormalization  <br/> |このクラスは、位置正規化規則のインスタンスを表すコンテナーです。  <br/> |-  <br/> |
|Msrtcsip-userenabled true-LocationContactMapping  <br/> |このクラスは、会議アテンダントアプリケーションによって作成され、地域ごとの会議電話番号の分類に使われる属性を保持します。  <br/> |Communications Server 2007 R2 の新サービスです。  <br/> |
|Msrtcsip-userenabled true-LocationContactMappings マッピング  <br/> |このクラスは、場所の連絡先マッピングの複数のインスタンスのコンテナーであり、属性自体は含まれません。  <br/> |Communications Server 2007 R2 の新サービスです。  <br/> |
|Msrtcsip-userenabled true-LocationProfile  <br/> |このクラスは、特定の位置情報プロファイルを表すコンテナーです。  <br/> |-  <br/> |
|Msrtcsip-userenabled true-LocationProfiles (廃止)  <br/> |このクラスは、複数の場所プロファイルのコンテナーであり、属性自体は含まれません。  <br/> |Lync Server 2010 では廃止されています。  <br/> |
|Msrtcsip-userenabled true-LocalNormalizations 廃止)  <br/> |このクラスは、複数のローカル正規化規則のコンテナーであり、属性自体は含まれません。  <br/> |Lync Server 2010 では廃止されています。  <br/> |
|Msrtcsip-userenabled true-MCU  <br/> |このクラスは、単一の会議サーバーを表します。  <br/> |Communications Server 2007 の新サービスです。  <br/> |
|Msrtcsip-userenabled true-MCUFactories  <br/> |このクラスは、複数の Msrtcsip-userenabled true を保持し、属性自体は持ちません。  <br/> |Communications Server 2007 の新サービスです。  <br/> |
|Msrtcsip-userenabled true-MCUFactory  <br/> |このクラスは、単一のメディアの種類の会議サーバーファクトリを表すコンテナーです。 このクラスのインスタンスは、この特定の種類とベンダーの最初の会議サーバーがアクティブ化されたときに作成されます。  <br/> |Communications Server 2007 の新サービスです。  <br/> |
|Msrtcsip-userenabled true-MCUFactoryService  <br/> |このクラスは、特定のプールから会議サーバーファクトリへの関連付けを提供します。  <br/> |Communications Server 2007 の新サービスです。  <br/> |
|Msrtcsip-userenabled true-MediationServer  <br/> |このクラスは、仲介サーバーのサービス制御ポイントのエントリを保持します。  <br/> |Communications Server 2007 の新サービスです。  <br/> |
|Msrtcsip-userenabled true-会議 (廃止)  <br/> |この補助クラスの Msrtcsip-userenabled true-GlobalContainer は、構成可能な会議の設定を示す属性を保持します。  <br/> |Lync Server 2010 では廃止されています。  <br/> |
|Msrtcsip-userenabled true  <br/> |グローバルモバイル設定を格納するコンテナー。  <br/> |-  <br/> |
|Msrtcsip-userenabled true-MonitoringServer  <br/> |このクラスは、単一の監視サーバーの設定を表す属性を保持します。  <br/> |Communications Server 2007 R2 の新サービスです。  <br/> |
|Msrtcsip-userenabled true-PhoneRoute (廃止)  <br/> |このクラスは、ゲートウェイまたはゲートウェイのセットへの最小料金のルートのインスタンスを示すコンテナーです。 この情報は、標準エディションを実行しているすべてのエンタープライズプールまたはサーバーが、発信した通話を、最もお得な方法で公衆交換電話網 (PSTN) にルーティングするために使用されます。  <br/> |Lync Server 2010 では廃止されています。  <br/> |
|Msrtcsip-userenabled true-PhoneRoutes (廃止)  <br/> |このクラスは、コストが最小の複数のルートのコンテナーであり、属性自体は含まれません。  <br/> |Lync Server 2010 では廃止されています。  <br/> |
|Msrtcsip-userenabled true-ポリシー (廃止)  <br/> |このクラスには、複数の Lync Server ポリシークラスが含まれており、属性自体は含まれていません。  <br/> |Lync Server 2010 では廃止されています。  <br/> |
|Msrtcsip-userenabled true プール  <br/> |このクラスは、1つの Skype for Business サーバープールを表します。  <br/> |-  <br/> |
|Msrtcsip-userenabled true-プール  <br/> |このクラスには、複数の Skype for Business サーバープールが含まれており、属性自体はありません。  <br/> |-  <br/> |
|Msrtcsip-userenabled true-PoolService  <br/> |このクラスは、プールのサービス制御ポイントサービス制御ポイントを表します。 プールでホストされているユーザーの Msrtcsip-userenabled true 属性ポイントは、このクラスのインスタンスになります。  <br/> |-  <br/> |
|Msrtcsip-userenabled true-プレゼンス  <br/> |グローバルプレゼンス設定を格納するコンテナー。  <br/> |-  <br/> |
|Msrtcsip-userenabled true-レジストラー  <br/> |この補助クラス to Msrtcsip-userenabled true-GlobalContainer は、SIP レジストラーサーバーによって管理されるユーザー設定を表す属性を保持します。  <br/> |-  <br/> |
|Msrtcsip-userenabled true-RouteUsage (廃止)  <br/> |このクラスは、電話ルートの使用状況のインスタンスを表すコンテナーです。 電話ルートの利用状況クラスは、属性フィールドと説明フィールドで構成されます。 属性フィールドには、使用の種類が定義されています。 [説明] フィールドでは、管理者が電話ルートでこの属性の使用を説明できます。  <br/> |Lync Server 2010 では廃止されています。  <br/> |
|Msrtcsip-userenabled true-RouteUsages (廃止)  <br/> |このクラスは、Msrtcsip-userenabled true-RouteUsage クラスの複数のインスタンスを保持します。属性自体はありません。  <br/> |Lync Server 2010 では廃止されています。  <br/> |
|Msrtcsip-userenabled true-検索  <br/> |この補助クラス to Msrtcsip-userenabled true-GlobalContainer は、検索結果の範囲を制限および制御する属性を保持します。  <br/> |-  <br/> |
|Msrtcsip-userenabled true-サーバー  <br/> |このクラスは、Skype for Business Server が実行されている1台のサーバーを表します。  <br/> |-  <br/> |
|Msrtcsip-userenabled true-サービス  <br/> |このクラスは、グローバル設定コンテナーと Msrtcsip-userenabled true オブジェクトを保持します。  <br/> |-  <br/> |
|Msrtcsip-userenabled true-TrustedMCU  <br/> |このクラスは、信頼できる会議サーバーの設定を表す属性を保持します。  <br/> |Communications Server 2007 の新サービスです。  <br/> |
|Msrtcsip-userenabled true-TrustedMCUs  <br/> |このクラスには、Msrtcsip-userenabled true の複数のインスタンスが含まれており、属性自体はありません。  <br/> |Communications Server 2007 の新サービスです。  <br/> |
|Msrtcsip-userenabled true-TrustedProxies  <br/> |このクラスは、複数の Msrtcsip-userenabled true プロキシクラスを保持し、属性自体は含まれません。  <br/> |Communications Server 2007 の新サービスです。  <br/> |
|Msrtcsip-userenabled true-TrustedProxy  <br/> |このクラスは、プロキシサーバーを実行しているサーバーを表すコンテナーです。 このクラスのインスタンスは、AD DS に参加しているコンピューターで新しいプロキシサーバーをアクティブ化するときに作成されます。  <br/> |Communications Server 2007 の新サービスです。  <br/> |
|Msrtcsip-userenabled true-TrustedServer  <br/> |このクラスは、信頼されたサーバーの設定を表す属性を保持します。  <br/> |-  <br/> |
|Msrtcsip-userenabled true-TrustedService  <br/> |このクラスは、グローバルルーティング可能なユーザーエージェント URI (GRUU) アドレスを使ってルーティング可能な、信頼されたサービスを表すコンテナーです。 このクラスのインスタンスは、Skype for Business Server によって信頼されている新しいサーバーがアクティブ化されたときに作成されます。 この信頼できるサーバーは Active Directory ドメインに参加している必要があります。  <br/> |Communications Server 2007 の新サービスです。  <br/> |
|Msrtcsip-userenabled true-TrustedServices  <br/> |このクラスは、複数の GRUU サーバーのコンテナーであり、属性自体は含まれていません。  <br/> |Communications Server 2007 の新サービスです。  <br/> |
|Msrtcsip-userenabled true-Trustedwebのサーバー  <br/> |このクラスは、信頼された web コンポーネントの設定を表す属性を保持します。  <br/> |Communications Server 2007 の新サービスです。  <br/> |
|Msrtcsip-userenabled true-Trustedwebservers サーバー  <br/> |このクラスは、Msrtcsip-userenabled true Webcomponentserver クラスの複数のインスタンスを保持します。属性自体はありません。  <br/> |Communications Server 2007 の新サービスです。  <br/> |
|Msrtcsip-userenabled true-UnifiedCommunications (廃止)  <br/> |この補助クラスの Msrtcsip-userenabled true-GlobalContainer は、統合された通信に関連する属性を保持します。  <br/> |Lync Server 2010 では廃止されています。  <br/> |
|Msrtcsip-userenabled true-Web コンポーネント  <br/> |このクラスは、インターネットインフォメーションサーバー (IIS) のサービスコントロールポイントサービス制御ポイントを保持します。 Web コンポーネントサーバーとしてサーバーを識別します。  <br/> |Communications Server 2007 の新サービスです。  <br/> |
|Msrtcsip-userenabled true-Webmessages サービス  <br/> |このクラスは、プールで使用される web コンポーネントと特定のプールとの関連付けを提供します。  <br/> |Communications Server 2007 の新サービスです。  <br/> |
|Msrtcsip-userenabled true-WebComponentSettings  <br/> |この補助クラスの Msrtcsip-userenabled true コンポーネントは、web コンポーネントの設定を表す属性を保持します。  <br/> |Communications Server 2007 の新サービスです。  <br/> |
   

