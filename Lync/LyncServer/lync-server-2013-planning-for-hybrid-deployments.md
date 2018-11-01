---
title: 'Lync Server 2013: ハイブリッド Lync Server 展開の計画'
TOCTitle: ハイブリッド Lync Server 展開の計画
ms:assetid: f8b3d240-bc2e-42c9-acf8-d532d641a14c
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205403(v=OCS.15)
ms:contentKeyID: 48274109
ms.date: 06/02/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 ハイブリッド展開の計画

 

_**トピックの最終更新日:** 2016-12-08_

ハイブリッド展開を計画する際は、ユーザーおよびネットワーク インフラストラクチャに対する次の必要条件を考慮する必要があります。

## インフラストラクチャの要件

Lync Server 2013 ハイブリッド展開を実装および構成するためには、ユーザーの環境において次のことが必要です。

  - Lync Online が有効化されている Office 365 テナント。

  - 内部設置型または Microsoft Azure を使用している Active Directory Federation Services (AD FS) Server。AD FS の詳細については、「[Active Directory Federation Services (AD FS) 2.0](http://go.microsoft.com/fwlink/p/?linkid=393795)」または「[Windows Azure Pack 用の Active Directory フェデレーション サービスの構成](http://go.microsoft.com/fwlink/p/?linkid=522475)」を参照してください。

  - Lync Server 2013 または Lync Server 2010 の累積的更新プログラム: 2013 年 3 月以降を適用した Lync Server 2010 の内部設置展開。

  - Lync Server 2013 管理ツール。

  - ディレクトリ同期。ディレクトリ同期の詳細については、「[ハイブリッド ID 管理](http://go.microsoft.com/fwlink/p/?linkid=231010)」を参照してください。

## Lync クライアント サポート

Lync クライアントでサポートされる機能には違いがあります。また、内部設置型環境とオンライン環境で使用できる機能にも違いがあります。ユーザーを組織のどこに置くかを決める前に、Lync Server の各種構成に対するクライアント サポートを確認できます。Lync のハイブリッド展開では、Skype for Business Online で次のクライアントがサポートされます。

  - Lync 2010

  - Lync 2013

  - Lync Windows ストア アプリ

  - Lync Web App

  - Lync Mobile

  - Lync for Mac 2011

  - Lync Room System

  - Lync Basic 2013

クライアント サポートの詳細については、次のトピックを参照してください。

  - [Lync Online のクライアント](http://go.microsoft.com/fwlink/?linkid=281902)

  - [Lync Server 2013 のクライアントの比較表](lync-server-2013-desktop-client-comparison-tables.md)

  - [Lync Server 2013 のモバイル クライアントの比較表](lync-server-2013-mobile-client-comparison-tables.md)

## トポロジ要件

Skype for Business Online とのハイブリッド用の Lync Server 2013 展開を構成するには、次のサポートされているトポロジのいずれかが必要です。

  - Microsoft Office Communications Server 2007 R2 と Lync Server 2013 の内部設置型。 Lync Server 2013 のフェデレーション エッジ サーバーとフェデレーション エッジ サーバーからの次のホップ サーバーで Lync Server 2013 が実行され、中央管理ストアが展開されている必要があります。 エッジ サーバーおよびプールは内部設置型で展開する必要があります。
    

    > [!IMPORTANT]
    > このトポロジをサポートすることにより、一部の機能が制限されることがあります。たとえば、Microsoft Lync Online ユーザーと社内の Office Communications Server 2007 R2 ユーザーの間のプレゼンス情報は想定どおりに機能しない場合があります。



  - Microsoft Lync Server 2010 (Lync Server 2010 の累積的な更新プログラム: 2013 年 3 月を適用済み) と内部設置された Lync Server 2013 管理ツール。フェデレーション エッジ サーバー とフェデレーション エッジ サーバー からの次のホップサーバーで、最新の累積的な更新プログラム 2013 年 3 月以降が適用された Microsoft Lync Server 2010 または Lync Server 2013 が実行されている必要があります。
    

    > [!IMPORTANT]
    > Lync Server 2013 管理ツールは、既存の Lync Server 2010 の展開にアクセスできる別個のサーバーにインストールされている必要があります。ユーザーを内部設置型展開から Lync Online に移動する Move-CsUser コマンドレットは、内部設置型展開に接続されている Lync Server 2013 管理ツールから実行する必要があります。



  - すべてのサーバーで Lync Server 2013 が実行されている Lync Server 2013 展開。

サポートされるトポロジの詳細については、「[Lync Server 2013 でサポートされるトポロジ](lync-server-2013-supported-topologies.md)」、および「[エンタープライズ ハイブリッド展開用の Lync Server 2013 参照トポロジ (Lync Server 2013 Reference Topologies for Enterprise Hybrid Deployments)](http://go.microsoft.com/fwlink/p/?linkid=398709)」を参照してください。

ハイブリッド展開や Lync Online への PowerShell の接続に関するトラブルシューティング情報については、「[Lync Online: Lync PowerShell とハイブリッド トラブルシューティング (Lync Online: Lync PowerShell and Hybrid Troubleshooting)](http://go.microsoft.com/fwlink/p/?linkid=306718)」を参照してください。

## フェデレーション許可/禁止の一覧の要件

許可ドメインの一覧には、パートナー エッジの完全修飾ドメイン名 (FQDN) が構成されているドメインが含まれます。これらは許可パートナー サーバー またはダイレクト フェデレーション パートナー と呼ばれることもあります。オープン フェデレーションとクローズド フェデレーションの違いをよく理解しておくことが必要です。内部設置型展開ではこれらはそれぞれパートナーの検出 および許可パートナー ドメインの一覧 と呼ばれます。

ハイブリッド展開を正しく構成するには、次の必要条件を満たす必要があります。

  - 内部設置型展開と Office 365 テナントでドメイン マッチングの構成を同一にする必要があります。内部設置型展開でパートナーの検出が有効になっている場合、オンライン テナントではオープン フェデレーションを有効にする必要があります。パートナーの検出が無効になっている場合、オンライン テナントではクローズド フェデレーションを構成する必要があります。

  - 内部設置型展開における禁止ドメインの一覧はオンライン テナントの禁止ドメインの一覧と正確に一致する必要があります。

  - 内部設置型展開における許可ドメインの一覧はオンライン テナントの許可ドメインの一覧と正確に一致する必要があります。

  - オンライン テナントの外部通信ではフェデレーションを有効にする必要があります。これは Lync Online のコントロール パネルを使用して構成します。

## DNS の設定

ハイブリッド展開の DNS SRV レコードを作成する場合は、\_sipfederationtls.\_tcp.\<domain\> と \_sip.\_tls.\<domain\> のレコードが内部設置型のアクセス ポリシーを指す必要があります。

## ファイアウォールの考慮

ネットワーク上のコンピューターは、標準のインターネット DNS 参照を実行できる必要があります。これらのコンピューターが標準のインターネット サイトに接続できれば、ネットワークはこの要件を満たしています。

また、Microsoft Online Services データ センターの場所によって、ワイルドカードを使用したドメイン名に基づく接続 (\*.outlook.com からのすべてのトラフィックなど) を受け付けるようにネットワーク ファイアウォール デバイスを構成する必要があります。組織のファイアウォールがワイルドカードを使用した名前の構成方法をサポートしない場合は、許可する IP アドレスの範囲および特定のポートを手動で決める必要があります。

ヘルプ トピック「[Office 365 の URL と IP アドレスの範囲](http://go.microsoft.com/fwlink/p/?linkid=252942)」を参照してください。

## ポートとプロトコルの要件

内部 Lync Server 2013 通信に必要なポートのほかに、次のポートも構成する必要があります。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>プロトコル/ポート</th>
<th>アプリケーション</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TCP 443</p></td>
<td><p>受信を開く</p>
<ul>
<li><p>Active Directory フェデレーション サービス (フェデレーション サーバーの役割)</p>
<p>詳細は、「<a href="http://go.microsoft.com/fwlink/p/?linkid=281899">AD FS の役割サービスとは</a>」を参照してください。</p></li>
<li><p>Active Directory フェデレーション サービス (プロキシ サーバーの役割)</p></li>
<li><p>Microsoft Online Services ポータル</p></li>
<li><p>ポータル サイト</p></li>
<li><p>Outlook Web App</p></li>
<li><p>Lync クライアント (内部設置型の Lync サーバーから Lync Online への通信)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>TCP 80 および 443</p></td>
<td><p>受信を開く</p>
<ul>
<li><p>Microsoft Online Services ディレクトリ同期ツール</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>TCP 5061</p></td>
<td><p>エッジ サーバーで受信/送信を開く</p></td>
</tr>
<tr class="even">
<td><p>PSOM/TLS 443</p></td>
<td><p>データ共有セッションで受信/送信を開く</p></td>
</tr>
<tr class="odd">
<td><p>STUN/TCP 443</p></td>
<td><p>音声、ビデオ、アプリケーション共有セッションで受信/送信を開く</p></td>
</tr>
<tr class="even">
<td><p>STUN/UDP 3478</p></td>
<td><p>音声およびビデオ セッションで受信/送信を開く</p></td>
</tr>
<tr class="odd">
<td><p>RTP/TCP 50000 ～ 59999</p></td>
<td><p>音声およびビデオ セッションで送信を開く</p></td>
</tr>
<tr class="even">
<td><p>TCP 443</p></td>
<td><p>受信を開く</p>
<ul>
<li><p>Active Directory フェデレーション サービス (フェデレーション サーバーの役割)</p>
<p>詳細は、「<a href="http://go.microsoft.com/fwlink/p/?linkid=281899">AD FS の役割サービスとは</a>」を参照してください。</p></li>
<li><p>Active Directory フェデレーション サービス (プロキシ サーバーの役割)</p></li>
<li><p>Microsoft Online Services ポータル</p></li>
<li><p>ポータル サイト</p></li>
<li><p>Outlook Web App</p></li>
<li><p>Lync クライアント (内部設置型の Lync サーバーから Lync Online への通信)</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>TCP 80 および 443</p></td>
<td><p>受信を開く</p>
<ul>
<li><p>Microsoft Online Services ディレクトリ同期ツール</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>TCP 5061</p></td>
<td><p>エッジ サーバーで受信/送信を開く</p></td>
</tr>
<tr class="odd">
<td><p>PSOM/TLS 443</p></td>
<td><p>データ共有セッションで受信/送信を開く</p></td>
</tr>
<tr class="even">
<td><p>STUN/TCP 443</p></td>
<td><p>音声、ビデオ、アプリケーション共有セッションで受信/送信を開く</p></td>
</tr>
<tr class="odd">
<td><p>STUN/UDP 3478</p></td>
<td><p>音声およびビデオ セッションで受信/送信を開く</p></td>
</tr>
<tr class="even">
<td><p>RTP/TCP 50000 ～ 59999</p></td>
<td><p>音声およびビデオ セッションで送信を開く</p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> Office Communications Server 2007 を実行しているパートナーとフェデレーションが必要な場合は、受信/送信 RTP/UDP および RTP/TCP ポート 50000 ～ 59999 を開く必要があります。A/V ファイアウォール要件の詳細については、「<a href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Lync Server 2013 の外部の音声ビデオ ファイアウォールおよびポートの要件を決定する</a>」を参照してください。ポートおよびプロトコルの詳細については、「<a href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">ポートの概要 - Lync Server 2013 の拡張統合エッジ (ロード バランサー機器を使用)</a>」を参照してください。


## ユーザー アカウントおよびデータ

Lync Server 2013 ハイブリッド展開では、ユーザー アカウントが Active Directory ドメイン サービス に作成されるように、内部設置型展開で最初に Lync Online に属するユーザーを作成する必要があります。これで、ユーザーを Skype for Business Online に移動でき、これによりユーザーの連絡先リストが移動します。

AD FS および Dirsync を使用して内部設置型 Lync 展開と Lync Online 展開間のユーザー アカウントを同期する場合、組織内のすべての Lync ユーザーの AD アカウントを内部設置 Lync 展開とオンライン Lync 展開間で同期する必要があります。これは、ユーザーが Lync Online に移動されていない場合でも該当します。すべてのユーザーを同期しない場合、組織の内部設置型展開のユーザーとオンライン ユーザーとの間の通信が正常に動作しない可能性があります。


> [!IMPORTANT]
> Office 365 のオンライン ポータルを使用してユーザーを作成した場合、ユーザー アカウントは内部設置型の Active Directory と同期されず、ユーザーは内部設置型の Active Directory には存在しません。Lync Online でユーザーを作成済みで、内部設置型の Lync Server とハイブリッドを構成する場合は、「<A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Lync Server 2013 での Lync Online から内部設置型 Lync へのユーザーの移動</A>」を参照してください。



また、ハイブリッド展開を計画する場合は、次のユーザー関連の問題も考慮する必要があります。

  - **ユーザーの連絡先**   Lync Online ユーザーの連絡先の上限は 250 です。その数を超えた連絡先は、アカウントが Lync Online に移動されるときにユーザーの連絡先リストから削除されます。

  - **インスタント メッセージングとプレゼンス**   ユーザーの連絡先リスト、グループ、およびアクセス制御リスト (ACL) はユーザー アカウントと一緒に移行されます。

  - **会議データ、会議コンテンツ、および予約済み会議**   このコンテンツはユーザー アカウントと一緒に移行されません。ユーザーは、アカウントが Lync Online に移行された後で会議を予約し直す必要があります。

## ユーザー ポリシーと機能

  - Lync Server 2013 のハイブリッド環境では、ユーザーに対してインスタント メッセージング、音声、および会議の内部設置型またはオンラインでの使用を許可できますが、両方を同時に許可することはできません。

  - **Lync クライアント**   ユーザーによっては、Lync Online への移動時に新しいクライアント バージョンを必要とする場合があります。Office Communications Server 2007 R2 では、ユーザーを Lync Online に移行する前に Lync Server 2013 プールに移動する必要があります。
    
    クライアント サポートの詳細については、「[Lync Online のクライアント](http://go.microsoft.com/fwlink/p/?linkid=281902)」および「[サポートされている Lync クライアントとネットワーク ポートの構成](http://go.microsoft.com/fwlink/p/?linkid=281901)」を参照してください。

  - **内部設置型ポリシーと構成 (非ユーザー)**   オンライン ポリシーと内部設置型ポリシーには個別の構成が必要です。両方に適用されるグローバル ポリシーを設定することはできません。

