---
title: Lync Server 2013 の会議の技術要件
TOCTitle: 会議の技術要件
ms:assetid: 3c0d89e1-53e6-46d7-bf8c-491260b292ea
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg425889(v=OCS.15)
ms:contentKeyID: 48271823
ms.date: 07/20/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の会議の技術要件

 

_**トピックの最終更新日:** 2016-12-08_

Lync Server 2013 では、ダイヤルイン会議、音声ビデオ会議、インスタント メッセージング (IM) 会議、および Web 会議の機能は、常に フロント エンド サーバーで実行されます。

ここでは、これらのサーバーのハードウェアおよびソフトウェア要件と、サポートされている併置について詳細に説明します。

ダイヤルイン会議は、さまざまなコンポーネントを含む機能です。コンポーネントの中には、ダイヤルイン会議固有のものも、エンタープライズ VoIP コンポーネントもあります。ここでは、ダイヤルイン会議に固有のコンポーネントの要件について説明します。 仲介サーバーおよび公衆交換電話網 (PSTN) ゲートウェイの要件の詳細については、「計画」のドキュメントの「[Lync Server 2013 の仲介サーバー コンポーネント](lync-server-2013-mediation-server-component.md)」および「[Lync Server 2013 の仲介サーバーのコンポーネントとトポロジ](lync-server-2013-components-and-topologies-for-mediation-server.md)」を参照してください。

## ハードウェア要件

Web 会議と音声ビデオ会議は フロント エンド サーバーに併置されるため、サーバーのハードウェア要件は フロント エンド サーバーの場合と同じです。ハードウェア要件の詳細については、「サポート」のドキュメントの「[Lync Server 2013　用のサーバー ハードウェア プラットフォーム](lync-server-2013-server-hardware-platforms.md)」を参照してください。ダイヤルイン会議で必要な次のコンポーネントのハードウェア要件も、フロント エンド サーバーのハードウェア要件と同じです。

  - アプリケーション サービス

  - 会議アテンダント アプリケーション

  - 会議アナウンス アプリケーション

フロント エンド サーバーのハードウェア要件は、Lync Server 2013 のその他の多くのサーバーの役割と同じです。概要については、次の表を参照してください。

## ソフトウェア要件

Web 会議と音声ビデオ会議は フロント エンド サーバーに併置されるため、サーバーのソフトウェア要件は フロント エンド サーバーの場合と同じです。ソフトウェア要件の詳細については、「サポート」のドキュメントの「[Lync Server 2013 でのサーバーおよびツールのオペレーティング システムのサポート](lync-server-2013-server-and-tools-operating-system-support.md)」を参照してください。

Web 会議については、PowerPoint プレゼンテーションを処理できるように、Lync Server 2013 には Office Web Apps および Office Web Apps サーバー (以前の WAC Server) も必要です。詳細については、「[Lync Server 2013 と Office Web Apps サーバーの統合の構成](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md)」を参照してください。

ダイヤルイン会議、アプリケーション サービス、会議アテンダント アプリケーション、および 会議アナウンス アプリケーションのオペレーティング システム要件は、フロント エンド サーバーの場合と同じです。ソフトウェア要件の詳細については、「サポート」のドキュメントの「[Lync Server 2013 でのサーバーおよびツールのオペレーティング システムのサポート](lync-server-2013-server-and-tools-operating-system-support.md)」を参照してください。

会議アテンダント アプリケーションと 会議アナウンス アプリケーションでは、フロント エンド サーバーに Windows Media フォーマット ランタイムをインストールする必要があります。Windows Media フォーマット ランタイムは、保留音、録音済みの名前、案内で使用される Windows Media オーディオ (WMA) ファイルの再生に必要です。 Windows Server 2012 と Windows Server 2012 R2 を除き、Windows Media フォーマット ランタイムはセットアップの実行時に Windows デスクトップ エクスペリエンスの一部として自動的にインストールされますが、コンピューターの再起動が必要な場合があります。したがって、セットアップの実行前に、Windows Media フォーマット ランタイムが含まれる Windows デスクトップ エクスペリエンスの一部としてインストールすることをお勧めします。 Windows Server 2012 と Windows Server 2012 R2 には Microsoft Media Foundation が必要です。

## ダイヤルイン会議のポート要件

次の表に、ダイヤルイン会議で使用されるポートを示します。ロード バランサーを使用する場合は、プールで実行するアプリケーションが使用するポートに合わせてロード バランサーを構成する必要があります。

これらのポートは既定の設定であり、**Set-CsApplicationServer** コマンドレットを使用して変更することができます。このコマンドレットの詳細については、「Lync Server 管理シェル」のドキュメントを参照してください。

> [!NOTE]
> 1 つのプール内にある同じアプリケーションのすべてのインスタンスは、同じ SIP リッスン ポートを使用します。


### ダイヤルイン会議で使用されるポート

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
<td><p>会議アテンダント アプリケーションが SIP リッスン要求のために使用</p></td>
</tr>
<tr class="even">
<td><p>5073</p></td>
<td><p>会議アナウンス アプリケーションが SIP リッスン要求のために使用</p></td>
</tr>
</tbody>
</table>


## ダイヤルイン会議でサポートされるクライアント

次のクライアントを使用して、ダイヤルイン アクセスをサポートする社内会議をスケジュールできます。

  - Lync 2013 用オンライン ミーティング アドイン (Lync 2013 または Attendee のインストール時に自動的にインストールされます)

## ダイヤルイン会議の設定ページの要件

ダイヤルイン会議の設定ページは、次の表に記載されているオペレーティング システムと Web ブラウザーの組み合わせをサポートします。

> [!NOTE]
> 32 ビットおよび 64 ビット版のオペレーティング システムがサポートされています。


### サポートされているオペレーティング システムおよび Web ブラウザー

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


## ダイヤルイン会議の音声ファイル要件

Lync Server 2013 は、音声案内とダイヤルイン会議用の音楽のカスタマイズはサポートしません。ただし、業務に役立てるために既定のオーディオ ファイルをどうしても変更しなければならない場合は、次の Web サイトで入手できるマイクロソフト サポート技術情報の記事 961177「[ハウツー解説: 音声プロンプトまたはダイヤルイン オーディオ会議で Microsoft Office Communications Server 2007 R2 の音楽ファイルをカスタマイズするには](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=961177)」を参照してください。

「[Microsoft Lync Server 会議アテンダントのカスタム音声プロンプト (英語)](http://go.microsoft.com/fwlink/p/?linkid=396880)」の管理ユーティリティも使用できます。管理者はこのユーティリティを使用して、電話の発信者が Lync 会議に参加する場合に使用する既定の音声プロンプトをカスタム プロンプトに置き換え、別の会議参加エクスペリエンスを提供できます。カスタム音声プロンプトは、Lync Server 2010 または Lync Server 2013 の Enterprise Edition または Standard Edition を実行しているサーバーにインストールできます。

会議アテンダント アプリケーションおよび 会議アナウンス アプリケーションには、保留音、録音済みの名前、および音声案内ファイルに関する次の要件があります。

  - Windows Media Audio (WMA) ファイル形式

  - 16 ビット モノラル

  - 48 Kbps 2-pass CBR (固定ビット レート)

  - \-24DB の音声レベル

## ダイヤルイン会議のユーザー要件

ダイヤルイン会議ユーザーは、そのアカウントに固有の電話番号または内線番号を割り当てておく必要があります。この要件によりダイヤルイン会議中の認証が可能になります。エンタープライズ ユーザー (つまり、Active Directory ドメイン サービス 資格情報と組織内の Lync Server アカウントを持つユーザー) は、その電話番号 (または内線番号) および暗証番号 (PIN) を入力して、認証済みユーザーとして会議にダイヤルインします。

