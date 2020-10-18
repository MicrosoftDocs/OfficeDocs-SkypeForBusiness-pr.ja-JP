---
title: Lync Server 2013 会議の技術要件
description: Lync Server 2013 会議の技術要件。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for conferencing
ms:assetid: 3c0d89e1-53e6-46d7-bf8c-491260b292ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425889(v=OCS.15)
ms:contentKeyID: 48183923
ms.date: 06/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b3b787d84288d789cd0d824081439004f19327e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577123"
---
# <a name="technical-requirements-for-conferencing-in-lync-server-2013"></a>Lync Server 2013 での会議の技術要件

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2014-06-25_

Lync Server 2013 の場合、ダイヤルイン会議、音声ビデオ会議、インスタントメッセージング (IM) 会議、および web 会議機能は、常にフロントエンドサーバー上で実行されます。

ここでは、これらのサーバーのハードウェアおよびソフトウェア要件と、サポートされている併置について詳細に説明します。

ダイヤルイン会議は、さまざまなコンポーネントを含む機能です。 コンポーネントの中には、ダイヤルイン会議固有のものも、エンタープライズ VoIP コンポーネントもあります。 ここでは、ダイヤルイン会議に固有のコンポーネントの要件について説明します。 仲介サーバーと公衆交換電話網 (PSTN) ゲートウェイの要件の詳細については、「計画」のドキュメントの「 [lync server 2013 の仲介サーバーコンポーネント](lync-server-2013-mediation-server-component.md) 」および「 [lync Server 2013 の仲介サーバーのコンポーネントとトポロジ](lync-server-2013-components-and-topologies-for-mediation-server.md) 」を参照してください。

<div>

## <a name="hardware-requirements"></a>ハードウェア要件

Web 会議と音声ビデオ会議はフロントエンドサーバーと併置されているため、サーバーハードウェア要件はフロントエンドサーバーの場合と同じです。 ハードウェア要件の詳細については、「サポート」のドキュメントの「 [Lync server 2013 のサーバーハードウェアプラットフォーム](lync-server-2013-server-hardware-platforms.md) 」を参照してください。 ダイヤルイン会議に必要な次のコンポーネントにも、フロントエンドサーバーと同じハードウェア要件があります。

  - アプリケーション サービス

  - 会議アテンダント アプリケーション

  - 会議アナウンス アプリケーション

フロントエンドサーバーのハードウェア要件は、Lync Server 2013 の他の多くのサーバーの役割と同じですが、次の表ではその概要について説明します。

</div>

<div>

## <a name="software-requirements"></a>ソフトウェア要件

Web 会議と音声ビデオ会議はフロントエンドサーバーに併置されているため、サーバーソフトウェア要件はフロントエンドサーバーと同じです。 ソフトウェア要件の詳細については、「サポート」のドキュメントの「 [Lync server 2013 のサーバーおよびツールのオペレーティングシステムのサポート](lync-server-2013-server-and-tools-operating-system-support.md) 」を参照してください。

Web 会議の場合、Lync Server 2013 には、PowerPoint プレゼンテーションを処理するために、Office Web Apps および Office Web Apps サーバー (旧称 WAC Server) が必要です。 詳細については、「 [Office Web Apps Server および Lync Server 2013 との統合の構成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)」を参照してください。

ダイヤルイン会議、アプリケーションサービス、会議アテンダントアプリケーション、および会議アナウンスアプリケーションでは、フロントエンドサーバーと同じオペレーティングシステム要件を使用します。 ソフトウェア要件の詳細については、「サポート」のドキュメントの「 [Lync server 2013 のサーバーおよびツールのオペレーティングシステムのサポート](lync-server-2013-server-and-tools-operating-system-support.md) 」を参照してください。

会議アテンダントアプリケーションおよび会議アナウンスアプリケーションでは、フロントエンドサーバーに Windows Media フォーマットランタイムがインストールされている必要があります。 Windows Media フォーマット ランタイムは、保留音、録音済みの名前、および案内で使用される Windows Media オーディオ (WMA) ファイルの再生に必要です。 Windows Server 2012 および Windows Server 2012 R2 を除き、windows Media フォーマットランタイムは、セットアップを実行するときに Windows デスクトップの機能の一部として自動的にインストールされますが、コンピューターを再起動する必要がある場合があります。 したがって、セットアップの実行前に、Windows Media フォーマット ランタイムが含まれる Windows デスクトップ エクスペリエンスの一部としてインストールすることをお勧めします。 Windows Server 2012 および Windows Server 2012 R2 には Microsoft Media Foundation が必要です。

</div>

<div>

## <a name="port-requirements-for-dial-in-conferencing"></a>ダイヤルイン会議のポート要件

次の表に、ダイヤルイン会議で使用されるポートを示します。 ロード バランサーを使用する場合は、プールで実行するアプリケーションが使用するポートに合わせてロード バランサーを構成する必要があります。

これらのポートは既定の設定であり、**Set-CsApplicationServer** コマンドレットを使用して変更することができます。 このコマンドレットの詳細については、「Lync Server Management Shell」のドキュメントを参照してください。

<div>


> [!NOTE]  
> 1 つのプール内にある同じアプリケーションのすべてのインスタンスは、同じ SIP リッスン ポートを使用します。



</div>

### <a name="ports-used-by-dial-in-conferencing"></a>ダイヤルイン会議で使用されるポート

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>ポート番号</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>5072</p></td>
<td><p>電話会議アテンダントアプリケーションによる SIP リスニング要求の使用</p></td>
</tr>
<tr class="even">
<td><p>5073</p></td>
<td><p>電話会議アナウンスアプリケーションが SIP リスニング要求のために使用</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients-for-dial-in-conferencing"></a>ダイヤルイン会議でサポートされるクライアント

次のクライアントを使用して、ダイヤルイン アクセスをサポートする社内会議をスケジュールできます。

  - Lync 2013 用オンラインミーティングアドイン (Lync 2013 または出席者をインストールすると自動的にインストールされます)

</div>

<div>

## <a name="dial-in-conferencing-settings-page-requirements"></a>ダイヤルイン会議の設定ページの要件

[ダイヤルイン会議の設定] ページでは、次の表に記載されているオペレーティングシステムと web ブラウザーの組み合わせをサポートしています。

<div>


> [!NOTE]  
> 32 ビットおよび 64 ビット版のオペレーティング システムがサポートされています。



</div>

### <a name="supported-operating-systems-and-web-browsers"></a>サポートされているオペレーティング システムおよび Web ブラウザー

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>オペレーティング システム</th>
<th>Web ブラウザー</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Windows 7</p></td>
<td><p>Internet Explorer 9</p>
<p>Internet Explorer 8</p>
<p>Firefox</p></td>
</tr>
<tr class="even">
<td> </td>
<td> </td>
</tr>
<tr class="odd">
<td> </td>
<td> </td>
</tr>
<tr class="even">
<td><p>Windows Server 2008 R2</p></td>
<td><p>Internet Explorer 9</p>
<p>Internet Explorer 8</p>
<p>Internet Explorer 7</p></td>
</tr>
<tr class="odd">
<td><p>Mac OS</p></td>
<td><p>Firefox</p>
<p>Safari</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="audio-file-requirements-for-dial-in-conferencing"></a>ダイヤルイン会議の音声ファイル要件

Lync Server 2013 では、ダイヤルイン会議の音声プロンプトおよび音楽のカスタマイズはサポートされていません。 ただし、既定のオーディオファイルの変更を必要とする強力なビジネスニーズがある場合は、microsoft サポート技術情報の記事961177、「 [Microsoft Office Communications Server 2007 R2 でダイヤルイン電話会議の音声プロンプトまたは音楽ファイルをカスタマイズする方法](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177)」を参照してください。

[Microsoft Lync Server 会議アテンダントのカスタム音声ガイダンス](https://go.microsoft.com/fwlink/p/?linkid=396880)管理ユーティリティを使用することもできます。これにより、電話の発信者が Lync 会議にカスタムの音声ガイダンスを参加させるときに使用する既定の音声ガイダンスを置き換えることができます。 カスタム音声プロンプトは、Lync Server 2010 または Lync Server 2013 (Enterprise または Standard Edition) を実行しているサーバーにインストールできます。

会議アテンダントアプリケーションおよび会議アナウンスアプリケーションには、保留音、録音済みの名前、および音声ガイダンスファイルに関する次の要件があります。

  - Windows Media Audio (WMA) ファイル形式

  - 16 ビット モノラル

  - 48 Kbps 2-pass CBR (固定ビット レート)

  - -24DB の音声レベル

</div>

<div>

## <a name="user-requirements-for-dial-in-conferencing"></a>ダイヤルイン会議のユーザー要件

ダイヤルイン会議ユーザーは、そのアカウントに固有の電話番号または内線番号を割り当てておく必要があります。 この要件によりダイヤルイン会議中の認証が可能になります。 エンタープライズユーザー (つまり、組織内の Active Directory ドメインサービス資格情報と Lync Server アカウントを持つユーザー) は、電話番号 (または内線番号) と個人識別番号 (PIN) を入力して、認証済みユーザーとして会議にダイヤルインします。

</div>

</div>

<span> </span>

</div>

</div>

</div>

