---
title: Lync Server 2013 の会議の技術要件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Technical requirements for conferencing
ms:assetid: 3c0d89e1-53e6-46d7-bf8c-491260b292ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425889(v=OCS.15)
ms:contentKeyID: 48183923
ms.date: 06/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 719bd7f8de6fd7356a6b2e454cc86e9aa85abd6e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848551"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-conferencing-in-lync-server-2013"></a>Lync Server 2013 の会議の技術要件

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2014-06-25_

Lync Server 2013、ダイヤルイン会議、A/V 会議、インスタントメッセージング (IM) 会議、および web 会議機能は、常にフロントエンドサーバーで実行されます。

このセクションでは、サポートされている collocation と共に、これらのサーバーのハードウェアとソフトウェアの要件について詳しく説明します。

ダイヤルイン会議は、さまざまなコンポーネントが含まれている機能です。 一部のコンポーネントは、ダイヤルイン会議に固有であり、一部はエンタープライズボイスコンポーネントです。 このセクションでは、ダイヤルイン会議に固有のコンポーネントの要件について説明します。 仲介サーバーと公衆交換電話網 (PSTN) ゲートウェイの要件の詳細については、「 [Lync server 2013 の仲介サーバーコンポーネント](lync-server-2013-mediation-server-component.md)」および「計画の[lync server 2013 での仲介サーバーのコンポーネントとトポロジ](lync-server-2013-components-and-topologies-for-mediation-server.md)」を参照してください。documentation.

<div>

## <a name="hardware-requirements"></a>ハードウェア要件

Web 会議と A/V の会議はフロントエンドサーバーと連携しているため、サーバーハードウェア要件は、フロントエンドサーバーの場合と同じです。 ハードウェア要件の詳細については、サポートドキュメントの「[サーバーハードウェアプラットフォーム (Lync server 2013 の場合](lync-server-2013-server-hardware-platforms.md))」を参照してください。 ダイヤルイン会議に必要な次のコンポーネントについても、フロントエンドサーバーと同じハードウェア要件があります。

  - アプリケーション サービス

  - 会議アテンダント アプリケーション

  - 会議アナウンス アプリケーション

フロントエンドサーバーのハードウェア要件は、Lync Server 2013 のその他の多くのサーバーの役割と同じで、次の表で説明します。

</div>

<div>

## <a name="software-requirements"></a>ソフトウェア要件

Web 会議と A/V の会議はフロントエンドサーバーと連携しているため、サーバーソフトウェアの要件は、フロントエンドサーバーの場合と同じです。 ソフトウェア要件の詳細については、サポートドキュメントの「 [Lync server 2013 でのサーバーとツールのオペレーティングシステムのサポート](lync-server-2013-server-and-tools-operating-system-support.md)」を参照してください。

Web 会議の場合は、Lync Server 2013 では、Office Web Apps と Office Web apps サーバー (旧 WAC Server) で PowerPoint プレゼンテーションを処理する必要があります。 詳細については、「 [Office Web Apps サーバーおよび Lync server 2013 との統合を構成する](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)」を参照してください。

ダイヤルイン会議、アプリケーションサービス、会議アテンダントアプリケーション、会議アナウンスメントアプリケーションには、フロントエンドサーバーと同じオペレーティングシステム要件があります。 ソフトウェア要件の詳細については、サポートドキュメントの「 [Lync server 2013 でのサーバーとツールのオペレーティングシステムのサポート](lync-server-2013-server-and-tools-operating-system-support.md)」を参照してください。

会議アテンダントアプリケーションと会議アナウンスメントアプリケーションでは、Windows Media Format Runtime がフロントエンドサーバーにインストールされている必要があります。 Windows Media 形式ランタイムは、音楽の保留、記録された名前、およびプロンプトに使用される Windows Media audio (WMA) ファイルを再生するために必要です。 Windows Server 2012 と Windows Server 2012 R2 を除き、windows Media 形式ランタイムは、セットアップの実行時に Windows デスクトップエクスペリエンスの一部として自動的にインストールされますが、コンピューターの再起動が必要になる場合もあります。 そのため、windows デスクトップエクスペリエンスの一部としてインストールすることをお勧めします。これには、セットアップを実行する前に Windows Media 形式ランタイムが含まれています。 Windows Server 2012 および Windows Server 2012 R2 には Microsoft メディアファンデーションが必要です。

</div>

<div>

## <a name="port-requirements-for-dial-in-conferencing"></a>ダイヤルイン会議のポート要件

次の表では、ダイヤルイン会議で使用されるポートについて説明します。 ロードバランサーを使用している場合は、プールで実行されるすべてのアプリケーションで使用されているポート用にロードバランサーが構成されていることを確認します。

これらのポートは既定の設定であり、**Set-CsApplicationServer** コマンドレットを使用して変更することができます。 このコマンドレットの詳細については、「Lync Server 管理シェルのドキュメント」を参照してください。

<div>


> [!NOTE]  
> プール内の同じアプリケーションのすべてのインスタンスは、同じ SIP リスニングポートを使用します。



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
<td><p>SIP リスニング要求用の会議アテンダントアプリケーションで使用</p></td>
</tr>
<tr class="even">
<td><p>5073</p></td>
<td><p>SIP リスニング要求の会議アナウンスメントアプリケーションで使用</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supported-clients-for-dial-in-conferencing"></a>ダイヤルイン会議でサポートされているクライアント

次のクライアントを使用して、ダイヤルインアクセスをサポートするオンプレミスの会議をスケジュールすることができます。

  - Lync 2013 用のオンライン会議アドイン (Lync 2013 または出席者をインストールしたときに自動的にインストールされます)

</div>

<div>

## <a name="dial-in-conferencing-settings-page-requirements"></a>ダイヤルイン会議の設定ページの要件

[ダイヤルイン会議の設定] ページでは、次の表に示すオペレーティングシステムと web ブラウザーの組み合わせがサポートされています。

<div>


> [!NOTE]  
> 32ビット版と64ビット版のオペレーティングシステムがサポートされています。



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

## <a name="audio-file-requirements-for-dial-in-conferencing"></a>ダイヤルイン会議のオーディオファイルの要件

Lync Server 2013 は、ダイヤルイン会議の音声メッセージや音楽のカスタマイズをサポートしていません。 ただし、既定のオーディオファイルを変更する必要がある強いビジネスニーズがある場合は、microsoft サポート技術情報の記事961177、「 [Microsoft Office Communications Server でダイヤルイン電話会議の音声メッセージまたは音楽ファイルをカスタマイズする方法」を参照してください。2007 R2](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177)。

[Microsoft Lync Server 会議アテンダントのカスタム音声指示](http://go.microsoft.com/fwlink/p/?linkid=396880)管理ユーティリティを使用することもできます。これにより、管理者は、電話の発信者が、ユーザー設定のプロンプトで Lync 会議に参加したときに使用される既定の音声プロンプトを、会議の入力エクスペリエンスが異なる。 カスタム音声プロンプトは、Lync Server 2010 または Lync Server 2013 (Enterprise または Standard Edition) を実行しているサーバーにインストールできます。

会議アテンダントアプリケーションと会議アナウンスメントアプリケーションには、音楽の保留、記録された名前、およびオーディオプロンプトファイルの次の要件があります。

  - Windows Media Audio (WMA) ファイル形式

  - 16 ビット モノラル

  - 48 Kbps 2-pass CBR (固定ビット レート)

  - -24DB の音声レベル

</div>

<div>

## <a name="user-requirements-for-dial-in-conferencing"></a>ダイヤルイン会議のユーザー要件

ダイヤルイン会議ユーザーは、そのアカウントに固有の電話番号または内線番号を割り当てておく必要があります。 この要件によりダイヤルイン会議中の認証が可能になります。 エンタープライズユーザー (つまり、組織内で Active Directory ドメインサービスの資格情報と Lync Server アカウントを持っているユーザー) は、電話番号 (または内線番号) と暗証番号 (PIN) を入力すると、会議には、認証されたユーザー。

</div>

</div>

<span> </span>

</div>

</div>

</div>

