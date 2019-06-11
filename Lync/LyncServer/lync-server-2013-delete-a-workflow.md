---
title: 'Lync Server 2013: ワークフローを削除する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete a workflow
ms:assetid: 0469a6b8-ce1e-459b-bc3d-4c8adf2d97d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520944(v=OCS.15)
ms:contentKeyID: 48183274
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1aabb1b46d3f67408d586bada6db3d1efaf0538e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833637"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-workflow-in-lync-server-2013"></a>Lync Server 2013 でワークフローを削除する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-11-01_

ワークフローを削除するには、次のいずれかの手順を使用します。

<div>

## <a name="to-use-lync-server-control-panel-delete-a-workflow"></a>Lync Server コントロールパネルを使用するにはワークフローを削除する

1.  RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーション バーで、[**応答グループ**] をクリックし、[**ワークフロー**] をクリックします。

4.  [**ワークフロー**] ページで、[**ワークフローの作成または編集**] をクリックします。

5.  **[サービスの選択**] の検索フィールドに、削除するワークフローをホストしている**ApplicationServer**サービスの名前の一部またはすべてを入力します。

6.  サービスの一覧で、目的のサービスをクリックし、[ **OK]** をクリックします。
    
    <div>
    

    > [!NOTE]  
    > 応答グループ構成ツールの web ページが開きます。 <STRONG>Https://&lt;webpoolfqdn&gt;/RgsConfig</STRONG>に接続して、Web ブラウザーから直接応答グループ構成ツールの web ページを開くこともできます。

    
    </div>

7.  [**既存のワークフローの管理**] で、削除するワークフローを見つけ、[**アクション**] の [**削除**] をクリックします。

8.  [**はい]** をクリックします。

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-a-workflow"></a>Windows PowerShell を使用してワークフローを削除するには

1.  RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  コマンド ラインで、次のコマンドを実行します。
    
        Get-CsRgsWorkflow -Identity <Application Server service> -Name "<name of workflow>" | Remove-CsRgsWorkflow
    
    例:
    
        Get-CsRgsWorkflow -Identity service:ApplicationServer:redmond.contoso.com -Name "Help Desk" | Remove-CsRgsWorkflow

</div>

</div>

<span> </span>

</div>

</div>

</div>

