---
title: 'Lync Server 2013: エッジ サーバーの計画に影響する Lync Server 2013 での変更点'
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
ms.openlocfilehash: 73eda15acbce7eb4b47a0a52602776e8fc830b0e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730147"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-in-lync-server-2013-that-affect-edge-server-planning"></a>エッジ サーバーの計画に影響する Lync Server 2013 での変更点

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-22_

Lync Server 2013 には、ユーザーの機能と通信方法を拡張する新機能が導入されています。 また、Lync Server 2013 では、組織で利用できるサービスをより適切に統合および拡張するために、既存のサービスへの変更が導入されています。 以下は、Lync Server 2013 Edge Server サービスの計画と展開に影響を与える可能性のある変更内容をまとめたものです。

<div>

## <a name="support-for-ipv6-addressing"></a>IPv6 アドレス指定のサポート

Lync Server 2013 は、すべての Edge Server サービスの IPv6 アドレス指定をサポートしています。 Windows Server の構成を通じてインターフェイスの IPv6 アドレスを指定している場合は、トポロジビルダーの IP アドレス構成を使用して、エッジサーバー構成の IPv6 アドレスを使うことができます。 さらに、拡張メッセージングとプレゼンスプロトコル (XMPP) は IPv6 をサポートしています。 追加の構成は必要ありません。 IPv6 がトポロジで構成されている場合、XMPP は IPv6 を使用します (必要な場合)。

Lync Server 2013 で IPv6 をサポートするための追加の要件として、IPv6 アドレスを検出し、解決する必要があるレコードのドメインネームシステムレコードを作成します。 IPv6 DNS は、 **AAAA**と呼ばれるホストレコードと "クワッド-A" を使用します。 その他の種類のレコードは、IPv4 に対応しています。

</div>

<div>

## <a name="support-for-extensible-messaging-and-presence-protocol-xmpp-deployment"></a>拡張メッセージングとプレゼンスプロトコル (XMPP) 展開のサポート

エッジサーバーでは、完全に統合された XMPP プロキシ (エッジサーバーに展開されている) と XMPP ゲートウェイ (フロントエンドサーバーに展開されている) が導入されています。 XMPP フェデレーションは、オプションのコンポーネントとして展開できます。 XMPP プロキシと XMPP ゲートウェイを追加して構成することにより、Microsoft Lync 2013 ユーザーは、インスタントメッセージング (IM) とプレゼンスのために、XMPP ベースのパートナーから連絡先を追加できるようになります。

<div>


> [!NOTE]  
> 現時点では、Edge Server の XMPP サービスは、Lync Server クライアントと XMPP ベースの連絡先との間で IM とプレゼンスを提供します。 さらに、XMPP は1つのサイトでのみホストされます。



</div>

<div>


> [!IMPORTANT]  
> Lync Server 2013 の XMPP 機能は、Google Talk とのインスタント メッセージングのフェデレーションについては Microsoft によってテストとサポートが行われています。その他の XMPP システムについては、Lync Server 2013 とのフェデレーションのサポートや、展開またはトラブルシューティングの推奨事項に関して、サード パーティ ベンダーに問い合わせて確認してください。



</div>

</div>

<div>

## <a name="support-for-rolling-audiovideo-authentication-and-server-to-server-authentication-certificates"></a>ローリングオーディオ/ビデオ認証とサーバー間認証証明書のサポート

証明書は、A/V 認証サービスのクライアントおよび他のコンシューマーに対して発行されたトークンを生成するために使用され、サーバー間の認証に使われます。 音声/ビデオ認証証明書は種類が*Audiovideoauthentication*であり、サーバー間認証証明書は*Oauthtokenissuer*型です。

音声/ビデオ認証の場合、トークンはポート割り当て要求を認証するために使用され、トークンは最大8時間 (トークンの既定の有効期間) キャッシュされます。 通常の操作では、このメソッドを使うと、認証資料を作成し、A/V コンシューマーに配布することができます。 ただし、証明書には有効期限があり、事前定義された日付と時刻で有効期限が切れています (作成日と、証明書を作成した証明機関によって適用されるポリシー (通常は、この種類の証明書の場合は2年間)。 証明書の有効期限が切れると、有効期限が切れた証明書によって作成され、コンシューマーによってキャッシュされたトークンは有効になりません。 有効期限が切れた証明書で作成されたトークンを使用しようとすると、メディアリレーの割り当てが失敗し、現在のオーディオ/ビデオセッションは失敗します。 クライアントは、通常の音声とビデオの機能を再開するために、有効な証明書によって作成された新しいトークンを取得する必要があります。

サーバー間認証は、展開されているすべてのサーバーに要求されて適用されるグローバル証明書によって管理されます。 この証明書は、Lync Server 2013 のサーバーの認証と、Exchange 2013 および Microsoft SharePoint Server 2013 の認証に責任を負います。 サーバー間認証のしくみの詳細については、「 [Lync server 2013 でサーバー間認証 (OAuth) とパートナーアプリケーションを管理](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)する」を参照してください。 音声/ビデオ認証プロセスとサーバー間の認証プロセスの間の重要な違いの1つは、認証 (トークン) の有効期間です。 音声/ビデオ認証の場合、認証は8時間後に期限切れとなります。 サーバー間認証には、24時間の有効期限があります。 各証明書の種類に応じて計画する必要があります。

Lync Server 2013 の新機能として、現在の証明書の有効期限が切れる前に、交換用のオーディオ/ビデオ認証証明書とサーバー認証証明書をステージすることができます。 新しい証明書を使って、新しいトークンを生成したり、新しい認証要求を生成したりします。 ただし、現在のセッションと認証を確認するための古い証明書は保持されます。 これにより、トークンと証明書の有効期限が切れたときに発生したほぼすべての障害を効果的に回避することができます。 この機能と構成方法の詳細については、「 [Lync Server 2013 でのステージング AV と OAuth 証明書の使用](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)」を参照してください。

</div>

<div>

## <a name="reduced-reliance-on-cookie-based-affinity"></a>Cookie ベースのアフィニティへの依存度の低下

以前のバージョンの Lync Server と Office Communications Server では、クライアントと Web サービスのセッション状態が維持されるように、Web サービスによって cookie ベースのアフィニティが使用されていました。 Lync Server 2013 Web サービスでは、cookie ベースのアフィニティの要件をほとんど解消する組み込みのアフィニティメカニズムを使用します。

<div>


> [!WARNING]  
> Microsoft Lync 2010 モバイルクライアントでは、依然として cookie ベースのアフィニティを使用する必要があります。すべてのクライアントを今後の Microsoft Lync モバイルクライアントに移行するまで、cookie ベースのアフィニティの構成が必要になります (リリース日はまだ確定していません)。



</div>

Lync Server 2013 での cookie ベースのアフィニティの詳細については、「 [Lync server 2013 での外部ユーザーアクセスに必要なコンポーネント](lync-server-2013-components-required-for-external-user-access.md)」を参照してください。

</div>

<div>

## <a name="autodiscover-enhancements"></a>自動検出の拡張機能

Lync Server 2013 の自動検出機能を使用すると、クライアントは通信可能なその他の機能を見つけることができます。 自動検出は、Lync Server 2010 の累積的な更新プログラムで導入されました。モビリティと Microsoft Lync 2010 Mobile 用の2011年11月。 自動検出機能 (DNS レコード名 LyncDiscover と LyncDiscoverInternal にも呼ばれます) を使うと、クライアントはモビリティサービス (Microsoft Lync 2010 モバイルクライアント)、Microsoft Lync Web App、Lync Web scheduler などを検索して使用することができます。Microsoft Exchange Server および SharePoint Server との通信。 自動検出は、インフラストラクチャと Lync Server 2013 サーバーのセットアップと展開の通常の部分としてインストールされます。 トポロジビルダーと Lync Server Deployment ウィザードを使用すると、Lync Server 2010 の累積的な更新プログラムで必要とされる構成タスクのほとんどが、2011年11月に行われなくなります。

</div>

<div>

## <a name="services-for-mobile-clients"></a>モバイルクライアント用のサービス

Lync Server 2010 の累積的な更新プログラムで導入されています。 Lync Server 2013 のモバイルサービス、Android、Windows Phone、Nokia のモバイルデバイスを使用して、Lync Mobile およびタブレットデバイスを実行している携帯電話を有効にし2011ます。インスタントメッセージの送受信、連絡先の表示、プレゼンスの表示などのアクティビティ。 さらに、モバイルデバイスでは、クリックして会議に参加したり、勤務先の電話、1回の通話、ボイスメール、不在着信通知など、一部のエンタープライズ音声機能をサポートしたりします。

<div>


> [!NOTE]  
> モビリティサービスは、フロントエンドサーバーに展開されているリバースプロキシと公開されたサービスを使用します。 エッジサーバーへの変更は必要ありません。 少なくとも、Lync Server アクセスエッジサービスを実行しているサーバーから発信 SIP/TCP/5061from 必要です。



</div>

</div>

<div>

## <a name="director-role-is-optional"></a>ディレクターの役割はオプション

Lync Server 2013 トポロジでのディレクターサーバーの役割が変更されていません。 さらに、web サービスをホストして、着信ユーザー要求を事前認証し、外部ユーザーをホームプールにリダイレクトします。 推奨された役割からディレクターをオプションの役割に変更することで、Microsoft はディレクターの価値を減少することを意図していません。 目的は、機能を損なうことなく、サーバー数とその他のハードウェア要件 (ディレクターのハードウェアロードバランサーなど) を削減することです。 フロントエンドサーバーは、提供されているサービスに影響を与えずにディレクターと同じジョブを実行できるため、選択する場合は、ディレクターを展開できます。 フロントエンドサーバーによってディレクターの代わりに同じサービスが提供されるという確信を持って、ディレクターを安全に除外することができます。

</div>

</div>

<span> </span>

</div>

</div>

</div>

