---
title: 'Lync Server 2013: qoe (Quality of Experience) の有効化'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Quality of Experience
ms:assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182583(v=OCS.15)
ms:contentKeyID: 48185385
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 539408bfaa32565ef76312e1b0d96767edecc169
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187870"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-quality-of-experience-in-lync-server-2013"></a>Lync Server 2013 の [qoe (Quality of Experience)] を有効にする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

QoE (Quality of Experience) は、メディアの品質と、通話およびセッションに関係する参加者、デバイス名、ドライバー、IP アドレス、およびエンドポイントの種類についての情報を示す数値データを記録します。 詳細については、「計画」のドキュメントの「 [planning for monitoring In Lync Server 2013](lync-server-2013-planning-for-monitoring.md) 」を参照してください。

組織全体または組織内の各サイトで QoE を有効にするには、次の手順を実行します。

<div>


> [!NOTE]  
> QoE を有効にするには、まず、監視を構成して、監視バック エンド データベースに接続する必要があります。 詳細については、「 <A href="lync-server-2013-deploying-monitoring.md">Lync Server 2013 での監視の展開</A>」を参照してください。



</div>

<div>

## <a name="to-enable-qoe-by-using-lync-server-control-panel"></a>Lync Server コントロールパネルを使用して QoE を有効にするには

1.  RTCUniversalServerAdmins グループのメンバーである (または同等のユーザー権限を持つ) ユーザー アカウント、または CsServerAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、Lync Server 2013 を展開したネットワーク内の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**監視およびアーカイブ**] をクリックし、[**QoE データ**] をクリックします。

4.  [**QoE データ**] ページで、表から該当するコレクションをクリックして、[**操作**]、[**QoE を有効にする**] の順にクリックします。

</div>

<div>

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して QoE を有効にする

QoE を有効にするには、Windows PowerShell と、 **-CsQoEConfiguration の設定**コマンドレットを使用します。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-enable-qoe-for-a-single-location"></a>1 つの場所に対して QoE を有効にするには

  - QoE を有効にするには、EnableQoE パラメーターを True ($True) に設定します。
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True

</div>

<div>

## <a name="to-disable-qoe-for-a-single-location"></a>1 つの場所に対して QoE を無効にするには

  - QoE を無効にするには、EnableQoE パラメーターを False ($False) に設定します。これによって監視がアンインストールされることはありません。QoE データの収集と保存が停止されるだけです。
    
        Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False

</div>

<div>

## <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a>複数の場所の QoE を 1 つのコマンドで有効にするには

  - このコマンドを実行すると、組織内で現在使用されているすべての QoE 構成設定に対して QoE が有効になります。
    
        Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True

</div>

詳細については、「 [-CsQoEConfiguration 設定](https://docs.microsoft.com/powershell/module/skype/Set-CsQoEConfiguration)」を参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 での監視の計画](lync-server-2013-planning-for-monitoring.md)  
[Lync Server 2013 での監視の展開](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

