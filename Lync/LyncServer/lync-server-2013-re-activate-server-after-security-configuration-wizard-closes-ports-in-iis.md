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
ms.openlocfilehash: 388a39c81af2f7e3ca4e0c61f468b283deaa7a4e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045729"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="re-activate-server-after-security-configuration-wizard-closes-ports-in-iis"></a>セキュリティ構成ウィザードで IIS のポートを閉じた後にサーバーを再アクティブ化する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-01_

一部の Lync Server 2013 の役割では、インターネットインフォメーションサービス (IIS) ポート4443で Web サービスを実行します。 Lync Server 展開ウィザード、ブートストラップを実行するか、また**はコマンドレット**を使用してファイアウォールで例外を作成し、ポートを開きます。 その後、Windows Server 2008 R2 セキュリティ構成ウィザード (またはその他の強化スクリプト) を実行すると、ポート4443がブロックされ、外部クライアントは Web サービスに接続できなくなります。 ポートを再度開くには、ファイアウォールの例外を直接変更するか、サーバーを再アクティブ化することができます。

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

