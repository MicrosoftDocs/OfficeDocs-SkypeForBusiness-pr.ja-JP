---
title: 'Lync Server 2013: モビリティポリシーを作成または変更する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a mobility policy
ms:assetid: fc2dfea0-2215-440d-9f4b-7c985da29211
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721946(v=OCS.15)
ms:contentKeyID: 49733884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a240c55b4478c5cf5f67a4f0774b1979e884b3b0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208003"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-mobility-policy-in-lync-server-2013"></a>Lync Server 2013 でのモビリティポリシーの作成または変更

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

モバイル ユーザーがインスタント メッセージング (IM)、プレゼンス、連絡先などの Lync 機能をサポートしているモバイル デバイスを使用できるよう、モビリティ ポリシーを作成または変更できます。 Lync Server 2013 コントロールパネルまたは Lync Server 2013 管理シェルからモビリティポリシーを作成または変更することができます。

<div>

## <a name="to-create-a-mobility-policy-with-lync-server-control-panel"></a>Lync Server コントロールパネルを使用してモビリティポリシーを作成するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**クライアント**] をクリックし、[**モビリティ ポリシー**] ナビゲーション ボタンをクリックします。

4.  [**モビリティポリシー** ] ページで、[**新規**] をクリックし、次のいずれかの操作を行います。
    
    1.  サイト モビリティ ポリシーを作成するには、[**サイト ポリシー**] をクリックし、サイトをクリックし、[**OK**] をクリックし、既定の設定を確認してから必要に応じて変更を加えます。
    
    2.  ユーザー モビリティ ポリシーを作成するには、[**ユーザー ポリシー**] をクリックし、名前を入力し、既定の設定を確認してから必要に応じて変更を加えます。

5.  [**確定**] をクリックします。

</div>

<div>

## <a name="to-modify-a-mobility-policy-with-lync-server-control-panel"></a>Lync Server コントロールパネルを使用してモビリティポリシーを変更するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**クライアント**] をクリックし、[**モビリティ ポリシー**] ナビゲーション ボタンをクリックします。

4.  [**モビリティポリシー** ] ページで、既存のモビリティポリシーのいずれかをクリックします。

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。

6.  設定を変更します。

7.  [**確定**] をクリックします。

</div>

<div>

## <a name="creating-external-access-policies-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して外部アクセスポリシーを作成する

Windows PowerShell と**get-csmobilitypolicy**コマンドレットを使用して、モビリティポリシー (サイトスコープまたはユーザーごとのスコープで) を作成できます。 加えて、**Set-CsMobilityPolicy** コマンドレットを使って、グローバル ポリシーを含む任意の既存のポリシーを変更できます。 これらのコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-create-a-mobility-policy-at-the-site-scope"></a>サイトスコープでモビリティポリシーを作成するには

  - このコマンドは、Redmond サイトのために新しいモビリティ ポリシーを作成します。
    
        New-CsMobilityPolicy -Identity "site:Redmond"
    
    前のコマンドでパラメーターが指定されていない (必須の Identity パラメーターを除く) ので、ポリシーはすべてのプロパティで既定値を使用します。

</div>

<div>

## <a name="to-create-a-mobility-policy-at-the-per-user-scope"></a>ユーザーごとのスコープでモビリティポリシーを作成するには

  - ユーザーごとのスコープでモビリティ ポリシーを作成するには、ポリシーに固有の Identity を指定します。
    
        New-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-a-mobility-policy"></a>モビリティポリシーの作成時に単一のプロパティ値を変更するには

  - 異なるプロパティ値を使用するポリシーを作成するには、適切なパラメーターおよびパラメーター値を含めます。たとえば、このコマンドは [勤務先から通話] を無効にするモビリティ ポリシーを作成します。
    
        New-CsMobilityPolicy -Identity "site:Redmond" -EnableOutsideVoice $False

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-a-mobility-policy"></a>モビリティポリシーの作成時に複数のプロパティ値を変更するには

  - 複数のプロパティ値は、複数のパラメーターを含めることによって変更できます。たとえば、このコマンドはモビリティと [勤務先から通話] の両方を無効にするポリシーを作成します。
    
        New-CsMobilityPolicy "site:Redmond" -EnableMobility $False -EnableOutsideVoice $False

</div>

詳細については、[New-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy) および [Set-CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy) コマンドレットのヘルプ トピックを参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのモビリティポリシーの構成](lync-server-2013-configuring-mobility-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

