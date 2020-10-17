---
title: 'Lync Server 2013: 2 要素認証の計画'
description: 'Lync Server 2013: 2 要素認証の計画。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for two-factor authentication
ms:assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308562(v=OCS.15)
ms:contentKeyID: 54973683
ms.date: 04/06/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a3a2cd5508f6ce9a8a389b0059a09747b9f9a09
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564003"
---
# <a name="planning-for-two-factor-authentication-in-lync-server-2013"></a>Lync Server 2013 での2要素認証の計画

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2015-04-06_

2要素認証をサポートするように Microsoft Lync Server 2013 環境を構成する場合の展開に関する考慮事項の一覧を次に示します。

<div>

## <a name="client-support"></a>クライアントサポート

Lync Server 2013 の Lync 2013 の累積的な更新プログラム: 7 月 2013 7 日のデスクトップクライアントとすべてのモバイルクライアントは、現在2要素認証をサポートしています。

</div>

<div>

## <a name="topology-requirements"></a>トポロジ要件

お客様は、Lync Server 2013 の累積的な更新プログラムと共に、専任の Lync Server 2013 を使用して2要素認証を展開することを強くお勧めします。 7 2013 月のエッジ、ディレクター、およびユーザープール。 Lync ユーザーのパッシブ認証を有効にするには、他の役割とサービスについて次のような他の認証方法を無効にする必要があります。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>構成の種類</th>
<th>サービス タイプ</th>
<th>サーバーの役割</th>
<th>無効にする認証の種類</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>(Web) サービス</p></td>
<td><p>サーバ</p></td>
<td><p>ディレクター</p></td>
<td><p>Kerberos、NTLM、証明書</p></td>
</tr>
<tr class="even">
<td><p>(Web) サービス</p></td>
<td><p>サーバ</p></td>
<td><p>フロントエンド</p></td>
<td><p>Kerberos、NTLM、証明書</p></td>
</tr>
<tr class="odd">
<td><p>プロキシ</p></td>
<td><p>EdgeServer</p></td>
<td><p>Edge</p></td>
<td><p>Kerberos および NTLM</p></td>
</tr>
<tr class="even">
<td><p>プロキシ</p></td>
<td><p>レジストラー</p></td>
<td><p>フロントエンド</p></td>
<td><p>Kerberos および NTLM</p></td>
</tr>
</tbody>
</table>


これらの認証の種類がサービスレベルで無効になっていない場合、展開内で2要素認証が有効になっていると、Lync クライアントの他のすべてのバージョンは正常にサインインできなくなります。

</div>

<div>

## <a name="lync-service-discovery"></a>Lync Service の検出

内部または外部のクライアントが Lync サービスを検出するために使用する DNS レコードは、2要素認証が有効になっていない Lync server に解決するように構成する必要があります。 この構成では、2要素認証が有効になっていない Lync プールのユーザーは、認証のために PIN を入力する必要はありませんが、2要素認証が有効になっている Lync プールのユーザーは認証のために PIN を入力する必要があります。

</div>

<div>

## <a name="exchange-authentication"></a>Exchange 認証

Microsoft Exchange の2要素認証を展開しているお客様は、Lync クライアントの特定の機能が使用できないことを確認できます。 現在、Lync クライアントは、Exchange 統合に依存する機能に対して2要素認証をサポートしていないため、これは現在設計になっています。

</div>

<div>

## <a name="lync-contacts"></a>Lync の連絡先

統合連絡先ストア機能を活用するように構成された Lync ユーザーは、2要素認証を使用してサインインした後、連絡先が使用できなくなっていることを確認できます。

2要素認証を有効にする前に、 **invoke-csucsrollback** コマンドレットを使用して、統合連絡先ストアから既存のユーザー連絡先を削除し、Lync Server 2013 に格納する必要があります。

</div>

<div>

## <a name="skill-search"></a>スキル検索

Lync 環境でスキル検索機能を構成したお客様は、Lync が2要素認証のために有効になっていると、この機能が機能しないことがわかります。 Microsoft SharePoint では、現在2要素認証がサポートされていないため、このような設計になっています。

</div>

<div>

## <a name="lync-credentials"></a>Lync 資格情報

保存された Lync 資格情報に関しては、2要素認証を使用するように構成されているユーザーに影響を与える可能性がある、いくつかの展開の考慮事項があります。

<div>

## <a name="deleting-saved-credentials"></a>保存された資格情報の削除

デスクトップクライアントのユーザーは、Lync クライアントの [ **サインイン情報の削除** ] オプションを使用して、 \\ \\ \\ \\ 2 要素認証を使用して初めて署名する前に、Microsoft Office 15.0 Lync から SIP プロファイルフォルダーを削除する必要があります。

</div>

<div>

## <a name="disablentcredentials"></a>DisableNTCredentials

Kerberos 認証方法または NTLM 認証方式では、ユーザーの Windows 資格情報が認証に自動的に使用されます。 Kerberos または NTLM 認証が有効になっている典型的な Lync Server 2013 の展開では、ユーザーはサインインするたびに資格情報を入力する必要はありません。

PIN の入力を求められる前に、ユーザーが誤って資格情報の入力を求められた場合は、クライアントコンピューターで **Disablentcredentials** レジストリキーが誤って構成されることがあります。グループポリシーを使用している可能性があります。

資格情報の追加を求めるプロンプトを表示しないようにするには、ローカルワークステーションに次のレジストリエントリを作成するか、または Lync 管理用テンプレートを使用して、グループポリシーを使用して特定のプールのすべてのユーザーに適用します。

HKEY \_ ローカル \_ コンピューター \\ ソフトウェア \\ ポリシー \\ Microsoft \\ Office \\ 15.0 \\ Lync

REG \_ DWORD: DisableNTCredentials

値: 0x0

</div>

<div>

## <a name="savepassword"></a>SavePassword

ユーザーが初めて Lync にサインインすると、ユーザーは自分のパスワードを保存するように求められます。 このオプションを選択すると、ユーザーのクライアント証明書を個人証明書ストアに格納し、ユーザーの Windows 資格情報をローカルコンピューターの資格情報マネージャーに保存できるようになります。

Lync が2要素認証をサポートするように構成されている場合は、 **Savepassword** レジストリ設定を無効にする必要があります。 ユーザーがパスワードを保存できないようにするには、ローカルワークステーションの次のレジストリエントリを変更するか、または Lync 管理用テンプレートを使用して、グループポリシーを使用して特定のプールのすべてのユーザーに適用します。

HKEY \_ CURRENT \_ USER \\ Software \\ Microsoft \\ Office \\ 15.0 \\ Lync

REG \_ DWORD: SavePassword

値: 0x0

</div>

</div>

<div>

## <a name="ad-fs-20-token-replay"></a>AD FS 2.0 トークンの再生

AD FS 2.0 は、トークン再生検出と呼ばれる機能を提供しており、同じトークンを使用して複数のトークン要求を検出して破棄することができます。 この機能が有効になっている場合は、同じトークンが一度も使用されないようにすることによって、WS-Federation パッシブプロファイルおよび SAML WebSSO profile の両方で認証要求の整合性を保護します。

この機能を有効にする必要があるのは、セキュリティがキオスクを使用する場合など、非常に高い問題である場合です。 トークンリプレイ検出の詳細については、「AD FS 2.0 のセキュリティで保護された計画と展開のベストプラクティス」を参照してください [https://go.microsoft.com/fwlink/p/?LinkId=309215](https://go.microsoft.com/fwlink/p/?linkid=309215) 。

</div>

<div>

## <a name="external-user-access"></a>外部ユーザー アクセス

外部ネットワークから Lync の2要素認証をサポートするように AD FS プロキシまたはリバースプロキシを構成する方法については、以下のトピックでは扱いません。

</div>

</div>

<span> </span>

</div>

</div>

</div>

