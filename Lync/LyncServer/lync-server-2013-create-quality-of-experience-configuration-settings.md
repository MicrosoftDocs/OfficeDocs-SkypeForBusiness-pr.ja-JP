---
title: 'Lync Server 2013: qoe (Quality of Experience) 構成設定の作成'
description: 'Lync Server 2013: qoe (Quality of Experience) 構成設定を作成します。'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create Quality of Experience configuration settings
ms:assetid: 64f05569-07c7-4f76-a96b-ea4125a510d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521006(v=OCS.15)
ms:contentKeyID: 48184357
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 279265f396fc8fcbfba80d195fc587924a2979f5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562193"
---
# <a name="create-quality-of-experience-configuration-settings-in-lync-server-2013"></a>Lync Server 2013 で qoe (Quality of Experience) 構成設定を作成する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

QoE (Quality of Experience) 指標は、ネットワーク パケットの損失数、バックグラウンド ノイズ、"ジッター" (パケット遅延のばらつき) の量など、組織内で行われる音声通話およびビデオ通話の品質を追跡します。これらの指標は、他のデータ (詳細な通話の記録など) とは別にデータベースに格納されます。このため、QoE は他のデータ記録と関係なく有効および無効にすることができます。

Microsoft Lync Server 2013 をインストールすると、QoE 構成設定のグローバルコレクションが1つ作成されます。 管理者は、サイト スコープでカスタム設定を作成することもできます。 これらのサイト スコープの設定は、グローバル設定に優先して使用されます。 たとえば、Redmond サイト用のサイト スコープの設定を作成した場合は、グローバル設定ではなくこれらの設定を使用して Redmond の QoE が管理されます。

QoE 構成設定を作成するには、Lync Server コントロールパネルまたは [新しい-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) コマンドレットを使用します。 Lync Server コントロールパネルを使用して新しい設定を作成する場合は、次のオプションを使用できます。


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
<td><p>ID</p></td>
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


<div>


> [!NOTE]  
> New-CsQoEConfiguration コマンドレットには、Lync Server コントロールパネルでは使用できない追加オプションが含まれています。 詳細については、 <A href="https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration">新しい-CsQoEConfiguration</A> のヘルプトピックを参照してください。



</div>

<div>

## <a name="to-create-qoe-configuration-settings-by-using-lync-server-control-panel"></a>Lync Server コントロールパネルを使用して QoE 構成設定を作成するには

1.  RTCUniversalServerAdmins グループのメンバーとして、または CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。 詳細については、「 [Lync Server 2013 でのセットアップのアクセス許可の委任](lync-server-2013-delegate-setup-permissions.md)」を参照してください。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**監視とアーカイブ**] をクリックし、[**QoE データ**] をクリックします。

4.  [**QoE データ**] ページで、[**新規**] をクリックします。

5.  [**サイトの選択**] でポリシーを適用するサイトをクリックし、[**OK**] をクリックします。

6.  [**新しい QoE の設定**] で、次の手順を実行します。
    
      - [**QoE データの監視を有効にする**] を選択して、監視を有効にします。
    
      - [**QoE データの削除を有効にする**] を選択して、削除を有効にします。
    
      - [**QoE の最大保持期間 (日)**] で、QoE レコードを保持する最大日数を選択します。

7.  [**確定**] をクリックします。

</div>

<div>

## <a name="creating-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して QoE 構成設定を作成する

QoE 構成設定は、Windows PowerShell と New-CsQoEConfiguration コマンドレットを使用して作成できます。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-create-a-new-collection-of-qoe-configuration-settings"></a>QoE 構成設定の新しいコレクションを作成するには

  - 次のコマンドは、Redmond サイトに適用される QoE 構成設定の新しいコレクションを作成します。
    
        New-CsQoEConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-collection-of-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a>QoE 監視が無効になっている QoE 構成設定の新しいコレクションを作成するには

  - 必須である Identity パラメーターを除いて、先行するコマンドでパラメーターが指定されないため、構成設定の新しいコレクションでは、すべてのプロパティで既定値が使用されます。別のプロパティ値を使用する設定を作成するには、単に適切なパラメーターとパラメーター値を指定します。たとえば、QoE レコードを既定で無効にする Quality of Experience 構成設定のコレクションを作成するには、次のようなコマンドを使用します。
    
        New-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-a-new-collection-of-qoe-configuration-settings"></a>QoE 構成設定の新しいコレクションを作成するときに複数のプロパティ値を指定するには

  - 複数のパラメーターを含めることで、複数のプロパティ値を指定できます。たとえば、次のコマンドは、QoE データを 30 日間保持し、古いデータを午前 3 時に削除する新しい設定を構成します。
    
        New-CsQoEConfiguration -Identity "site:Redmond" -KeepQoEDataForDays 30 -PurgeHourOfDay 3

</div>

詳細については、 [新しい-CsQoEConfiguration/](https://docs.microsoft.com/powershell/module/skype/New-CsQoEConfiguration) コマンドレットのヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

