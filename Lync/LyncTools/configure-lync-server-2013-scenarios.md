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
ms.openlocfilehash: 789c3ee8c18b5fb0e92ef9a520152644bebbdde1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730723"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-lync-server-2013-scenarios"></a>Lync Server 2013 のシナリオを構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2016-12-28_

Lync Server 2013 応力とパフォーマンスツール (LyncPerfTool) を実行するには、最初に Lync Server 2013 トポロジを実行するシナリオに対して構成する必要があります。 Lync Server 2013 が構成されていないか、正しく構成されていない場合、ほとんどの場合、読み込みシミュレーションは失敗します。 Lync server 2013 のストレスとパフォーマンスツールを使って、lync server の管理シェルスクリプトと基本的なリソースファイルの例を提供して、Lync Server 2013 の構成の出発点として使用することができます。 このトピックでは、提供されている Windows PowerShell の例について説明します。 Lync Server 2013 全般を構成する方法については、このトピックの目標ではありません。 Lync Server 2013 での Windows PowerShell の使用の詳細については、「Lync Server 管理<https://technet.microsoft.com/en-us/library/gg398474.aspx>シェルに関するドキュメント」を参照してください。

<div>

## <a name="about-running-lync-server-management-shell-scripts"></a>Lync Server 管理シェルスクリプトの実行について

ここでは、ロードシミュレーションを実行するための準備として使用される可能性のある Lync Server Management Shell スクリプトの例を提供しています。 このスクリプトは、読み込みシミュレーションを目的としているため、単純で寛容なものであるため、運用には適していない可能性があります。 すべてのスクリプトは例であり、確認する必要があります。また、場合によっては、トポロジを反映するように変更されます。 少なくとも、応答グループサービス (RGS) シナリオは、エージェントグループに割り当てられているエージェントを指定するように変更する必要があることを前提としています。 ただし、このロードをシミュレートするオプションはありません。

<div>


> [!WARNING]  
> 提供されている例を確認して理解してください。 スクリプトはトポロジ内の既存の設定を上書きします。



</div>

<div>


> [!NOTE]  
> Windows PowerShell と Lync Server 管理シェルの使用の詳細については、「Lync Server 2013 Windows PowerShell <A href="https://go.microsoft.com/fwlink/?linkid=203150">https://go.microsoft.com/fwlink/?LinkId=203150</A>のブログ」を参照してください。



</div>

</div>

<div>

## <a name="stress-and-performance-tool-client-version-monikers"></a>ストレスとパフォーマンスのツールクライアントバージョンのモニカー

既定値の設定を変更した場合は、クライアントのバージョンチェックポリシーの構成が必要になることがあります。 詳細については、「サポートされて<https://technet.microsoft.com/en-us/library/gg412832(v=ocs.15).aspx>いるクライアントバージョンを構成する」を参照してください。 Lync Server 2013 のストレスとパフォーマンスツールでは、Lync Server 2013 と通信するときに、次のユーザーエージェントバージョンが既定で使用されます。

  - LSPT/15.0.0.0 (Lync Server 2013 応力とパフォーマンスツール)

  - OCPHONE 電話/0.522

LyncPerfTool のモビリティ (UCWA) クライアントの場合は、次のようになります。

  - Ucwa Perf ツール/Web 会議

  - Ucwa Perf ツール/モバイル

</div>

</div>

<span> </span>

</div>

</div>

</div>

