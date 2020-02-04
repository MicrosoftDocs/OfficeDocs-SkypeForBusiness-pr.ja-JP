---
title: 'Lync Server 2013: E9 の展開チェックリスト-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for E9-1-1
ms:assetid: cc6a656a-6043-4b9b-85c2-5708b9bb1c06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398864(v=OCS.15)
ms:contentKeyID: 48185655
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5efe5c55386eb431c91e798ad960cc510ce33ce1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763451"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-e9-1-1-in-lync-server-2013"></a>Lync Server 2013 の E9-1 の展開チェックリスト

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-03_

強化された 9-1-1 (E9) を効率的に計画するには、次の展開要件を必ず含めてください。

  - E9 を展開するための前提条件-1-1。

  - E9 の展開に必要な手順。-1-1。

<div>

## <a name="deployment-prerequisites-for-e9-1-1"></a>E9-1-1 の展開前提条件

E9-1 を展開する前に、一元管理ストア、フロントエンドプール、Standard Edition サーバー、1つ以上の仲介サーバーまたは仲介サーバー、Lync Server クライアントなど、Lync Server の内部サーバーを既に展開している必要があります。 さらに、E9-1-1 の展開では、認定された E9-1-1 サービス プロバイダーへの SIP トランク、または公衆交換電話網 (PSTN) への緊急位置識別番号 (ELIN) ゲートウェイも必要とします。 Lync Server は、米国内でのみ E9 サービスプロバイダーを使用することをサポートしています。

</div>

<div>

## <a name="deployment-process"></a>展開プロセス

次の表に、E9-1-1 展開プロセスの概要を示します。 展開手順の詳細については、展開ドキュメントの「 [Lync Server 2013 で強化](lync-server-2013-configure-enhanced-9-1-1.md)された9-1-1 を構成する」を参照してください。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>段階</th>
<th>手順</th>
<th>役割</th>
<th>「展開」のドキュメント</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>音声使用、ルート、およびトランクを構成する</p></td>
<td><ol>
<li><p>新しい PSTN 使用法レコードを作成します。これは、場所のポリシーの [<strong>PSTN の使用法</strong>] 設定で使用する名前と同じです。</p></li>
<li><p>前のステップで作成した PSTN 使用法レコードに対するボイス ルートを作成するか割り当て、ゲートウェイ属性が E9-1-1 SIP トランクまたは ELIN ゲートウェイを指すようにします。 </p></li>
<li><p>SIP トランク E9-1-1 サービス プロバイダーの場合は、<strong>Set-CsTrunkConfiguration –EnablePIDFLOSupport</strong> コマンドレットを使用して、SIP 経由の E9-1-1 呼び出しを処理するトランクが PIDF-LO データを渡すように設定します。</p></li>
<li><p>必要に応じて、SIP トランク E9-1-1 サービス プロバイダーの場合は、E9-1-1 サービス プロバイダーの SIP トランクによって処理されない呼び出しに対するローカル PSTN ルートを作成するか、割り当てます。このルートは、E9-1-1 サービス プロバイダーへの接続が利用できない場合に使用されます。E9-1-1 サービス プロバイダーがサポートしている場合は、911 ダイヤル文字列を国または地域の Emergency Call Response Center (ECRC) の Direct Inward Dialing (DID) 番号に変換するトランク構成ルールをゲートウェイに割り当てます。</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p></td>
<td><p><a href="lync-server-2013-configure-an-e9-1-1-voice-route.md">Lync Server 2013 での E9 音声ルートの構成</a></p></td>
</tr>
<tr class="even">
<td><p>場所のポリシーを作成し、ユーザーおよびサブネットに割り当てる</p></td>
<td><ol>
<li><p>グローバルの場所のポリシーを確認します。</p></li>
<li><p>ユーザーレベル スコープで場所のポリシーを作成します。または、組織に緊急使用法が異なる複数のサイトがある場合は、ネットワークレベル スコープで場所のポリシーを作成します。</p></li>
<li><p>場所のポリシーをネットワーク サイトに割り当てます。</p></li>
<li><p>適切なサブネットをネットワーク サイトに追加します。</p></li>
<li><p>(必要に応じて) 場所のポリシーをユーザー ポリシーに割り当てます。</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p>
<p>CSLocationAdmin (場所のポリシーの作成を除く)</p></td>
<td><p><a href="lync-server-2013-create-location-policies.md">Lync Server 2013 で位置情報のポリシーを作成する</a></p>
<p><a href="lync-server-2013-add-a-location-policy-to-a-network-site.md">Lync Server 2013 でネットワークサイトに位置情報ポリシーを追加する</a></p>
<p><a href="lync-server-2013-associate-subnets-with-network-sites-for-e9-1-1.md">Lync Server 2013 での E9-1 のネットワークサイトへのサブネットの関連付け</a></p></td>
</tr>
<tr class="odd">
<td><p>場所データベースを構成する</p></td>
<td><ol>
<li><p>ネットワーク要素と場所のマッピングをデータベースに設定します。</p></li>
<li><p>ELIN ゲートウェイの場合は、[ &lt;CompanyName&gt; ] 列に elins を追加します。</p></li>
<li><p>アドレスを確認するために、E9-1-1 サービス プロバイダーへの接続を構成します。</p></li>
<li><p>E9-1-1 サービス プロバイダーでアドレスを確認します。</p></li>
<li><p>更新したデータベースを公開します。</p></li>
<li><p>ELIN ゲートウェイの場合は、ELIN を PSTN 通信業者の自動ロケーション識別 (ALI) データベースにアップロードします。</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p>
<p>CSLocationAdmin</p></td>
<td><p><a href="lync-server-2013-configure-the-location-database.md">Configure the location database in Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>高度な機能を構成する (オプション)</p></td>
<td><ol>
<li><p>SNMP アプリケーションの URL を構成します。</p></li>
<li><p>セカンダリの場所情報サービスの場所の URL を構成します。</p></li>
</ol></td>
<td><p>CSVoiceAdmin</p></td>
<td><p><a href="lync-server-2013-configure-an-snmp-application.md">Lync Server 2013 での SNMP アプリケーションの構成</a></p>
<p><a href="lync-server-2013-configure-a-secondary-location-information-service.md">Lync Server 2013 でセカンダリ場所情報サービスを構成する</a></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

