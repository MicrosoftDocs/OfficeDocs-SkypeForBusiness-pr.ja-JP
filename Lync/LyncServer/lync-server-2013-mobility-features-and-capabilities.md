---
title: 'Lync Server 2013: モビリティの機能'
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
ms.openlocfilehash: 3e00274e62cc0fe7cf55c45e11a49670c7f1e6a0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758699"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobility-features-and-capabilities-in-lync-server-2013"></a>Lync Server 2013 のモビリティの機能

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-19_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

Lync Server 2013 の累積更新プログラムで導入されたモバイル機能: 2 月2013は Lync 2010 Mobile および Lync 2013 モバイルクライアント機能をサポートしています。 Lync Server 2013 モビリティサービスを展開すると、サポートされている Apple iOS、Android、Windows Phone、Nokia Symbian モバイルデバイスを使って、インスタントメッセージの送受信、連絡先の表示、プレゼンスの表示などの操作を実行できます。 さらに、モバイルデバイスでは、クリックして電話会議に参加したり、勤務先の電話による通話、ボイスメール、不在着信など、一部のエンタープライズ音声機能をサポートしたりします。 Lync Server 2013 の累積更新プログラムで導入された新機能: 2013 年2月電話には、会議出席者のためのボイスオーバー IP (VoIP) 機能とビデオ (.H) が含まれています。

Lync Server 2013 の累積更新プログラムで導入されたモバイル機能: 2013 年2月のモバイルクライアントの機能が2013サポートされています。 Lync Server 2013 向けの累積的な更新プログラム: 年 2 2013 月ユニファイドコミュニケーションの Web API、または UCWA をインストールします。 UCWA は、Lync 2013 モバイルクライアントで使用されるコンポーネントです。 Lync Server 2013 では、Mcx が Lync 2010 モバイルクライアントで使用されます。 Lync Server 2013 の累積更新プログラム: 2013 年2月に、モビリティサービスの新しいエントリポイントとして UCWA が導入されています。 Lync Server 2013 は、Lync Server 2010: 2011 年11月の累積更新プログラムで導入されたモビリティサービス (Mcx) を同時に実装し、Lync 2010 Mobile のサポートを提供します。 Lync Server 2013 2013 の累積更新プログラムを展開する場合、ユーザーはサポートされている Apple iOS、Android、Windows Phone のモバイルデバイスを使用して、次のような操作を実行できます。

<div>


> [!IMPORTANT]  
> Lync Server 2010 の累積的な更新プログラムのモビリティサービスでサポートされている機能: 2011 年11月には、(Mcx) と記載されています。 リストされたすべての機能は、UCWA でサポートされます。 Lync Server 2013 の累積更新プログラムで導入されました。2013年2月。



</div>

  - インスタントメッセージ (Mcx) を送受信する

  - プレゼンスを表示する (Mcx)

  - 連絡先を表示する (Mcx)

  - クリックして会議に参加する (Mcx)

  - 職場での通話 (Mcx)

  - 1つの番号への到達 (Mcx)

  - ボイスメール (Mcx)

  - 不在着信通知 (Mcx)

  - ボイス オーバー IP (VoIP)

  - 出席者のビデオ (H.264)

<div>


> [!NOTE]  
> Lync 2010 Mobile では、Nokia Symbian デバイス用のクライアントが用意されています。 Lync 2013 Mobile には、Nokia Symbian ベースのデバイスのクライアントはありません。



</div>

Apple iPad ユーザーは、強化された機能にアクセスできます。 音声通話を使用して会議に参加した後、iPad ユーザーは、会議中にアップロードされた Microsoft PowerPoint プレゼンテーションを表示したり、アプリケーションとデスクトップを共有したり、会議参加者リストを表示したり、他のコンテンツタイプの通知を受信したりすることができます。会議内で共有されている。

<div>


> [!TIP]  
> 1つの番号に到達すると、勤務先の電話番号にダイヤルされた携帯電話で着信を受けることができます。 勤務先からの通話では、ユーザーは携帯電話番号ではなく勤務先の電話番号を使用して、Lync モバイルクライアントから発信通話を発信します。 ダイヤルアウトの場合、クライアントは Mcx または UCWA (Lync モバイルバージョンに基づく) に要求を送信して、通話を発信します。 サーバーによって通話が開始され、携帯電話に発信されます。 ユーザーが応答すると、相手にダイヤルすることによってサーバーが通話を完了します。 勤務先から通話を使用することで、ユーザーは通話中に作業の id を保持することができます。つまり、通話の受信者には発信者の携帯電話番号が表示されず、発信者は発信通話料金を伴わなくなります。



</div>

<div>


> [!NOTE]  
> すべての機能が、すべてのモバイルデバイスでまったく同じであるとは限りません。 モバイルデバイスでサポートされている機能の詳細については、 <A href="http://go.microsoft.com/fwlink/p/?linkid=234777">http://go.microsoft.com/fwlink/p/?LinkId=234777</A>のモバイルクライアントの比較表を参照してください。 サポートされているデバイスとオペレーティングシステムの詳細については、「 <A href="lync-server-2013-planning-for-mobile-clients.md">Lync Server 2013 のモバイルクライアントの計画</A>」の要件に関するトピックを参照してください。



</div>

Lync Server 2013 自動検出機能を使用すると、モバイルアプリケーションは、ユーザーがデバイスの設定で Url を手動で入力する必要なく、Lync Server 2013 Web サービスを自動的に見つけることができます。 モバイルデバイスの設定では、手動での Url の入力もサポートされます。主にトラブルシューティングを目的としています。

<div>


> [!IMPORTANT]  
> Mcx と UCWA は、無料サービスであり、両方とも Lync 2010 Mobile および Lync 2013 モバイルクライアントをサポートするために展開されています。 Lync 2013 Mobile では、Lync Server 2010 の展開にサインインすることはできません。 Lync 2010 Mobile および Lync 2013 Mobile では、lync server 2013 の累積更新プログラムで Lync Server 2013 の展開を使用できるようになります。2月2013適用されています。



</div>

モビリティ機能では、バックグラウンドで実行されているアプリケーションをサポートしないモバイル デバイス用の*プッシュ通知*もサポートされます。 プッシュ通知は、モバイル アプリケーションが非アクティブなときに発生したイベントについてモバイル デバイスに送信される通知です。 たとえば、不在着信したインスタントメッセージング (IM) 招待は、プッシュ通知につながる可能性があります。

Mcx、UCWA、自動検出サービス、およびプッシュ通知のサポートについては、「Lync Server 2013」をご利用ください。 更新されたクライアント機能、機能、および UCWA の使用は、モビリティーエントリポイントが Lync Server 2013 の累積更新プログラムで導入されています (2013 年2月)。

</div>

<span> </span>

</div>

</div>

</div>

