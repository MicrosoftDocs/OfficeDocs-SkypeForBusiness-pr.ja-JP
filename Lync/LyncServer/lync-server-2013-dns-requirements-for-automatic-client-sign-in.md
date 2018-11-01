---
title: Lync Server 2013 での自動クライアント サインインの DNS 要件
TOCTitle: Lync Server 2013 での自動クライアント サインインの DNS 要件
ms:assetid: 3bcd4bb3-a022-4ffa-b005-1a95ad2b1796
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg425884(v=OCS.15)
ms:contentKeyID: 48271831
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での自動クライアント サインインの DNS 要件

 

_**トピックの最終更新日:** 2015-03-09_

ここでは、自動クライアント サインインに必要なドメイン ネーム システム (DNS) レコードについて説明します。Standard Edition サーバーまたはフロントエンド プールを展開するときに、クライアントが自動検出を使用して適切な Standard Edition サーバーまたはフロントエンド プールにサインインするように構成できます。クライアントが Lync Server 2013 に手動で接続する必要がある場合は、このセクションを読む必要はありません。

自動クライアント サインインをサポートするには、次のことを行う必要があります。

  - クライアントのサインイン要求を分散および認証する 1 つのサーバーまたはプールを指定します。 組織内のユーザーをホストする既存のサーバーまたはプールを使用できます。ユーザーをホストしない、この目的専用のサーバーまたはプールを指定することもできます。 可用性を高めるには、この機能用のフロントエンド プールを指定することをお勧めします。

  - このサーバーまたはプールで自動クライアント サインインをサポートする内部 DNS SRV レコードを作成します。
    
    > [!NOTE]
    > 次のレコード要件では、SIP ドメインは、ユーザーに割り当てられる SIP URI のホスト部分です。たとえば、SIP URI が *@contoso.com という形式の場合は、contoso.com が SIP ドメインです。SIP ドメインは、内部 Active Directory ドメインと異なる場合がよくあります。また、1 つの組織が複数の SIP ドメインをサポートする場合もあります。


クライアントに対して自動構成を有効にするには、次のレコードの 1 つを、Lync クライアントからのサインイン要求を分散させるフロントエンド プールまたは Standard Edition サーバーの完全修飾ドメイン名 (FQDN) にマップする内部 DNS SRV レコードを作成する必要があります。

  - \_sipinternaltls.\_tcp.*\<ドメイン\>* - 内部 TLS 接続の場合

SRV レコードは、サインイン要求を分散させるフロントエンド プールまたは Standard Edition サーバーに対して 1 つだけ作成します。

次の表は、架空の Contoso という会社に必要なレコードの例をいくつか示しています。この会社では、contoso.com と retail.contoso.com という SIP ドメインをサポートしています。

### 複数の SIP ドメインを持つクライアントの自動サインインに必要な DNS レコードの例

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>サインイン要求の分散に使用されるフロントエンド プールの FQDN</th>
<th>SIP ドメイン</th>
<th>DNS SRV レコード</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>pool01.contoso.com</p></td>
<td><p>contoso.com</p></td>
<td><p>pool01.contoso.com にマップするポート 5061 経由の _sipinternaltls._tcp.contoso.com ドメイン用の SRV レコード</p></td>
</tr>
<tr class="even">
<td><p>pool01.contoso.com</p></td>
<td><p>retail.contoso.com</p></td>
<td><p>pool01.contoso.com にマップするポート 5061 経由の _sipinternaltls._tcp.retail.contoso.com ドメイン用 SRV レコード</p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> 既定では、DNS レコードのクエリは、ユーザー名のドメインと SRV レコードの間で一致する厳密なドメイン名に従います。サフィックスの一致を使用するクライアント DNS クエリを使用する場合は、DisableStrictDNSNaming グループ ポリシーを構成できます。詳細については、「計画」のドキュメントの「<a href="lync-server-2013-planning-for-clients-and-devices.md">Lync Server 2013 のクライアントとデバイスの計画</a>」を参照してください。


## 自動クライアント サインインに必要な証明書および DNS レコードの例

この例では、前の表と同じ例の名前を使用します。 Contoso 社の組織は contoso.com および retail.contoso.com の SIP ドメインをサポートし、そのユーザー全員の SIP URI が次のいずれかの形式となります。

  - *\<ユーザー\>*@retail.contoso.com

  - *\<ユーザー\>*@contoso.com

