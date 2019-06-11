---
title: 'Lync Server 2013: スキーマのクラスと説明'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Schema classes and descriptions
ms:assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398625(v=OCS.15)
ms:contentKeyID: 48184612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 39bd0b3ff3c99e7de731f94eda0d3775ac4bd7cb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822140"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="schema-classes-and-descriptions-in-lync-server-2013"></a>Lync Server 2013 のスキーマクラスと説明

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-30_

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
<td><p>メール受信者</p></td>
<td><p>Exchange ユニファイドメッセージング (UM) メール受信者。</p></td>
<td><p>この補助クラスは Exchange UM と共有されます。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-ApplicationContacts</p></td>
<td><p>このクラスは、複数のアプリケーションの連絡先のコンテナーであり、属性自体は含まれません。</p></td>
<td><p>Microsoft Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-ApplicationServer</p></td>
<td><p>このクラスは、ユニファイドコミュニケーションアプリケーションサービス (UCAS) のインスタンスのサービスコントロールポイントのエントリを保持します。</p></td>
<td><p>Office Communications Server 2007 R2 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-ApplicationServerService</p></td>
<td><p>このクラスは、特定のプールからそのアプリケーションサービスへの関連付けを提供します。</p></td>
<td><p>Communications Server 2007 R2 の新サービスです。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-ApplicationServerSettings</p></td>
<td><p>この補助クラスと Msrtcsip-userenabled true-ApplicationServer は、アプリケーションサービスのインスタンスの設定を表す属性を保持します。</p></td>
<td><p>Communications Server 2007 R2 の新サービスです。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-アーカイブ (廃止)</p></td>
<td><p>この補助クラス to Msrtcsip-userenabled true-GlobalContainer は、アーカイブに関連するすべての設定を保持します。</p></td>
<td><p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-ArchivingServer (廃止)</p></td>
<td><p>このクラスは、単一のインスタントメッセージングアーカイブサーバーを表します。 このクラスのインスタンスは、インスタントメッセージアーカイブサービスがインストールされているコンピューターなど、コンピューターがインスタントメッセージングアーカイブサーバーとしてアクティブ化されたときに作成されます。</p></td>
<td><p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-ConferenceDirectories</p></td>
<td><p>このクラスは、会議ディレクトリの複数のインスタンスのコンテナーであり、属性自体は含まれません。</p></td>
<td><p>Communications Server 2007 R2 の新サービスです。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-ConferenceDirectory</p></td>
<td><p>このクラスには、特定の会議ディレクトリの設定を表す属性が保持しています。</p></td>
<td><p>Communications Server 2007 R2 の新サービスです。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-ConnectionPoint</p></td>
<td><p>[汎用サービス制御ポイント (SCP)] は、Lync Server を実行しているサーバーとしてコンピューターを指定します。</p></td>
<td><p>Lync 2010 の新方法。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-DefaultCWABank</p></td>
<td><p>この補助クラスは、Microsoft Lync Web App bank の設定を保持します。</p></td>
<td><p>Communications Server 2007 R2 の新サービスです。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-ドメイン</p></td>
<td><p>このクラスは、SIP レジストラーの構成済みドメインを定義する属性を保持します。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-EdgeProxy</p></td>
<td><p>このクラスコンテナーは、単一のアクセスエッジサービスを表します。 アクセスエッジサービスは境界ネットワークに展開されているため、ユーザーは通常、境界ネットワークからの Active Directory ドメインサービスへのアクセスを許可しません。アクセスエッジサービスのインスタンスは、イントラネットの Active Directory ネットワークには参加していません。 そのため、アクセスプロキシは AD DS に自動的に登録されません。 管理者は、AD DS のアクセスエッジサービスの各インスタンスの存在を手動で構成する必要があります。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-EnterpriseMCUSettings</p></td>
<td><p>この補助クラスから Msrtcsip-userenabled true への属性は、会議サーバーの設定を表す属性を保持します。</p></td>
<td><p>Microsoft Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-EnterpriseMediationServerSettings</p></td>
<td><p>この補助クラスの Msrtcsip-userenabled true-MediationServer は、仲介サーバーの設定を表す属性を保持します。</p></td>
<td><p>Office Communications Server 2007 の新製品。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-EnterpriseServerSettings</p></td>
<td><p>Msrtcsip-userenabled true への補助クラスは、SIP サーバーの設定を表す属性を保持します。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-フェデレーション</p></td>
<td><p>この補助クラス to Msrtcsip-userenabled true-GlobalContainer は、フェデレーションに関連するすべての設定を保持します。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-GlobalContainer</p></td>
<td><p>このクラスは、Lync Server の展開全体で適用されるすべての設定を保持します。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-GlobalUserPolicy (廃止)</p></td>
<td><p>このクラスは、1つの Office Communications Server 会議ポリシーを表します。</p></td>
<td><p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-GlobalTopologySetting</p></td>
<td><p>ローカルグローバルトポロジ設定オブジェクト。</p></td>
<td><p>Lync Server 2010 の新サービスです。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-GlobalTopologySettings</p></td>
<td><p>グローバルトポロジ設定オブジェクトを保持するコンテナー。</p></td>
<td><p>Lync Server 2010 の新サービスです。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-LocalNormalization</p></td>
<td><p>このクラスは、位置正規化規則のインスタンスを表すコンテナーです。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-LocationContactMapping</p></td>
<td><p>このクラスは、会議アテンダントアプリケーションによって作成され、地域ごとの会議電話番号の分類に使われる属性を保持します。</p></td>
<td><p>Communications Server 2007 R2 の新サービスです。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-LocationContactMappings マッピング</p></td>
<td><p>このクラスは、場所の連絡先マッピングの複数のインスタンスのコンテナーであり、属性自体は含まれません。</p></td>
<td><p>Communications Server 2007 R2 の新サービスです。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-LocationProfile</p></td>
<td><p>このクラスは、特定の位置情報プロファイルを表すコンテナーです。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-LocationProfiles (廃止)</p></td>
<td><p>このクラスは、複数の場所プロファイルのコンテナーであり、属性自体は含まれません。</p></td>
<td><p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-LocalNormalizations 廃止)</p></td>
<td><p>このクラスは、複数のローカル正規化規則のコンテナーであり、属性自体は含まれません。</p></td>
<td><p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-MCU</p></td>
<td><p>このクラスは、単一の会議サーバーを表します。</p></td>
<td><p>Communications Server 2007 の新サービスです。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-MCUFactories</p></td>
<td><p>このクラスは、複数の Msrtcsip-userenabled true を保持し、属性自体は持ちません。</p></td>
<td><p>Communications Server 2007 の新サービスです。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-MCUFactory</p></td>
<td><p>このクラスは、単一のメディアの種類の会議サーバーファクトリを表すコンテナーです。 このクラスのインスタンスは、この特定の種類とベンダーの最初の会議サーバーがアクティブ化されたときに作成されます。</p></td>
<td><p>Communications Server 2007 の新サービスです。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-MCUFactoryService</p></td>
<td><p>このクラスは、特定のプールから会議サーバーファクトリへの関連付けを提供します。</p></td>
<td><p>Communications Server 2007 の新サービスです。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-MediationServer</p></td>
<td><p>このクラスは、仲介サーバーのサービス制御ポイントのエントリを保持します。</p></td>
<td><p>Communications Server 2007 の新サービスです。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-会議 (廃止)</p></td>
<td><p>この補助クラスの Msrtcsip-userenabled true-GlobalContainer は、構成可能な会議の設定を示す属性を保持します。</p></td>
<td><p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true</p></td>
<td><p>グローバルモバイル設定を格納するコンテナー。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-MonitoringServer</p></td>
<td><p>このクラスは、単一の監視サーバーの設定を表す属性を保持します。</p></td>
<td><p>Communications Server 2007 R2 の新サービスです。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-PhoneRoute (廃止)</p></td>
<td><p>このクラスは、ゲートウェイまたはゲートウェイのセットへの最小料金のルートのインスタンスを示すコンテナーです。 この情報は、標準エディションを実行しているすべてのエンタープライズプールまたはサーバーが、発信した通話を、最もお得な方法で公衆交換電話網 (PSTN) にルーティングするために使用されます。</p></td>
<td><p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-PhoneRoutes (廃止)</p></td>
<td><p>このクラスは、コストが最小の複数のルートのコンテナーであり、属性自体は含まれません。</p></td>
<td><p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-ポリシー (廃止)</p></td>
<td><p>このクラスには、複数の Lync Server ポリシークラスが含まれており、属性自体は含まれていません。</p></td>
<td><p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true プール</p></td>
<td><p>このクラスは、単一の Lync サーバープールを表します。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-プール</p></td>
<td><p>このクラスは、複数の Lync Server プールを保持しており、属性自体を持ちません。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-PoolService</p></td>
<td><p>このクラスは、プールのサービス制御ポイントサービス制御ポイントを表します。 プールでホストされているユーザーの Msrtcsip-userenabled true 属性ポイントは、このクラスのインスタンスになります。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-プレゼンス</p></td>
<td><p>グローバルプレゼンス設定を格納するコンテナー。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-レジストラー</p></td>
<td><p>この補助クラス to Msrtcsip-userenabled true-GlobalContainer は、SIP レジストラーサーバーによって管理されるユーザー設定を表す属性を保持します。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-RouteUsage (廃止)</p></td>
<td><p>このクラスは、電話ルートの使用状況のインスタンスを表すコンテナーです。 電話ルートの利用状況クラスは、属性フィールドと説明フィールドで構成されます。 属性フィールドには、使用の種類が定義されています。 [説明] フィールドでは、管理者が電話ルートでこの属性の使用を説明できます。</p></td>
<td><p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-RouteUsages (廃止)</p></td>
<td><p>このクラスは、Msrtcsip-userenabled true-RouteUsage クラスの複数のインスタンスを保持します。属性自体はありません。</p></td>
<td><p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-検索</p></td>
<td><p>この補助クラス to Msrtcsip-userenabled true-GlobalContainer は、検索結果の範囲を制限および制御する属性を保持します。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-サーバー</p></td>
<td><p>このクラスは、Lync Server を実行している1台のサーバーを表します。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-サービス</p></td>
<td><p>このクラスは、グローバル設定コンテナーと Msrtcsip-userenabled true オブジェクトを保持します。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-TrustedMCU</p></td>
<td><p>このクラスは、信頼できる会議サーバーの設定を表す属性を保持します。</p></td>
<td><p>Communications Server 2007 の新サービスです。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-TrustedMCUs</p></td>
<td><p>このクラスには、Msrtcsip-userenabled true の複数のインスタンスが含まれており、属性自体はありません。</p></td>
<td><p>Communications Server 2007 の新サービスです。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-TrustedProxies</p></td>
<td><p>このクラスは、複数の Msrtcsip-userenabled true プロキシクラスを保持し、属性自体は含まれません。</p></td>
<td><p>Communications Server 2007 の新サービスです。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-TrustedProxy</p></td>
<td><p>このクラスは、プロキシサーバーを実行しているサーバーを表すコンテナーです。 このクラスのインスタンスは、AD DS に参加しているコンピューターで新しいプロキシサーバーをアクティブ化するときに作成されます。</p></td>
<td><p>Communications Server 2007 の新サービスです。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-TrustedServer</p></td>
<td><p>このクラスは、信頼されたサーバーの設定を表す属性を保持します。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-TrustedService</p></td>
<td><p>このクラスは、グローバルルーティング可能なユーザーエージェント URI (GRUU) アドレスを使ってルーティング可能な、信頼されたサービスを表すコンテナーです。 このクラスのインスタンスは、Lync Server によって信頼されている新しいサーバーがアクティブ化されたときに作成されます。 この信頼できるサーバーは Active Directory ドメインに参加している必要があります。</p></td>
<td><p>Communications Server 2007 の新サービスです。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-TrustedServices</p></td>
<td><p>このクラスは、複数の GRUU サーバーのコンテナーであり、属性自体は含まれていません。</p></td>
<td><p>Communications Server 2007 の新サービスです。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-Trustedwebのサーバー</p></td>
<td><p>このクラスは、信頼された web コンポーネントの設定を表す属性を保持します。</p></td>
<td><p>Communications Server 2007 の新サービスです。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-Trustedwebservers サーバー</p></td>
<td><p>このクラスは、Msrtcsip-userenabled true Webcomponentserver クラスの複数のインスタンスを保持します。属性自体はありません。</p></td>
<td><p>Communications Server 2007 の新サービスです。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-UnifiedCommunications (廃止)</p></td>
<td><p>この補助クラスの Msrtcsip-userenabled true-GlobalContainer は、統合された通信に関連する属性を保持します。</p></td>
<td><p>Lync Server 2010 では廃止されています。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-Web コンポーネント</p></td>
<td><p>このクラスは、インターネットインフォメーションサーバー (IIS) のサービスコントロールポイントサービス制御ポイントを保持します。 Web コンポーネントサーバーとしてサーバーを識別します。</p></td>
<td><p>Communications Server 2007 の新サービスです。</p></td>
</tr>
<tr class="even">
<td><p>Msrtcsip-userenabled true-Webmessages サービス</p></td>
<td><p>このクラスは、プールで使用される web コンポーネントと特定のプールとの関連付けを提供します。</p></td>
<td><p>Communications Server 2007 の新サービスです。</p></td>
</tr>
<tr class="odd">
<td><p>Msrtcsip-userenabled true-WebComponentSettings</p></td>
<td><p>この補助クラスの Msrtcsip-userenabled true コンポーネントは、web コンポーネントの設定を表す属性を保持します。</p></td>
<td><p>Communications Server 2007 の新サービスです。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

