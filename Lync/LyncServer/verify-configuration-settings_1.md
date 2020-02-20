---
title: 構成の設定を確認する
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
ms.openlocfilehash: 40beac1b249b09ef493b7f95cbb9380b307eda63
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147900"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-configuration-settings"></a>構成の設定を確認する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-28_

トポロジをマージし、 **import-cslegacyconfiguration**コマンドレットを実行した後、Office Communications Server 2007 R2 のポリシーと設定が Lync Server 2013 にインポートされたことを確認します。 次の表に、確認が必要なポリシーと設定を示します。

<div>

## <a name="policies-and-settings-to-verify-after-migration"></a>移行後に確認が必要なポリシーと設定


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>このワークロードを使用する場合:</th>
<th>確認が必要なポリシーと設定:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>インスタント メッセージング (IM) および電話会議</p></td>
<td><p>プレゼンス ポリシー</p>
<p>会議ポリシー</p></td>
</tr>
<tr class="even">
<td><p>ダイヤルイン会議</p></td>
<td><p>ダイヤルイン アクセス番号</p>
<p>ダイヤル プラン</p></td>
</tr>
<tr class="odd">
<td><p>エンタープライズ VoIP</p></td>
<td><p>音声ポリシー</p>
<p>音声ルート</p>
<p>ダイヤル プラン</p>
<p>PSTN 使用法設定</p></td>
</tr>
<tr class="even">
<td><p>Communicator Web Access</p></td>
<td><p>簡易 URL</p></td>
</tr>
<tr class="odd">
<td><p>外部ユーザー</p></td>
<td><p>外部アクセス ポリシー</p></td>
</tr>
<tr class="even">
<td><p>アーカイブ</p></td>
<td><p>アーカイブ ポリシー</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-verify-policies-and-settings"></a>ポリシーと設定を確認するには

1.  Office Communications Server 2007 R2 環境で、ダイヤルプランの名前 (以前の場所のプロファイル)、ダイヤルインアクセス番号 (会議アテンダントアクセスの電話番号と地域)、音声ルート、およびに一覧表示されているポリシーをメモしてください。前の表。また、Communicator Web Access に使用される Url にも対応しています。

2.  Lync Server 2013 のフロントエンドサーバーで、[Lync Server コントロールパネル] を開きます。

3.  インポートされた電話会議ポリシーを確認するには、左側のウィンドウで [**会議**] をクリックし、[**会議ポリシー**] をクリックして、Office Communications Server 2007 R2 環境のすべての電話会議ポリシーがリストに含まれていることを確認します。
    
    <div>
    

    > [!NOTE]  
    > 以前のバージョンの Office Communications Server からの<STRONG>会議</STRONG>ポリシーは、Lync Server 2013 の会議ポリシーと呼ばれるようになりました。 さらに、以前のバージョンの Office Communications Server からの<STRONG>匿名</STRONG>の管理設定は、Lync Server 2013 の電話会議ポリシーの設定になっています。

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Office Communications Server 2007 R2 では、会議ポリシーが<STRONG>ユーザーごとに使用</STRONG>するように設定されていない場合は、グローバルポリシー設定のみがインポートされます。 この場合、他の会議ポリシーはインポートされません。

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <STRONG>匿名参加者</STRONG>が Office Communications Server 2007 R2 会議ポリシーの<STRONG>ユーザーごとに適用</STRONG>するように設定されている場合は、移行中に2つの会議ポリシーが作成されます。1つは<STRONG>AllowAnonymousParticipantsInMeetings</STRONG>を<STRONG>True</STRONG>に設定し、もう1つは<STRONG>AllowAnonymousParticipantsInMeetings</STRONG>を<STRONG>False</STRONG>に設定します。

    
    </div>

4.  インポートされたダイヤル プランを確認するには、[**音声のルーティング**] をクリックし、[**ダイヤル プラン**] をクリックして、Office Communicator 2007 R2 環境のダイヤル プランがリストにすべて含まれていることを確認します。
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 では、<STRONG>場所のプロファイル</STRONG>が<STRONG>ダイヤルプラン</STRONG>と呼ばれるようになりました。

    
    </div>

5.  インポートされた音声ポリシーを確認するには、[**音声のルーティング**] をクリックし、[**音声ポリシー**] をクリックして、 Office Communicator 2007 R2 環境の音声ポリシーがリストにすべて含まれていることを確認します。
    
    <div>
    

    > [!NOTE]  
    > 音声ポリシーが Office Communications Server 2007 R2 環境の<STRONG>ユーザーごとに使用</STRONG>するように設定されていない場合は、グローバルポリシー設定のみがインポートされます。 この場合、音声ポリシーはインポートされません。

    
    </div>

6.  インポートされた音声ルートを確認するには、[**音声のルーティング**] をクリックし、[**ルート**] をクリックして、Office Communicator 2007 R2 環境の音声ルートがリストにすべて含まれていることを確認します。

7.  インポートされた PSTN 使用法の設定を確認するには、[**音声のルーティング**] をクリックし、[**PSTN 使用法**] をクリックして、Office Communicator 2007 R2 環境の PSTN 使用法の設定がリストに含まれていることを確認します。

8.  インポートされた外部アクセス ポリシーを確認するには、[**フェデレーションと外部アクセス**] をクリックし、[**外部アクセス ポリシー**] をクリックして、Office Communicator 2007 R2 環境のすべての外部アクセス ポリシーがリストに含まれていることを確認します。

9.  アーカイブポリシーを確認するには、[**監視とアーカイブ**] をクリックし、[**アーカイブポリシー**] をクリックして、Office Communications Server 2007 R2 環境のすべてのアーカイブポリシーがリストに含まれていることを確認します。

10. Lync Server 管理シェルを開きます。

11. プレゼンス ポリシーを確認するには、コマンド ラインで次のように入力します。
    
        Get-CsPresencePolicy
    
    **Identity**パラメーターの名前を参照して、Office Communications Server 2007 R2 環境のすべてのプレゼンスポリシーがインポートされたことを確認します。

</div>

<div>

## <a name="to-verify-policies-and-settings-by-using-cmdlets"></a>コマンドレットを使用してポリシーと設定を確認するには

1.  Lync Server 管理シェルを開きます。

2.  次の表に示すコマンドレットを実行して、ポリシーと設定を確認します。
    
    これらのコマンドレットの構文は次のようになります。
    
        Get-CsConferencingPolicy
    
    これらのコマンドレットの詳細については、次のように実行してください。
    
        Get-Help <cmdlet name> -Detailed


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>次のポリシーまたは設定を確認する場合:</th>
<th>使用するコマンドレット:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>プレゼンス ポリシー</p></td>
<td><p><strong>Get-CsPresencePolicy</strong></p></td>
</tr>
<tr class="even">
<td><p>会議ポリシー</p></td>
<td><p><strong>Get-CsConferencingPolicy</strong></p></td>
</tr>
<tr class="odd">
<td><p>ダイヤルイン アクセス番号</p></td>
<td><p><strong>Get-csdialinconferencingaccessnumber</strong></p></td>
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
<td><p><strong>Get-csvoiceroute</strong></p></td>
</tr>
<tr class="odd">
<td><p>PSTN の使用法</p></td>
<td><p><strong>Get-CsPstnUsage</strong></p></td>
</tr>
<tr class="even">
<td><p>URL</p></td>
<td><p><strong>取得-CsSimpleUrlConfiguration</strong></p></td>
</tr>
<tr class="odd">
<td><p>外部アクセス ポリシー</p></td>
<td><p><strong>Get-CsExternalAccessPolicy</strong></p></td>
</tr>
<tr class="even">
<td><p>アーカイブ ポリシー</p></td>
<td><p><strong>Grant-csarchivingpolicy</strong></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

