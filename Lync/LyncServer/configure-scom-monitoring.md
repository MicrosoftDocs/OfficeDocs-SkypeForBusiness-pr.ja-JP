---
title: SCOM 監視の構成
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure SCOM monitoring
ms:assetid: 4003d225-2a33-448c-abd9-571750661140
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688033(v=OCS.15)
ms:contentKeyID: 49733624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7904edf9723dacdd28f69a75bec17cb5db3c2061
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728143"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-scom-monitoring"></a>SCOM 監視の構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-04_

Microsoft Lync Server 2013 に移行した後、いくつかのタスクを実行して、Lync Server 2013 が System Center Operations Manager と連携するように構成する必要があります。

  - サーバーに Lync Server 2010 更新プログラムを適用して、セントラル検出ロジックを管理します。

  - セントラル探索候補サーバーのレジストリキーを更新します。

  - "候補" セントラル探索ノードを上書きするように、プライマリ System Center Operations Manager management サーバーを構成します。

これらの各タスクを実行する手順については、以下で説明します。

**サーバーに Lync Server 2010 更新プログラムを適用して、セントラル検出ロジックを管理します。**

1.  System Center Operations Manager エージェントファイルがインストールされ、候補探索ノードとして構成されているサーバーを選びます。

2.  このサーバーに Lync Server 2010 の更新プログラムを適用します。 「 [Lync Server 2010 更新プログラムの適用](apply-lync-server-2010-updates.md)」のトピックを参照してください。

**セントラル探索候補サーバーのレジストリキーを更新します。**

1.  サーバー上でセントラル検出ロジックを管理することを選択した場合は、Windows PowerShell コマンドウィンドウを開きます。

2.  コマンドラインで、次のように入力します。
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
       ```
    
       ```PowerShell
        New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
       ```
    
    <div class="">
    

    > [!NOTE]  
    > レジストリを編集すると、レジストリキーが既に存在する場合に、コマンドが失敗するというエラーが発生する場合があります。 この問題が発生した場合は、エラーを無視しても問題ありません。

    
    </div>

**主要な System Center Operations Manager management server を構成して、[セントラル探索の候補となるサービスの管理者ノードを上書きする。**

1.  System Center Operations Manager コンソールがインストールされているコンピューターで、[**管理パックのオブジェクト**] を展開し、[**オブジェクト**検出] を選択します。

2.  [**範囲の変更] を**クリックします。

3.  [**スコープ管理パックのオブジェクト**] ページで、[ **LS 検出候補**] を選択します。

4.  **LS 検出候補の有効値**を、前の手順で選択した候補サーバーの名前に上書きします。

最後に、変更内容を確定するには、System Center Operations Manager ルート管理サーバーで正常性サービスを再起動します。

</div>

<span> </span>

</div>

</div>

</div>

