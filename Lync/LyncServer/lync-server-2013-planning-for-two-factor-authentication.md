---
title: 2 要素認証の計画
TOCTitle: 2 要素認証の計画
ms:assetid: 16f08710-8961-4659-acbf-ebb95a198fb4
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Dn308562(v=OCS.15)
ms:contentKeyID: 56270056
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 2 要素認証の計画

 

_**トピックの最終更新日:** 2016-12-08_

2 要素認証をサポートするように Microsoft Lync Server 2013 環境を構成する場合の展開に関する考慮事項を次に示します。

## クライアント サポート

Lync 2013 の "Lync Server 2013 の累積的な更新プログラム: 2013 年 7 月" のデスクトップ クライアントは、現在 2 要素認証をサポートしている唯一の Lync クライアントです。

## トポロジの要件

専用の Lync Server 2013 および "Lync Server 2013 の累積的な更新プログラム: 2013 年 7 月" のエッジ プール、ディレクター プール、ユーザー プールを使用して 2 要素認証を展開することを強くお勧めします。Lync ユーザーに対してパッシブ認証を有効にするには、次に示すように、他の役割およびサービスに対してその他の認証方法を無効にする必要があります。


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
<td><p>エッジ</p></td>
<td><p>Kerberos および NTLM</p></td>
</tr>
<tr class="even">
<td><p>プロキシ</p></td>
<td><p>Registrar</p></td>
<td><p>フロントエンド</p></td>
<td><p>Kerberos および NTLM</p></td>
</tr>
</tbody>
</table>


これらの認証の種類がサービス レベルで無効になっていない限り、2 要素認証が展開内で有効になっても、他のすべてのバージョンの Lync クライアントでは正常にサインインできません。

## Lync サービスの検出

Lync サービスを検出するために内部および外部のクライアントで使用される DNS レコードは、2 要素認証が有効になっていない Lync サーバーに解決するように構成する必要があります。この構成を使用すると、2 要素認証が有効になっていない Lync プールのユーザーは認証時に PIN を入力する必要がありません。一方、2 要素認証が有効な Lync プールのユーザーは、認証時に PIN を入力する必要があります。

## Exchange 認証

Microsoft Exchange 用に 2 要素認証を展開したユーザーは、Lync クライアントの特定の機能を使用できない場合があります。Lync クライアントでは Exchange 統合に依存する機能に対する 2 要素認証がサポートされていないため、現時点でこれは仕様です。

## Lync 連絡先

統合連絡先ストア機能を利用するように構成されている Lync ユーザーは、2 要素認証を使用してサインインすると連絡先を使用できなくなります。

**Invoke-CsUcsRollback** コマンドレットを使用して、統合連絡先ストアから既存のユーザーの連絡先を削除し、Lync Server 2013 に保存してから 2 要素認証を有効にする必要があります。

## スキル検索

Lync 環境でスキル検索機能を構成したユーザーは、Lync で 2 要素認証が有効な場合は、その機能を使用できません。現在、Microsoft SharePoint では 2 要素認証がサポートされていないため、これは仕様です。

## Lync の資格情報

保存された Lync の資格情報に関連する展開の考慮事項がいくつか存在します。これは、2 要素認証を使用するように構成されたユーザーに影響を与える可能性があります。

## 保存された資格情報の削除

ユーザーは、2 要素認証を使用してサインインを初めて試行する前に、Lync クライアントの \[**サインイン情報を削除**\] オプションを使用して、%localappdata%\\Microsoft\\Office\\15.0\\Lync からユーザーの SIP プロファイル フォルダーを削除する必要があります。

## DisableNTCredentials

認証方法が Kerberos または NTLM の場合は、ユーザーの Windows 資格情報が自動的に認証に使用されます。Kerberos または NTLM 認証が有効になっている一般的な Lync Server 2013 展開の場合、サインインのたびにユーザーが資格情報を入力する必要はありません。

PIN の入力を求めるメッセージが表示される前に、意図せず資格情報の入力を求められた場合は、クライアント コンピューターで **DisableNTCredentials** レジストリ キーが誤って (おそらくグループ ポリシーを使用して) 構成されている可能性があります。

資格情報の入力を求める追加のメッセージが表示されないようにするには、ローカル ワークステーションで次のレジストリ エントリを作成するか、すべてのユーザーに適用する Lync 管理用テンプレートを、グループ ポリシーを使用する特定のプールに対して使用します。

HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Office\\15.0\\Lync

REG\_DWORD: DisableNTCredentials

値: 0x0

## SavePassword

ユーザーが初めて Lync にサインインすると、パスワードを保存するよう求められます。このオプションを選択すると、ユーザーのクライアント証明書を個人証明書ストアに保存したり、ユーザーの Windows 資格情報をローカル コンピューターの資格情報マネージャーに保存したりできます。

2 要素認証をサポートするように Lync が構成されている場合は、**SavePassword** レジストリ設定を無効にする必要があります。ユーザーがパスワードを保存できないようにするには、ローカル ワークステーションで次のレジストリ エントリを変更するか、すべてのユーザーに適用する Lync 管理用テンプレートを、グループ ポリシーを使用する特定のプールに対して使用します。

HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync

REG\_DWORD: SavePassword

値: 0x0

## AD FS 2.0 のトークンのリプレイ

AD FS 2.0 には、トークン リプレイ検出と呼ばれる機能が用意されています。この機能によって、同じトークンを使用する複数のトークン要求を検出して破棄できます。この機能が有効な場合は、同じトークンが複数回使用されることがなくなるため、WS-Federation パッシブ プロファイルと SAML WebSSO プロファイルの両方において認証要求の整合性が確保されます。

キオスクを使用する場合など、セキュリティが最も重視される状況では、この機能を有効にする必要があります。トークン リプレイ検出の詳細については、「Best Practices for Secure Planning and Deployment of AD FS 2.0」([http://go.microsoft.com/fwlink/p/?LinkId=309215](http://go.microsoft.com/fwlink/p/?linkid=309215)) を参照してください。

## 外部ユーザー アクセス

外部ネットワークから Lync の 2 要素認証をサポートするように ADFS プロキシまたはリバース プロキシを構成する方法については、これらのトピックでは説明しません。

