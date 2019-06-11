---
title: 'Lync Server 2013: モバイル機能ポリシーを作成または変更する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a mobility policy
ms:assetid: fc2dfea0-2215-440d-9f4b-7c985da29211
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721946(v=OCS.15)
ms:contentKeyID: 49733884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 91d3f03735048ab4354db9653554b6227bb7399e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833793"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-mobility-policy-in-lync-server-2013"></a>Lync Server 2013 でモバイル機能ポリシーを作成または変更する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-23_

モバイルユーザーがインスタントメッセージング (IM)、プレゼンス、連絡先などの Lync 機能に対してサポートされているモバイルデバイスを使用できるようにするには、モビリティーポリシーを作成または変更します。 Lync Server 2013 コントロールパネルまたは Lync Server 2013 Management Shell からモバイルポリシーを作成または変更することができます。

<div>

## <a name="to-create-a-mobility-policy-with-lync-server-control-panel"></a>Lync Server コントロールパネルを使用してモビリティポリシーを作成するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで、[**クライアント**] をクリックし、[**モビリティポリシー** ] ナビゲーションボタンをクリックします。

4.  [**モビリティポリシー** ] ページで、[**新規**] をクリックし、次のいずれかの操作を行います。
    
    1.  サイトモビリティポリシーを作成するには、[**サイトポリシー**] をクリックし、サイトをクリックし、[ **OK**] をクリックして既定の設定を確認し、必要に応じて変更を行います。
    
    2.  ユーザーモビリティポリシーを作成するには、[**ユーザーポリシー**] をクリックし、名前を入力して、既定の設定を確認し、必要に応じて変更を加えます。

5.  [**コミット**] をクリックします。

</div>

<div>

## <a name="to-modify-a-mobility-policy-with-lync-server-control-panel"></a>Lync Server コントロールパネルを使用してモビリティポリシーを変更するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで、[**クライアント**] をクリックし、[**モビリティポリシー** ] ナビゲーションボタンをクリックします。

4.  [**モビリティポリシー** ] ページで、既存のモバイルポリシーのいずれかをクリックします。

5.  [**編集**] メニューの [**詳細の表示**] をクリックします。

6.  いずれかの設定を編集します。

7.  [**コミット**] をクリックします。

</div>

<div>

## <a name="creating-external-access-policies-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用した外部アクセスポリシーの作成

Windows PowerShell と**set-csmobilitypolicy**コマンドレットを使用して、モバイルポリシー (サイトのスコープまたはユーザーごとのスコープ) を作成できます。 さらに、 **Set-set-csmobilitypolicy**コマンドレットを使用して、グローバルポリシーを含む既存のポリシーを変更することもできます。 これらのコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。

<div>

## <a name="to-create-a-mobility-policy-at-the-site-scope"></a>サイトのスコープでモビリティポリシーを作成するには

  - このコマンドを実行すると、Redmond サイトの新しいモビリティポリシーが作成されます。
    
        New-CsMobilityPolicy -Identity "site:Redmond"
    
    パラメーター (必須の Identity パラメーター以外) は前のコマンドで指定されているため、ポリシーではすべてのプロパティに既定値が使用されます。

</div>

<div>

## <a name="to-create-a-mobility-policy-at-the-per-user-scope"></a>ユーザーごとのスコープでモバイルポリシーを作成するには

  - ユーザーごとのスコープでモバイルポリシーを作成するには、ポリシーの一意の Id を指定します。
    
        New-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-a-mobility-policy"></a>モバイル機能ポリシーを作成するときに1つのプロパティの値を変更するには

  - 異なるプロパティ値を使うポリシーを作成するには、適切なパラメーターとパラメーター値を含めます。 たとえば、次のコマンドは、勤務先からの通話を無効にするモビリティーポリシーを作成します。
    
        New-CsMobilityPolicy -Identity "site:Redmond" -EnableOutsideVoice $False

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-a-mobility-policy"></a>モバイル機能ポリシーを作成するときに複数のプロパティ値を変更するには

  - 複数のパラメーターを含めることにより複数のプロパティ値を変更できます。 たとえば、次のコマンドは、機動性と通話の両方を無効にするポリシーを作成します。
    
        New-CsMobilityPolicy "site:Redmond" -EnableMobility $False -EnableOutsideVoice $False

</div>

詳細については、 [set-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy)および[set-csmobilitypolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy)コマンドレットのヘルプトピックを参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのモビリティ ポリシーの構成](lync-server-2013-configuring-mobility-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

