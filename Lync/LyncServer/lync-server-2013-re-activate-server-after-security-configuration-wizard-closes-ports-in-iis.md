---
title: セキュリティ構成ウィザードで IIS のポートを閉じた後にサーバーを再アクティブ化する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Re-activate server after Security Configuration Wizard closes ports in IIS
ms:assetid: cb8e17cf-f8c1-4099-b63b-c242d656c26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398851(v=OCS.15)
ms:contentKeyID: 48185644
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a72bfcf9facfeaa3ca943275d9cdcb3b1ac7705
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512044"
---
# <a name="re-activate-server-after-security-configuration-wizard-closes-ports-in-iis"></a>セキュリティ構成ウィザードで IIS のポートを閉じた後にサーバーを再アクティブ化する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-01_

一部の Lync Server 2013 の役割では、インターネットインフォメーションサービス (IIS) ポート4443で Web サービスを実行します。 Lync Server 展開ウィザードの実行、Bootstrapper.exe、またはを使用し **て、ファイア** ウォールで例外を作成し、ポートを開きます。 その後、Windows Server 2008 R2 セキュリティ構成ウィザード (またはその他の強化スクリプト) を実行すると、ポート4443がブロックされ、外部クライアントは Web サービスに接続できなくなります。 ポートを再度開くには、ファイアウォールの例外を直接変更するか、サーバーを再アクティブ化することができます。

<div>

## <a name="to-re-activate-the-server-by-using-the-deployment-wizard"></a>展開ウィザードを使用してサーバーを再アクティブ化するには

1.  [Lync Server 展開ウィザード] ページで、[**ステップ 2: Lync Server コンポーネントのセットアップまたは削除**] の横にある [**実行**] をクリックします。

2.  [**Lync Server コンポーネントの設定**] ページで、[**次へ**] をクリックします。

3.  [**コマンドの実行**] ページで、タスク状態が完了と表示されたら、[**完了**] をクリックします。
    
    <div>
    

    > [!NOTE]
    > bootstrapper.exe または <STRONG>Enable-CsComputer</STRONG> を使用して、サーバーを再アクティブ化することもできます。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

