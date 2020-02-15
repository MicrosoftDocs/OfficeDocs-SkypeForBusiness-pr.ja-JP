---
title: 'Lync Server 2013: モビリティの特徴と機能'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobility features and capabilities
ms:assetid: 12517a88-2531-44a5-bea5-d8884aff53eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689983(v=OCS.15)
ms:contentKeyID: 48183457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ac62cb2fe222a2a36c0fc0aeb79a4aaa37e9964
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044829"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobility-features-and-capabilities-in-lync-server-2013"></a>Lync Server 2013 のモビリティ機能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-19_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013 の累積的な更新プログラムで導入されたモビリティ機能: 2 月2013は Lync 2010 Mobile および Lync 2013 Mobile クライアント機能をサポートしています。 Lync Server 2013 Mobility Service を展開すると、ユーザーはサポートされている Apple iOS、Android、Windows Phone、または Nokia Symbian モバイルデバイスを使用して、インスタントメッセージの送受信、連絡先の表示、プレゼンスの表示などのアクティビティを実行できます。 また、クリックして会議に参加、勤務先から通話、同一番号接続、ボイス メール、不在着信など、モバイル デバイスでいくつかのエンタープライズ VoIP 機能がサポートされます。 Lync Server 2013 の累積的な更新プログラムで導入された新機能: 2 月2013には、会議の出席者のボイスオーバー IP (VoIP) 機能とビデオ (.H) が含まれています。

Lync Server 2013 の累積的な更新プログラムで導入されたモビリティ機能: 2 月2013は Lync 2013 Mobile クライアント機能をサポートしています。 Lync Server 2013 の累積的な更新プログラム: 2 月2013統合コミュニケーション Web API または UCWA。 UCWA は、Lync 2013 モバイルクライアントに使用されるコンポーネントです。 Lync Server 2013 では、Mcx が Lync 2010 モバイルクライアントに使用されます。 Lync Server 2013 の累積的な更新プログラム: 2 月2013は、mobility services の新しいエントリポイントとして UCWA を導入します。 Lync Server 2013 は、Lync Server 2010:11 月2011の累積的な更新プログラムで導入された Mobility Service (Mcx) を同時に実装し、Lync 2010 Mobile のサポートを提供します。 Lync Server 2013 の累積的な更新プログラム (2 月 2013) を展開する場合、ユーザーはサポートされている Apple iOS、Android、および Windows Phone モバイルデバイスを使用して、次のような操作を実行できます。

<div>


> [!IMPORTANT]  
> Mobility Service でサポートされている機能 (Lync Server 2010 の累積的な更新プログラム):11 月2011は、(Mcx) で示されています。 リストされているすべての機能は、Lync Server 2013 の累積的な更新プログラムで導入された、UCWA でサポートされています (2013 年2月)。



</div>

  - インスタントメッセージを送受信する (Mcx)

  - プレゼンスの表示 (Mcx)

  - 連絡先を表示する (Mcx)

  - クリックして会議に参加する (Mcx)

  - 勤務先から通話 (Mcx)

  - 単一番号のリーチ (Mcx)

  - ボイスメール (Mcx)

  - 不在着信通知 (Mcx)

  - ボイス オーバー IP (VoIP)

  - 出席者のビデオ (.H)

<div>


> [!NOTE]  
> Lync 2010 Mobile には、Nokia Symbian デバイス用のクライアントが用意されています。 Lync 2013 Mobile には、Nokia Symbian ベースのデバイスのクライアントはありません。



</div>

Apple iPad ユーザーは強化機能を利用できるようになります。 音声通話を使用して会議に参加した後、iPad ユーザーは、会議内でアップロードされた Microsoft PowerPoint プレゼンテーションを表示したり、アプリケーションやデスクトップを共有したり、会議参加者リストを表示したり、その他のコンテンツタイプの通知を受信したりできます。が会議内で共有されている。

<div>


> [!TIP]  
> 1つの番号がある場合、ユーザーは勤務先番号にダイヤルされた携帯電話の通話を受信します。 [勤務先から通話] を使用すると、ユーザーは携帯電話番号ではなく勤務先電話番号を使用して Lync Mobile クライアントからの発信通話を配置します。 ダイヤルアウトの場合、クライアントは Mcx または UCWA (Lync Mobile バージョンに基づいて) に要求を送信して、それらの呼び出しを行います。 サーバーは通話を開始し、ユーザーに電話をかけ直します。 ユーザーが応答すると、サーバーは相手をダイヤルして通話を完了します。 通話による通話を使用することで、ユーザーは通話中に作業の id を維持することができます。つまり、通話受信者は発信者の携帯電話番号を表示せず、発信者が発信通話料金を発生させないようにします。



</div>

<div>


> [!NOTE]  
> すべてのモバイル デバイスですべての機能がまったく同じように動作するとは限りません。 モバイルデバイスでサポートされている機能の詳細については、 <A href="http://go.microsoft.com/fwlink/p/?linkid=234777">http://go.microsoft.com/fwlink/p/?LinkId=234777</A>「」のモバイルクライアントの比較表を参照してください。 サポートされているデバイスとオペレーティングシステムの詳細については、「 <A href="lync-server-2013-planning-for-mobile-clients.md">Planning for mobile clients In Lync Server 2013</A>」の「要件」のトピックを参照してください。



</div>

Lync Server 2013 自動検出機能を使用すると、モバイルアプリケーションは、ユーザーが自分のデバイス設定に Url を手動で入力する必要なく、Lync Server 2013 Web サービスを自動的に検索できます。 URL をモバイル デバイスの設定に手動で入力することも、主にトラブルシューティングの目的でサポートされます。

<div>


> [!IMPORTANT]  
> Mcx および UCWA は補完的なサービスで、両方とも、Lync 2010 Mobile および Lync 2013 モバイルクライアントをサポートするために展開されています。 Lync 2013 Mobile は Lync Server 2010 の展開にサインインできません。 Lync 2010 Mobile および Lync 2013 Mobile は、lync Server 2013 の累積的な更新プログラムで Lync Server 2013 展開を使用できるようになります。 2 2013 月適用。



</div>

モビリティ機能では、バックグラウンドで実行されているアプリケーションをサポートしないモバイル デバイス用のプッシュ通知** もサポートされます。 プッシュ通知は、モバイル アプリケーションが非アクティブなときに発生したイベントについてモバイル デバイスに送信される通知です。 たとえば、不在着信したインスタントメッセージング (IM) の招待には、プッシュ通知が発生することがあります。

Mcx、UCWA、自動検出サービス、およびプッシュ通知のサポートは、Lync Server 2013 で提供されます。 Lync Server 2013 の累積的な更新プログラム (2013 年2月) でのモビリティエントリポイントの導入において、クライアントの機能、機能、および UCWA の使用が更新されました。

</div>

<span> </span>

</div>

</div>

</div>

