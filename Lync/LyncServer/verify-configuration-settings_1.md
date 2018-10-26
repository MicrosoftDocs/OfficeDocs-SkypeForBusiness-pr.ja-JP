---
title: 構成設定の確認
TOCTitle: 構成設定の確認
ms:assetid: 41dbf91c-f2e1-4b9a-88cf-959575558cf2
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204848(v=OCS.15)
ms:contentKeyID: 48271902
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 構成設定の確認

 

_**トピックの最終更新日:** 2015-03-09_

トポロジを統合して **Import-CsLegacyConfiguration** コマンドレットを実行した後、Office Communications Server 2007 R2 のポリシーと設定が Lync Server 2013 にインポートされたことを確認します。次の表に、確認が必要なポリシーと設定を示します。

## 移行後に確認が必要なポリシーと設定


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


## ポリシーと設定を確認するには

1.  Office Communications Server 2007 R2 環境で、Communicator Web Access に使用される URL に加えて、ダイヤル プラン (旧称は場所のプロファイル) の名前、ダイヤルイン アクセス番号 (会議アテンダントのアクセス電話番号と地域)、ボイス ルート、および前記の表に示されているポリシーを記録しておきます。

2.  Lync Server 2013 フロントエンド サーバーで、Lync Server コントロール パネルを開きます。

3.  インポートされた会議ポリシーを確認するには、左側のウィンドウで \[**電話会議**\] をクリックし、\[**電話会議ポリシー**\] をクリックして、Office Communications Server 2007 R2 環境のすべての会議ポリシーがリストに含まれていることを確認します。
    
    > [!NOTE]
    > 以前のバージョンの Office Communications Server で <strong>ミーティング</strong> ポリシーと呼ばれていたものは、Lync Server 2013 では会議ポリシーと呼ばれるようになっています。また、以前のバージョンの Office Communications Server での [<strong>匿名参加者</strong>] の設定は、Lync Server 2013 では会議ポリシーの設定になっています。
    
    > [!NOTE]
    > Office Communications Server 2007 R2 で会議ポリシーが [<strong>ユーザー単位のポリシーを使用する</strong>] に設定されていない場合、グローバル ポリシーの設定のみがインポートされます。この場合、他の会議ポリシーはインポートされません。
    
    > [!NOTE]
    > Office Communications Server 2007 R2 の会議ポリシーで [<strong>AnonymousParticipants</strong>] が [<strong>ユーザーごとに適用</strong>] に設定されている場合は、移行時に 2 つの会議ポリシー ([<strong>AllowAnonymousParticipantsInMeetings</strong>] が <strong>True</strong> に設定されているものと [<strong>AllowAnonymousParticipantsInMeetings</strong>] が <strong>False</strong> に設定されているもの) が作成されます。


4.  インポートされたダイヤル プランを確認するには、\[**音声のルーティング**\] をクリックし、\[**ダイヤル プラン**\] をクリックして、Office Communicator 2007 R2 環境のダイヤル プランがリストにすべて含まれていることを確認します。
    
    > [!NOTE]
    > Lync Server 2013 では、[<strong>場所のプロファイル</strong>] は [<strong>ダイヤル プラン</strong>] と呼ばれるようになっています。


5.  インポートされた音声ポリシーを確認するには、\[**音声のルーティング**\] をクリックし、\[**音声ポリシー**\] をクリックして、 Office Communicator 2007 R2 環境の音声ポリシーがリストにすべて含まれていることを確認します。
    
    > [!NOTE]
    > 音声ポリシーが Office Communications Server 2007 R2 環境で [<strong>ユーザー単位のポリシーを使用する</strong>] に設定されていない場合は、グローバル ポリシーの設定のみがインポートされます。この場合、音声ポリシーはインポートされません。


6.  インポートされた音声ルートを確認するには、\[**音声のルーティング**\] をクリックし、\[**ルート**\] をクリックして、Office Communicator 2007 R2 環境の音声ルートがリストにすべて含まれていることを確認します。

7.  インポートされた PSTN 使用法の設定を確認するには、\[**音声のルーティング**\] をクリックし、\[**PSTN 使用法**\] をクリックして、Office Communicator 2007 R2 環境の PSTN 使用法の設定がリストに含まれていることを確認します。

8.  インポートされた外部アクセス ポリシーを確認するには、\[**フェデレーションと外部アクセス**\] をクリックし、\[**外部アクセス ポリシー**\] をクリックして、Office Communicator 2007 R2 環境のすべての外部アクセス ポリシーがリストに含まれていることを確認します。

9.  アーカイブ ポリシーを確認するには、\[**監視およびアーカイブ**\] をクリックし、\[**アーカイブ ポリシー**\] をクリックして、Office Communications Server 2007 R2 環境のアーカイブ ポリシーがリストにすべて含まれていることを確認します。

10. Lync Server 管理シェルを開きます。

11. プレゼンス ポリシーを確認するには、コマンド ラインで次のように入力します。
    
        Get-CsPresencePolicy
    
    **Identity** パラメーターの名前を調べて、Office Communications Server 2007 R2 環境のすべてのプレゼンス ポリシーがインポートされたことを確認します。

## コマンドレットを使用してポリシーと設定を確認するには

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
<td><p>PSTN の使用法</p></td>
<td><p><strong>Get-CsPstnUsage</strong></p></td>
</tr>
<tr class="even">
<td><p>URL</p></td>
<td><p><strong>Get-CsSimpleUrlConfiguration</strong></p></td>
</tr>
<tr class="odd">
<td><p>外部アクセス ポリシー</p></td>
<td><p><strong>Get-CsExternalAccessPolicy</strong></p></td>
</tr>
<tr class="even">
<td><p>アーカイブ ポリシー</p></td>
<td><p><strong>Get-CsArchivingPolicy</strong></p></td>
</tr>
</tbody>
</table>

