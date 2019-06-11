---
title: セキュリティ構成ウィザードで IIS のポートを閉じた後にサーバーを再アクティブ化する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Re-activate server after Security Configuration Wizard closes ports in IIS
ms:assetid: cb8e17cf-f8c1-4099-b63b-c242d656c26a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398851(v=OCS.15)
ms:contentKeyID: 48185644
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9c939996c10c85141d3c3751ce84b0cf642007b9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823610"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="re-activate-server-after-security-configuration-wizard-closes-ports-in-iis"></a>セキュリティ構成ウィザードで IIS のポートを閉じた後にサーバーを再アクティブ化する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-01_

一部の Lync Server 2013 ロールでは、インターネットインフォメーションサービス (IIS) ポート4443で Web サービスが実行されます。 Lync Server 展開ウィザード、ブートストラップを実行するか、または**CsComputer**コマンドレットを使用して、ファイアウォールで例外を作成し、ポートを開きます。 その後、Windows Server 2008 R2 セキュリティ構成ウィザード (またはその他の強化スクリプト) を実行すると、ポート4443はブロックされ、外部クライアントは Web サービスに接続できなくなります。 ポートをもう一度開くには、ファイアウォールの例外を直接変更するか、サーバーを再アクティブ化することができます。

<div>

## <a name="to-re-activate-the-server-by-using-the-deployment-wizard"></a>展開ウィザードを使用してサーバーを再アクティブ化するには

1.  Lync Server の展開ウィザードのページで、[**手順 2: Lync サーバーコンポーネントをセットアップまたは削除**する] の横にある [**実行**] をクリックします。

2.  [ **Lync Server コンポーネントのセットアップ**] ページで、[**次へ**] をクリックします。

3.  [**コマンドの実行**] ページで、タスクの状態が [完了] と表示されたら、[**完了**] をクリックします。
    
    <div>
    

    > [!NOTE]
    > また、client.exe を使用してサーバー <STRONG></STRONG>を再アクティブ化することもできます。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

