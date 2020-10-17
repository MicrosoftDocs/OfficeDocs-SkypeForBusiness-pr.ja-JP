---
title: Lync Server 2013 のシナリオを構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Lync Server 2013 Scenarios
ms:assetid: 6705346b-1512-4af3-85e4-64dfa6ee6f80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945596(v=OCS.15)
ms:contentKeyID: 51541420
ms.date: 12/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d108cc3a2c49c40eb04c9039c83689fb8c5abf4c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499944"
---
# <a name="configure-lync-server-2013-scenarios"></a>Lync Server 2013 のシナリオを構成する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2016-12-28_

Lync Server 2013 のストレスおよびパフォーマンスツール (LyncPerfTool) を実行するには、最初に Lync Server 2013 トポロジを、実行するシナリオに対して構成する必要があります。 Lync Server 2013 が構成されていない場合や、正しく構成されていない場合は、ほとんどの場合、負荷シミュレーションは失敗します。 Lync server 2013 のストレスおよびパフォーマンスツールを使用して、lync server の管理シェルスクリプトと基本的なリソースファイルの例をご用意しました。これは、Lync Server 2013 を構成するための開始点として使用できます。 このトピックでは、提供されている Windows PowerShell の例について説明します。 このトピックでは、一般に Lync Server 2013 を構成する方法については説明していないことに注意してください。 Lync Server 2013 での Windows PowerShell の使用の詳細については、「Lync Server Management Shell」のドキュメントを参照してください <https://technet.microsoft.com/library/gg398474.aspx> 。

<div>

## <a name="about-running-lync-server-management-shell-scripts"></a>Lync Server 管理シェルスクリプトの実行について

ここでは、負荷シミュレーションを実行するための準備に使用できる Lync Server 管理シェルスクリプトの例を提供しています。 スクリプトは負荷シミュレーションを目的としているため、単純で寛容なものであるため、運用環境には適していない場合があります。 すべてのスクリプトは例であり、場合によっては、トポロジを反映するように変更する必要があります。 少なくとも、応答グループサービス (RGS) シナリオは、エージェントグループに割り当てられるエージェントを指定するように変更する必要があると考えられます。 ただし、この負荷をシミュレートするオプションはありません。

<div>


> [!WARNING]  
> 提供される例を確認し、理解してください。 スクリプトは、トポロジ内の既存の設定を上書きします。



</div>

<div>


> [!NOTE]  
> Windows PowerShell および Lync Server 管理シェルの使用の詳細については、「Lync Server 2013 Windows PowerShell のブログ」を参照してください <A href="https://go.microsoft.com/fwlink/?linkid=203150">https://go.microsoft.com/fwlink/?LinkId=203150</A> 。



</div>

</div>

<div>

## <a name="stress-and-performance-tool-client-version-monikers"></a>ストレスおよびパフォーマンスツールクライアントバージョンモニカー

既定値の設定を変更した場合、クライアントバージョンチェックポリシーを構成する必要がある場合があります。 詳細については、「」の「サポートされているクライアントバージョンを構成する」を参照してください <https://technet.microsoft.com/library/gg412832(v=ocs.15).aspx> 。 Lync server 2013 のストレスおよびパフォーマンスツールは、Lync Server 2013 と通信するときに既定で次のユーザーエージェントバージョンを使用します。

  - LSPT/15.0.0.0 です (Lync Server 2013 ストレスおよびパフォーマンスツール)

  - OCPHONE/. 0.522

LyncPerfTool のモビリティ (UCWA) クライアントの場合は、次のようになります。

  - Ucwa Perf ツール/Web 会議

  - Ucwa Perf ツール/モバイル

</div>

</div>

<span> </span>

</div>

</div>

</div>

