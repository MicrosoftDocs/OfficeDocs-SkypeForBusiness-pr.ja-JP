---
title: 'Lync Server 2013: スキーマのクラスと説明'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Schema classes and descriptions
ms:assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398625(v=OCS.15)
ms:contentKeyID: 48184612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e7dd3deff8a64b1dd153a9717d0ce2be2f28de8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182550"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="schema-classes-and-descriptions-in-lync-server-2013"></a>Lync Server 2013 のスキーマクラスと説明

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-30_

このセクションでは、Lync Server 2013 で使用されるすべてのスキーマクラスについて説明します。

<div>

## <a name="schema-classes-and-descriptions"></a>スキーマのクラスと説明


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>クラス</th>
<th>説明</th>
<th>コメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Mail-Recipient</p></td>
<td><p>Exchange ユニファイドメッセージング (UM) 電子メール受信者。</p></td>
<td><p>この補助クラスは、Exchange UM と共有されています。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationContacts</p></td>
<td><p>複数のアプリケーションの連絡先のコンテナーです。属性そのものは含まれません。</p></td>
<td><p>Microsoft Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationServer</p></td>
<td><p>統合コミュニケーション アプリケーション サービス (UCAS) のインスタンスのサービス制御ポイントのエントリを保持するクラスです。</p></td>
<td><p>Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationServerService</p></td>
<td><p>このクラスは、特定のプールからそのアプリケーションサービスへの関連付けを提供します。</p></td>
<td><p>Communications Server 2007 R2 の新サービス。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationServerSettings</p></td>
<td><p>この補助クラスから msRTCSIP への ApplicationServer は、アプリケーションサービスのインスタンスの設定を表す属性を保持します。</p></td>
<td><p>Communications Server 2007 R2 の新サービス。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Archive (廃止)</p></td>
<td><p>アーカイブに関連するすべての設定を保持する msRTCSIP-GlobalContainer の補助型クラスです。</p></td>
<td><p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchivingServer (廃止)</p></td>
<td><p>1 つのインスタント メッセージング アーカイブ サーバーを表すクラスです。 このクラスのインスタンスは、コンピューター (インスタント メッセージング アーカイブ サービスがインストールされたコンピューターなど) がインスタント メッセージング アーカイブ サーバーとしてアクティブ化されると作成されます。</p></td>
<td><p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Microsoft.rtc.management.writableconfig.settings.pstnconf.conferencedirectories</p></td>
<td><p>会議ディレクトリの複数のインスタンスを格納するコンテナーです。属性そのものは含まれません。</p></td>
<td><p>Communications Server 2007 R2 の新サービス。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectory</p></td>
<td><p>特定の会議ディレクトリの設定を表す属性を保持します。</p></td>
<td><p>Communications Server 2007 R2 の新サービス。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Msrtcsip-connectionpoint</p></td>
<td><p>Lync Server を実行しているサーバーとしてコンピューターを指定する汎用サービス制御ポイント (SCP)。</p></td>
<td><p>Lync 2010 の新。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultCWABank</p></td>
<td><p>この補助クラスは、Microsoft Lync Web App bank の設定を保持します。</p></td>
<td><p>Communications Server 2007 R2 の新サービス。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ドメイン</p></td>
<td><p>SIP レジストラーの構成済みドメインを定義する属性を保持するクラスです。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EdgeProxy</p></td>
<td><p>このクラスコンテナーは、1つのアクセスエッジサービスを表します。 アクセスエッジサービスは境界ネットワークに展開され、ユーザーは通常、境界ネットワークからの Active Directory ドメインサービスのアクセスを許可していないため、アクセスエッジサービスのインスタンスはイントラネットの Active Directory ネットワークには参加しません。 したがって、アクセス プロキシは、自動的には AD DS に登録されません。 管理者は、AD DS のアクセスエッジサービスの各インスタンスの存在を手動で構成する必要があります。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnterpriseMCUSettings</p></td>
<td><p>電話会議サーバーの設定を表す属性を保持する msRTCSIP-MCU の補助型クラスです。</p></td>
<td><p>Microsoft Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EnterpriseMediationServerSettings</p></td>
<td><p>仲介サーバーの設定を表す属性を保持する msRTCSIP-MediationServer の補助型クラスです。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnterpriseServerSettings</p></td>
<td><p>SIP サーバーの設定を表す属性を保持する msRTCSIP-Server の補助型クラスです。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP</p></td>
<td><p>フェデレーションに関連するすべての設定を保持する msRTCSIP-GlobalContainer の補助型クラスです。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalContainer</p></td>
<td><p>このクラスは、Lync Server 展開全体で適用されるすべての設定を保持します。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-GlobalUserPolicy (廃止)</p></td>
<td><p>このクラスは、1つの Office Communications Server 会議ポリシーを表します。</p></td>
<td><p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalTopologySetting</p></td>
<td><p>ローカルのグローバル トポロジ設定オブジェクトです。</p></td>
<td><p>Lync Server 2010 の新。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-GlobalTopologySettings</p></td>
<td><p>グローバル トポロジ設定オブジェクトを保持するコンテナーです。</p></td>
<td><p>Lync Server 2010 の新。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocalNormalization</p></td>
<td><p>ローカル正規化ルールのインスタンスを表すコンテナーです。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocationContactMapping</p></td>
<td><p>このクラスは、会議アテンダントアプリケーションによって作成され、電話会議の電話番号を地域別に分類するために使用される属性を保持します。</p></td>
<td><p>Communications Server 2007 R2 の新サービス。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationContactMappings</p></td>
<td><p>場所と連絡先のマッピングの複数のインスタンスを保持するコンテナーです。属性そのものは含まれません。</p></td>
<td><p>Communications Server 2007 R2 の新サービス。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocationProfile</p></td>
<td><p>特定の場所のプロファイルを表すコンテナーです。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationProfiles (廃止)</p></td>
<td><p>複数の場所のプロファイルのコンテナーです。属性そのものは含まれません。</p></td>
<td><p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalizations (廃止)</p></td>
<td><p>複数のローカル正規化ルールのコンテナーです。属性そのものは含まれません。</p></td>
<td><p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCU</p></td>
<td><p>1 つの電話会議サーバーを表すクラスです。</p></td>
<td><p>Communications Server 2007 の新情報。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactories</p></td>
<td><p>複数の msRTCSIP-MCUFactory クラスを保持するクラスです。属性そのものは含まれません。</p></td>
<td><p>Communications Server 2007 の新情報。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUFactory</p></td>
<td><p>1 つのメディアの種類の会議サーバー ファクトリを表すコンテナーです。 このクラスのインスタンスは、この特定の種類およびベンダーの最初の電話会議サーバーがアクティブ化されると作成されます。</p></td>
<td><p>Communications Server 2007 の新情報。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactoryService</p></td>
<td><p>特定のプールからその会議サーバー ファクトリへの関連付けを提供するクラスです。</p></td>
<td><p>Communications Server 2007 の新情報。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MediationServer</p></td>
<td><p>仲介サーバーのサービス制御ポイントのエントリを保持するクラスです。</p></td>
<td><p>Communications Server 2007 の新情報。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Meeting (廃止)</p></td>
<td><p>構成可能な会議の設定を表す属性を保持する msRTCSIP-GlobalContainer の補助型クラスです。</p></td>
<td><p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP</p></td>
<td><p>グローバル モビリティ設定を格納するコンテナーです。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MonitoringServer</p></td>
<td><p>このクラスは、単一の監視サーバーの設定を表す属性を保持します。</p></td>
<td><p>Communications Server 2007 R2 の新サービス。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PhoneRoute (廃止)</p></td>
<td><p>ゲートウェイまたはゲートウェイのセットへの最小コスト経路のインスタンスを表すコンテナーです。 この情報は、すべてのエンタープライズ プールや Standard Edition サーバーによって、最もコストの小さい方法で、発信通話を公衆交換電話網 (PSTN) にルーティングするために使用されます。</p></td>
<td><p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PhoneRoutes (廃止)</p></td>
<td><p>複数の最小コスト経路のコンテナーです。属性そのものは含まれません。</p></td>
<td><p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Policies (廃止)</p></td>
<td><p>複数の Lync Server ポリシークラスを保持するクラスです。属性そのものは含まれません。</p></td>
<td><p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP</p></td>
<td><p>このクラスは、1つの Lync Server プールを表します。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP</p></td>
<td><p>複数の Lync Server プールを保持するクラスです。属性そのものは含まれません。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolService</p></td>
<td><p>プールのサービス制御ポイントを表すクラスです。プールでホストされるユーザーは、msRTCSIP-PrimaryHomeServer 属性をこのクラスのインスタンスに設定します。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-プレゼンス</p></td>
<td><p>グローバル プレゼンス設定を格納するコンテナーです。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP</p></td>
<td><p>SIP レジストラー サーバーによって管理されるユーザー設定を表す属性を保持する msRTCSIP-GlobalContainer の補助型クラスです。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RouteUsage (廃止)</p></td>
<td><p>電話ルート使用法のインスタンスを表すコンテナーです。電話ルート使用法クラスは、属性フィールドと説明フィールドで構成されています。属性フィールドは使用法の種類を定義します。管理者は説明フィールドに、電話ルートでのその属性の使用法の説明を記入できます。</p></td>
<td><p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RouteUsages (廃止)</p></td>
<td><p>msRTCSIP-RouteUsage クラスの複数のインスタンスを保持するクラスです。属性そのものは含まれません。</p></td>
<td><p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-検索</p></td>
<td><p>検索結果の範囲を制限および制御する属性を保持する msRTCSIP-GlobalContainer の補助型クラスです。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-サーバー</p></td>
<td><p>このクラスは、Lync Server を実行している1台のサーバーを表します。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP</p></td>
<td><p>グローバル設定コンテナーと msRTCSIP-Domain オブジェクトを保持するクラスです。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedMCU</p></td>
<td><p>1 つの信頼済み電話会議サーバーの設定を表す属性を保持するクラスです。</p></td>
<td><p>Communications Server 2007 の新情報。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedMCUs</p></td>
<td><p>msRTCSIP-TrustedMCU クラスの複数のインスタンスを保持するクラスです。属性そのものは含まれません。</p></td>
<td><p>Communications Server 2007 の新情報。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedProxies</p></td>
<td><p>複数の msRTCSIP-TrustedProxy クラスを保持するクラスです。属性そのものは含まれません。</p></td>
<td><p>Communications Server 2007 の新情報。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedProxy</p></td>
<td><p>プロキシ サーバーを実行しているサーバーを表すコンテナーです。 このクラスのインスタンスは、AD DS に参加しているコンピューターで新しいプロキシ サーバーがアクティブ化されると作成されます。</p></td>
<td><p>Communications Server 2007 の新情報。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServer</p></td>
<td><p>1 つの信頼済みサーバーの設定を表す属性を保持するクラスです。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedService</p></td>
<td><p>グローバルにルーティング可能なユーザー エージェント (GRUU) アドレスを使用してルーティングできる信頼済みサービスを表すコンテナーです。 このクラスのインスタンスは、Lync Server によって信頼されている新しいサーバーがアクティブ化されたときに作成されます。 この信頼済みサーバーは Active Directory ドメインに参加している必要があります。</p></td>
<td><p>Communications Server 2007 の新情報。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServices</p></td>
<td><p>複数の GRUU サーバーのコンテナーです。属性そのものは含まれません。</p></td>
<td><p>Communications Server 2007 の新情報。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Trustedwebコンポーネントサーバー</p></td>
<td><p>1 つの信頼済み Web コンポーネントの設定を表す属性を保持するクラスです。</p></td>
<td><p>Communications Server 2007 の新情報。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Trustedwebコンポーネントサーバー</p></td>
<td><p>msRTCSIP-TrustedWebComponentServer クラスの複数のインスタンスを保持するクラスです。属性そのものは含まれません。</p></td>
<td><p>Communications Server 2007 の新情報。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UnifiedCommunications (廃止)</p></td>
<td><p>統合コミュニケーションに関連する属性を保持する msRTCSIP-GlobalContainer の補助型クラスです。</p></td>
<td><p>Lync Server 2010 では廃止されました。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponents</p></td>
<td><p>インターネット インフォメーション サーバー (IIS) のサービス制御ポイントを保持するクラスです。サーバーを Web コンポーネント サーバーとして識別します。</p></td>
<td><p>Communications Server 2007 の新情報。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Webコンポーネントサービス</p></td>
<td><p>特定のプールからそのプールが使用する Web コンポーネントへの関連付けを提供するクラスです。</p></td>
<td><p>Communications Server 2007 の新情報。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponentSettings</p></td>
<td><p>Web コンポーネントの設定を表す属性を保持する msRTCSIP-WebComponents の補助型クラスです。</p></td>
<td><p>Communications Server 2007 の新情報。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

