---
title: 'Lync Server 2013: CDR データの保持期間の指定'
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
ms.openlocfilehash: 3dc5d09e2ebb417f801ddab3f7fb8f444957e9d2
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519564"
---
# <a name="specifying-retention-of-cdr-data-in-lync-server-2013"></a>Lync Server 2013 での CDR データの保持期間の指定

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

既定では、通話詳細記録 (CDR) データは 60 日後に削除されます。 [**通話詳細記録**] ページの設定を使用して、このデータを既定よりも長期間、または短期間保持できます。 CDR を無効にすると、CDR を有効にする前に取得されたデータも削除の対象になります。

<div>


> [!NOTE]  
> CDR と QoE (Quality of Experience) を構成して、データが同じ日数保持されるようにする必要があります。 通話詳細記録 (CDR) 内の各通話は、監視サーバー レポートの Web ページから取得できます。これには、CDR 情報と QoE 情報の両方が含まれます。 削除期間が CDR と QoE で異なると、CDR データのみ含む通話がある一方で、QoE データのみ含む通話があることになります。



</div>

CDR データの削除設定を構成するには、次の手順を実行します。

<div>

## <a name="to-specify-retention-of-cdr-data"></a>CDR データの保持期間を指定するには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Lync Server 2013 を展開したネットワーク内の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで、[**監視とアーカイブ**] をクリックし、[**通話詳細記録**] をクリックします。

4.  [**通話詳細記録**] ページで、表から適切なサイトをクリックし、[**編集**] をクリックしてから、[**詳細の表示**] をクリックします。

5.  削除を有効にするには、[**CDR の削除を有効にする**] を選択します。

6.  [**CDR を保持する最大期間 (日数)**] で、通話詳細記録を保持する必要のある最大日数を選択します。

7.  [**エラー報告データの最大保持期間 (日)**] で、 エラー報告を保持する必要のある最大日数を選択します。

8.  [**確定**] をクリックします。

</div>

<div>

## <a name="specifying-cdr-retention-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用した CDR の保持期間の指定

Windows PowerShell と Set-CsCdrConfiguration コマンドレットを使用して、CDR の保持設定を作成できます。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-specify-cdr-retention-for-a-specific-location"></a>特定のロケーションに対して CDR の保持を指定するには

  - このコマンドを実行すると、レドモンド サイトでの CDR データの削除が有効になり、CDR データとエラー レポートの両方を 20 日間保持するようにサイトが構成されます。
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20

</div>

<div>

## <a name="to-specify-cdr-retention-for-multiple-locations"></a>複数のロケーションに対して CDR の保持を指定するには

  - このコマンドを実行すると、組織内で使用されているすべての CDR 構成設定に対して CDR の保持が構成されます。
    
        Get-CsCdrConfiguration | Set-CsCdrConfiguration-EnablePurging -KeepCallDetailForDays 20 -KeepErrorReportForDays 20

</div>

詳細については、 [set-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) コマンドレットのヘルプトピックを参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での通話詳細記録 (CDR)](lync-server-2013-call-detail-recording-cdr.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

