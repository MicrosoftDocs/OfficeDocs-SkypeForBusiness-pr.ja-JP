---
title: 'Lync Server 2013: 証明書の概要-NAT を使用したプライベート IP アドレスを持つ単一統合エッジ'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Single consolidated edge with private IP addresses using NAT
ms:assetid: 6de6680e-5f47-48e6-8e06-4994d710ea6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398519(v=OCS.15)
ms:contentKeyID: 48184433
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e41a2734feed26a929ed35fef3ec2c1dd320d9ac
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507904"
---
# <a name="certificate-summary---single-consolidated-edge-with-private-ip-addresses-using-nat-in-lync-server-2013"></a>証明書の概要-Lync Server 2013 で NAT を使用するプライベート IP アドレスを持つ単一統合エッジ

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-22_

Microsoft Lync Server 2013 は、証明書を使用して、他のサーバーを相互に認証し、サーバーからサーバーおよびサーバーからクライアントへデータを暗号化します。 証明書では、サーバーに関連付けられているドメイン ネーム システム (DNS) レコードの名前と、証明書のサブジェクト名 (SN) およびサブジェクトの別名 (SAN) の名前が一致している必要があります。 サーバー、DNS レコード、および証明書のエントリを正常にマッピングするには、DNS に登録される目的のサーバーの完全修飾ドメイン名、および証明書の SN エントリと SAN エントリを慎重に計画する必要があります。

エッジサーバーの外部インターフェイスに割り当てられた証明書は、パブリック証明機関 (CA) から要求されます。 ユニファイドコミュニケーションの目的で証明書の提供が成功したことを示すパブリック Ca は、次の記事に記載されています [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=929395](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=929395) 。 証明書を要求するときは、Lync Server 展開ウィザードによって生成された証明書要求を使用することも、Lync Server 管理シェルコマンドレットまたはパブリック CA によって提供されるプロセスを使用して要求を手動で作成することもできます。 証明書管理用の Lync Server 管理シェルコマンドレットの詳細については、「 [証明書と認証のコマンドレット (Lync server 2013](https://docs.microsoft.com/powershell/module/skype/) )」を参照してください。証明書を割り当てるときは、アクセスエッジサービスインターフェイス、Web 会議エッジサービスインターフェイス、および音声ビデオ認証サービスに証明書が割り当てられます。 音声ビデオ認証サービスを音声ビデオエッジサービスと混同しないようにしてください。これは、オーディオおよびビデオストリームを暗号化するために証明書を使用しません。 内部エッジサーバーインターフェイスは、内部 (組織の場合) CA またはパブリック CA からの証明書からの証明書を使用できます。 内部インターフェイス証明書は SN のみを使用し、SAN エントリを必要としたり使用したりすることはありません。

<div>


> [!NOTE]  
> 次の表では、参考のためにサブジェクトの別名一覧の 2 つ目の SIP エントリ (sip.fabrikam.com) を示しています。組織内の各 SIP ドメインに対して、証明書のサブジェクトの別名一覧に記載されている対応する FQDN を追加する必要があります。



</div>

<div>

## <a name="certificates-required-for-single-consolidated-edge-with-private-ip-addresses-using-nat"></a>NAT を使用したプライベート IP アドレスを持つ単一統合エッジで必要な証明書


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>コンポーネント</th>
<th>サブジェクト名 (SN)</th>
<th>サブジェクトの別名 (SAN)/順序</th>
<th>Comments</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>単一の統合エッジ (外部エッジ)</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>証明書は公的 CA のものである必要があります。また、AOL とのパブリック IM 接続を展開する場合は、サーバー EKU およびクライアント EKU が必要です。証明書は、次のエッジの外部エッジ インターフェイスに割り当てられます。</p>
<ul>
<li><p>アクセス エッジ</p></li>
<li><p>会議エッジ</p></li>
<li><p>音声ビデオ エッジ</p></li>
</ul>
<p>SAN は、トポロジ ビルダーの定義に基づいて自動的に証明書に追加されます。追加の SIP ドメインで必要な SAN エントリや、サポートする必要がある他のエントリを追加します。SAN にはサブジェクト名がレプリケートされるため、正常に動作するためにはサブジェクト名が存在している必要があります。</p></td>
</tr>
<tr class="even">
<td><p>単一の統合エッジ (内部エッジ)</p></td>
<td><p>lsedge.contoso.net</p></td>
<td><p>SAN 必要なし</p></td>
<td><p>証明書は、公的 CA またはプライベート CA が発行でき、サーバー EKU が含まれている必要があります。証明書は、内部エッジ インターフェイスに割り当てられます。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="certificate-summary--public-instant-messaging-connectivity"></a>証明書の概要 - パブリック インスタント メッセージング接続


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>コンポーネント</th>
<th>サブジェクト名</th>
<th>サブジェクトの別名 (SAN)/順序</th>
<th>Comments</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部/アクセス エッジ</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>証明書は公的 CA のものである必要があります。また、AOL とのパブリック IM 接続を展開する場合は、サーバー EKU およびクライアント EKU が必要です。証明書は、次のエッジの外部エッジ インターフェイスに割り当てられます。</p>
<ul>
<li><p>アクセス エッジ</p></li>
<li><p>会議エッジ</p></li>
<li><p>音声ビデオ エッジ</p></li>
</ul>
<p>SAN は、トポロジ ビルダーの定義に基づいて自動的に証明書に追加されます。追加の SIP ドメインで必要な SAN エントリや、サポートする必要がある他のエントリを追加します。SAN にはサブジェクト名がレプリケートされるため、正常に動作するためにはサブジェクト名が存在している必要があります。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="certificate-summary-for-extensible-messaging-and-presence-protocol"></a>XMPP (eXtensible Messaging and Presence Protocol) の証明書の概要


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>コンポーネント</th>
<th>サブジェクト名</th>
<th>サブジェクトの別名 (SAN)/順序</th>
<th>Comments</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>エッジサーバーまたはエッジプールのアクセスエッジサービスへの割り当て</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>webcon.contoso.com</p>
<p>sip.contoso.com</p>
<p>sip.fabrikam.com</p>
<p>xmpp.contoso.com</p>
<p><strong>*. contoso.com</strong></p></td>
<td><p>最初の3つの SAN エントリは、完全なエッジサーバーの通常の SAN エントリです。 contoso.com は、ルート ドメイン レベルでの XMPP パートナーとのフェデレーションに必要なエントリです。 このエントリは、suffix *.contoso.com ですべてのドメインに対する XMPP を許可します。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

