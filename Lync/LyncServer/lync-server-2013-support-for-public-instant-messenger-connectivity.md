---
title: Lync Server 2013 パブリックインスタントメッセンジャー接続のサポート
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Support for public instant messenger connectivity
ms:assetid: 9c6eb500-647b-4ccd-a00e-2b8dd7c44a76
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn458579(v=OCS.15)
ms:contentKeyID: 59170234
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be14e3dedf39883a81a040ed31ae38d2966ab647
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208283"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="support-for-public-instant-messenger-connectivity-in-lync-server-2013"></a>Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-10-07_

<div>

## <a name="support-for-public-instant-messenger-connectivity"></a>パブリックインスタントメッセンジャー接続のサポート

この記事では、パブリック IM 接続 (PIC) のサポートに関する情報を提供します。 PIC は Microsoft Lync の機能です。これにより、組織は lync ユーザーが特定のパブリックインスタントメッセージング (IM) サービスのユーザーと Lync クライアントおよび id を介して接続できるようになります。

エンドユーザーにとっては、顧客、パートナー、およびベンダーとの間で顧客、パートナー、およびベンダーと接続できるという利点があります。 Lync の制御、コンプライアンス、およびアーカイブ機能を維持しながら、1つのリアルタイム通信クライアントをサポートすることでメリットを得られます。 Lync と Skype の接続は、2013年 5[月に公開](https://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx)されていますが、Lync/Office Communications SERVER (OCS)/Live communications SERVER (LCS) を最初に、MSN/Windows LIVE、AOL、および Yahoo に接続する PIC で確立したものに依存しています。Lync と Skype の接続の詳細については、「 [lync-skype の接続](https://office.microsoft.com/lync/lync-skype-connectivity-fx103789635.aspx)」を参照してください。 Windows Live、AOL、および Yahoo とのフェデレーションは、それぞれ有効期限までの経路上にあります。このページには、各サービスの状態が記載されています。

PIC を使用するには、お客様がパブリック IM サービスプロバイダーごとにサービスをアクティブにする必要があります。 これを行う方法の要件と詳細については、「IM サービスプロバイダー」および「お客様の基になるライセンスプログラム」を参照してください。

<div>

## <a name="windows-live-messenger"></a>Windows Live Messenger

Microsoft は、Windows Live Messenger と Skype を一緒にご提供しています。 2013年4月に、メッセンジャーユーザーが Skype For-サインインに移行されました。 メッセンジャーとのフェデレーションを利用している Lync のお客様は、Skype に更新された後であっても、引き続きメッセンジャーの連絡先と通信できるようになります。 Lync 管理者または Lync エンドユーザーがサービスの連続性を維持するために必要なことはありません。また、Lync 内でのこの機能の管理は、Messenger との通信のために維持されています。 

Messenger ユーザーが自分の Microsoft アカウント (Messenger に使用される同じ資格情報) を使用して Skype にサインインするときに、Lync の連絡先を含むすべてのメッセンジャー連絡先 (たとえば、Skype に依存している)。 これらの連絡先については、Skype と Lync 間のプレゼンス情報の共有とインスタントメッセージングを利用できます。 

Lync-Skype 接続-Lync および Skype ユーザー間の連絡先追加、プレゼンス共有、インスタントメッセージング、および音声通話は、すべての Lync お客様が利用できるようになりました。

</div>

<div>

## <a name="yahoo-and-aol-instant-messenger"></a>Yahoo\! および AOL インスタントメッセンジャー

Yahoo とのフェデレーション\! および AOL は、Lync (および Office Communications Server) のお客様のために、エンドツーライフのパスにあります。 これらの各サービスを提供する Microsoft の機能は、Yahoo からのサポートに応じて異なります。\! および AOL は、これらの基礎となる契約が下になります。 両方の Yahoo\! AOL の場合、サービスは2014年6月に継続されます。

  - **Yahoo** Service は2014年6月に継続され、お客様は引き続き Microsoft LYNC パブリック IM 接続ユーザーサブスクリプションライセンス ("PIC USL") を使用してライセンスを供与する必要があります。2012年9月1日時点で、PIC USL は、新規または契約の更新の購入に使用できなくなりました。この日以前に購入したライセンスを持つお客様は、Yahoo とのフェデレーションを続行できます。\! サービスの以前の終了日まで、またはそのライセンスの有効期限が切れるまで。「Lync チームブログ」の[アナウンス](https://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx)を参照してください。2014年6月30日よりも後の契約で PIC ライセンスを持っているお客様は、2014年6月30日以降の期間における支払い額に比例してクレジットを受け取ります。

  - **AOL** -2014 年6月30日に、LYNC の IM 接続 ("PIC") サービスは使用できなくなります。サービスの終了時に顧客の中断を制限するために、お客様の追加のドメインのプロビジョニングは廃止されました。 2014年6月30日まで、お客様は、ターゲットとのフェデレーション通信を引き続きサポートするために何もする必要はありません。 この日以降 (または、その間に追加のドメインをプロビジョニングしたいと考えているお客様の場合)、AOL から直接代替サービスを利用できます。 AOL の新しいサービスの詳細については、「   [AIM を使用して直接フェデレーションを確立](http://aimenterprise.aol.com/pic.php)する (AOL.com で新しいページを開く)」を参照してください。  

</div>

<div>

## <a name="public-im-provider-summary"></a>パブリック IM プロバイダーの概要

次の表は、パブリック IM サービスプロバイダー、Lync とのフェデレーション機能、およびライセンス要件の概要を示しています。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>パブリック IM サービスプロバイダー</th>
<th>フェデレーション機能</th>
<th>ライセンス要件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Skype</p></td>
<td><p>IM、プレゼンス、オーディオ</p></td>
<td><p>Lync Server クライアントアクセスライセンス、Lync Online プラン1/2/3</p></td>
</tr>
<tr class="even">
<td><p>Windows Live Messenger</p></td>
<td><p>IM、プレゼンス、音声ビデオ</p></td>
<td><p>Lync Server クライアントアクセスライセンス (WLM が市場にある限り、サポートされています)</p></td>
</tr>
<tr class="odd">
<td><p>AOL</p></td>
<td><p>IM、プレゼンス</p></td>
<td><p>Lync Server クライアントアクセスライセンス。既存のお客様に対して、2014年6月にサポートされます。</p></td>
</tr>
<tr class="even">
<td><p>Yahoo!</p></td>
<td><p>IM、プレゼンス</p></td>
<td><p>Lync Server クライアントアクセスライセンスに加えて、追加の Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス ("PIC USL") が必要です。 2012年9月の価格リストの時点で、PIC USL は購入できなくなりました。 アクティブなライセンスを持つお客様は、Yahoo! とのフェデレーションを続行できます。 2014年6月30日にサービスがシャットダウンされるまでメッセンジャー。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

