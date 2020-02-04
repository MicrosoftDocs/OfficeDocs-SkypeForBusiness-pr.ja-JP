---
title: 'Lync Server 2013: ブランチ サイトの復元要件'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency requirements
ms:assetid: a570922c-52bd-42d7-bd64-226578b3d110
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412772(v=OCS.15)
ms:contentKeyID: 48184984
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f146f2c358e6eb6718aa60f8a51106430e6a4a3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741637"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-requirements-for-lync-server-2013"></a>Lync Server 2013 のブランチ サイトの復元要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-02-25_

このトピックでは、ブランチ サイトの復元およびボイス メールの存続性に対するユーザーの準備と、関連するハードウェアとソフトウェアの要件について説明します。

<div>

## <a name="preparing-branch-users-for-branch-site-resiliency"></a>ブランチ サイトの復元に対するブランチ サイトのユーザーの準備

ユーザーのレジストラープールを Survivable Branch Appliance (SBA) または Survivable Branch Server として設定することにより、ブランチサイトの回復力を持つユーザーを準備します。

<div>

## <a name="registrar-assignments-for-branch-users"></a>ブランチ ユーザーのレジストラーへの割り当て

どのブランチサイトの復元ソリューションを選んでも、プライマリレジストラーを各ユーザーに割り当てる必要があります。 ブランチサイトユーザーは、レジストラーが Survivable Branch Appliance、Survivable Branch Server、またはスタンドアロンの Lync Server 2013 Standard または Enterprise Edition サーバーのどちらに存在するかに関係なく、常にブランチサイトのレジストラーに登録する必要があります。 クライアントがレジストラープールを検出できるように、ドメインネームシステム (DNS) サービス (SRV) リソースレコードが必要です。 Survivable Branch アプライアンスが使用できなくなった場合は、ブランチサイトクライアントでバックアップレジストラーが自動的に検出されます。

ブランチサイトに DNS サーバーがない場合は、次の2つの方法で、Survivable Branch Appliance または Survivable Branch Server の検出を構成することができます。

  - Survivable Branch Appliance または Survivable Branch Server の完全修飾ドメイン名 (FQDN) をポイントするように、ブランチサイトの動的ホスト構成プロトコル (DHCP) サーバー上の DHCP オプション120を構成します。

  - DHCP 120 クエリに応答するように、Survivable Branch Appliance または Survivable Branch Server を構成します。

</div>

<div>

## <a name="voice-routing-for-branch-users"></a>ブランチ ユーザーの音声ルーティング

ブランチサイトのユーザーに対して、個別のユーザーレベルのボイスメールインターネットプロトコル (VoIP) ポリシーを作成することをお勧めします。 このポリシーには、Survivable Branch Appliance またはブランチサーバーゲートウェイを使用するプライマリルートと、セントラルサイトで公衆交換電話網 (PSTN) ゲートウェイを使用するトランクを使用する1つ以上のバックアップルートを含める必要があります。 プライマリルートを使用できない場合は、1つ以上のセントラルサイトゲートウェイを使用するバックアップルートが代わりに使用されます。 この方法では、ユーザーが登録されている場所に関係なく、ブランチサイトレジストラーまたはセントラルサイトのバックアップレジストラープールで、ユーザーの VoIP ポリシーが常に有効になります。 これは、フェールオーバーシナリオの重要な考慮事項です。 たとえば、Survivable Branch Appliance の名前を変更する必要がある場合、または Survivable Branch アプライアンスを再構成してセントラルサイトのバックアップレジストラープールに接続する必要がある場合は、その期間、ブランチサイトユーザーをセントラルサイトに移動する必要があります。 (Survivable Branch アプライアンスの名前の変更または再構成の詳細については、「[付録 B: 展開ドキュメントの Lync Server 2013 で Survivable Branch appliance を管理](lync-server-2013-appendix-b-managing-a-survivable-branch-appliance.md)する」を参照してください。)このようなユーザーが、ユーザーレベルの VoIP ポリシーまたはユーザーレベルのダイヤルプランを持っていない場合は、ユーザーが別のサイトに移動すると、ブランチサイトのサイトレベルの VoIP ポリシーとダイヤルプランの代わりに、セントラルサイトのサイトレベルの VoIP ポリシーとサイトレベルのダイヤルプランが既定でユーザーに適用されます。 このシナリオでは、バックアップレジストラープールで使用されるサイトレベルの VoIP ポリシーやサイトレベルのダイヤルプランもブランチサイトユーザーに適用できる場合を除き、その呼び出しは失敗します。 たとえば、日本に配置されている支店のユーザーが Redmond のセントラルサイトに移動した場合、すべての7桁の通話に + 1425 を付加する正規化ルールが適用されているダイヤルプランでは、これらのユーザーへの通話を適切に翻訳できない可能性があります。

<div>


> [!IMPORTANT]  
> ブランチ オフィスのバックアップ ルートを作成するときは、ブランチ オフィスのユーザー ポリシーに 2 つの PSTN 電話使用法レコードを追加し、各電話使用法レコードに個別のルートを割り当てることをお勧めします。 第1または第1のルートでは、Survivable Branch Appliance (SBA) またはブランチサーバーに関連付けられているゲートウェイに直接通話を発信できます。2番目の (バックアップ) ルートは、中央サイトのゲートウェイに直接通話を発信します。 SBA またはブランチ サーバーは通話を振り分けるときに、最初の PSTN 使用法レコードに割り当てられたすべてのルートを試みてから、2 番目の使用法レコードのルートを試みます。



</div>

Survivable Branch Appliance サイトのブランチゲートウェイまたは Windows コンポーネントが利用できない場合 (たとえば、Survivable Branch Appliance またはブランチの場合など) に、ブランチサイトユーザーへの着信通話がそれらのユーザーに届くようにするために役立ちます。ゲートウェイはメンテナンスのために停止していました)、ゲートウェイでフェールオーバールートを作成します (または、直接内向きダイヤル (DID) プロバイダーと協力して、中央サイトのバックアップレジストラープールに着信通話をリダイレクトします。 通話は、そこから WAN リンク経由でブランチ ユーザーにルーティングされます。 ルートによって番号が PSTN ゲートウェイまたは他のトランク ピアの受け付け済み電話番号方式に準拠するように変換されることを確認します。 フェールオーバールートの作成の詳細については、「 [Lync Server 2013 でのフェールオーバールートの構成](lync-server-2013-configuring-a-failover-route.md)」を参照してください。 また、ブランチ サイトのゲートウェイに関連付けられたトランクにサービスレベルのダイヤル プランを作成して着信通話を正規化します。 ブランチサイトに2つの Survivable Branch アプライアンスがある場合は、それぞれについて、それぞれのサービスレベルのプランが必要な場合を除き、両方のサイトレベルのダイヤルプランを作成することができます。

<div>


> [!NOTE]  
> プレゼンス、会議、またはフェールオーバーの実行を中央サイトに頼っているすべてのブランチ サイトのユーザーによる中央サイトのリソース消費に対応するには、各ブランチ サイトのユーザーを、中央サイトに登録されたユーザーとしてみなすことをお勧めします。 現時点では、Survivable Branch Appliance に登録されているユーザーを含む、ブランチサイトユーザーの数に制限はありません。



</div>

なお、ユーザー レベルのダイヤル プランと音声ポリシーを作成してから、ブランチ サイトのユーザーに割り当てることもお勧めします。 詳細については、「 [Lync server 2013 でダイヤルプランを作成](lync-server-2013-create-a-dial-plan.md)する」および「展開ドキュメントの[lync server 2013 でブランチユーザー用に VoIP ルーティングポリシーを作成](lync-server-2013-create-the-voip-routing-policy-for-branch-users.md)する」を参照してください。

<div>

## <a name="routing-extension-numbers"></a>内線番号のルーティング

ブランチサイトユーザーのダイヤルプランと音声ポリシーを準備する場合は、Msrtcsip-userenabled true line (または Line URI) 属性で使用される文字列と数値の書式に一致する正規化ルールと翻訳ルールを含めるようにしてください。そのため、Lync 2013 の通話がブランチ間で有効になります。サイトユーザーとセントラルサイトユーザーは正しくルーティングされます。特に、WAN リンクが利用できないため、PSTN 経由で通話を再ルーティングする必要がある場合。 また、電話番号だけではなく、内線番号を含むダイヤル番号には特別な考慮事項があります。

内線番号を単独で含むか、E.164 準拠の電話番号に追加して含むかにかかわらず、内線番号を含む回線 URI を照合する正規化ルールと変換ルールには要件が追加されます。このセクションでは、いくつかのシナリオ例を挙げて、内線番号を含む回線 URI の通話をルーティングする方法について説明します。

組織で個々のユーザーに Direct Inward Dial (DID) 電話番号を構成しないで、各ユーザーの回線 URI を内線番号のみで構成している場合、内部ユーザーは、内線番号のみをダイヤルして通話できます。** ただし、ブランチ サイトのユーザーから、内線番号が一致する中央サイトのユーザーへの通話に適用できる正規化ルールを構成する必要があります。

ブランチ サイトのユーザーと中央サイトのユーザーの間で WAN リンクを使用できる場合、ブランチ サイトのユーザーから中央サイトのユーザーへの通話は PSTN 経由でルーティングされないため、マッチング正規化ルールで番号を変換する必要はありません。次に例を示します。


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>ルール名</th>
<th>説明</th>
<th>番号のパターン</th>
<th>変換</th>
<th>例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>5digitExtensions</p></td>
<td><p>5 桁の番号を変換しません。</p></td>
<td><p>^ (\d{5}) $</p></td>
<td><p>$1</p></td>
<td><p>10001 は変換されません。</p></td>
</tr>
</tbody>
</table>


また、ブランチ サイトと中央サイトの間で WAN リンクを使用できない場合や、ブランチ サイトからの通話を PSTN 経由でルーティングする必要がある場合などのシナリオの内線番号に対応する必要もあります。WAN の停止時に、ブランチ サイトのユーザーが、中央サイトのユーザーの内線番号のみをダイヤルして中央サイトのユーザーと通話する場合は、中央サイトのユーザーの完全な電話番号を追加する発信変換ルールが必要です。ユーザーの回線 URI に、組織の完全な電話番号とユーザーの一意の内線番号 (ユーザーの一意の完全な電話番号ではなく) が含まれている場合は、組織の完全な電話番号を追加する発信変換ルールが必要です。次に例を示します。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>説明</th>
<th>一致パターン</th>
<th>変換</th>
<th>例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>5 桁の番号をユーザーの電話番号と内線番号に変換します。</p></td>
<td><p>^ (\d{5}) $</p></td>
<td><p>+14255550123;ext=$1</p></td>
<td><p>10001 は +14255550123;ext=10001 に変換されます。</p></td>
</tr>
<tr class="even">
<td><p>5 桁の番号を組織の電話番号とユーザーの内線番号に変換します。</p></td>
<td><p>^ (\d{5}) $</p></td>
<td><p>+14255550100;ext=$1</p></td>
<td><p>10001 は +14255550100;ext=10001 に変換されます。</p></td>
</tr>
</tbody>
</table>


このシナリオで、PSTN への再ルーティングを処理するトランク ピアが、内線番号をサポートしていない場合は、発信変換ルールによって内線番号を削除する必要もあります。次に例を示します。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>説明</th>
<th>一致パターン</th>
<th>変換</th>
<th>例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>内線番号付きの電話番号から内線番号を削除します。</p></td>
<td><p>^\+(\d *); ext = (\d*) $</p></td>
<td><p>+$1</p></td>
<td><p>+14255550123;ext=10001 は +14255550123 に変換されます。</p></td>
</tr>
</tbody>
</table>


WAN リンクが使用できるかどうかにかかわらず、組織で個々のユーザーに DID 番号を構成しないで、ユーザーの回線 URI に組織の電話番号とユーザーの一意の内線番号を含める場合は、組織の電話番号の回線 URI を、ブランチ サイトのトランク ピアまたは PSTN ゲートウェイから到達可能な番号で構成する必要があります。また、組織の電話番号の回線 URI に独自の一意の内線番号を含めて、その番号に通話をルーティングする必要もあります。

サイト間の WAN リンクが利用できない場合の中央サイトユーザーからブランチサイトユーザーへの通話について詳しくは、このトピックの後半の「ボイスメールの Survivability の準備」をご覧ください。 その他のサンプルルールなど、ダイヤルプランと正規化ルールの詳細については、展開ドキュメントの「会議の計画と lync [server 2013 でのダイヤルプランの構成](lync-server-2013-configuring-dial-plans.md)」を参照して[2013](lync-server-2013-dial-plans-and-normalization-rules.md)ください。 送信翻訳ルールの詳細については、「計画ドキュメントの「 [Lync server 2013 の翻訳ルール](lync-server-2013-translation-rules.md)」および「展開ドキュメントの[lync server 2013 での翻訳ルールの定義](lync-server-2013-defining-translation-rules.md)」を参照してください。

</div>

</div>

</div>

<div>

## <a name="preparing-for-voice-mail-survivability"></a>ボイス メールの存続性の準備

通常、Exchange ユニファイドメッセージング (UM) は、ブランチサイトではなくセントラルサイトにのみインストールされます。 ブランチ サイトと中央サイトの間で WAN リンクを使用できない場合でも、発信者がボイス メール メッセージを残すことをできるようにする必要があります。 結果として、ブランチサイトユーザーのボイスメールを提供する Exchange UM 自動応答の電話番号の行 URI を構成するには、そのボイスメールに適用される音声ポリシー、ダイヤルプラン、正規化ルールに加えて、特別な考慮事項が必要です。単位.

Survivable Branch アプライアンス (SBAs) と Survivable ブランチサーバーは、WAN の停止中に支店のユーザー向けにボイスメール survivability を提供します。 特に、Survivable Branch Appliance または Survivable Branch Server を使用していて、WAN が利用できなくなった場合、SBA または Survivable ブランチサーバーは、PSTN 経由で、不在着信した通話を中央サイトの Exchange UM に再ルーティングします。 SBA または Survivable ブランチサーバーでは、ユーザーは、WAN の停止中に PSTN 経由でボイスメールメッセージを受信することもできます。 最後に、WAN の停止中に、Survivable Branch Appliance または Survivable Branch Server は、不在着信通知をキューに置いて、WAN が復元されたときにそれらを Exchange UM サーバーにアップロードします。 ボイスメールの再ルーティングが確実に復元されるようにするには、セントラルサイトプールの FQDN と、エッジサーバーの FQDN のエントリを、Survivable Branch Server 上の hosts ファイルに追加してください。 そうしないと、ブランチサイトに DNS サーバーがない場合に、DNS 解決がタイムアウトする可能性があります。

ブランチ サイトのユーザーに対してボイス メールの存続性を構成するには、次のような構成が推奨されます。

  - Microsoft Exchange 管理者は、Exchange UM 自動応答 (AA) でメッセージのみを受け入れるように構成する必要があります。 この構成により、ユーザーへの転送やオペレーターへの転送など、その他の一般的な機能がすべて無効になり、自動応答 (AA) をメッセージの受け取りのみに制限します。 または、Exchange の管理者は、汎用の自動応答 (AA) を使ったり、自動応答 (AA) をカスタマイズしたりして、通話をオペレーターへルーティングすることができます。

  - Lync Server の管理者は、AA の電話番号を取得し、Survivable Branch Appliance またはブランチサーバーのボイスメールの再ルーティング設定で、その電話番号を**exchange um 自動応答**番号として使用する必要があります。

  - Lync Server の管理者は、Exchange UM サブスクライバーアクセス用の電話番号を取得し、Survivable Branch Appliance または Survivable ブランチサーバーのボイスメール再ルーティング設定で、**サブスクライバーのアクセス**番号としてその番号を使用します。

  - Lync Server 管理者は、WAN の停止中にボイスメールへのアクセスを必要とするすべての支店ユーザーと関連付けられるダイヤルプランが1つだけであるように、Exchange UM を構成する必要があります。

  - WAN リンクを使用できない場合、ブランチ サイトのユーザーとの通話をユーザーの Exchange ユニファイド メッセージング (UM) ボイス メールボックスにルーティングできます。ただし、これは、その通話に適用される音声ポリシーに、内線番号を含まない一意のボイス メール電話番号が指定されている場合に限られます。

</div>

<div>

## <a name="hardware-and-software-requirements-for-branch-site-resiliency"></a>ブランチ サイトの復元のハードウェアおよびソフトウェア要件

ハードウェアおよびソフトウェア要件は、復元ソリューションによって異なります。

<div>

## <a name="requirements-for-survivable-branch-appliances"></a>存続可能ブランチ アプライアンスの要件

Survivable Branch アプライアンスには、必要なハードウェアとソフトウェアが組み込まれています。 ただし、各ブランチサイトでクライアントの IP アドレスを取得するために DHCP サーバーを展開することもお勧めします。そうしないと、DHCP リースの有効期限が切れると、クライアントに IP 接続ができなくなります。

エンタープライズ DNS サーバーがセントラルサイトのみにある場合、ブランチサイトユーザーは、WAN の停止中にそれらのサーバーに接続できず、DNS SRV (service (SRV) リソースレコード) を使用する Lync Server discovery は失敗します。 WAN の停止時に迅速に再ルーティングされるように、ブランチ サイトで DNS レコードをキャッシュする必要があります。 ブランチのルーターが DNS キャッシュをサポートする場合は、DNS キャッシュを有効にします。 または、ブランチに DNS サーバーを展開することもできます。 これは、スタンドアロンサーバーでも、DNS 機能をサポートする Survivable Branch アプライアンスのバージョンでもかまいません。 詳細については、Survivable Branch Appliance プロバイダーにお問い合わせください。

<div>


> [!NOTE]  
> ブランチサイトにドメインコントローラーが存在する必要はありません。 Survivable Branch アプライアンスは、サインイン時にクライアントの証明書要求に応じてクライアントを送信する特別な証明書を使ってクライアントを認証します。



</div>

Lync クライアントは、DHCP オプション 120 (SIP レジストラーオプション) を使って Lync サーバーを見つけることができます。 これは、次の 2 つのいずれかの方法で構成できます。

  - Survivable Branch Appliance または Survivable Branch Server で、レジストラーの FQDN を返す DHCP 120 クエリに応答するように、ブランチサイトで DHCP サーバーを構成します。

  - Lync Server DHCP を有効にします。 この設定を有効にすると、Lync Server レジストラーは DHCP オプション120クエリに応答します。 レジストラーは、DHCP オプション 120 以外の DHCP クエリには応答しません。

また、より大きなブランチ サイトで複数のサブネットがある場合は、DHCP オプション 120 のクエリが DHCP サーバー (構成 1) またはレジストラー (構成 2) に転送されるように、DHCP リレー エージェントを有効にする必要があります。

最後に、ブランチサイトユーザーはエンタープライズ Voip 用に構成し、適切なユニファイドコミュニケーションエンドポイントを使用してプロビジョニングする必要があります。

</div>

<div>

## <a name="requirements-for-survivable-branch-servers"></a>存続可能ブランチ サーバーの要件

Survivable ブランチサーバーの要件は、フロントエンドサーバーの要件と同じです。 詳細については、計画ドキュメントの「 [Lync server 2013 用のサーバーハードウェアプラットフォーム](lync-server-2013-server-hardware-platforms.md)」を参照してください。

</div>

<div>

## <a name="requirements-for-full-scale-lync-server-branch-site-deployments"></a>フルスケールの Lync Server ブランチサイト展開の要件

詳細については、計画ドキュメントで「 [Lync Server 2013 のインフラストラクチャ要件を決定](lync-server-2013-determining-your-infrastructure-requirements.md)する」を参照してください。

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

