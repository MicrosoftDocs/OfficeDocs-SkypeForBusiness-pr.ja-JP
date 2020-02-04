---
title: Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート
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
ms.openlocfilehash: 2cd3c8cf89b9d5e1637db893b57e6b5955fbcee9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764373"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="support-for-public-instant-messenger-connectivity-in-lync-server-2013"></a>Lync Server 2013 でのパブリックインスタントメッセンジャー接続のサポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-10-07_

<div>

## <a name="support-for-public-instant-messenger-connectivity"></a>パブリックインスタントメッセンジャーの接続のサポート

この記事では、パブリック IM 接続 (PIC) のサポートについて説明します。 PIC は、Microsoft Lync の機能で、組織が lync クライアントや id を通じて、特定のパブリックインスタントメッセージング (IM) サービスのユーザーとつながることができるようにします。

エンドユーザーは、顧客、パートナー、ベンダーとの間で利用できるようになります。 Lync の制御機能、コンプライアンス機能、アーカイブ機能を維持しながら、単一のリアルタイム通信クライアントをサポートすることができます。 Lync-Skype の接続機能は、2013年 5[月に公開](http://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx)されています。 Lync/Office communications SERVER (OCS)/Live communications SERVER (LCS) は、最初に MSN、Windows LIVE、AOL、Yahoo に接続するための PIC で確立されています。Lync-Skype の接続について詳しくは、「 [lync-skype の接続](http://office.microsoft.com/en-us/lync/lync-skype-connectivity-fx103789635.aspx)」をご覧ください。 Windows Live、AOL、Yahoo とのフェデレーションはそれぞれ、ライフサイクルの終了までのパスにあります。このページでは、各サービスの状態が記載されています。

PIC を使用するには、各パブリック IM サービスプロバイダーのサービスをアクティブ化する必要があります。 この方法の要件と詳細は、IM サービスプロバイダーと顧客の基になるライセンスプログラムによって異なります。

<div>

## <a name="windows-live-messenger"></a>Windows Live Messenger

Microsoft は、Windows Live Messenger と Skype を連携させることができました。 2013年4月に、Messenger ユーザーはサインイン時に Skype に移行されました。 Lync とのフェデレーションを利用している Lync のお客様は、Skype に更新した後でも、Messenger の連絡先と通信することができます。 Lync 管理者または Lync のエンドユーザーがサービスの継続性を維持するために必要な操作はありません。また、Lync 内でのこの機能の管理は、Messenger との通信を行う場合と同じです。 

Messenger ユーザーが Microsoft アカウント (つまり、Messenger に使用されるのと同じ資格情報) を使って Skype にサインインしたときに、Lync のフェデレーションを含むすべての Messenger の連絡先が表示されます。 Skype に連絡してください。 この連絡先の Skype と Lync 間のプレゼンス共有とインスタントメッセージ (im) は、ご利用いただけます。 

Lync-Skype 接続-連絡先の追加、プレゼンスの共有、インスタントメッセージング、および Lync と Skype ユーザー間の音声通話は、すべての Lync ユーザーが利用できるようになりました。

</div>

<div>

## <a name="yahoo-and-aol-instant-messenger"></a>!\! AOL のインスタントメッセンジャー

Yahoo とのフェデレーション\! また、AOL は、Lync (および Office Communications Server) のお客様にとって、エンドツーエンドのパスにあります。 これらの各サービスを提供するための Microsoft の機能は、Yahoo のサポートによって異なります。\! および AOL では、これらの契約の基になっています。 両方の Yahoo の場合\! また AOL は、2014年6月に引き続きご利用いただけます。

  - **Yahoo** -サービスは2014年6月に継続され、お客様は引き続き Microsoft LYNC パブリック IM 接続ユーザーサブスクリプションライセンス ("PIC USL") でライセンスを取得する必要があります。2012年9月1日時点で、PIC USL は、新規または更新契約の購入に使用できなくなりました。この日付より前に購入したライセンスをお持ちのお客様は、引き続き Yahoo とのフェデレーションを行うことができます。\! サービス終了日またはライセンスの有効期限が切れるまでの間。Lync チームブログの[お知らせ](http://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx)を参照してください。2014年6月30日以降の契約について、お客様は、2014年6月30日以降の期間における支払い金額に応じてクレジットを受け取ります。

  - **AOL** -2014 年6月30日に、LYNC の IM 接続 ("PIC") サービスは利用できなくなります。サービス終了時に顧客の中断を抑えるため、お客様の追加のドメインのプロビジョニングは廃止されました。 2014年6月30日まで、お客様はターゲットとのフェデレーションコミュニケーションを引き続きサポートするために何もする必要はありません。 この日付 (またはその間に追加のドメインをプロビジョニングしたいお客様向け) には、AOL から直接代替サービスを利用できます。 AOL の新しいサービスの詳細については、「   [AIM と直接フェデレーションを確立](http://aimenterprise.aol.com/pic.php)する (AOL.com で新しいページを開く)」を参照してください。  

</div>

<div>

## <a name="public-im-provider-summary"></a>パブリック IM プロバイダーの概要

次の表では、パブリック IM サービスプロバイダーの概要、Lync とのフェデレーション機能、およびライセンスの要件について説明します。


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
<td><p>IM、プレゼンス、音声</p></td>
<td><p>Lync Server クライアントアクセスライセンス、Lync Online Plan 1/2/3</p></td>
</tr>
<tr class="even">
<td><p>Windows Live Messenger</p></td>
<td><p>IM、プレゼンス、音声/ビデオ</p></td>
<td><p>Lync Server クライアントアクセスライセンス (WLM が市場にある限りサポートされます)</p></td>
</tr>
<tr class="odd">
<td><p>AOL</p></td>
<td><p>IM、プレゼンス</p></td>
<td><p>Lync Server クライアントアクセスライセンス既存のお客様は、2014年6月にサポートされます。</p></td>
</tr>
<tr class="even">
<td><p>Yahoo!</p></td>
<td><p>IM、プレゼンス</p></td>
<td><p>Lync Server クライアントアクセスライセンスに加えて、追加の Microsoft Lync パブリック IM 接続ユーザーサブスクリプションライセンス ("PIC USL") が必要です。 2012年9月の価格表の時点では、PIC USL は購入できなくなりました。 アクティブなライセンスを持つユーザーは Yahoo! とのフェデレーションを続行できる 2014年6月30日にサービスが終了するまでの Messenger。</p></td>
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

