---
title: 'Lync Server 2013: 2 要素認証の計画'
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
ms.openlocfilehash: e610990182e01c0e9e2d7199bd3a34f70fbe3132
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41750437"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-two-factor-authentication-in-lync-server-2013"></a>Lync Server 2013 での2要素認証の計画

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2015-04-06_

Microsoft Lync Server 2013 環境を構成して、2段階認証をサポートする場合の展開に関する考慮事項の一覧を次に示します。

<div>

## <a name="client-support"></a>クライアントのサポート

Lync 2013 の Lync Server 2013 の累積更新プログラム: 2013 デスクトップクライアントとすべてのモバイルクライアントで現在、2要素認証がサポートされています。

</div>

<div>

## <a name="topology-requirements"></a>トポロジ要件

お客様は、lync Server 2013 の累積更新プログラムを使用して、専用の Lync Server 2013 を使って2要素認証を展開することを強くお勧めします。これには、2013年7月のエッジ、監督、ユーザープールがあります。 Lync ユーザーに対してパッシブ認証を有効にするには、他の役割やサービスについて、次のような他の認証方法を無効にする必要があります。


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
<th>サービスの種類</th>
<th>サーバーの役割</th>
<th>無効にする認証の種類</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Web サービス</p></td>
<td><p>WebServer</p></td>
<td><p>ディレクター</p></td>
<td><p>Kerberos、NTLM、証明書</p></td>
</tr>
<tr class="even">
<td><p>Web サービス</p></td>
<td><p>WebServer</p></td>
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


これらの認証の種類がサービスレベルで無効にされていない限り、展開で2要素認証が有効になると、Lync クライアントの他のすべてのバージョンが正常にサインインできなくなります。

</div>

<div>

## <a name="lync-service-discovery"></a>Lync サービスの検出

内部および外部のクライアントによって使用される DNS レコードは、2要素認証が有効になっていない Lync サーバーに解決するように構成する必要があります。 この構成では、2要素認証が有効になっていない Lync プールのユーザーは、認証のために PIN の入力を求められますが、2要素認証が有効になっている Lync プールのユーザーは PIN を入力する必要があります。相互.

</div>

<div>

## <a name="exchange-authentication"></a>Exchange 認証

Microsoft Exchange の2要素認証を展開しているお客様は、Lync クライアントの一部の機能が利用できない可能性があります。 現時点では、Lync クライアントは Exchange の統合に依存する機能に対して2要素認証をサポートしていないため、現在の設計になっています。

</div>

<div>

## <a name="lync-contacts"></a>Lync の連絡先

統合連絡先ストア機能を利用するように構成されている Lync ユーザーは、2要素認証を使用してサインインした後、連絡先が利用できなくなります。

2要素認証を有効にする前に、 **CsUcsRollback**コマンドレットを使用して、統合された連絡先ストアから既存のユーザーの連絡先を削除し、それらを Lync Server 2013 に保存する必要があります。

</div>

<div>

## <a name="skill-search"></a>スキル検索

Lync 環境でスキル検索機能を構成している場合は、Lync が2要素認証を有効にしている場合、この機能が機能しないことがわかります。 現在、Microsoft SharePoint では 2 要素認証がサポートされていないため、これは仕様です。

</div>

<div>

## <a name="lync-credentials"></a>Lync の資格情報

2要素認証を使用するように構成されているユーザーに影響を与える可能性のある Lync 資格情報が保存されていることについて、いくつかの展開の考慮事項があります。

<div>

## <a name="deleting-saved-credentials"></a>保存された資格情報の削除

デスクトップクライアントユーザーは、Lync クライアントで **[サインイン情報の削除**] オプションを使用し、2段階認証を使用して初めて\\サインイン\\する\\前\\に、% localappdata% Microsoft Office 15.0 Lync から SIP プロファイルフォルダーを削除する必要があります。

</div>

<div>

## <a name="disablentcredentials"></a>DisableNTCredentials

認証方法が Kerberos または NTLM の場合は、ユーザーの Windows 資格情報が自動的に認証に使用されます。 認証に Kerberos または NTLM が有効になっている一般的な Lync Server 2013 の展開では、ユーザーがサインインするたびに資格情報を入力する必要はありません。

PIN の入力を求めるメッセージが表示される前に、意図せず資格情報の入力を求められた場合は、クライアント コンピューターで **DisableNTCredentials** レジストリ キーが誤って (おそらくグループ ポリシーを使用して) 構成されている可能性があります。

追加の資格情報の入力を求めるメッセージが表示されないようにするには、ローカルワークステーションで次のレジストリエントリを作成するか、グループポリシーを使って特定のプールのすべてのユーザーに適用する Lync 管理用テンプレートを使用します。

HKEY\_ローカル\_コンピューター\\ソフトウェア\\ポリシー\\Microsoft\\Office\\15.0\\Lync

REG\_DWORD: DisableNTCredentials

値: 0x0

</div>

<div>

## <a name="savepassword"></a>SavePassword

ユーザーが初めて Lync にサインインしたときに、ユーザーにパスワードの保存を促すメッセージが表示されます。 このオプションを選択すると、ユーザーのクライアント証明書を個人証明書ストアに保存したり、ユーザーの Windows 資格情報をローカル コンピューターの資格情報マネージャーに保存したりできます。

Lync が2要素認証をサポートするように構成されている場合は、 **Savepassword**レジストリ設定を無効にする必要があります。 ユーザーがパスワードを保存できないようにするには、ローカルワークステーションの次のレジストリエントリを変更するか、グループポリシーを使って、特定のプールのすべてのユーザーに適用する Lync 管理用テンプレートを使用します。

HKEY\_現在\_の\\ユーザー\\ソフトウェア\\Microsoft\\Office\\15.0 Lync

REG\_DWORD: savepassword

値: 0x0

</div>

</div>

<div>

## <a name="ad-fs-20-token-replay"></a>AD FS 2.0 のトークンのリプレイ

AD FS 2.0 には、トークン リプレイ検出と呼ばれる機能が用意されています。この機能によって、同じトークンを使用する複数のトークン要求を検出して破棄できます。この機能が有効な場合は、同じトークンが複数回使用されることがなくなるため、WS-Federation パッシブ プロファイルと SAML WebSSO プロファイルの両方において認証要求の整合性が確保されます。

キオスクを使用する場合など、セキュリティが最も重視される状況では、この機能を有効にする必要があります。 トークンの再生検出の詳細については、「AD FS 2.0 のセキュリティで保護され[http://go.microsoft.com/fwlink/p/?LinkId=309215](http://go.microsoft.com/fwlink/p/?linkid=309215)た計画と展開のためのベストプラクティス」を参照してください。

</div>

<div>

## <a name="external-user-access"></a>外部ユーザー アクセス

外部ネットワークからの Lync の2要素認証をサポートするように AD FS プロキシまたはリバースプロキシを構成する方法については、以下のトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

