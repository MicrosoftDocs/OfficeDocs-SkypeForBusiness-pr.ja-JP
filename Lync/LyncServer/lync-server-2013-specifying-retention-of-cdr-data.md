---
title: 'Lync Server 2013: CDR データの保持を指定する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Specifying retention of CDR data
ms:assetid: c0fd6056-87bc-4136-902a-f1b37cd3a1ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182581(v=OCS.15)
ms:contentKeyID: 48185299
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 32eee413b25da3231d5633e89571bbc08deb1f38
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764453"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="specifying-retention-of-cdr-data-in-lync-server-2013"></a>Lync Server 2013 での CDR データの保持の指定

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

既定では、通話詳細記録 (CDR) データは 60 日後に削除されます。 [**通話詳細記録**] ページの設定を使用して、このデータを既定よりも長期間、または短期間保持できます。 CDR を無効にすると、CDR を有効にする前に取得されたデータも削除の対象になります。

<div>


> [!NOTE]  
> CDR と QoE (Quality of Experience) を構成して、データが同じ日数保持されるようにする必要があります。通話詳細記録 (CDR) 内の各通話は、監視サーバー レポートの Web ページから取得できます。これには、CDR 情報と QoE 情報の両方が含まれます。削除期間が CDR と QoE で異なると、CDR データのみ含む通話がある一方で、QoE データのみ含む通話があることになります。



</div>

CDR データの削除設定を構成するには、次の手順を実行します。

<div>

## <a name="to-specify-retention-of-cdr-data"></a>CDR データの保持期間を指定するには

1.  RTCUniversalServerAdmins グループのメンバーであるか (または同等のユーザー権限を持っている)、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザーアカウントで、Lync Server 2013 を展開したネットワーク上のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**通話詳細記録**] をクリックします。

4.  [**通話詳細記録**] ページで、表から適切なサイトをクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。

5.  削除を有効にするには、[**CDR の削除を有効にする**] を選択します。

6.  [**CDR を保持する最大期間 (日数)**] で、通話詳細記録を保持する必要のある最大日数を選択します。

7.  [**エラー報告データの最大保持期間 (日)**] で、 エラー報告を保持する必要のある最大日数を選択します。

8.  [**確定**] をクリックします。

</div>

<div>

## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して CDR の保持期間を指定する

CDR retention の設定は、Windows PowerShell と CsCdrConfiguration コマンドレットを使って作成できます。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-specify-cdr-retention-for-a-specific-location"></a>特定の場所の CDR の保持期間を指定するには

  - このコマンドを実行すると、レドモンド サイトでの CDR データの削除が有効になり、CDR データとエラー レポートの両方を 20 日間保持するようにサイトが構成されます。
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20

</div>

<div>

## <a name="to-specify-cdr-retention-for-multiple-locations"></a>複数の場所の CDR の保持期間を指定するには

  - このコマンドを実行すると、組織内で使用されているすべての CDR 構成設定に対して CDR の保持期間が構成されます。
    
        Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20

</div>

詳細については、 [CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration)コマンドレットのヘルプトピックを参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での通話の詳細記録 (CDR)](lync-server-2013-call-detail-recording-cdr.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

