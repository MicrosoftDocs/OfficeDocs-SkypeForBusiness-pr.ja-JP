---
title: Lync Server 2013 でのスキーマのクラスと説明
TOCTitle: Lync Server 2013 でのスキーマのクラスと説明
ms:assetid: 7d43b920-ac37-40cc-adfe-be289bda6e9e
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398625(v=OCS.15)
ms:contentKeyID: 48272639
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのスキーマのクラスと説明

 

_**トピックの最終更新日:** 2015-03-09_

ここでは、Lync Server 2013 で使用されるすべてのスキーマ クラスについて説明します。

## スキーマのクラスと説明


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
<td><p>Exchange ユニファイド メッセージング (UM) 電子メール受信者。</p></td>
<td><p>Exchange UM と共有される補助型クラスです。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationContacts</p></td>
<td><p>複数のアプリケーションの連絡先のコンテナーです。属性そのものは含まれません。</p></td>
<td><p>Microsoft Office Communications Server 2007 R2 で新規。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationServer</p></td>
<td><p>統合コミュニケーション アプリケーション サービス (UCAS) のインスタンスのサービス制御ポイントのエントリを保持するクラスです。</p></td>
<td><p>Office Communications Server 2007 R2 で新規。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ApplicationServerService</p></td>
<td><p>特定のプールからそのアプリケーション サービスへの関連付けを提供するクラスです。</p></td>
<td><p>Communications Server 2007 R2 で新規。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ApplicationServerSettings</p></td>
<td><p>アプリケーション サービスのインスタンスの設定を表す属性を保持する msRTCSIP-ApplicationServer の補助型クラスです。</p></td>
<td><p>Communications Server 2007 R2 で新規。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Archive (廃止)</p></td>
<td><p>アーカイブに関連するすべての設定を保持する msRTCSIP-GlobalContainer の補助型クラスです。</p></td>
<td><p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ArchivingServer (廃止)</p></td>
<td><p>1 つのインスタント メッセージング アーカイブ サーバーを表すクラスです。 このクラスのインスタンスは、コンピューター (インスタント メッセージング アーカイブ サービスがインストールされたコンピューターなど) がインスタント メッセージング アーカイブ サーバーとしてアクティブ化されると作成されます。</p></td>
<td><p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ConferenceDirectories</p></td>
<td><p>会議ディレクトリの複数のインスタンスを格納するコンテナーです。属性そのものは含まれません。</p></td>
<td><p>Communications Server 2007 R2 で新規。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-ConferenceDirectory</p></td>
<td><p>特定の会議ディレクトリの設定を表す属性を保持します。</p></td>
<td><p>Communications Server 2007 R2 で新規。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-ConnectionPoint</p></td>
<td><p>コンピューターを Lync Server を実行しているサーバーとして指定する、汎用のサービス制御ポイント (SCP) です。</p></td>
<td><p>Lync 2010 で新規。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-DefaultCWABank</p></td>
<td><p>Microsoft Lync Web App バンクの設定を保持する補助型クラスです。</p></td>
<td><p>Communications Server 2007 R2 で新規。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Domain</p></td>
<td><p>SIP レジストラーの構成済みドメインを定義する属性を保持するクラスです。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EdgeProxy</p></td>
<td><p>1 つのアクセス エッジ サービスを表すクラス コンテナーです。アクセス エッジ サービスは境界ネットワークに展開され、通常は、境界ネットワークから Active Directory ドメイン サービス へのアクセスは許可されないため、アクセス エッジ サービスのインスタンスはイントラネットの Active Directory ネットワークに参加しません。 したがって、アクセス プロキシは、自動的には AD DS に登録されません。 管理者が手動で、アクセス エッジ サービスの各インスタンスの存在を AD DS で構成する必要があります。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnterpriseMCUSettings</p></td>
<td><p>電話会議サーバーの設定を表す属性を保持する msRTCSIP-MCU の補助型クラスです。</p></td>
<td><p>Microsoft Office Communications Server 2007 で新規。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-EnterpriseMediationServerSettings</p></td>
<td><p>仲介サーバーの設定を表す属性を保持する msRTCSIP-MediationServer の補助型クラスです。</p></td>
<td><p>Office Communications Server 2007 で新規。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-EnterpriseServerSettings</p></td>
<td><p>SIP サーバーの設定を表す属性を保持する msRTCSIP-Server の補助型クラスです。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Federation</p></td>
<td><p>フェデレーションに関連するすべての設定を保持する msRTCSIP-GlobalContainer の補助型クラスです。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalContainer</p></td>
<td><p>Lync Server の展開全体に適用されるすべての設定を保持するクラスです。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-GlobalUserPolicy (廃止)</p></td>
<td><p>1 つの Office Communications Server 会議ポリシーを表すクラスです。</p></td>
<td><p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-GlobalTopologySetting</p></td>
<td><p>ローカルのグローバル トポロジ設定オブジェクトです。</p></td>
<td><p>Lync Server 2010 で新規。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-GlobalTopologySettings</p></td>
<td><p>グローバル トポロジ設定オブジェクトを保持するコンテナーです。</p></td>
<td><p>Lync Server 2010 で新規。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocalNormalization</p></td>
<td><p>ローカル正規化ルールのインスタンスを表すコンテナーです。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocationContactMapping</p></td>
<td><p>会議アテンダント アプリケーションによって作成され、会議電話番号を地域別に分類するために使用される属性を保持するクラスです。</p></td>
<td><p>Communications Server 2007 R2 で新規。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationContactMappings</p></td>
<td><p>場所と連絡先のマッピングの複数のインスタンスを保持するコンテナーです。属性そのものは含まれません。</p></td>
<td><p>Communications Server 2007 R2 で新規。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocationProfile</p></td>
<td><p>特定の場所のプロファイルを表すコンテナーです。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-LocationProfiles (廃止)</p></td>
<td><p>複数の場所のプロファイルのコンテナーです。属性そのものは含まれません。</p></td>
<td><p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-LocalNormalizations (廃止)</p></td>
<td><p>複数のローカル正規化ルールのコンテナーです。属性そのものは含まれません。</p></td>
<td><p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCU</p></td>
<td><p>1 つの電話会議サーバーを表すクラスです。</p></td>
<td><p>Communications Server 2007 で新規。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactories</p></td>
<td><p>複数の msRTCSIP-MCUFactory クラスを保持するクラスです。属性そのものは含まれません。</p></td>
<td><p>Communications Server 2007 で新規。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MCUFactory</p></td>
<td><p>1 つのメディアの種類の会議サーバー ファクトリを表すコンテナーです。 このクラスのインスタンスは、この特定の種類およびベンダーの最初の電話会議サーバーがアクティブ化されると作成されます。</p></td>
<td><p>Communications Server 2007 で新規。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MCUFactoryService</p></td>
<td><p>特定のプールからその会議サーバー ファクトリへの関連付けを提供するクラスです。</p></td>
<td><p>Communications Server 2007 で新規。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-MediationServer</p></td>
<td><p>仲介サーバーのサービス制御ポイントのエントリを保持するクラスです。</p></td>
<td><p>Communications Server 2007 で新規。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Meeting (廃止)</p></td>
<td><p>構成可能な会議の設定を表す属性を保持する msRTCSIP-GlobalContainer の補助型クラスです。</p></td>
<td><p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Mobility</p></td>
<td><p>グローバル モビリティ設定を格納するコンテナーです。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-MonitoringServer</p></td>
<td><p>1 つの監視サーバーの設定を表す属性を保持するクラスです。</p></td>
<td><p>Communications Server 2007 R2 で新規。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-PhoneRoute (廃止)</p></td>
<td><p>ゲートウェイまたはゲートウェイのセットへの最小コスト経路のインスタンスを表すコンテナーです。 この情報は、すべてのエンタープライズ プールや Standard Edition サーバーによって、最もコストの小さい方法で、発信通話を公衆交換電話網 (PSTN) にルーティングするために使用されます。</p></td>
<td><p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PhoneRoutes (廃止)</p></td>
<td><p>複数の最小コスト経路のコンテナーです。属性そのものは含まれません。</p></td>
<td><p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Policies (廃止)</p></td>
<td><p>複数のLync Server ポリシー クラスを保持するクラスです。属性そのものは含まれません。</p></td>
<td><p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Pool</p></td>
<td><p>1 つの Lync Server プールを表すクラスです。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Pools</p></td>
<td><p>複数の Lync Server プールを保持するクラスです。属性そのものは含まれません。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-PoolService</p></td>
<td><p>プールのサービス制御ポイントを表すクラスです。プールでホストされるユーザーは、msRTCSIP-PrimaryHomeServer 属性をこのクラスのインスタンスに設定します。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Presence</p></td>
<td><p>グローバル プレゼンス設定を格納するコンテナーです。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Registrar</p></td>
<td><p>SIP レジストラー サーバーによって管理されるユーザー設定を表す属性を保持する msRTCSIP-GlobalContainer の補助型クラスです。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-RouteUsage (廃止)</p></td>
<td><p>電話ルート使用法のインスタンスを表すコンテナーです。電話ルート使用法クラスは、属性フィールドと説明フィールドで構成されています。属性フィールドは使用法の種類を定義します。管理者は説明フィールドに、電話ルートでのその属性の使用法の説明を記入できます。</p></td>
<td><p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-RouteUsages (廃止)</p></td>
<td><p>msRTCSIP-RouteUsage クラスの複数のインスタンスを保持するクラスです。属性そのものは含まれません。</p></td>
<td><p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Search</p></td>
<td><p>検索結果の範囲を制限および制御する属性を保持する msRTCSIP-GlobalContainer の補助型クラスです。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-Server</p></td>
<td><p>Lync Server を実行している 1 つのサーバーを表すクラスです。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-Service</p></td>
<td><p>グローバル設定コンテナーと msRTCSIP-Domain オブジェクトを保持するクラスです。</p></td>
<td><p>-</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedMCU</p></td>
<td><p>1 つの信頼済み電話会議サーバーの設定を表す属性を保持するクラスです。</p></td>
<td><p>Communications Server 2007 で新規。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedMCUs</p></td>
<td><p>msRTCSIP-TrustedMCU クラスの複数のインスタンスを保持するクラスです。属性そのものは含まれません。</p></td>
<td><p>Communications Server 2007 で新規。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedProxies</p></td>
<td><p>複数の msRTCSIP-TrustedProxy クラスを保持するクラスです。属性そのものは含まれません。</p></td>
<td><p>Communications Server 2007 で新規。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedProxy</p></td>
<td><p>プロキシ サーバーを実行しているサーバーを表すコンテナーです。 このクラスのインスタンスは、AD DS に参加しているコンピューターで新しいプロキシ サーバーがアクティブ化されると作成されます。</p></td>
<td><p>Communications Server 2007 で新規。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServer</p></td>
<td><p>1 つの信頼済みサーバーの設定を表す属性を保持するクラスです。</p></td>
<td><p>-</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedService</p></td>
<td><p>グローバルにルーティング可能なユーザー エージェント (GRUU) アドレスを使用してルーティングできる信頼済みサービスを表すコンテナーです。 このクラスのインスタンスは、Lync Server によって信頼されている新しいサーバーがアクティブ化されると作成されます。この信頼済みサーバーは Active Directory ドメインに参加している必要があります。</p></td>
<td><p>Communications Server 2007 で新規。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedServices</p></td>
<td><p>複数の GRUU サーバーのコンテナーです。属性そのものは含まれません。</p></td>
<td><p>Communications Server 2007 で新規。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-TrustedWebComponentsServer</p></td>
<td><p>1 つの信頼済み Web コンポーネントの設定を表す属性を保持するクラスです。</p></td>
<td><p>Communications Server 2007 で新規。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-TrustedWebComponentsServers</p></td>
<td><p>msRTCSIP-TrustedWebComponentServer クラスの複数のインスタンスを保持するクラスです。属性そのものは含まれません。</p></td>
<td><p>Communications Server 2007 で新規。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-UnifiedCommunications (廃止)</p></td>
<td><p>統合コミュニケーションに関連する属性を保持する msRTCSIP-GlobalContainer の補助型クラスです。</p></td>
<td><p>Lync Server 2010 で廃止。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponents</p></td>
<td><p>インターネット インフォメーション サーバー (IIS) のサービス制御ポイントを保持するクラスです。サーバーを Web コンポーネント サーバーとして識別します。</p></td>
<td><p>Communications Server 2007 で新規。</p></td>
</tr>
<tr class="even">
<td><p>msRTCSIP-WebComponentsService</p></td>
<td><p>特定のプールからそのプールが使用する Web コンポーネントへの関連付けを提供するクラスです。</p></td>
<td><p>Communications Server 2007 で新規。</p></td>
</tr>
<tr class="odd">
<td><p>msRTCSIP-WebComponentSettings</p></td>
<td><p>Web コンポーネントの設定を表す属性を保持する msRTCSIP-WebComponents の補助型クラスです。</p></td>
<td><p>Communications Server 2007 で新規。</p></td>
</tr>
</tbody>
</table>

