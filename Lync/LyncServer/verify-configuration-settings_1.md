---
title: 構成の設定の確認
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify configuration settings
ms:assetid: 41dbf91c-f2e1-4b9a-88cf-959575558cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204848(v=OCS.15)
ms:contentKeyID: 48183997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc4d13f3bdd5af1a2c9b90e190775522ea6f11b8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738567"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-configuration-settings"></a>構成の設定の確認

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-28_

トポロジをマージして、 **CsLegacyConfiguration**コマンドレットを実行した後、Office Communications Server 2007 R2 のポリシーと設定が Lync Server 2013 にインポートされたことを確認します。 次の表に、確認する必要があるポリシーと設定を示します。

<div>

## <a name="policies-and-settings-to-verify-after-migration"></a>移行後に確認するポリシーと設定


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>この作業負荷を使用する場合:</th>
<th>以下のポリシーと設定を確認します。</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>インスタントメッセージング (IM) と会議</p></td>
<td><p>プレゼンスポリシー</p>
<p>会議ポリシー</p></td>
</tr>
<tr class="even">
<td><p>ダイヤルイン会議</p></td>
<td><p>ダイヤルインアクセス番号</p>
<p>ダイヤル プラン</p></td>
</tr>
<tr class="odd">
<td><p>エンタープライズ VoIP</p></td>
<td><p>音声ポリシー</p>
<p>音声ルート</p>
<p>ダイヤル プラン</p>
<p>PSTN 使用状況の設定</p></td>
</tr>
<tr class="even">
<td><p>Communicator Web Access</p></td>
<td><p>簡易 URL</p></td>
</tr>
<tr class="odd">
<td><p>外部ユーザー</p></td>
<td><p>外部アクセスポリシー</p></td>
</tr>
<tr class="even">
<td><p>アーカイブ</p></td>
<td><p>アーカイブポリシー</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-verify-policies-and-settings"></a>ポリシーと設定を確認するには

1.  Office Communications Server 2007 R2 環境で、ダイヤルプラン (以前は位置情報プロファイル)、ダイヤルインアクセス番号 (会議アテンダントアクセス電話番号と地域)、音声ルート、および以下に記載されているポリシーの名前をメモしておきます。Communicator Web Access で使用される Url に加えて、前の表が表示されます。

2.  Lync Server 2013 フロントエンドサーバーで、[Lync Server] コントロールパネルを開きます。

3.  インポートした会議ポリシーを確認するには、左側のウィンドウで [**会議**] をクリックし、[**会議ポリシー**] をクリックして、Office Communications Server 2007 R2 環境のすべての会議ポリシーが一覧に含まれていることを確認します。
    
    <div>
    

    > [!NOTE]  
    > 以前のバージョンの Office Communications Server の<STRONG>会議</STRONG>ポリシーは、Lync Server 2013 の会議ポリシーと呼ばれるようになりました。 さらに、以前のバージョンの Office Communications Server からの<STRONG>匿名</STRONG>の管理設定は、Lync Server 2013 会議ポリシーの設定になりました。

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Office Communications Server 2007 R2 で、会議ポリシーが<STRONG>ユーザーごとに使用</STRONG>するように設定されていない場合は、グローバルポリシー設定のみがインポートされます。 この状況では、他の会議ポリシーはインポートされません。

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Office Communications Server 2007 R2 会議ポリシーで<STRONG>ユーザーごとに適用</STRONG>するように<STRONG>匿名の参加者</STRONG>が設定されている場合、移行中に2つの会議ポリシーが作成されます。1つは、 <STRONG>AllowAnonymousParticipantsInMeetings</STRONG>が<STRONG>True</STRONG>に設定されている場合と、 <STRONG>AllowAnonymousParticipantsInMeetings</STRONG>が<STRONG>False</STRONG>に設定されている場合です。

    
    </div>

4.  インポートしたダイヤルプランを確認するには、[**音声ルーティング**]、[**ダイヤルプラン**] の順にクリックし、Office Communicator 2007 R2 環境のすべてのダイヤルプランがリストに含まれていることを確認します。
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 では、<STRONG>位置情報プロファイル</STRONG>は<STRONG>ダイヤルプラン</STRONG>として参照されるようになりました。

    
    </div>

5.  インポートした音声ポリシーを確認するには、[**音声ルーティング**]、[**音声ポリシー**] の順にクリックし、Office Communicator 2007 R2 環境のすべての音声ポリシーが一覧に含まれていることを確認します。
    
    <div>
    

    > [!NOTE]  
    > Office Communications Server 2007 R2 環境で<STRONG>ユーザーごとに使用</STRONG>するようにボイスポリシーが設定されていない場合、グローバルポリシー設定のみがインポートされます。 この状況では、他の音声ポリシーはインポートされません。

    
    </div>

6.  インポートした音声ルートを確認するには、[**音声ルーティング**] をクリックし、[**ルーティング**] をクリックして、Office Communicator 2007 R2 環境のすべてのボイスルートがリストに含まれていることを確認します。

7.  インポートした PSTN 使用状況の設定を確認するには、[**音声ルーティング**] をクリックし、[ **pstn 使用状況**] をクリックして、Office Communicator 2007 R2 環境からの pstn 使用の設定が一覧に含まれていることを確認します。

8.  インポートされた外部アクセスポリシーを確認するには、[**フェデレーションと外部アクセス**] をクリックし、[**外部アクセスポリシー**] をクリックして、Office Communicator 2007 R2 環境のすべての外部アクセスポリシーがリストに含まれていることを確認します。

9.  アーカイブポリシーを確認するには、[**監視およびアーカイブ**] をクリックし、[**アーカイブポリシー**] をクリックして、Office Communications Server 2007 R2 環境のすべてのアーカイブポリシーが一覧に含まれていることを確認します。

10. Lync Server 管理シェルを開きます。

11. プレゼンスポリシーを確認するには、コマンドラインで次のように入力します。
    
        Get-CsPresencePolicy
    
    **Identity**パラメーターの名前を確認して、Office Communications Server 2007 R2 環境のすべてのプレゼンスポリシーがインポートされていることを確認します。

</div>

<div>

## <a name="to-verify-policies-and-settings-by-using-cmdlets"></a>コマンドレットを使用してポリシーと設定を確認するには

1.  Lync Server 管理シェルを開きます。

2.  ポリシーと設定を確認するには、次の表のコマンドレットを実行します。
    
    これらのコマンドレットの構文は、次の例のようになります。
    
        Get-CsConferencingPolicy
    
    これらのコマンドレットの詳細については、次を実行します。
    
        Get-Help <cmdlet name> -Detailed


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>このポリシーまたは設定:</th>
<th>次のコマンドレットを使用します。</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>プレゼンスポリシー</p></td>
<td><p><strong>Get-CsPresencePolicy</strong></p></td>
</tr>
<tr class="even">
<td><p>会議ポリシー</p></td>
<td><p><strong>Get-CsConferencingPolicy</strong></p></td>
</tr>
<tr class="odd">
<td><p>ダイヤルインアクセス番号</p></td>
<td><p><strong>Get-CsDialInConferencingAccessNumber</strong></p></td>
</tr>
<tr class="even">
<td><p>ダイヤル プラン</p></td>
<td><p><strong>Get-CsDialPlan</strong></p></td>
</tr>
<tr class="odd">
<td><p>音声ポリシー</p></td>
<td><p><strong>Get-CsVoicePolicy</strong></p></td>
</tr>
<tr class="even">
<td><p>音声ルート</p></td>
<td><p><strong>Get-CsVoiceRoute</strong></p></td>
</tr>
<tr class="odd">
<td><p>PSTN 使用法</p></td>
<td><p><strong>Get-CsPstnUsage</strong></p></td>
</tr>
<tr class="even">
<td><p>Url</p></td>
<td><p><strong>CsSimpleUrlConfiguration の入手</strong></p></td>
</tr>
<tr class="odd">
<td><p>外部アクセスポリシー</p></td>
<td><p><strong>Get-CsExternalAccessPolicy</strong></p></td>
</tr>
<tr class="even">
<td><p>アーカイブポリシー</p></td>
<td><p><strong>Get-CsArchivingPolicy</strong></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

