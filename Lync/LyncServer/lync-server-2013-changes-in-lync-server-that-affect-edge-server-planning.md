---
title: 'Lync server 2013: エッジサーバーの計画に影響する Lync Server の変更点'
description: 'Lync server 2013: エッジサーバーの計画に影響する Lync Server の変更点。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes in Lync Server 2013 that affect Edge Server planning
ms:assetid: 66305160-c9b8-4bc4-9f24-8ee8d9a294f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204965(v=OCS.15)
ms:contentKeyID: 48184378
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8660a281d858cf92a48d5eaed6d5caf3141b3817
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543753"
---
# <a name="changes-in-lync-server-2013-that-affect-edge-server-planning"></a>エッジサーバーの計画に影響する Lync Server 2013 の変更点

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-22_

Lync Server 2013 には、ユーザーの機能や通信方法を拡張する新機能が導入されています。 また、Lync Server 2013 では、組織で使用できるサービスをより適切に統合および拡張するための既存のサービスへの変更が導入されています。 Lync Server 2013 エッジサーバーサービスの計画と展開に影響する可能性のある変更の概要を次に示します。

<div>

## <a name="support-for-ipv6-addressing"></a>IPv6 アドレス指定のサポート

Lync Server 2013 は、すべてのエッジサーバーサービスの IPv6 アドレスをサポートしています。 Windows Server の構成を使用してインターフェイスの IPv6 アドレスを指定した場合は、トポロジビルダーの IP アドレス構成を使用して、エッジサーバー構成で IPv6 アドレスを使用できます。 さらに、XMPP (Extensible Messaging and Presence Protocol) も IPv6 をサポートします。 追加構成は必要ありません。 トポロジで IPv6 を構成すると、XMPP で IPv6 が使用されます (必要な場合)。

Lync Server 2013 で IPv6 をサポートするための追加の要件は、検出して IPv6 アドレスに解決する必要があるレコードのドメインネームシステムレコードを作成することです。 IPv6 DNS は、**AAAA** と定義され、"quad-A" と呼ばれるホスト レコードを使用します。 他のレコードの種類は、IPv4 の対応する種類と一致します。

</div>

<div>

## <a name="support-for-extensible-messaging-and-presence-protocol-xmpp-deployment"></a>XMPP (Extensible Messaging and Presence Protocol) 展開のサポート

エッジサーバーでは、完全に統合された XMPP プロキシ (エッジサーバーに展開される) と XMPP ゲートウェイ (フロントエンドサーバーに展開される) が導入されています。 オプションのコンポーネントとして XMPP フェデレーションを展開できます。 XMPP プロキシと XMPP ゲートウェイを追加して構成することで、Microsoft Lync 2013 ユーザーがインスタントメッセージング (IM) とプレゼンスの XMPP ベースのパートナーから連絡先を追加できるようにすることができます。

<div>


> [!NOTE]  
> 現時点では、エッジサーバーの XMPP サービスでは、Lync Server クライアントと XMPP ベースの連絡先の間で IM とプレゼンスのみが提供されています。 さらに、XMPP は 1 つのサイトでのみホストされます。



</div>

<div>


> [!IMPORTANT]  
> Lync Server 2013 の XMPP 機能は、Google Talk とのインスタント メッセージングのフェデレーションについては Microsoft によってテストとサポートが行われています。その他の XMPP システムについては、Lync Server 2013 とのフェデレーションのサポートや、展開またはトラブルシューティングの推奨事項に関して、サード パーティ ベンダーに問い合わせて確認してください。



</div>

</div>

<div>

## <a name="support-for-rolling-audiovideo-authentication-and-server-to-server-authentication-certificates"></a>音声ビデオ認証証明書およびサーバー間認証証明書のサポート

証明書は、音声ビデオ認証サービスのクライアントおよび他のコンシューマーに対して発行されるトークンを生成するため、およびサーバー間認証のために使用されます。音声ビデオ認証証明書の種類は AudioVideoAuthentication** であり、サーバー間認証証明書の種類は OAuthTokenIssuer です。**

音声ビデオ認証では、トークンを使用してポート割り当て要求が認証されます。このトークンは、最大 8 時間 (トークンの既定のライフタイム)、キャッシュされます。通常の操作では、これは、認証マテリアルを作成して音声ビデオ コンシューマーに配布するための非常に信頼できる方法です。ただし、証明書のライフタイムは有限であり、あらかじめ定義された日時に期限切れになります (日時は作成日と、証明書を作成した証明機関で採用されているポリシーに基づきます。この種類の証明書は、通常は 2 年間有効です）。証明書が期限切れになると、期限切れになった証明書によって作成され、コンシューマーによってキャッシュされたすべてのトークンは無効になります。期限切れの証明書によって作成されたトークンを使用しようとすると、メディア リレーの割り当てが失敗し、現在の音声ビデオ セッションが失敗します。クライアントが通常の音声ビデオ機能を再開するには、有効な証明書によって作成された新しいトークンを取得する必要があります。

サーバー間認証は、展開内のすべてのサーバーに対して要求され、適用されるグローバル証明書によって管理されます。 この証明書は、Lync Server 2013 のサーバーの認証と、Exchange 2013 および Microsoft SharePoint Server 2013 への認証を担当します。 サーバー間認証のしくみの詳細については、「 [Lync server 2013 でのサーバー間認証 (OAuth) およびパートナーアプリケーションの管理](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)」を参照してください。 音声ビデオ認証プロセスとサーバー間認証プロセスの非常に重要な相違点は、認証 (トークン) のライフタイムです。 音声ビデオ認証では、認証は 8 時間後に期限が切れます。 サーバー間認証のライフタイムは 24 時間です。 これらの証明書の種類に応じて、計画を立てる必要があります。

Lync Server 2013 の新機能は、現在の証明書の有効期限が切れる前に、代替の音声/ビデオ認証証明書およびサーバーからサーバーへの認証証明書をステージングできる機能です。 この操作の後、新しい証明書を使用して、新しいトークンと新しい認証要求が生成されます。 ただし、古い証明書は、現在のセッションと認証を検証するために保持されます。 これにより、トークンと証明書の期限切れによるエラーのほぼすべてを効果的に防止できます。 この機能とその構成方法の詳細については、「 [Lync Server 2013 でのステージング AV および OAuth 証明書」を](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)参照してください。

</div>

<div>

## <a name="reduced-reliance-on-cookie-based-affinity"></a>Cookie ベースのアフィニティに対する依存性の低減

以前のバージョンの Lync Server と Office Communications Server では、Web サービスが cookie ベースのアフィニティを使用して、クライアントと Web サービスのセッション状態が確実に維持されていました。 Lync Server 2013 Web サービスは、cookie ベースのアフィニティのほとんどの要件を排除する組み込みのアフィニティメカニズムを使用します。

<div>


> [!WARNING]  
> Microsoft Lync 2010 モバイルクライアントは依然として cookie ベースのアフィニティを使用する必要があります。すべてのクライアントを今後の Microsoft Lync Mobile クライアントに移行するまでは、cookie ベースのアフィニティを構成する必要があります (リリースされていない日付はまだ確定していません)。



</div>

Lync Server 2013 における cookie ベースのアフィニティの詳細については、「 [Lync server 2013 での外部ユーザーアクセスに必要なコンポーネント](lync-server-2013-components-required-for-external-user-access.md)」を参照してください。

</div>

<div>

## <a name="autodiscover-enhancements"></a>自動検出の拡張

Lync Server 2013 の自動検出機能を使用すると、クライアントは通信に使用できるその他の機能を検索できます。 自動検出は、Lync Server 2010 用の累積的な更新プログラム (2011 年11月、モビリティと Microsoft Lync 2010 Mobile) で初めて導入されました。 自動検出機能 (DNS レコード名 LyncDiscover および LyncDiscoverInternal にも含まれる) を使用すると、クライアントは、mobility services (Microsoft Lync 2010 モバイルクライアントの場合)、Microsoft Lync Web App、および Lync Web スケジューラを検索して使用したり、Microsoft Exchange Server と SharePoint Server との通信を使用したりすることができます。 自動検出は、インフラストラクチャおよび Lync Server 2013 サーバーのセットアップと展開の通常の一部としてインストールされます。 トポロジビルダーおよび Lync Server 展開ウィザードは、Lync Server 2010 の累積的な更新プログラム (11 月 2011) で必要だった構成タスクの大部分を排除します。

</div>

<div>

## <a name="services-for-mobile-clients"></a>モバイル クライアントに対するサービス

Lync server 2010 の累積的な更新プログラム (2011 年11月) で導入されました。 lync Mobile およびタブレットデバイスを使用して2013、サポートされている Apple iOS、Android、Windows Phone、または Nokia のモバイルデバイスを使用して、インスタントメッセージの送受信、連絡先の表示、プレゼンスの表示などのアクティビティを実行します。 また、クリックして会議に参加、勤務先から通話、同一番号接続、ボイス メール、不在着信など、いくつかのエンタープライズ VoIP 機能もサポートされます。

<div>


> [!NOTE]  
> モビリティ サービスは、フロントエンド サーバーに展開されたリバース プロキシと公開されたサービスを使用します。 エッジ サーバーの変更は必要ありません。 少なくとも、Lync Server アクセスエッジサービスを実行しているサーバーからの送信 SIP/TCP/5061from 必要です。



</div>

</div>

<div>

## <a name="director-role-is-optional"></a>ディレクターの役割はオプション

Lync Server 2013 トポロジ内のディレクターサーバーの役割は変更されていません。 これまでと同様、Web サービスをホストし、ユーザーからの要求を事前認証し、外部ユーザーをそれぞれのホーム プールに導きます。 推奨される役割からオプションの役割にディレクターを変更することで、Microsoft はディレクターの価値を減少することを意図したものではありません。 この目的は、機能を損なうことなく、サーバー数とその他のハードウェア要件 (ディレクターのハードウェアロードバランサーなど) を削減することです。 フロントエンドサーバーは、提供されるサービスに影響を与えることなく、ディレクターと同じジョブを実行できるため、ディレクターを展開することができます。 フロントエンドサーバーがディレクターの代わりに同じサービスを提供するという自信を持ってディレクターを除外することができます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

