---
title: 'Lync Server 2013: ワークフローの削除'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a workflow
ms:assetid: 0469a6b8-ce1e-459b-bc3d-4c8adf2d97d5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520944(v=OCS.15)
ms:contentKeyID: 48183274
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b46f3b9bd89df2594c7ca8a3b382839437e40eb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516294"
---
# <a name="delete-a-workflow-in-lync-server-2013"></a>Lync Server 2013 でワークフローを削除する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-11-01_

ワークフローを削除するには、以下に示す手順の 1 つを実行します。

<div>

## <a name="to-use-lync-server-control-panel-delete-a-workflow"></a>Lync Server コントロールパネルを使用するにはワークフローを削除する

1.  RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで、[**応答グループ**] をクリックし、[**ワークフロー**] をクリックします。

4.  [**ワークフロー**] ページで、[**ワークフローの作成または編集**] をクリックします。

5.  [**サービスの選択**] 検索フィールドに、削除するワークフローをホストする **ApplicationServer** サービスの名前、または名前の一部を入力します。

6.  サービスの一覧で、対象のサービスをクリックして、**[OK]** をクリックします。
    
    <div>
    

    > [!NOTE]  
    > 応答グループ構成ツールの web ページが開きます。 <STRONG>Https:// &lt; webpoolfqdn &gt; /RgsConfig</STRONG>に接続することによって、Web ブラウザーから応答グループ構成ツールの web ページを直接開くこともできます。

    
    </div>

7.  [**既存ワークフローの管理**] で、削除するワークフローを見つけて、[**アクション**] の [**削除**] をクリックします。

8.  [**はい**] をクリックします。

</div>

<div>

## <a name="to-use-windows-powershell-to-delete-a-workflow"></a>Windows PowerShell を使用してワークフローを削除するには

1.  RTCUniversalServerAdmins グループのメンバーまたは応答グループをサポートする定義済みの管理者の役割のいずれかのメンバーとしてログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  コマンド ラインで、次のコマンドを実行します。
    
        Get-CsRgsWorkflow -Identity <Application Server service> -Name "<name of workflow>" | Remove-CsRgsWorkflow
    
    次に例を示します。
    
        Get-CsRgsWorkflow -Identity service:ApplicationServer:redmond.contoso.com -Name "Help Desk" | Remove-CsRgsWorkflow

</div>

</div>

<span> </span>

</div>

</div>

</div>

