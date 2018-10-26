---
title: QoE (Quality of Experience) 構成設定の作成
TOCTitle: QoE (Quality of Experience) 構成設定の作成
ms:assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg521006(v=OCS.15)
ms:contentKeyID: 48272273
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# QoE (Quality of Experience) 構成設定の作成

 

_**トピックの最終更新日:** 2015-03-09_

Quality of Experience (QoE) 指標では、失われたネットワーク パケット数、背景ノイズ、"ジッター" (パケット遅延の差分) 量など、組織で行われる音声通話とビデオ通話の品質を追跡します。これらの指標は、他のデータ (詳細な通話の記録など) とは別にデータベースに格納されます。このため、QoE は他のデータ記録と関係なく有効および無効にすることができます。

Microsoft Lync Server 2013 をインストールすると、QoE 構成設定の単一のグローバル コレクションが作成されます。管理者は、サイト スコープでカスタム設定を作成することもできます。これらのサイト スコープの設定は、グローバル設定に優先して使用されます。たとえば、Redmond サイト用のサイト スコープの設定を作成した場合は、グローバル設定ではなくこれらの設定を使用して Redmond の QoE が管理されます。

QoE 構成設定は、Lync Server コントロール パネルまたは [New-CsQoEConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsQoEConfiguration) コマンドレットを使用して作成できます。Lync Server コントロール パネルを使用して新しい設定を作成する場合は、次のオプションを使用できます。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>UI 設定</th>
<th>PowerShell パラメーター</th>
<th>説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>名前</p></td>
<td><p>Identity</p></td>
<td><p>作成される設定の一意の ID。QoE 構成設定は、サイト スコープでのみ作成できます。</p></td>
</tr>
<tr class="even">
<td><p>QoE データの監視を有効にする</p></td>
<td><p>EnableQoE</p></td>
<td><p>QoE レコードを収集し、監視データベースに保存するかどうかを指定します。</p></td>
</tr>
<tr class="odd">
<td><p>QoE データの消去を有効にする</p></td>
<td><p>EnablePurging</p></td>
<td><p>[<strong>QoE データの最大保持期間 (日)</strong>] プロパティに定義された期間が経過した後、レコードを削除するかどうかを指定します。</p></td>
</tr>
<tr class="even">
<td><p>QoE データの最大保存期間 (日)</p></td>
<td><p>KeepQoEDataForDays</p></td>
<td><p>データベースから削除するまで QoE データを保存する日数。削除が無効の場合、この値は無視されます。</p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> New-CsQoEConfiguration コマンドレットには、Lync Server コントロール パネルでは使用できないオプションがあります。詳細については、<a href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsQoEConfiguration">New-CsQoEConfiguration</a>のヘルプ トピックを参照してください。


## QoE 構成設定を Lync Server コントロール パネルを使用して作成するには

1.  RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。詳細については、「[Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**監視とアーカイブ**\] をクリックし、\[**QoE データ**\] をクリックします。

4.  \[**QoE データ**\] ページで、\[**新規**\] をクリックします。

5.  \[**サイトの選択**\] でポリシーを適用するサイトをクリックし、\[**OK**\] をクリックします。

6.  \[**新しい QoE の設定**\] で、次の手順を実行します。
    
      - \[**QoE データの監視を有効にする**\] を選択して、監視を有効にします。
    
      - \[**QoE データの削除を有効にする**\] を選択して、削除を有効にします。
    
      - \[**QoE の最大保持期間 (日)**\] で、QoE レコードを保持する最大日数を選択します。

7.  \[**確定**\] をクリックします。

## QoE 構成設定を Windows PowerShell コマンドレットを使用して作成するには

QoE 構成設定は、Windows PowerShell と New-CsQoEConfiguration コマンドレットを使用して作成することもできます。このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモート セッションから実行できます。リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 ([http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)) を参照してください。

## QoE 構成設定の新しいコレクションを作成するには

  - 次のコマンドは、Redmond サイトに適用される QoE 構成設定の新しいコレクションを作成します。
    
        New-CsQoEConfiguration -Identity "site:Redmond"

## QoE 監視が無効になっている QoE 構成設定の新しいコレクションを作成するには

  - 必須である Identity パラメーターを除いて、先行するコマンドでパラメーターが指定されないため、構成設定の新しいコレクションでは、すべてのプロパティで既定値が使用されます。別のプロパティ値を使用する設定を作成するには、単に適切なパラメーターとパラメーター値を指定します。たとえば、QoE レコードを既定で無効にする Quality of Experience 構成設定のコレクションを作成するには、次のようなコマンドを使用します。
    
        New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

## QoE 構成設定の新しいコレクションを作成するときに複数のプロパティ値を指定するには

  - 複数のパラメーターを含めることで、複数のプロパティ値を指定できます。たとえば、次のコマンドは、QoE データを 30 日間保持し、古いデータを午前 3 時に削除する新しい設定を構成します。
    
        New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3

詳細については、[New-CsQoEConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsQoEConfiguration) コマンドレットのヘルプ トピックを参照してください。

