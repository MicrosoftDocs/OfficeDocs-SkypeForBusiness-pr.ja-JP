---
title: Microsoft Lync クライアントのポート範囲の構成
TOCTitle: Microsoft Lync クライアントのポート範囲の構成
ms:assetid: 287d5cea-7ada-461c-9b4a-9da2af315e71
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204760(v=OCS.15)
ms:contentKeyID: 48271625
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Microsoft Lync クライアントのポート範囲の構成

 

_**トピックの最終更新日:** 2015-03-09_

既定では、Lync クライアント アプリケーションが通信セッションに参加する場合、1024 ～ 65535 の範囲の任意のポートを使用できます。これは、クライアントに対して特定のポート範囲が自動的には有効化されないためです。ただし、サービス品質 (QoS) を使用するためには、さまざまなトラフィックの種類 (音声、ビデオ、メディア、アプリケーション共有、およびファイル送信) を一意のポート範囲のセットに再割り当てする必要があります。この操作は、Set-CsConferencingConfiguration コマンドレットを使用して実行できます。

Microsoft Lync Server 2013 管理シェルで次のコマンドを実行して、通信セッションで現在使用されているポート範囲を特定できます。

    Get-CsConferencingConfiguration

Lync Server 2013 をインストールした後に会議の設定を変更していない場合は、次のプロパティ値を含む情報が返されます。

    ClientMediaPortRangeEnabled : False
    ClientAudioPort             : 5350
    ClientAudioPortRange        : 40
    ClientVideoPort             : 5350
    ClientVideoPortRange        : 40
    ClientAppSharingPort        : 5350
    ClientAppSharingPortRange   : 40
    ClientFileTransferPort      : 5350
    ClientTransferPortRange     : 40

ここに示した出力には、重要な情報が 2 つ含まれています。1 つ目は、ClientMediaPortRangeEnabled プロパティが False に設定されていることです。

    ClientMediaPortRangeEnabled : False

このことが重要なのは、このプロパティが False に設定されている場合は、Lync クライアントが通信セッションに参加する場合に、他のポート設定 (ClientMediaPort や ClientVideoPort など) にかかわらず 1024 ～ 65535 の範囲の利用可能な任意のポートが使用されるためです。指定したポートのセットのみを使用するように制限する場合 (サービス品質の実装を計画している場合はこのような制限を行います)、最初にクライアントのメディア ポート範囲を有効にする必要があります。メディア ポート範囲の有効化は、次の Windows PowerShell コマンドを使用して実行できます。

    Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True

上記のコマンドを実行すると、会議の構成設定のグローバル コレクションに対してクライアントのメディア ポート範囲が有効化されます。ただし、これらの設定は、サイト範囲またはサービスの範囲 (電話会議サーバー サービスのみ) に対しても適用できます。特定のサイトまたはサーバーに対してクライアントのメディア ポート範囲を有効にするには、Set-CsConferencingConfiguration の呼び出し時にそのサイトまたはサーバーの ID を指定します。

    Set-CsConferencingConfiguration -Identity "site:Redmond" -ClientMediaPortRangeEnabled $True

次のコマンドを使用して、会議のすべての構成設定に対して同時にポート範囲を有効化することもできます。

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration  -ClientMediaPortRangeEnabled $True

2 つ目の重要な情報は、サンプルの出力では、既定で、各種類のネットワーク トラフィックに対して同じメディア ポート範囲が設定されていることです。

    ClientAudioPort             : 5350
    ClientVideoPort             : 5350
    ClientAppSharingPort        : 5350
    ClientFileTransferPort      : 5350

QoS を実装するためには、これらの各ポート範囲が一意であることが必要です。たとえば、次のようにポート範囲を構成します。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>クライアント トラフィックの種類</th>
<th>開始ポート</th>
<th>ポート範囲</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>音声</p></td>
<td><p>50020</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>ビデオ</p></td>
<td><p>58000</p></td>
<td><p>20</p></td>
</tr>
<tr class="odd">
<td><p>アプリケーション共有</p></td>
<td><p>42000</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>ファイル送信</p></td>
<td><p>42020</p></td>
<td><p>20</p></td>
</tr>
</tbody>
</table>


上記の表では、クライアントのポート範囲はサーバーに構成されたポート範囲のサブセットを表しています。たとえば、サーバーではアプリケーション共有が 40803 ～ 49151 のポートを使用するように構成されており、クライアント コンピューターではアプリケーション共有が 42000 ～ 42019 のポートを使用するように構成されています。このように構成されているのは、主に QoS を管理しやすくするためです。クライアントのポートは、サーバーで使用されるポートのサブセットになっている必要はありません (たとえば、クライアント コンピューターで、アプリケーション共有が 10000 ～ 10019 のポートを使用するように構成できます)。ただし、クライアントのポート範囲がサーバーのポート範囲のサブセットになるように構成することをお勧めします。

また、サーバー上でアプリケーション共有のために 8348 個のポートが用意されているにもかかわらず、クライアントでアプリケーション共有のために確保されているポートが 20 個のみであることに気付きます。これも推奨されるルールですが、どのような場合でも必ず守る必要があるルールではありません。一般的に、1 つの利用可能なポートは、それぞれ 1 件の通信セッションを表していると考えることができます。ポート範囲に 100 個の利用可能なポートがある場合は、そのコンピューターが任意の時点で最大 100 件の通信セッションに参加する可能性があることを意味します。通常、サーバーはクライアントよりも多くの通信に参加するため、サーバー上でクライアントよりもはるかに多くのポートが開かれるのは当然のことです。クライアントでアプリケーション共有のために 20 個のポートを確保するということは、ユーザーが、指定したデバイスで同時に 20 のアプリケーション共有セッションに参加できることを意味します。大多数のユーザーにとっては、セッション数が 20 あれば十分です。

上記のポート範囲を会議の構成設定のグローバル コレクションに割り当てるには、次の Lync Server 管理シェル コマンドを使用します。

    Set-CsConferencingConfiguration -Identity global -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

または、次のコマンドを使用して、この同じポート範囲を会議のすべての構成設定に割り当てます。

    Get-CsConferencingConfiguration | Set-CsConferencingConfiguration -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 - ClientFileTransferPort 42020 -ClientFileTransferPortRange 20

これらの変更内容を実際に有効にするには、各ユーザーが一度 Lync からログオフして、再度ログオンする必要があります。

> [!NOTE]
> 1 つのコマンドで、クライアントのメディア ポート範囲を有効化し、これらのポート範囲を割り当てることもできます。次に例を示します。<br />
> <code>Set-CsConferencingConfiguration -ClientMediaPortRangeEnabled $True -ClientAudioPort 50020 -ClientAudioPortRange 20 -ClientVideoPort 58000 -ClientVideoPortRange 20 -ClientAppSharingPort 42000 -ClientAppSharingPortRange 20 -ClientFileTransferPort 42020 -ClientFileTransferPortRange 20</code>

